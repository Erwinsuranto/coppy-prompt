```
Lakukan audit penuh terhadap fitur Download pada Website Telegram Drive.

Saat ini terdapat dua bug:

BUG 1
- Tombol "Copy Link" tidak menyalin link apa pun.
- Tidak muncul link di clipboard.

BUG 2
- Tombol "Download Now" menampilkan toast:
  "Download Started"
- Progress berjalan.
- Tetapi browser tidak mengunduh file.

Target:

==================================================
COPY LINK
==================================================

Periksa seluruh implementasi Copy Link.

Pastikan:

- navigator.clipboard.writeText() digunakan dengan benar.
- Ada fallback untuk browser yang tidak mendukung Clipboard API.
- Link yang dicopy adalah URL download publik yang benar.
- Setelah berhasil copy tampilkan toast:
  "Link berhasil disalin."
- Jika gagal tampilkan alasan yang jelas.

==================================================
DOWNLOAD
==================================================

Audit seluruh alur download.

Periksa:

- Frontend
- API Download
- Download Token
- Endpoint REST
- Redirect Telegram
- Content-Disposition
- Content-Type
- Response Header
- Blob Download
- Browser Download

Pastikan tombol Download benar-benar mengunduh file.

==================================================
ENDPOINT
==================================================

Audit endpoint download.

Pastikan endpoint mengembalikan:

HTTP 200

Content-Type sesuai file.

Content-Length benar.

Content-Disposition:

attachment;
filename="..."

==================================================
TOKEN
==================================================

Pastikan download memakai downloadToken yang sama dengan:

Website

Bot Telegram

Preview

My Files

Search

==================================================
BROWSER
==================================================

Jika download dilakukan menggunakan fetch():

Pastikan Blob dibuat dengan benar.

Gunakan:

URL.createObjectURL()

buat element <a>

download

click()

revokeObjectURL()

Jika menggunakan redirect:

Pastikan browser menerima file.

==================================================
ERROR
==================================================

Jika download gagal:

Jangan tampilkan:

Download Started

Pastikan toast menampilkan penyebab sebenarnya.

==================================================
VALIDASI
==================================================

Uji:

JPG

PNG

PDF

ZIP

MP4

Audio

Pastikan semua dapat diunduh.

==================================================
OUTPUT
==================================================

Berikan laporan:

1. Penyebab Copy Link gagal.
2. Penyebab Download tidak berjalan.
3. File yang diubah.
4. Endpoint yang diperbaiki.
5. Bukti bahwa Copy Link berhasil.
6. Bukti bahwa Download berhasil di Chrome Android dan Desktop.
7. Jalankan npm run build frontend dan backend hingga sukses.

```

