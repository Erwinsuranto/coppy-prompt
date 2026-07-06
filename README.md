```
# IMPLEMENTASI LENGKAP DASHBOARD ADMIN OPERASIONAL DIGITAL CELL (PRODUCTION READY)

Lanjutkan project Digital Cell tanpa mengubah fitur yang sudah selesai (Digiflazz, Checkout, Deposit Otomatis, Wallet Payment, Refund, Ledger, Recovery, Notifikasi Real-Time, dan Riwayat Transaksi).

Tujuan tahap ini adalah membangun Dashboard Admin Operasional yang benar-benar digunakan untuk mengelola website setiap hari, memonitor transaksi, provider, payment gateway, wallet, deposit, refund, server, dan seluruh aktivitas sistem.

==================================================
ATURAN
==================================================

- Jangan mengubah UI user.
- Jangan mengubah alur checkout.
- Jangan mengubah Wallet.
- Jangan mengubah Refund.
- Jangan mengubah Deposit.
- Jangan mengubah Digiflazz.
- Jangan membuat dummy, mock, fake data, maupun hardcode.
- Semua data berasal dari database dan service yang sudah ada.
- Semua endpoint admin wajib menggunakan autentikasi dan otorisasi admin.
- Dashboard hanya dapat diakses admin.

==================================================
DASHBOARD UTAMA
==================================================

Buat dashboard modern dengan ringkasan realtime.

Tampilkan:

- Total Order Hari Ini
- Total Order Bulan Ini
- Order Success
- Order Processing
- Order Pending
- Order Failed
- Total Deposit Hari Ini
- Total Refund Hari Ini
- Total Wallet Payment
- Total Pendapatan
- Total User
- User Aktif
- Provider Online
- Provider Offline
- Gateway Aktif
- Recovery Queue
- Notifikasi Penting

Semua card update otomatis tanpa refresh.

==================================================
LIVE ORDER MONITOR
==================================================

Buat halaman monitoring order realtime.

Kolom:

- Invoice
- User
- Produk
- Provider
- Tujuan
- Harga
- Payment
- Status
- Waktu
- Tombol Detail

Filter:

- Pending
- Paid
- Processing
- Success
- Failed
- Refund
- Recovery

Search:

- Invoice
- Nomor Tujuan
- Username

Sorting:

- Terbaru
- Terlama

==================================================
DETAIL ORDER ADMIN
==================================================

Saat admin membuka detail order tampilkan:

- Invoice
- Order ID
- Ref ID Provider
- Buyer SKU Code
- Produk
- Provider
- Nomor Tujuan
- Harga
- Payment
- Deposit
- Wallet
- Refund
- Callback
- Timeline
- Raw Response Provider
- Audit Log
- Retry History

==================================================
MONITOR PROVIDER
==================================================

Halaman Provider Monitor.

Untuk setiap provider tampilkan:

- Nama Provider
- Status
- Online/Offline
- Latency
- Last Sync
- Saldo Provider
- Total Order Hari Ini
- Success Rate
- Timeout Rate
- Retry Rate
- Last Callback

Jika provider offline tampilkan alert realtime.

==================================================
PAYMENT GATEWAY
==================================================

Monitor:

- Tripay
- Midtrans
- Xendit
- Duitku
- iPaymu
- Gateway lain yang aktif

Tampilkan:

- Status
- Callback terakhir
- Pending Payment
- Success
- Failed
- Timeout
- Response Time
- Health Status

==================================================
DEPOSIT MONITOR
==================================================

Halaman Deposit.

Filter:

- Pending
- Success
- Failed
- Expired

Tampilkan:

- User
- Invoice
- Nominal
- Gateway
- Status
- Callback
- Ledger

==================================================
REFUND MONITOR
==================================================

Halaman Refund.

Filter:

- Pending
- Approved
- Success
- Failed

Tampilkan:

- User
- Order
- Nominal
- Status
- Admin
- Ledger
- Timeline

==================================================
WALLET MONITOR
==================================================

Tampilkan:

- Total Saldo User
- Total Saldo Beredar
- Top Up
- Pengeluaran
- Refund
- Koreksi Saldo

Cari berdasarkan user.

==================================================
RECOVERY QUEUE
==================================================

Buat halaman Recovery.

Menampilkan:

- Provider Timeout
- Waiting Callback
- Retry
- Queue
- Recovery Status
- Last Retry
- Retry Count

==================================================
SERVER MONITOR
==================================================

Tampilkan:

- CPU
- RAM
- Storage
- Node.js
- MongoDB
- Uptime
- Response API
- Ping Provider
- Ping Gateway

Refresh otomatis.

==================================================
AUDIT LOG
==================================================

Semua aktivitas admin wajib tercatat.

Contoh:

- Login
- Logout
- Edit Produk
- Koreksi Saldo
- Refund
- Deposit
- Hapus Produk
- Tambah Produk
- Maintenance
- Pengaturan

Filter:

- Admin
- Jenis Aktivitas
- Tanggal

==================================================
MAINTENANCE
==================================================

Admin dapat:

- Aktifkan Maintenance
- Nonaktifkan Maintenance
- Atur Pesan Maintenance
- Countdown Maintenance
- Whitelist Admin/IP
- Preview Halaman Maintenance

==================================================
BACKUP
==================================================

Menu Backup Database.

Fitur:

- Backup Manual
- Restore
- Riwayat Backup
- Download Backup
- Jadwal Backup Otomatis
- Status Backup

==================================================
PENGATURAN WEBSITE
==================================================

Kelola:

- Nama Website
- Logo
- Banner
- Kontak
- WhatsApp
- Email
- SEO
- Jam Operasional
- Maintenance
- Provider Aktif
- Gateway Aktif

==================================================
NOTIFIKASI ADMIN
==================================================

Realtime.

Admin mendapat notifikasi:

- Order Baru
- Provider Offline
- Payment Error
- Callback Gagal
- Refund Baru
- Deposit Baru
- Recovery
- Login Mencurigakan
- Server Error

==================================================
KEAMANAN
==================================================

Dashboard hanya bisa diakses admin.

Semua endpoint:

- Auth
- Role Admin
- Audit Log
- CSRF Protection (jika digunakan)
- Rate Limit
- Validasi Input

Tidak boleh ada IDOR.

==================================================
REALTIME
==================================================

Gunakan Notification/Event Bus yang sudah ada.

Dashboard otomatis update ketika:

- Order berubah
- Deposit masuk
- Refund dibuat
- Wallet berubah
- Provider berubah
- Gateway berubah
- Recovery berjalan

Tanpa refresh halaman.

==================================================
UI
==================================================

Tambahkan:

- Loading
- Skeleton
- Empty State
- Error State
- Retry
- Responsive
- Dark Mode mengikuti tema
- Pagination
- Search
- Filter
- Export CSV

==================================================
VALIDASI
==================================================

Pastikan:

- npm run lint berhasil.
- npm run build berhasil.
- Tidak ada TypeScript error.
- Tidak ada data dummy.
- Tidak ada hardcode.
- Semua data realtime berasal dari database.
- Dashboard tidak mempengaruhi transaksi user.
- Seluruh endpoint admin aman.
- Tidak ada memory leak.
- Tidak ada query lambat.
- Tidak ada duplicate data.

==================================================
AUDIT
==================================================

Lakukan simulasi:

- Order Baru
- Payment Success
- Payment Failed
- Provider Timeout
- Recovery
- Refund
- Deposit
- Wallet Update
- Server Restart
- Gateway Offline
- Provider Offline
- Multi Admin Login
- Spam Request
- Reconnect Realtime

==================================================
LAPORAN AKHIR
==================================================

Setelah implementasi selesai tampilkan laporan lengkap:

1. File yang ditambah atau diubah.
2. Struktur Dashboard Admin.
3. Endpoint baru.
4. Integrasi dengan Digiflazz, Payment Gateway, Wallet, Refund, Deposit, Recovery, dan Notifikasi.
5. Hasil lint dan build.
6. Hasil audit keamanan.
7. Hasil simulasi seluruh fitur.
8. Risiko yang masih tersisa.
9. Skor keamanan Dashboard Admin.
10. Production Readiness.

Jangan berhenti sebelum implementasi, pengujian, audit, validasi, dan laporan selesai.
```
