```
# IMPLEMENTASI LENGKAP MODUL PROFIL PENGGUNA (USER PROFILE) DIGITAL CELL

Lakukan audit terlebih dahulu sebelum mengubah kode.

Jangan langsung membuat fitur baru.

Periksa seluruh project, frontend, backend, database, API, authentication, dashboard admin, dan relasi data.

Jika fitur sudah ada sebagian, lanjutkan dan sempurnakan tanpa membuat versi baru.

==================================================

TARGET

Menyelesaikan seluruh modul Profil Pengguna hingga Production Ready.

Semua data harus berasal dari database.

Tidak boleh ada data dummy.

Tidak boleh ada hardcode.

Harus kompatibel dengan seluruh sistem transaksi yang sudah selesai.

==================================================

AUDIT

Periksa terlebih dahulu:

- Struktur tabel/collection user
- Authentication
- JWT
- Session
- Login
- Register
- Dashboard User
- Dashboard Admin
- Notification
- Wallet
- Order
- Riwayat
- Deposit
- Refund
- Upload File
- Storage Avatar

Buat laporan:

- Yang sudah ada
- Yang belum ada
- Yang perlu diperbaiki
- Yang berpotensi merusak sistem jika diubah

==================================================

PROFIL USER

Lengkapi halaman Profil.

Minimal memiliki:

Foto Profil

Nama Lengkap

Username

Email

Nomor HP

Tanggal Daftar

Status Akun

Role

Saldo

Jumlah Order

Total Deposit

Total Refund

Terakhir Login

==================================================

EDIT PROFIL

User dapat mengubah:

Nama

Username (jika diizinkan)

Email

Nomor HP

Foto Profil

Bio (opsional)

Semua perubahan harus divalidasi backend.

==================================================

UPLOAD FOTO

Upload Avatar.

Validasi:

jpg

jpeg

png

webp

Ukuran maksimal.

Resize otomatis bila perlu.

Hapus file lama bila diganti.

Tidak boleh overwrite avatar user lain.

==================================================

EMAIL

Audit apakah email sudah digunakan.

Jika belum:

Tambahkan.

Jika sudah:

Pastikan unik.

Tidak boleh duplicate.

Semua perubahan email dicatat.

==================================================

NOMOR HP

Audit field nomor HP.

Validasi format Indonesia.

Tidak boleh duplicate bila kebijakan sistem mengharuskan unik.

==================================================

PASSWORD

Audit sistem password.

Pastikan:

Hash aman.

Tidak ada plaintext.

User harus memasukkan:

Password lama

Password baru

Konfirmasi password

Logout semua session lama bila password diganti.

==================================================

LOGIN SESSION

Audit:

JWT

Refresh Token

Session

Remember Login

Perangkat aktif

Tambahkan halaman:

Perangkat yang sedang login.

Logout device tertentu.

Logout semua device.

==================================================

RIWAYAT LOGIN

Catat:

IP

Browser

OS

Tanggal

Jam

Lokasi bila tersedia.

==================================================

ADMIN PANEL

Tambahkan halaman Kelola User.

Admin dapat melihat:

Semua User

Search

Filter

Pagination

Status

Role

Saldo

Deposit

Order

Refund

Login Terakhir

==================================================

DETAIL USER

Admin dapat melihat:

Profil lengkap

Wallet

Deposit

Refund

Riwayat Order

Notifikasi

Riwayat Login

Audit Log

==================================================

ADMIN ACTION

Admin dapat:

Reset Password

Nonaktifkan User

Aktifkan User

Verifikasi Email

Verifikasi Nomor HP

Ganti Role

Lihat Avatar

Hapus Avatar

Semua aksi harus masuk Audit Log.

==================================================

KEAMANAN

Pastikan:

JWT tetap aman.

IDOR tidak ada.

User hanya dapat melihat profil miliknya.

Admin hanya melalui endpoint admin.

Tidak ada data sensitif bocor.

==================================================

DATABASE

Audit apakah perlu migration.

Jangan merusak collection lama.

Jika menambah field baru:

Gunakan migration.

Pastikan kompatibel dengan data lama.

==================================================

NOTIFIKASI

Jika user mengubah:

Password

Email

Nomor HP

Foto Profil

Kirim notifikasi ke user.

==================================================

REALTIME

Perubahan profil harus langsung muncul di:

Header Website

Dashboard

Menu Akun

Admin Panel

Tanpa refresh manual bila memungkinkan.

==================================================

VALIDASI

Jalankan:

npm run lint

npm run build

Pastikan:

Tidak ada TypeScript Error.

Tidak ada Build Error.

Tidak ada Runtime Error.

==================================================

SIMULASI

Lakukan audit dan simulasi:

- Edit Profil
- Upload Avatar
- Ganti Password
- Ganti Email
- Ganti Nomor HP
- Logout Semua Device
- Admin Reset Password
- Admin Nonaktifkan User
- Admin Aktifkan User
- Admin Ganti Role
- User mencoba membuka profil user lain
- Admin membuka detail user
- Upload file gagal
- Avatar corrupt
- Email duplicate
- Nomor HP duplicate

==================================================

LAPORAN AKHIR

Tampilkan laporan lengkap:

1. File yang diubah.
2. Endpoint yang ditambah atau diperbaiki.
3. Collection/tabel yang berubah.
4. Migration yang dibuat.
5. Audit keamanan.
6. Hasil simulasi.
7. Risiko yang masih tersisa.
8. Skor keamanan modul Profil User.
9. Production Readiness.
10. Pastikan seluruh fitur lama (checkout, transaksi, wallet, deposit, refund, notifikasi, riwayat transaksi, dashboard admin, dan sinkronisasi Digiflazz) tetap berjalan normal tanpa regresi.
```
