import { randomBytes, randomUUID } from 'node:crypto';
import {
  connectDatabase,
  isDatabaseConnected,
} from '../bot/src/database/mongoose';
import { FileMetadataModel } from '../bot/src/models/file-metadata.model';
import {
  FileModel,
  FolderModel,
  UploadHistoryModel,
} from '../models';

const DEFAULT_MAX_UPLOAD_MB = 20;
const TELEGRAM_API_BASE = 'https://api.telegram.org';

export type WebsiteUploadResult = {
  id: string;
  downloadToken: string;
  telegramFileId: string;
  telegramFileUniqueId: string;
  telegramMessageId: number;
  fileName: string;
  mimeType: string;
  size: number;
  uploadedAt: Date;
};

type TelegramDocument = {
  file_id: string;
  file_unique_id: string;
  file_name?: string;
  mime_type?: string;
  file_size?: number;
};

type TelegramSendDocumentResponse = {
  ok: boolean;
  description?: string;
  result?: {
    message_id: number;
    document?: TelegramDocument;
  };
};

export class WebsiteUploadError extends Error {
  constructor(
    message: string,
    public readonly status = 500,
  ) {
    super(message);
    this.name = 'WebsiteUploadError';
  }
}

function requiredEnvironment(
  name: 'BOT_TOKEN' | 'CHANNEL_ID',
) {
  const value = process.env[name]?.trim();

  if (!value) {
    throw new WebsiteUploadError(
      `${name} is not configured`,
      503,
    );
  }

  return value;
}

function maxUploadBytes() {
  const configured = Number(
    process.env.WEBSITE_UPLOAD_MAX_FILE_SIZE_MB ??
      process.env.MAX_UPLOAD_FILE_SIZE_MB ??
      DEFAULT_MAX_UPLOAD_MB,
  );

  const megabytes =
    Number.isFinite(configured) && configured > 0
      ? configured
      : DEFAULT_MAX_UPLOAD_MB;

  return Math.floor(megabytes * 1024 * 1024);
}

function websiteUserId() {
  const value = Number(
    process.env.WEBSITE_UPLOAD_USER_ID ?? 0,
  );

  return Number.isSafeInteger(value) ? value : 0;
}

function extensionOf(fileName: string) {
  const index = fileName.lastIndexOf('.');

  return index > 0 && index < fileName.length - 1
    ? fileName.slice(index + 1).toLowerCase()
    : null;
}

export function validateWebsiteUpload(file: File) {
  const name = file.name.trim();

  if (!name || name === '.' || name === '..') {
    throw new WebsiteUploadError(
      'File name is invalid',
      400,
    );
  }

  if (name.length > 255) {
    throw new WebsiteUploadError(
      'File name is too long',
      400,
    );
  }

  if (file.size <= 0) {
    throw new WebsiteUploadError(
      'Empty files cannot be uploaded',
      400,
    );
  }

  if (file.size > maxUploadBytes()) {
    throw new WebsiteUploadError(
      `File exceeds the ${Math.round(
        maxUploadBytes() / 1024 / 1024,
      )} MB upload limit`,
      413,
    );
  }

  return {
    name,
    mimeType:
      file.type || 'application/octet-stream',
  };
}

async function uploadToTelegram(
  file: File,
  fileName: string,
) {
  const token = requiredEnvironment('BOT_TOKEN');
  const channelId = requiredEnvironment('CHANNEL_ID');

  const body = new FormData();

  body.set('chat_id', channelId);
  body.set('document', file, fileName);
  body.set(
    'caption',
    `Website upload: ${fileName}`,
  );

  const response = await fetch(
    `${TELEGRAM_API_BASE}/bot${token}/sendDocument`,
    {
      method: 'POST',
      body,
    },
  );

  const payload = (await response
    .json()
    .catch(
      () => null,
    )) as TelegramSendDocumentResponse | null;

  if (
    !response.ok ||
    !payload?.ok ||
    !payload.result?.document
  ) {
    throw new WebsiteUploadError(
      payload?.description ||
        'Telegram rejected the upload',
      502,
    );
  }

  return {
    messageId: payload.result.message_id,
    document: payload.result.document,
    channelId,
  };
}

async function deleteTelegramMessage(
  messageId: number,
  channelId: string,
) {
  const token = process.env.BOT_TOKEN?.trim();

  if (!token) return;

  await fetch(
    `${TELEGRAM_API_BASE}/bot${token}/deleteMessage`,
    {
      method: 'POST',
      headers: {
        'content-type': 'application/json',
      },
      body: JSON.stringify({
        chat_id: channelId,
        message_id: messageId,
      }),
    },
  ).catch(() => undefined);
}

export async function uploadWebsiteFile(
  file: File,
  folderId: string | null = null,
): Promise<WebsiteUploadResult> {
  const validated = validateWebsiteUpload(file);

  const connection = await connectDatabase();

  if (!connection || !isDatabaseConnected()) {
    throw new WebsiteUploadError(
      'MongoDB is unavailable',
      503,
    );
  }

  if (folderId) {
    const folder = await FolderModel.findOne({
      id: folderId,
    })
      .lean()
      .exec();

    if (!folder) {
      throw new WebsiteUploadError(
        'Selected destination folder does not exist',
        400,
      );
    }
  }

  const telegram = await uploadToTelegram(
    file,
    validated.name,
  );

  const id = randomUUID();
  const downloadToken = randomBytes(24).toString(
    'hex',
  );
  const uploadedAt = new Date();
  const userId = websiteUserId();

  let metadataCreated = false;
  let fileCreated = false;

  try {
    await FileMetadataModel.create({
      user_id: userId,
      message_id: telegram.messageId,
      file_id: telegram.document.file_id,
      file_unique_id:
        telegram.document.file_unique_id,
      file_name:
        telegram.document.file_name ??
        validated.name,
      file_size:
        telegram.document.file_size ??
        file.size,
      file_type: 'document',
      download_token: downloadToken,
      upload_date: uploadedAt,
    });

    metadataCreated = true;

    await FileModel.create({
      id,
      downloadToken,
      telegramFileId:
        telegram.document.file_id,
      telegramMessageId:
        telegram.messageId,
      fileName:
        telegram.document.file_name ??
        validated.name,
      originalName: validated.name,
      extension: extensionOf(validated.name),
      mimeType:
        telegram.document.mime_type ??
        validated.mimeType,
      size:
        telegram.document.file_size ??
        file.size,
      thumbnail: null,
      uploadedBy: `website:${userId}`,
      folderId,
      uploadedAt,
      deletedAt: null,
      downloadCount: 0,
    });

    fileCreated = true;

    await UploadHistoryModel.create({
      uploadTime: uploadedAt,
      uploader: `website:${userId}`,
      fileId: id,
      status: 'stored',
    });

    return {
      id,
      downloadToken,
      telegramFileId:
        telegram.document.file_id,
      telegramFileUniqueId:
        telegram.document.file_unique_id,
      telegramMessageId:
        telegram.messageId,
      fileName:
        telegram.document.file_name ??
        validated.name,
      mimeType:
        telegram.document.mime_type ??
        validated.mimeType,
      size:
        telegram.document.file_size ??
        file.size,
      uploadedAt,
    };
  } catch (error) {
    if (fileCreated) {
      await FileModel.deleteOne({
        id,
      }).catch(() => undefined);
    }

    if (metadataCreated) {
      await FileMetadataModel.deleteOne({
        download_token: downloadToken,
      }).catch(() => undefined);
    }

    await UploadHistoryModel.create({
      uploadTime: new Date(),
      uploader: `website:${userId}`,
      fileId: id,
      status: 'failed',
    }).catch(() => undefined);

    await deleteTelegramMessage(
      telegram.messageId,
      telegram.channelId,
    );

    throw new WebsiteUploadError(
      error instanceof Error
        ? `Metadata persistence failed: ${error.message}`
        : 'Metadata persistence failed',
      500,
    );
  }
}
