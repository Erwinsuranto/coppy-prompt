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
