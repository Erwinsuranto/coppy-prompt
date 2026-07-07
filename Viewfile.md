```
Tambahkan fitur View Mode pada halaman My Files dan Admin Files.

Jangan menghapus tampilan yang sekarang.

Jangan mengubah backend.

Jangan mengubah API.

Jangan mengubah struktur database.

Semua hanya perubahan frontend.

==================================================
VIEW MODE
==================================================

Sekarang terdapat 3 mode tampilan.

1. 📱 Mobile Card (yang sekarang)
2. 🖼 Grid View
3. 📋 Detail View

Mode Mobile Card yang sekarang HARUS tetap dipertahankan.

Jangan dihapus.

Jangan diubah layout utamanya.

Hanya dirapikan jika diperlukan.

==================================================
1. MOBILE CARD (EXISTING)
==================================================

Ini adalah tampilan default sekarang.

Pertahankan seluruh fungsi:

- Thumbnail
- Nama File
- Status
- Download
- Copy Link
- Preview
- Folder
- Checkbox
- Pagination
- Search
- Filter

Hanya lakukan perbaikan UI:

- spacing
- alignment
- responsive
- ukuran tombol
- overflow text

Tanpa mengubah konsep.

==================================================
2. GRID VIEW
==================================================

Tambahkan Grid View.

Layout seperti Google Drive.

Isi card:

Thumbnail besar

Nama File

Ukuran

Jenis

Folder

Tanggal Upload

Jumlah Download

Status

Klik card membuka:

/file/{downloadToken}

Hover desktop:

shadow

scale sedikit

Mobile:

tap sekali.

==================================================
3. DETAIL VIEW
==================================================

Tambahkan Detail View seperti Windows Explorer.

Kolom:

☑

Thumbnail

Nama File

Ukuran

Jenis

Folder

Tanggal Upload

Downloads

Status

Action

Nama file dapat diklik.

Klik membuka halaman detail.

Kolom bisa diurutkan:

Nama

Ukuran

Tanggal

Downloads

==================================================
SWITCH VIEW
==================================================

Tambahkan tombol kecil di kanan Search Box.

Mode:

📱 Card

🖼 Grid

📋 Detail

User dapat berpindah kapan saja.

Pilihan disimpan di localStorage.

Saat membuka website lagi otomatis menggunakan mode terakhir.

==================================================
THUMBNAIL
==================================================

Image

thumbnail asli.

Video

thumbnail video.

PDF

preview halaman pertama.

Office

icon.

ZIP

archive icon.

Audio

music icon.

Unknown

default icon.

Gunakan metadata dan cache.

Jangan request Telegram setiap render.

==================================================
SEARCH
==================================================

Semua mode harus memakai Search yang sama.

Realtime.

Highlight keyword.

==================================================
FILTER
==================================================

Semua mode memakai filter yang sama.

Tidak boleh ada duplikasi.

==================================================
ACTION
==================================================

Semua mode memiliki fungsi yang sama.

Preview

Download

Copy Link

Rename

Move Folder

Delete

Properties

==================================================
RESPONSIVE
==================================================

Desktop

Grid:
5-6 kolom.

Detail:
Table.

Card:
Tetap seperti sekarang.

Tablet

Grid:
3-4 kolom.

Mobile

Grid:
2 kolom.

Card:
Tetap.

Detail:
Responsive tanpa overflow horizontal.

==================================================
PERFORMANCE
==================================================

Lazy loading.

Thumbnail cache.

Pagination.

Tidak duplicate request.

==================================================
VALIDASI
==================================================

Pastikan:

Card View berjalan.

Grid View berjalan.

Detail View berjalan.

Search berjalan.

Filter berjalan.

Rename berjalan.

Copy Link berjalan.

Preview berjalan.

Download berjalan.

Pagination berjalan.

Bulk Action berjalan.

Thumbnail berjalan.

Tidak ada React error.

Tidak ada hydration error.

Tidak ada Prisma error.

Tidak ada TypeScript error.

==================================================
BUILD
==================================================

Jalankan:

npm run lint

npm run build

Pastikan build berhasil tanpa warning maupun error.

Jika menemukan bug lain selama implementasi, langsung perbaiki sampai ketiga mode tampilan (Card, Grid, dan Detail) stabil, konsisten, responsif, dan production-ready tanpa mengubah arsitektur backend maupun bot Telegram yang sudah ada.



```
