```
# LANJUTKAN IMPLEMENTASI AUTHENTICATION DIGITAL CELL (PRODUCTION READY)

Lanjutkan project Digital Cell.

Jangan membuat sistem authentication baru.

Gunakan sistem login yang sudah ada dan sempurnakan menjadi production ready.

==================================================

TARGET

Selesaikan seluruh Authentication sampai Production Ready.

Seluruh fitur login harus menggunakan database yang sama.

Satu user hanya memiliki satu akun walaupun login menggunakan Email atau Google.

Tidak boleh membuat akun ganda.

==================================================

IMPLEMENTASI

Lanjutkan seluruh implementasi yang sudah diaudit sebelumnya.

Selesaikan:

✅ Profil User
✅ Upload Avatar
✅ Edit Profil
✅ Ganti Password
✅ Login History
✅ Session Manager
✅ Admin User Management

Setelah itu lanjutkan Authentication.

==================================================

PENDAFTARAN EMAIL OTP

Tambahkan sistem register menggunakan Email.

Flow:

Nama

Email

Password

Konfirmasi Password

Kirim OTP ke Email

Verifikasi OTP

Akun aktif

Login otomatis.

OTP memiliki masa berlaku.

OTP hanya sekali pakai.

OTP disimpan aman di database.

Rate limit pengiriman OTP.

==================================================

LOGIN EMAIL

User login menggunakan:

Email

Password

Jika belum verifikasi email:

Tolak login.

Tawarkan kirim ulang OTP.

==================================================

LOGIN GOOGLE

Tambahkan Login menggunakan Google OAuth.

Gunakan OAuth resmi Google.

Jangan menggunakan library yang sudah deprecated.

==================================================

FLOW LOGIN GOOGLE

Klik Login Google

Pilih akun Google

Verifikasi token Google

Jika email belum ada:

Buat akun baru.

Jika email sudah ada:

Hubungkan ke akun lama.

Login berhasil.

==================================================

LINK ACCOUNT

Jika user awalnya daftar Email OTP lalu login Google dengan email yang sama:

Jangan membuat akun baru.

Hubungkan provider Google ke akun tersebut.

==================================================

DATABASE

Tambahkan field yang diperlukan:

google_id

auth_provider

email_verified

last_login

avatar_url

token_version

login_history

session

==================================================

LOGIN HISTORY

Simpan:

IP

Browser

OS

Tanggal

Jam

Provider Login

==================================================

SESSION

User dapat melihat:

Perangkat aktif

Logout device tertentu

Logout semua device

==================================================

LUPA PASSWORD

Flow:

Masukkan Email

Kirim OTP

Verifikasi OTP

Password Baru

Login kembali

==================================================

ADMIN PANEL

Tambahkan menu Authentication.

Admin dapat melihat:

Jumlah User

User Google

User Email

User Belum Verifikasi

Login Hari Ini

Login Gagal

User Terblokir

==================================================

KEAMANAN

Password wajib hash.

OTP hash.

JWT tetap digunakan.

Refresh Token tetap aman.

Rate Limit Login.

Rate Limit OTP.

Captcha support bila diperlukan.

==================================================

EMAIL

Gunakan SMTP production.

Jangan hardcode akun email.

Gunakan ENV.

==================================================

NOTIFIKASI

Kirim Email ketika:

Register

OTP

Login Baru

Password Diganti

Email Diganti

Google berhasil dihubungkan

==================================================

VALIDASI

Pastikan:

npm run lint

npm run build

Tidak ada TypeScript Error.

Tidak ada Build Error.

==================================================

SIMULASI

Lakukan audit:

Register Email OTP

OTP salah

OTP expired

Resend OTP

Login Email

Login Google

Hubungkan akun Google

Reset Password

Logout Semua Device

Login Multi Device

Admin melihat user

Admin reset password

==================================================

LAPORAN

Tampilkan:

1. File yang diubah.

2. Endpoint baru.

3. Collection yang berubah.

4. Migration.

5. Audit keamanan.

6. Hasil simulasi.

7. Risiko yang tersisa.

8. Production Readiness.

9. Skor keamanan Authentication.

10. Pastikan seluruh sistem lama (Checkout, Wallet, Deposit, Refund, Riwayat, Notifikasi, Dashboard Admin, Produk, Sinkronisasi Digiflazz) tetap berjalan normal tanpa regresi.
```

