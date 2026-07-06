```
# IMPLEMENTASI LENGKAP RIWAYAT TRANSAKSI DIGITAL CELL (PRODUCTION READY)

Lanjutkan project Digital Cell tanpa mengubah fitur yang sudah selesai (Digiflazz, Checkout, Deposit Otomatis, Wallet Payment, Refund, Ledger, Recovery, Dashboard Keuangan, dan Notifikasi Real-Time).

Tujuan tahap ini adalah membangun sistem Riwayat Transaksi yang lengkap, aman, realtime, dan production-ready.

==================================================
ATURAN
==================================================

- Jangan merusak UI lama.
- Jangan mengubah alur checkout.
- Jangan mengubah alur Digiflazz.
- Jangan mengubah Wallet.
- Jangan mengubah Deposit.
- Jangan mengubah Refund.
- Jangan menggunakan dummy, fake data, hardcode, maupun mock.
- Semua data harus berasal dari database.
- Semua endpoint wajib login.
- User hanya boleh melihat transaksi miliknya.
- Admin memiliki endpoint sendiri.

==================================================
HALAMAN RIWAYAT TRANSAKSI
==================================================

Buat halaman Riwayat Transaksi yang modern dan responsif.

Setiap transaksi menampilkan:

- Nama Produk
- Logo Provider
- Nomor Tujuan
- Kategori
- Provider
- Invoice / ID Order
- Tanggal
- Jam
- Harga
- Metode Pembayaran
- Status
- Badge Status
- Tombol Detail

==================================================
STATUS
==================================================

Gunakan badge berwarna.

Waiting Payment

Paid

Processing

Success

Failed

Refund

Refund Success

Cancelled

Expired

Recovery

==================================================
FILTER
==================================================

Semua

Hari Ini

7 Hari

30 Hari

Berhasil

Diproses

Pending

Refund

Deposit

Wallet

Kategori

Provider

==================================================
SEARCH
==================================================

Cari berdasarkan

Invoice

Nomor Tujuan

Nama Produk

Provider

==================================================
SORT
==================================================

Terbaru

Terlama

Harga terbesar

Harga terkecil

==================================================
DETAIL TRANSAKSI
==================================================

Saat klik Detail.

Tampilkan:

ID Order

Invoice

Ref ID Provider

Buyer SKU Code

Provider

Kategori

Nama Produk

Nomor Tujuan

Harga Produk

Biaya Admin

Diskon

Total

Metode Pembayaran

Status

Tanggal

Jam

Catatan

==================================================
TIMELINE
==================================================

Tampilkan timeline.

Order dibuat

↓

Waiting Payment

↓

Payment Success

↓

Processing

↓

Provider

↓

Success

atau

↓

Failed

↓

Refund

↓

Refund Success

Semua timeline berasal dari database.

==================================================
DETAIL PAYMENT
==================================================

Jika payment gateway dipakai.

Tampilkan

Invoice Gateway

Gateway

Reference

Callback

Payment Time

Expired Time

==================================================
DETAIL REFUND
==================================================

Jika refund ada.

Tampilkan

Nominal

Tanggal

Status

Admin

Alasan

Ledger

==================================================
DETAIL WALLET
==================================================

Jika menggunakan wallet.

Tampilkan

Saldo Sebelum

Saldo Sesudah

Debit

Credit

Ledger Reference

==================================================
DETAIL DIGIFLAZZ
==================================================

Jika provider Digiflazz.

Tampilkan

Buyer SKU Code

Ref ID

SN

Message

Status Provider

Last Update

==================================================
DETAIL DEPOSIT
==================================================

Jika order berasal dari saldo deposit.

Tampilkan

Deposit ID

Saldo Dipakai

Ledger

==================================================
REALTIME
==================================================

Jika status berubah.

Halaman otomatis update.

Tanpa refresh.

Gunakan Notification/Event yang sudah dibuat.

==================================================
EXPORT
==================================================

User dapat

Download PDF Invoice

Download CSV Riwayat

Print Invoice

==================================================
KEAMANAN
==================================================

User tidak boleh melihat transaksi user lain.

Gunakan auth user.

Validasi owner.

Cegah IDOR.

Endpoint admin dipisahkan.

==================================================
ENDPOINT
==================================================

GET

/orders

/orders/history

/orders/{id}

/orders/{id}/timeline

/orders/{id}/invoice

/orders/search

/orders/filter

ADMIN

/admin/orders

/admin/orders/{id}

==================================================
ADMIN
==================================================

Admin melihat seluruh transaksi.

Filter:

Provider

Kategori

Status

Payment

Refund

Wallet

Deposit

Tanggal

User

==================================================
STATISTIK
==================================================

Hitung otomatis

Total Order

Total Success

Total Failed

Total Refund

Total Pending

Total Deposit

Total Wallet Payment

Total Belanja

==================================================
UI
==================================================

Tambahkan

Loading

Skeleton

Retry

Pagination

Infinite Scroll

Responsive

Dark Mode mengikuti tema website.

==================================================
AUDIT
==================================================

Uji:

Order sukses

Order gagal

Refund

Wallet

Deposit

Provider timeout

Recovery

Restart server

Double callback

Spam refresh

Multi tab

==================================================
VALIDASI
==================================================

Pastikan

npm run lint

npm run build

berhasil.

Tidak ada TypeScript error.

Tidak ada duplicate order.

Tidak ada transaksi hilang.

Tidak ada transaksi user lain terbuka.

Timeline sinkron dengan database.

Invoice sinkron.

Refund sinkron.

Wallet sinkron.

Deposit sinkron.

Notifikasi sinkron.

Digiflazz sinkron.

==================================================
LAPORAN AKHIR
==================================================

Setelah implementasi selesai tampilkan:

1. File yang diubah.
2. Struktur endpoint.
3. Struktur database yang digunakan.
4. Hasil audit keamanan.
5. Hasil simulasi transaksi.
6. Risiko tersisa.
7. Skor keamanan Riwayat Transaksi.
8. Production Readiness.
9. Rekomendasi tahap berikutnya.

Jangan berhenti sebelum implementasi, audit, validasi, pengujian, dan laporan selesai.
```
