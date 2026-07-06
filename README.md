```
# IMPLEMENTASI LENGKAP MANAJEMEN PRODUK DIGITAL CELL (PRODUCTION READY)

Lanjutkan project Digital Cell.

Jangan mengubah sistem Checkout, Wallet, Deposit, Refund, Ledger, Recovery, Dashboard Admin, Notifikasi, maupun Riwayat Transaksi yang sudah selesai.

Fokus tahap ini adalah membuat sistem Manajemen Produk Production Ready yang sepenuhnya sinkron dengan Digiflazz dan database.

==================================================

TARGET

Semua produk yang tampil di website harus berasal dari database.

Database disinkronkan dari Digiflazz.

Admin dapat mengelola produk tanpa mengubah source code.

Tidak boleh ada data dummy.

==================================================

HALAMAN PRODUK ADMIN

Buat halaman Kelola Produk modern.

Fitur:

- Search
- Filter
- Pagination
- Sorting
- Bulk Action
- Refresh
- Sinkronisasi Digiflazz
- Import
- Export CSV

==================================================

FILTER

Filter berdasarkan:

- Provider
- Kategori
- Brand
- Status
- Digiflazz
- Manual
- Promo
- Featured
- Stock
- Hidden

==================================================

CARD PRODUK

Setiap produk menampilkan:

Nama

Brand

Kategori

Provider

Buyer SKU Code

Harga Modal

Markup

Harga Jual

Status

Stock

Terjual

Terakhir Update

==================================================

EDIT PRODUK

Admin dapat mengubah:

Nama

Deskripsi

Kategori

Brand

Ikon

Banner

Markup

Harga Manual

Urutan

Featured

Promo

Hidden

Status

SEO

==================================================

YANG TIDAK BOLEH DIUBAH

Buyer SKU Code

Provider

Product ID

Ref Digiflazz

Supplier

Karena berasal dari Digiflazz.

==================================================

SINKRONISASI DIGIFLAZZ

Tambahkan tombol

Sinkronisasi Produk

Ketika ditekan:

Ambil Pricelist terbaru.

Update produk lama.

Tambah produk baru.

Nonaktifkan produk yang sudah tidak ada.

Jangan menghapus histori transaksi.

==================================================

VALIDASI

Buyer SKU Code wajib unik.

Tidak boleh duplicate.

Tidak boleh kehilangan relasi order lama.

==================================================

MARKUP

Harga jual dihitung otomatis:

Modal + Markup

Markup dapat:

Global

Per Brand

Per Provider

Per Produk

Preview harga sebelum disimpan.

==================================================

PROMO

Admin dapat:

Aktifkan Promo

Diskon %

Harga Coret

Tanggal Mulai

Tanggal Berakhir

Auto selesai saat expired.

==================================================

FEATURED

Admin dapat memilih produk Featured.

Featured tampil di Homepage.

==================================================

HIDDEN

Produk Hidden:

Tidak tampil di website.

Tetapi histori order tetap ada.

==================================================

IMPORT EXPORT

Support:

CSV

Excel

Export:

Semua Produk

Kategori

Brand

Harga

Markup

==================================================

RIWAYAT PERUBAHAN

Semua perubahan produk masuk Audit Log.

Catat:

Admin

Field yang diubah

Nilai lama

Nilai baru

Tanggal

==================================================

REALTIME

Jika admin mengubah produk:

Website otomatis update.

Search update.

Kategori update.

Homepage update.

Tanpa refresh.

==================================================

VALIDASI

Pastikan:

npm run lint berhasil.

npm run build berhasil.

Tidak ada TypeScript Error.

Tidak ada hardcode.

Tidak ada data dummy.

Semua data berasal dari database.

==================================================

AUDIT

Lakukan simulasi:

Sinkronisasi Digiflazz.

Tambah produk baru.

Produk hilang dari Digiflazz.

Update harga.

Update markup.

Produk promo.

Produk featured.

Produk hidden.

Import.

Export.

Realtime update.

==================================================

LAPORAN AKHIR

Tampilkan:

1. File yang diubah.

2. Endpoint baru.

3. Struktur database.

4. Sinkronisasi Digiflazz.

5. Audit keamanan.

6. Hasil simulasi.

7. Risiko yang tersisa.

8. Production Readiness.

9. Skor keamanan modul Produk.

10. Pastikan seluruh transaksi lama tetap berjalan tanpa perubahan.
```
