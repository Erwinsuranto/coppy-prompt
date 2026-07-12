









# 
```

Server berjalan normal.

Log menunjukkan:
- GET /upload 200
- GET /my-files 200
- GET /api/files 200

Tetapi saat tombol Upload ditekan tidak ada request:

POST /api/uploads/file

Audit frontend.

Cari mengapa klik tombol Upload tidak memicu request upload.

Periksa:
1. Event onClick tombol Upload.
2. input[type=file].
3. Apakah file picker benar-benar mengembalikan File.
4. Apakah fetch('/api/uploads/file') pernah dipanggil.
5. Buka browser console dan Network.
6. Perbaiki sampai POST /api/uploads/file benar-benar muncul di log server.

Jangan hanya commit kode. Verifikasi upload benar-benar berjalan.



```
# 
```

BUG: Tombol Upload tidak berfungsi.

Kondisi saat ini:
- Halaman My Files terbuka.
- Tombol Upload tampil di kanan bawah.
- Saat tombol Upload ditekan, tetap berada di halaman yang sama.
- Tidak muncul file picker.
- Tidak muncul dialog upload.
- Tidak muncul drag & drop.

Tugas:

1. Cari event onClick tombol Upload.
2. Pastikan tombol Upload membuka file picker atau Upload Studio.
3. Jika memakai input[type=file], pastikan input tersebut dipanggil melalui tombol Upload.
4. Jika memakai modal Upload Studio, pastikan modal dirender dan terbuka.
5. Jika routing salah, perbaiki routing.
6. Setelah diperbaiki, uji bahwa:
   - Klik Upload → file picker muncul.
   - Pilih file → file masuk ke upload queue.
   - Upload berjalan ke backend Telegram.
7. Jalankan build dan pastikan tidak ada error.
8. Commit perubahan dan laporkan file yang diubah.



```
# 
```


Halaman web sudah dapat dibuka, tetapi fitur Upload belum tampil.

Yang terjadi:
- Halaman Telegram Drive terbuka.
- Hanya muncul tulisan:
  "Choose My Files to manage uploads."
- Tidak ada drag & drop.
- Tidak ada tombol Choose File.
- Tidak ada tombol Upload.

Tugas:

1. Audit komponen Upload.
2. Cari mengapa Upload Studio tidak dirender.
3. Pastikan halaman Upload langsung menampilkan:
   - Drag & Drop area
   - Tombol Choose File
   - Daftar file yang dipilih
   - Progress upload
   - Tombol Upload
4. Jangan mengubah desain yang sudah ada.
5. Pastikan setelah memilih file, upload benar-benar berjalan ke backend Telegram.
6. Jika Upload Studio belum dipanggil, perbaiki routing atau import.
7. Jalankan build dan pastikan halaman Upload berfungsi.

Berikan daftar file yang diubah beserta alasan setiap perubahan.


```
# 
```

Audit selesai.

Sekarang jangan hanya membaca struktur project.

Lanjutkan implementasi sampai selesai.

Target:

1. Pastikan halaman app/download/[id]/page.tsx benar-benar bekerja.
2. Pastikan DownloadLanding dapat mengambil data file berdasarkan downloadToken.
3. Jika ada import yang salah, perbaiki tanpa mengubah struktur project.
4. Pastikan download menggunakan API backend yang sudah ada.
5. Pastikan halaman menampilkan:
   - nama file
   - ukuran file
   - tombol Download
   - progress download
   - error handling
6. Jika ada file yang belum ada, buat otomatis.
7. Jalankan build sampai berhasil.
8. Commit semua perubahan ke branch aktif.

Jangan berhenti setelah audit. Lanjutkan implementasi sampai build berhasil.



```
# 
```

STOP.

Backend upload sudah saya terima.

Saya tidak membutuhkan audit atau penjelasan lagi.

Sekarang kirim implementasi FRONTEND Upload dan Download yang benar-benar dipakai website.

Kirim source code lengkap berikut secara utuh:

1.
components/final-ui/upload-studio.tsx

2.
components/final-ui/upload-dropzone.tsx

3.
components/final-ui/upload-progress.tsx

4.
components/final-ui/upload-queue.tsx

5.
components/final-ui/upload-toolbar.tsx

6.
app/download/[id]/page.tsx

7.
components/final-ui/download-view.tsx

8.
Semua hook yang dipakai upload/download.

Jangan ringkas.

Jangan audit.

Jangan menjelaskan.

Kirim source code penuh satu file per balasan sampai seluruh Upload UI dan Download UI selesai.

Jika suatu file mengimpor komponen lain, lanjutkan otomatis sampai semua implementasi Upload dan Download selesai.



```
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
