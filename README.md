```
# Telegram Drive Website - Tahap 19 : User Management (Professional User Administration)

Tahap Statistics & Analytics telah selesai.

Project saat ini memiliki:

✅ Telegram Bot
✅ Upload Engine
✅ Download Engine
✅ Storage Service
✅ REST API
✅ Authentication
✅ Dashboard
✅ Files Manager
✅ Upload Manager
✅ Settings Center
✅ Statistics & Analytics

JANGAN mengubah fitur yang sudah berjalan.

Gunakan Design System yang sudah ada.

====================================================

TUJUAN

Membangun User Management profesional.

Semua user Telegram Drive dikelola dari Dashboard.

====================================================

ROUTE

/admin/users

====================================================

TABLE

Gunakan Data Table modern.

Kolom:

Avatar

Nama

Username

Telegram ID

Role

Status

Total Upload

Total Download

Storage

Tanggal Daftar

Terakhir Aktif

Action

====================================================

SEARCH

Realtime

Debounce

Cari berdasarkan:

Nama

Username

Telegram ID

====================================================

FILTER

Role

Status

Tanggal Daftar

Premium

====================================================

SORT

Nama

Upload

Download

Storage

Tanggal Daftar

====================================================

ROLE

Owner

Admin

Moderator

User

====================================================

STATUS

Active

Suspended

Banned

Deleted

====================================================

ACTION

View

Edit

Change Role

Suspend

Ban

Activate

Delete

====================================================

DETAIL DRAWER

Saat klik user tampilkan:

Foto Profil

Nama

Username

Telegram ID

Role

Status

Tanggal Daftar

Login Terakhir

Jumlah Upload

Jumlah Download

Storage Digunakan

File Terakhir

IP Terakhir (placeholder jika belum tersedia)

====================================================

EDIT USER

Role

Status

Catatan Admin

====================================================

MULTI SELECT

Suspend Selected

Ban Selected

Delete Selected

Export Selected

====================================================

EXPORT

CSV

JSON

====================================================

USER ACTIVITY

Upload History

Download History

Generate Link

Login History

====================================================

EMPTY STATE

Gunakan Design System.

====================================================

LOADING

Skeleton.

====================================================

RESPONSIVE

Mobile

Tablet

Desktop

====================================================

ANIMATION

Framer Motion

Fade

Slide

Drawer Animation

====================================================

API

Gunakan endpoint backend.

Jika endpoint belum tersedia tambahkan tanpa merusak endpoint lama:

GET /api/users

GET /api/users/:id

PUT /api/users/:id

DELETE /api/users/:id

POST /api/users/:id/role

POST /api/users/:id/status

GET /api/users/:id/activity

GET /api/users/export

====================================================

DATABASE

Gunakan tabel User yang sudah ada.

Jangan membuat tabel baru jika tidak diperlukan.

Jika beberapa data belum tersedia tampilkan placeholder dan beri komentar TODO.

====================================================

SECURITY

Semua endpoint wajib menggunakan Admin Authentication.

Owner tidak boleh dihapus.

Role Owner tidak boleh diturunkan kecuali oleh Owner lain.

====================================================

DESIGN

Gunakan seluruh komponen Design System.

Glass Card

Rounded

Dark Mode

Light Mode

====================================================

CODING STYLE

Reusable Components

TypeScript Strict

SOLID

Repository Pattern

Tidak menggunakan any

====================================================

PENTING

Belum membuat:

Folder Management

Category Management

Audit Log

Backup Manager

Notification Center

Premium System

Production Ready

====================================================

OUTPUT

1. Jelaskan struktur User Management.

2. Jelaskan endpoint yang digunakan.

3. Jelaskan Role dan Permission.

4. Jelaskan placeholder yang digunakan bila data belum tersedia.

5. Pastikan:

npm install

npx prisma generate

npx prisma migrate dev

npm run build

npm run dev

berjalan tanpa error.

6. Jangan mengubah Upload Manager, Files Manager, Dashboard, Settings, Statistics, REST API, Bot Telegram, Download Engine maupun Storage Service.

7. Berhenti setelah User Management selesai.
```
