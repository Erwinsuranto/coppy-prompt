```


# Telegram Drive Website - Tahap 13 : Authentication & Admin Foundation

Tahap sebelumnya telah selesai.

Saat ini project telah memiliki:

✅ Telegram Bot
✅ Storage Service
✅ REST API
✅ Swagger
✅ Website Foundation
✅ Design System
✅ Landing Page
✅ Premium Download Page

JANGAN mengubah backend yang sudah berjalan.

JANGAN mengubah REST API yang sudah ada kecuali menambah endpoint authentication.

Semua fitur lama harus tetap berjalan.

====================================================

TUJUAN

Membangun Authentication dan Admin Foundation.

Tahap ini hanya membuat sistem login dan pondasi admin.

Belum membuat Dashboard lengkap.

Belum membuat Upload.

Belum membuat Statistics.

====================================================

AUTHENTICATION

Gunakan JWT.

Support:

Access Token

Refresh Token

Remember Login

Logout

Session Validation

====================================================

ROLE

Admin

Moderator

User

Role disimpan di database.

====================================================

DATABASE

Tambahkan model bila diperlukan:

AdminUser

atau sesuaikan dengan struktur project.

Field minimal:

id

username

email

passwordHash

role

isActive

lastLogin

createdAt

updatedAt

Password wajib menggunakan bcrypt.

====================================================

API

POST /api/auth/login

POST /api/auth/logout

POST /api/auth/refresh

GET /api/auth/me

====================================================

LOGIN

Login menggunakan:

Username atau Email

Password

====================================================

MIDDLEWARE

adminAuth

requireLogin

requireRole

====================================================

FRONTEND

Route:

/login

/admin

====================================================

HALAMAN LOGIN

Desain premium.

Glassmorphism.

Gradient Background.

Responsive.

Dark Mode.

Light Mode.

Logo Telegram Drive.

Input Username/Email.

Input Password.

Remember Me.

Show Password.

Forgot Password (placeholder).

Login Button.

Loading Animation.

====================================================

VALIDASI

Gunakan Zod.

====================================================

ERROR

Wrong Password

Account Disabled

Token Expired

Unauthorized

====================================================

SESSION

Gunakan HTTP Only Cookie bila memungkinkan.

Jika belum memungkinkan, gunakan JWT Storage yang mudah diganti nanti.

====================================================

ADMIN LAYOUT

Buat layout admin.

Sidebar kosong.

Header kosong.

Content Area.

Belum perlu isi menu.

====================================================

SIDEBAR

Tempatkan placeholder:

Dashboard

Files

Upload

Users

Channels

Statistics

Settings

Storage

Premium

API

Logs

====================================================

HEADER

Avatar

Theme Toggle

Notification Placeholder

====================================================

ACCESS

Jika belum login.

Redirect ke Login.

Jika bukan Admin.

Tampilkan halaman Unauthorized.

====================================================

ANIMATION

Gunakan Framer Motion.

Fade

Slide

Scale

====================================================

RESPONSIVE

Mobile

Tablet

Desktop

====================================================

CODING STYLE

Gunakan:

Clean Architecture

TypeScript Strict

Reusable Components

Tidak menggunakan any

====================================================

PENTING

Belum membuat:

Dashboard

Upload

Statistics

Settings

Premium

Folder

Kategori

====================================================

OUTPUT

1.

Jelaskan perubahan database.

2.

Jelaskan endpoint authentication.

3.

Jelaskan middleware.

4.

Jelaskan struktur admin.

5.

Pastikan:

npm install

npm run build

npm run dev

berjalan tanpa error.

6.

Berhenti setelah Authentication & Admin Foundation selesai.




```
