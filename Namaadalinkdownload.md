```

Sekarang jangan hanya memperbaiki bug. Saya ingin meningkatkan Telegram Drive menjadi cloud storage yang profesional seperti Google Drive, Dropbox, OneDrive, atau Pixeldrain tanpa mengubah arsitektur backend yang sudah ada.

Aturan utama:
- Jangan mengubah alur upload Telegram yang sudah berjalan.
- Jangan mengubah downloadToken yang sudah digunakan website dan bot.
- Semua fitur lama tetap berfungsi.
- Jika menemukan bug selama pengerjaan, langsung perbaiki tanpa menunggu instruksi.
- Jangan meminta saya mengedit kode manual.
- Kerjakan sampai production ready.

==================================================================
1. ADMIN FILES
==================================================================

Perbarui halaman Admin Files agar tampil modern.

Kolom:

☐
Thumbnail
Nama File
Ukuran
Jenis
Folder
Tanggal Upload
Downloads
Status
Action

==================================================================
2. THUMBNAIL
==================================================================

Thumbnail harus berasal dari metadata database.

Image
→ tampilkan thumbnail asli.

Video
→ tampilkan frame pertama atau thumbnail Telegram.

PDF
→ preview halaman pertama.

Audio
→ icon music.

ZIP/RAR
→ archive icon.

Office
→ office icon.

Unknown
→ default icon.

Jangan request Telegram setiap render.

Gunakan cache.

Jika thumbnail gagal maka gunakan icon sesuai tipe file.

==================================================================
3. NAMA FILE
==================================================================

Nama file jangan hanya text.

Nama file harus clickable.

Klik nama file membuka halaman detail:

/file/{downloadToken}

atau

/admin/files/{id}

Desktop:
Hover berubah warna.

Mobile:
Tap sekali.

==================================================================
4. HALAMAN DETAIL FILE
==================================================================

Halaman detail harus seperti cloud storage profesional.

Tampilkan:

Thumbnail besar

Nama file

Ukuran

Jenis

Folder

Tanggal upload

Uploader

Telegram Message ID

Download Token

Jumlah download

Status

Lalu tombol:

Download

Copy Link

Share

Rename

Move Folder

Delete

==================================================================
5. DOWNLOAD
==================================================================

Perbaiki bug download.

Saat klik Download:

Pastikan frontend memanggil endpoint backend yang benar.

Jangan mengarah ke route yang menghasilkan:

Cannot GET

Gunakan route backend yang benar.

Pastikan backend mengirim stream file Telegram.

Jika Telegram gagal:

retry.

Jika gagal lagi:

toast error.

==================================================================
6. COPY LINK
==================================================================

Copy Link harus menyalin URL publik.

Contoh:

https://domain/file/{downloadToken}

Bukan API URL.

Toast:

Link berhasil disalin.

==================================================================
7. SHARE
==================================================================

Gunakan navigator.share().

Jika browser tidak mendukung:

fallback ke Copy Link.

==================================================================
8. PREVIEW
==================================================================

Image

fullscreen preview.

Video

video player.

Audio

audio player.

PDF

viewer.

Office

preview bila tersedia.

Jika tidak bisa preview

langsung download.

==================================================================
9. BULK ACTION
==================================================================

Checkbox.

Jika memilih beberapa file tampil toolbar.

Delete

Move

Download ZIP

Copy Link

==================================================================
10. SEARCH
==================================================================

Realtime search.

Highlight keyword.

Klik hasil langsung membuka halaman detail.

==================================================================
11. CONTEXT MENU
==================================================================

Tambahkan menu:

Preview

Download

Copy Link

Rename

Move

Delete

Properties

==================================================================
12. RESPONSIVE
==================================================================

Desktop

table.

Tablet

card.

Mobile

card list.

Tidak boleh overflow horizontal.

==================================================================
13. CACHE
==================================================================

Thumbnail memakai cache.

Metadata memakai database.

Jangan request Telegram setiap render.

==================================================================
14. BACKEND
==================================================================

Jangan membuat token baru.

Gunakan downloadToken yang sudah ada.

Upload

↓

Database

↓

DownloadToken

↓

Website

↓

Bot

↓

Share

↓

Download

Semua memakai token yang sama.

==================================================================
15. ERROR HANDLING
==================================================================

Thumbnail gagal

gunakan fallback.

Download gagal

toast.

Copy gagal

toast.

Telegram timeout

retry otomatis.

==================================================================
16. PERFORMANCE
==================================================================

Pagination.

Lazy loading.

Virtual list.

Optimasi thumbnail.

Optimasi query database.

Hilangkan duplicate request.

==================================================================
17. UI
==================================================================

Tambahkan hover.

Transition.

Skeleton loading.

Loading indicator.

Toast notification.

Progress upload.

Progress download.

==================================================================
18. VALIDASI
==================================================================

Pastikan:

Upload berhasil.

Thumbnail muncul.

Download berhasil.

Copy Link berhasil.

Share berhasil.

Preview berhasil.

Admin Files stabil.

Dashboard stabil.

My Files stabil.

Search stabil.

Folder stabil.

Tidak ada hydration error.

Tidak ada React error.

Tidak ada Prisma error.

Tidak ada TypeScript error.

Tidak ada warning.

Tidak ada memory leak.

==================================================================
19. BUILD
==================================================================

Jalankan otomatis:

npm run lint

npm run build

Pastikan build berhasil tanpa warning atau error.

==================================================================
20. SELESAIKAN SEMUA
==================================================================

Jangan berhenti ketika menemukan bug.

Jika ada bug baru selama implementasi, langsung perbaiki.

Teruskan sampai seluruh website Telegram Drive benar-benar stabil, modern, konsisten, production-ready, dan setara pengalaman penggunaan Google Drive, Dropbox, atau OneDrive, tanpa merusak arsitektur backend maupun bot Telegram yang sudah ada.


```
