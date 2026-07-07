```

# ROLE

Kamu adalah Senior Prisma Engineer, Senior SQLite Engineer, Senior Backend Node.js Engineer, Senior Next.js Engineer, dan Senior Telegram Bot Engineer.

Jangan hanya memperbaiki error yang muncul.

Lakukan audit menyeluruh terhadap sinkronisasi Prisma, SQLite, Backend API, Upload, dan Database sampai benar-benar stabil untuk production.

==========================================================
MASALAH SAAT INI
==========================================================

Upload file sebenarnya BERHASIL.

Alurnya:

✔ File berhasil dipilih.
✔ Progress mencapai 100%.
✔ File berhasil dikirim ke Telegram.
✔ File muncul di Channel Telegram.
✔ Bot berhasil mengirim file.
✔ Download Token berhasil dibuat.

Tetapi setelah upload selesai muncul error:

Invalid prisma.file.findUnique()

The column

main.File.originalName

does not exist in the current database.

Selain itu migration gagal dengan:

Error P3018

Cannot add a column with non-constant default

Migration:

20260707120000_add_upload_metadata

Artinya kode sudah menggunakan schema terbaru tetapi database SQLite masih schema lama.

==========================================================
TARGET
==========================================================

Jangan membuat solusi sementara.

Perbaiki akar masalah.

Pastikan schema Prisma, migration, SQLite, backend, dan frontend semuanya sinkron.

==========================================================
STEP 1
Audit Prisma Schema
==========================================================

Periksa:

prisma/schema.prisma

Cari seluruh field baru terutama:

originalName

mimeType

telegramFileId

telegramMessageId

downloadToken

description

createdAt

updatedAt

Pastikan semua field sesuai dengan SQLite.

==========================================================
STEP 2
Audit Migration
==========================================================

Periksa migration:

20260707120000_add_upload_metadata

Cari seluruh default value yang menyebabkan SQLite gagal.

Contoh:

cuid()

uuid()

randomUUID()

now()

dbgenerated()

expression SQL

atau default lain yang tidak didukung ALTER TABLE SQLite.

==========================================================
STEP 3
Perbaiki Migration
==========================================================

Jangan memakai solusi yang menghapus database.

Jangan memakai:

prisma migrate reset

Jangan menghapus:

dev.db

Gunakan strategi migration yang aman.

Jika perlu:

Tambah kolom nullable terlebih dahulu.

Isi data lama.

Lalu ubah menjadi NOT NULL bila memang diperlukan.

Migration harus bisa dijalankan pada database yang sudah berisi data.

==========================================================
STEP 4
Audit Existing Data
==========================================================

Pastikan seluruh file lama tetap ada.

Jangan kehilangan:

Telegram Message ID

Telegram File ID

Download Token

Metadata lama

==========================================================
STEP 5
Audit Upload API
==========================================================

Pastikan setelah upload Telegram berhasil:

metadata tersimpan

findUnique berhasil

response sukses

HTTP 200 / 201

Tidak boleh ada HTTP 400.

==========================================================
STEP 6
Audit Prisma Query
==========================================================

Cari seluruh:

findUnique()

findFirst()

findMany()

select

include

Pastikan tidak meminta kolom yang belum ada.

==========================================================
STEP 7
Audit Download
==========================================================

Pastikan:

Download Token tetap sama.

Bot Telegram.

Website.

Preview.

Download.

Search.

My Files.

Admin Files.

Semua memakai downloadToken yang sama.

==========================================================
STEP 8
Audit Frontend
==========================================================

Jika upload berhasil:

✔ tampilkan Upload Success

✔ jangan tampilkan Upload gagal

✔ progress selesai

✔ tampilkan metadata

✔ tampilkan file

==========================================================
STEP 9
Audit Backend
==========================================================

Jika Telegram berhasil upload tetapi database gagal,

Backend harus rollback dengan benar.

Tidak boleh mengembalikan response sukses palsu.

Jika database sukses,

Response harus:

HTTP 200

atau

HTTP 201

==========================================================
STEP 10
Logging
==========================================================

Tambahkan logging lengkap:

Upload dimulai

Upload Telegram berhasil

Metadata disimpan

Prisma Query berhasil

Response dikirim

Jika gagal:

log alasan lengkap

==========================================================
STEP 11
Testing
==========================================================

Lakukan pengujian:

Upload JPG

Upload PNG

Upload PDF

Upload ZIP

Upload Video

Upload File Besar

Pastikan:

✔ berhasil

✔ metadata benar

✔ database benar

✔ Telegram benar

✔ download benar

==========================================================
STEP 12
Production Ready
==========================================================

Setelah selesai jalankan:

Backend

npm install

npm run build

Frontend

npm install

npm run build

Migration

npx prisma generate

npx prisma migrate deploy

Pastikan semuanya berhasil tanpa warning yang menyebabkan aplikasi gagal.

==========================================================
OUTPUT
==========================================================

Berikan laporan:

1. Penyebab utama error.

2. File yang diubah.

3. Migration yang diubah.

4. Query Prisma yang diperbaiki.

5. Alasan perubahan.

6. Bukti bahwa upload berhasil.

7. Bukti bahwa metadata berhasil.

8. Bukti bahwa My Files bekerja.

9. Bukti bahwa Search bekerja.

10. Bukti bahwa Download bekerja.

11. Bukti bahwa Preview bekerja.

12. Pastikan tidak ada lagi error:

The column main.File.originalName does not exist

13. Pastikan migration dapat dijalankan pada SQLite production tanpa menghapus database.

Jangan berhenti sampai seluruh sistem Upload Telegram Drive benar-benar siap production.
```
