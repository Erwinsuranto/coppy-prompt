```

Lakukan audit fitur Thumbnail Telegram Drive.

Saat ini thumbnail belum benar.

Masalah:

- Foto masih memakai icon default.
- Video memakai thumbnail buatan.
- Padahal Telegram sudah memiliki thumbnail/preview asli.

Target:

==================================================

Jangan membuat thumbnail buatan untuk image.

Gunakan thumbnail asli dari Telegram.

==================================================

Saat upload:

Simpan seluruh metadata Telegram:

file_id

file_unique_id

photo sizes

thumb

document.thumb

width

height

==================================================

Jika file adalah IMAGE:

Gunakan thumbnail Telegram.

Jangan icon default.

==================================================

Jika file adalah VIDEO:

Gunakan thumbnail Telegram jika tersedia.

Hanya generate thumbnail menggunakan ffmpeg apabila Telegram tidak menyediakan thumbnail.

==================================================

Admin Files

My Files

Search

Preview

Dashboard

semuanya harus menggunakan thumbnail yang berasal dari metadata file.

==================================================

Jika thumbnail Telegram tidak ada:

baru gunakan fallback icon.

==================================================

Periksa StorageService dan UploadService.

Pastikan metadata thumbnail Telegram disimpan ke database saat upload.

==================================================

Jika schema Prisma belum memiliki field yang diperlukan:

tambahkan migration baru.

==================================================

Output:

1. Dari mana thumbnail diambil.
2. File backend yang diubah.
3. File frontend yang diubah.
4. Contoh response API yang berisi thumbnail.
5. Pastikan foto menampilkan preview asli, bukan icon default.
6. Pastikan video menggunakan thumbnail Telegram bila tersedia.
7. npm run build backend dan frontend harus sukses.


```
