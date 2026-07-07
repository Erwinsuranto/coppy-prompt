```
Lakukan implementasi fitur Thumbnail Preview pada Telegram Drive Website.

Saat ini halaman:

- Admin Files
- My Files
- Search
- Preview
- Dashboard

masih menggunakan icon default.

Saya ingin setiap file yang mendukung preview memiliki thumbnail asli.

==================================================
TARGET
==================================================

Website harus seperti Google Drive / Telegram.

Daftar file tidak lagi memakai icon default.

Thumbnail muncul otomatis.

==================================================
JENIS FILE
==================================================

IMAGE

jpg
jpeg
png
gif
webp
bmp
svg

→ tampilkan thumbnail asli.

--------------------------------------------------

VIDEO

mp4
mov
mkv
avi
webm

→ tampilkan frame pertama video.

Tambahkan icon Play kecil di tengah thumbnail.

--------------------------------------------------

PDF

Preview halaman pertama.

--------------------------------------------------

AUDIO

Jika ada album cover gunakan album cover.

Jika tidak ada gunakan icon music.

--------------------------------------------------

ZIP

zip
rar
7z

Gunakan icon archive.

--------------------------------------------------

OFFICE

doc
docx

xls
xlsx

ppt
pptx

Gunakan icon sesuai jenis.

==================================================
BACKEND
==================================================

Saat upload selesai:

1.
Simpan file ke Telegram.

2.
Generate thumbnail.

3.
Upload thumbnail ke storage.

4.
Simpan metadata thumbnail di Prisma.

Tambahkan field bila belum ada:

thumbnailUrl

thumbnailFileId

thumbnailMime

thumbnailWidth

thumbnailHeight

==================================================
DATABASE
==================================================

Jika migration diperlukan:

buat migration baru.

Jangan merusak database lama.

Pastikan migration aman.

==================================================
API
==================================================

Endpoint File Detail mengembalikan:

thumbnailUrl

thumbnailWidth

thumbnailHeight

hasThumbnail

==================================================
FRONTEND
==================================================

Semua halaman memakai thumbnail.

Admin Files

My Files

Search

Dashboard

Recent Upload

Preview

==================================================
LAZY LOAD
==================================================

Gunakan loading lazy.

Thumbnail hanya di-load saat muncul.

==================================================
CACHE
==================================================

Gunakan browser cache.

Jangan request thumbnail berulang.

==================================================
FALLBACK
==================================================

Jika thumbnail gagal dibuat:

Gunakan icon sesuai tipe file.

Jangan sampai gambar rusak.

==================================================
RESPONSIVE
==================================================

Desktop

Tablet

Mobile

Thumbnail tetap proporsional.

object-fit: cover

Border radius mengikuti card.

==================================================
PERFORMANCE
==================================================

Thumbnail maksimal:

512 px

Kompresi otomatis.

Jangan kirim gambar ukuran asli.

==================================================
VIDEO
==================================================

Thumbnail video dibuat otomatis menggunakan ffmpeg.

Jika VPS belum memiliki ffmpeg:

install otomatis.

==================================================
PDF
==================================================

Gunakan preview halaman pertama.

==================================================
SEARCH
==================================================

Thumbnail juga muncul pada hasil pencarian.

==================================================
MY FILES
==================================================

Thumbnail muncul pada daftar file.

==================================================
ADMIN FILES
==================================================

Tambahkan thumbnail sebagai kolom pertama.

Jika gambar:

langsung tampil.

Jika video:

thumbnail + icon play.

==================================================
PREVIEW
==================================================

Jika thumbnail tersedia:

gunakan thumbnail.

Jika tidak:

fallback icon.

==================================================
MIGRATION
==================================================

Jika schema Prisma berubah:

buat migration baru.

Jangan menghapus data lama.

==================================================
VALIDASI
==================================================

Uji:

JPG

PNG

GIF

WEBP

MP4

MOV

MKV

AVI

PDF

ZIP

RAR

DOCX

XLSX

PPTX

==================================================
BUILD
==================================================

Pastikan seluruh project lolos:

npm run lint

npm run build

Backend

Frontend

==================================================
OUTPUT
==================================================

Berikan laporan:

1.
File backend yang diubah.

2.
File frontend yang diubah.

3.
Migration Prisma.

4.
Cara generate thumbnail.

5.
Cara cache thumbnail.

6.
Contoh response API.

7.
Hasil pengujian semua tipe file.

8.
Pastikan thumbnail tampil pada:

- Admin Files
- My Files
- Search
- Preview
- Dashboard

9.
Pastikan tidak ada error TypeScript, Prisma maupun Next.js.

```


