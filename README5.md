```

Lakukan audit penuh fitur Download Telegram Drive.

Saat menekan Download muncul:

Cannot GET
/api/download/{downloadToken}/file

Artinya endpoint download tidak ditemukan.

Target:

==================================================

Cari penyebab kenapa route:

GET /api/download/:downloadToken/file

menghasilkan 404.

==================================================

Periksa:

routes

controller

router

Express/Fastify

Next.js proxy

API base URL

Rewrite

Middleware

==================================================

Pastikan endpoint download benar-benar terdaftar.

Jika route berubah:

ubah frontend mengikuti backend.

Jika frontend benar:

perbaiki backend.

==================================================

Download harus memakai downloadToken yang sama dengan:

Website

Bot Telegram

My Files

Search

Preview

==================================================

Pastikan endpoint:

GET /api/download/:downloadToken/file

mengembalikan file.

Bukan JSON.

Bukan HTML.

Bukan Cannot GET.

==================================================

Response wajib:

200 OK

Content-Disposition

Content-Length

Content-Type

==================================================

Jika file berada di Telegram:

ambil file Telegram

stream ke browser

==================================================

Audit seluruh flow:

Database

downloadToken

Telegram file_id

StorageService

DownloadService

Controller

Routes

==================================================

Setelah diperbaiki:

- Download berhasil di Chrome Android
- Download berhasil di Desktop
- Copy Link juga menggunakan endpoint yang benar
- npm run build backend sukses
- npm run build frontend sukses

Laporan akhir:

1. Penyebab Cannot GET.
2. File yang diperbaiki.
3. Route akhir yang digunakan.
4. Contoh URL download yang benar.
5. Bukti download berhasil.

```
