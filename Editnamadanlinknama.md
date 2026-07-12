




# 
```

You are a senior TypeScript, Next.js and Telegram Bot engineer.

Build a complete production-ready Telegram Bot.

IMPORTANT

- Do NOT create placeholder code.
- Do NOT leave TODOs.
- Every feature must be fully implemented.
- Production quality.
- Clean architecture.
- TypeScript.
- Next.js App Router.
- Telegram Bot API.
- Environment variables.
- Error handling.
- Logging.
- Rate limiting.
- Security.
- README.

================================================

BOT FLOW

/start

Display:

Welcome

Paste a supported media URL.

The bot should:

- validate URL
- detect supported platform
- fetch media metadata through a compliant provider/API
- show:

Thumbnail

Title

Duration

Author

Available formats

Then display inline keyboard.

Example

Video
Audio
Cancel

If user selects Video

Display available qualities reported by the provider.

Example

144p
240p
360p
480p
720p
1080p

Only display qualities actually available.

If user selects Audio

Display

MP3 128k
MP3 320k
Original Audio

================================================

DOWNLOAD FLOW

When user selects a format:

Show progress

Fetching metadata...
Preparing...
Downloading...
Uploading...

Then send media.

Large files should stream when possible.

================================================

ADMIN

/admin

Dashboard

Users

Downloads

Errors

Logs

Broadcast

Statistics

================================================

DATABASE

Store

Users

Download history

Statistics

Blocked users

================================================

FEATURES

Rate limiting

Queue system

Retry failed downloads

Temporary cache

Automatic cleanup

Logging

================================================

SECURITY

Validate URL

Prevent spam

Prevent abuse

Prevent invalid requests

================================================

PROJECT STRUCTURE

app/

bot/

lib/

components/

utils/

types/

config/

================================================

README

Include complete installation.

Environment variables.

Run commands.

Deployment instructions.

Troubleshooting.

================================================

Generate production-ready code.



```

```

Selesaikan fitur File Manager yang belum selesai.

Jangan mengubah arsitektur backend.

Tetap gunakan downloadToken yang sudah ada.

==================================================
1. Nama File Harus Clickable
==================================================

Nama file bukan hanya text.

Contoh:

photo-AQADCBNrGzINU...

Saat diklik:

membuka

/file/{downloadToken}

atau

/admin/files/{id}

dengan halaman detail file.

Hover desktop berubah warna.

Cursor pointer.

Mobile cukup tap sekali.

==================================================
2. Copy Link dari Nama File
==================================================

Saat user:

Long press (mobile)

atau

Klik kanan (desktop)

munculkan menu

Copy Link
Open Detail
Preview

Jika memilih Copy Link

copy

https://domain/file/{downloadToken}

ke clipboard.

Toast:

"Link berhasil disalin"

Jika Clipboard API tidak tersedia

gunakan fallback.

==================================================
3. Rename File
==================================================

Saat klik Rename

munculkan dialog.

Isi:

Nama File

Extension tidak boleh berubah.

Contoh:

video.mp4

boleh menjadi

Tutorial Telegram.mp4

tetapi

tidak boleh menjadi

Tutorial.zip

==================================================
4. Backend Rename
==================================================

Rename hanya mengubah metadata database.

Jangan upload ulang file Telegram.

Jangan mengubah downloadToken.

Jangan mengubah messageId Telegram.

Yang berubah hanya:

displayName

atau

originalName

sesuai schema.

==================================================
5. Validasi Rename
==================================================

Tidak boleh kosong.

Tidak boleh karakter ilegal.

Panjang maksimal 255.

Pertahankan extension.

==================================================
6. Setelah Rename
==================================================

Refresh cache.

Update card.

Update detail page.

Update search index.

Tidak perlu reload halaman.

==================================================
7. Copy Link Button
==================================================

Tombol Copy sekarang juga harus memakai helper yang sama.

Semua Copy Link harus menghasilkan URL publik:

https://domain/file/{downloadToken}

bukan API URL.

==================================================
8. Halaman Detail
==================================================

Nama file di halaman detail juga bisa Rename.

Tanpa reload.

==================================================
9. Search
==================================================

Setelah Rename

Search langsung menggunakan nama baru.

==================================================
10. Build
==================================================

Jalankan:

npm run lint

npm run build

Pastikan tidak ada warning maupun error.

Jika menemukan bug lain selama implementasi, langsung perbaiki sampai fitur clickable nama file, copy link, dan rename benar-benar berfungsi di desktop maupun mobile.


```
