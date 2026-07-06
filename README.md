```
Lakukan implementasi lengkap sistem autentikasi Admin Telegram Drive. Jangan berhenti sampai login benar-benar berfungsi.

TARGET AKHIR
- Saya bisa membuka /login.
- Login menggunakan akun admin default.
- Setelah login langsung masuk ke /admin/dashboard.
- Refresh halaman tidak membuat logout.
- Logout berfungsi.
- Semua route admin terlindungi.

====================================================
1. DATABASE
====================================================

Buat tabel/collection Admin jika belum ada.

Field:

id
username (unique)
email (unique)
passwordHash
role
isActive
createdAt
updatedAt

Role:
SUPER_ADMIN
ADMIN

====================================================
2. SEED ADMIN
====================================================

Jika database kosong, otomatis buat akun:

Username:
admin

Email:
admin@example.com

Password:
admin123

Password wajib di-hash menggunakan bcrypt.

Jangan simpan password plaintext.

====================================================
3. LOGIN API
====================================================

Buat endpoint login.

Validasi:

- username atau email
- password

Jika salah:
401

Jika benar:
buat session menggunakan HttpOnly Cookie (atau JWT HttpOnly).

====================================================
4. SESSION
====================================================

Session bertahan setelah refresh.

Middleware membaca session.

Jika belum login:

redirect ke

/login

====================================================
5. PROTECTED ROUTES
====================================================

Lindungi:

/admin

/admin/*

Tanpa login tidak boleh diakses.

====================================================
6. LOGOUT
====================================================

Hapus cookie/session.

Redirect ke /login.

====================================================
7. FRONTEND LOGIN
====================================================

Perbaiki halaman login.

Hilangkan "Network Error".

Pastikan request menuju endpoint login yang benar.

Jika backend memakai port berbeda,
sesuaikan BASE_URL/API_URL.

====================================================
8. ENV
====================================================

Buat .env jika belum ada.

Tambahkan seluruh variabel yang diperlukan.

====================================================
9. ERROR HANDLING
====================================================

Tampilkan pesan:

Username atau Password salah

Server tidak tersedia

Session habis

====================================================
10. TEST
====================================================

Jalankan seluruh project.

Lakukan login menggunakan:

Username:
admin

Password:
admin123

Pastikan berhasil masuk dashboard.

====================================================
11. HASIL AKHIR
====================================================

Setelah selesai tampilkan:

- file yang diubah
- endpoint login
- struktur session
- akun admin default
- cara menjalankan backend
- cara menjalankan frontend
- cara login

Jangan berhenti sampai login benar-benar berhasil dan tidak ada lagi "Network Error".



```
