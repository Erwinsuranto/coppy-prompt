```
Lanjutkan pengembangan website Digital Cell.

PENTING:
- Jangan mengubah UI pelanggan yang sudah ada.
- Jangan mengubah alur checkout.
- Jangan mengubah sistem transaksi yang sudah stabil.
- Fokus hanya membuat Dashboard Keuangan (Wallet & Deposit Center) untuk Admin.

==================================================
TUJUAN
==================================================

Buat Dashboard Keuangan yang menjadi pusat kontrol seluruh saldo member dan transaksi deposit.

Dashboard harus real-time dan mengambil data dari MongoDB, bukan data dummy.

==================================================
MENU BARU
==================================================

Tambah menu Admin:

💰 Keuangan

Sub menu:

1. Dashboard Keuangan
2. Wallet Member
3. Deposit
4. Ledger
5. Koreksi Saldo
6. Statistik
7. Audit Log

==================================================
DASHBOARD KEUANGAN
==================================================

Tampilkan card:

• Total Saldo Member
• Total Deposit Hari Ini
• Total Deposit Bulan Ini
• Deposit Pending
• Deposit Berhasil
• Deposit Gagal
• Total Refund
• Total Transaksi Produk
• Total Pendapatan Hari Ini
• Total Pendapatan Bulan Ini

Semua data realtime dari database.

==================================================
WALLET MEMBER
==================================================

Tampilkan tabel:

Nama User

Email

Nomor HP

Saldo

Total Deposit

Total Belanja

Tanggal Daftar

Status

Pencarian cepat.

Sorting.

Pagination.

==================================================
DETAIL WALLET
==================================================

Klik user.

Tampilkan:

Saldo sekarang

Riwayat Deposit

Riwayat Pembelian

Riwayat Refund

Riwayat Penyesuaian Saldo

Ledger lengkap

==================================================
LEDGER
==================================================

Semua perubahan saldo harus tampil.

Kolom:

Tanggal

User

Jenis

Nominal

Saldo Sebelum

Saldo Sesudah

Referensi

Admin

Status

Filter:

Tanggal

User

Jenis

Nominal

==================================================
KOREKSI SALDO
==================================================

Admin dapat:

Tambah saldo

Kurangi saldo

Wajib:

Alasan

Catatan

Password admin

Semua koreksi masuk ledger.

Tidak boleh ada update saldo langsung.

==================================================
DEPOSIT
==================================================

Halaman Deposit Admin.

Filter:

Pending

Processing

Success

Failed

Expired

Cancelled

Cari:

Invoice

User

Gateway

Reference

==================================================
DETAIL DEPOSIT
==================================================

Klik deposit.

Tampilkan:

Invoice

Gateway

Reference

Nominal

Fee

Total

Status

Callback

Recovery

Timeline

Raw Callback

Raw Response

==================================================
STATISTIK
==================================================

Grafik:

Deposit harian

Deposit bulanan

Top member deposit

Top member belanja

Pendapatan

Refund

Wallet Growth

==================================================
AUDIT LOG
==================================================

Catat:

Login admin

Koreksi saldo

Refund

Perubahan gateway

Perubahan status

Semua immutable.

==================================================
EXPORT
==================================================

Tambah Export:

CSV

Excel

PDF

Untuk:

Wallet

Deposit

Ledger

Statistik

==================================================
NOTIFIKASI
==================================================

Jika:

Deposit sukses

Refund

Koreksi saldo

Kirim notifikasi:

Website

Telegram Admin

WhatsApp Admin (jika aktif)

==================================================
SECURITY
==================================================

Pastikan:

Hanya Admin dapat membuka Dashboard Keuangan.

User tidak dapat mengakses endpoint admin.

Gunakan role-based permission.

==================================================
PERFORMANCE
==================================================

Gunakan pagination.

Gunakan index MongoDB.

Jangan query seluruh collection.

==================================================
VALIDASI
==================================================

Jalankan:

npm run lint

npm run build

==================================================
LAPORAN
==================================================

Setelah selesai tampilkan:

- File yang diubah
- Collection yang digunakan
- Endpoint baru
- Menu baru
- Statistik yang dibuat
- Fitur keamanan yang ditambahkan
- Risiko yang masih tersisa
- Skor keamanan Dashboard Keuangan
```
