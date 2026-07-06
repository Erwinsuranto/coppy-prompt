```
# IMPLEMENTASI LENGKAP SISTEM NOTIFIKASI REAL-TIME DIGITAL CELL (PRODUCTION READY)

Lanjutkan pengembangan project Digital Cell tanpa mengubah UI maupun fitur yang sudah selesai (Digiflazz, Checkout, Wallet Payment, Deposit Otomatis, Refund, Ledger, Recovery, Dashboard Keuangan, dll).

Tujuan tahap ini adalah membangun sistem Notifikasi Real-Time yang benar-benar production-ready, aman, scalable, dan terintegrasi dengan seluruh aktivitas website.

==================================================
ATURAN UMUM
==================================================

- Jangan membuat ulang fitur yang sudah selesai.
- Jangan merusak alur transaksi yang sudah ada.
- Jangan menggunakan dummy, mock, fake data, ataupun hardcode.
- Gunakan database sebagai sumber utama.
- Gunakan arsitektur event-driven.
- Semua perubahan harus lolos npm run lint dan npm run build.
- Tidak boleh ada TypeScript Error.
- Pertahankan seluruh UI yang sudah ada.

==================================================
EVENT YANG WAJIB MEMBUAT NOTIFIKASI
==================================================

ORDER

- Order dibuat
- Menunggu pembayaran
- Pembayaran berhasil
- Pembayaran gagal
- Order diproses
- Order dikirim ke provider
- Provider timeout
- Recovery berjalan
- Order berhasil
- Order gagal
- Order dibatalkan
- Order expired

DEPOSIT

- Deposit dibuat
- Deposit pending
- Deposit berhasil
- Deposit gagal
- Deposit expired

WALLET

- Saldo bertambah
- Saldo berkurang
- Refund masuk
- Koreksi saldo admin

REFUND

- Refund dibuat
- Refund diproses
- Refund berhasil
- Refund ditolak

DIGIFLAZZ

- Provider offline
- Provider online kembali
- Callback gagal
- Callback berhasil
- Recovery berhasil

SYSTEM

- Maintenance aktif
- Maintenance selesai
- Login baru
- Password diubah
- Aktivitas admin penting

==================================================
DATABASE
==================================================

Buat collection/table notifications apabila belum ada.

Field minimum:

id

userId

title

message

type

entityType

entityId

status

icon

color

isRead

metadata

createdAt

updatedAt

Tambahkan index yang diperlukan agar query cepat.

==================================================
NOTIFICATION SERVICE
==================================================

Buat service khusus NotificationService.

Minimal memiliki fungsi:

createNotification()

createAdminNotification()

broadcastUser()

broadcastAdmin()

getNotifications()

countUnread()

markAsRead()

markAllRead()

deleteNotification()

cleanupOldNotifications()

Seluruh project wajib menggunakan service ini.

==================================================
EVENT BUS
==================================================

Jangan memanggil NotificationService langsung dari semua file.

Gunakan Event Bus.

Contoh event:

OrderCreated

PaymentSuccess

PaymentFailed

ProviderSuccess

ProviderFailed

RefundCreated

RefundSuccess

DepositSuccess

WalletUpdated

MaintenanceStarted

MaintenanceFinished

AdminLogin

Semua event otomatis menghasilkan notification.

==================================================
REALTIME
==================================================

Gunakan websocket/socket server yang sudah ada.

Jika belum tersedia maka implementasikan.

Saat status berubah:

Backend

↓

Event

↓

NotificationService

↓

Database

↓

Socket

↓

Frontend

Tanpa refresh halaman.

==================================================
USER NOTIFICATION
==================================================

User hanya boleh melihat notifikasi miliknya.

Contoh:

Pembayaran berhasil

Order sedang diproses

Produk berhasil dikirim

Refund berhasil

Deposit berhasil

Saldo bertambah

==================================================
ADMIN NOTIFICATION
==================================================

Admin memiliki notification sendiri.

Contoh:

Order baru

Deposit baru

Refund baru

Provider timeout

Gateway error

Recovery berjalan

Server error

User baru

==================================================
BELL NOTIFICATION
==================================================

Aktifkan icon lonceng.

Badge otomatis berubah.

Contoh

1

5

10

99+

Saat dibuka

badge langsung sinkron.

==================================================
DROPDOWN
==================================================

Klik icon lonceng.

Tampilkan:

Icon

Judul

Isi

Waktu

Status

Belum dibaca diberi highlight.

==================================================
HALAMAN NOTIFIKASI
==================================================

Tambahkan halaman:

/notifications

Berisi:

Semua

Belum dibaca

Order

Deposit

Refund

Wallet

System

Search

Filter

Pagination

Infinite Scroll

Relative Time

==================================================
AKSI USER
==================================================

Klik notifikasi Order

↓

Buka Detail Order

Klik Deposit

↓

Buka Detail Deposit

Klik Refund

↓

Buka Detail Refund

Klik Wallet

↓

Buka Riwayat Wallet

==================================================
KEAMANAN
==================================================

Semua endpoint wajib login.

Validasi userId.

Tidak boleh ada IDOR.

Tidak boleh membaca notification milik user lain.

Admin dan user dipisahkan.

==================================================
ENDPOINT
==================================================

GET

/notifications

/notifications/unread

/notifications/count

POST

/notifications/read

/notifications/read-all

DELETE

/notifications/{id}

ADMIN

/admin/notifications

/admin/notifications/system

/admin/notifications/provider

==================================================
UI
==================================================

Tambahkan:

Loading

Skeleton

Empty State

Retry

Relative Time

Pull Refresh Mobile

Responsive

Dark Mode mengikuti tema website.

==================================================
PERFORMA
==================================================

Notification tidak boleh duplicate.

Socket tidak boleh reconnect berulang.

Gunakan pagination.

Query wajib memakai index.

==================================================
AUDIT
==================================================

Lakukan simulasi berikut:

Spam klik checkout

Double payment

Double callback

Provider timeout

Recovery

Refund

Deposit

Wallet Update

Maintenance

Restart Server

Reconnect Socket

Semua harus menghasilkan notification yang benar.

==================================================
VALIDASI AKHIR
==================================================

Pastikan:

- npm run lint berhasil.
- npm run build berhasil.
- Tidak ada TypeScript error.
- Tidak ada duplicate notification.
- Badge selalu sinkron.
- Socket realtime berjalan normal.
- Notification tersimpan di database.
- Admin dan user terpisah.
- Tidak ada memory leak.
- Tidak mengubah UI lama.
- Tidak mengubah alur transaksi Digiflazz.
- Tidak mengubah Checkout.
- Tidak mengubah Wallet Payment.
- Tidak mengubah Deposit Otomatis.
- Tidak mengubah Refund.
- Tidak mengubah Ledger.
- Tidak mengubah Recovery.

==================================================
LAPORAN AKHIR
==================================================

Setelah implementasi selesai, tampilkan laporan lengkap berisi:

1. Semua file yang ditambah atau diubah.
2. Struktur database notifikasi.
3. Diagram alur event hingga notifikasi tampil di frontend.
4. Hasil pengujian seluruh skenario.
5. Hasil lint dan build.
6. Risiko yang masih tersisa.
7. Skor keamanan fitur notifikasi.
8. Penilaian production readiness.
9. Rekomendasi tahap pengembangan berikutnya.

Jangan berhenti sebelum seluruh implementasi, pengujian, audit, validasi, dan laporan selesai.
```
