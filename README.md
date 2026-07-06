```
# Telegram Drive Website - Tahap 21 : Audit Log & Activity History (Enterprise Audit System)

Tahap Folder Management telah selesai.

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
✅ Statistics
✅ User Management
✅ Folder Management

JANGAN mengubah fitur yang sudah berjalan.

JANGAN merusak REST API.

Gunakan seluruh Design System.

====================================================

TUJUAN

Membangun Audit Log profesional.

Semua aktivitas penting harus tercatat otomatis.

Audit Log hanya bisa dilihat oleh Owner dan Admin.

Moderator hanya boleh melihat log yang diizinkan.

User tidak memiliki akses.

====================================================

ROUTE

/admin/audit

====================================================

DATABASE

Jika belum ada buat tabel:

AuditLog

id

userId

username

role

action

module

description

targetType

targetId

metadata (JSON)

ipAddress

userAgent

status

createdAt

====================================================

CATAT OTOMATIS

Login

Logout

Upload File

Delete File

Rename File

Move File

Copy Link

Generate Link

Disable Link

Enable Link

Download Link Generate

Tambah Folder

Rename Folder

Delete Folder

Move Folder

Tambah User

Edit User

Delete User

Suspend User

Promote Admin

Demote Admin

Role Change

Update Settings

Force Join ON

Force Join OFF

Tambah Channel

Hapus Channel

Login Gagal

Token Expired

Backup

Restore

====================================================

STATUS

Success

Failed

Warning

====================================================

MODULE

Authentication

Upload

Download

Files

Folders

Users

Settings

Statistics

Storage

Telegram

System

====================================================

TABLE

Kolom:

Tanggal

User

Role

Module

Action

Status

IP Address

====================================================

DETAIL DRAWER

Klik log.

Tampilkan:

ID

Tanggal

Username

Telegram ID

Role

Module

Action

Description

Target

Metadata JSON

IP Address

User Agent

Status

====================================================

SEARCH

Realtime

Cari berdasarkan:

Nama

Username

Action

Module

====================================================

FILTER

Tanggal

Role

Module

Status

====================================================

SORT

Tanggal

User

Module

Action

====================================================

EXPORT

CSV

JSON

====================================================

RETENTION

Tambahkan pengaturan:

Simpan log:

30 Hari

90 Hari

180 Hari

365 Hari

Unlimited

====================================================

AUTO CLEANUP

Jika retention aktif.

Hapus log lama otomatis.

====================================================

SECURITY

Owner melihat semua.

Admin melihat semua.

Moderator hanya membaca.

User tidak boleh akses.

Audit Log tidak boleh diedit.

Audit Log tidak boleh dihapus manual kecuali oleh Owner.

====================================================

NOTIFICATION

Jika terjadi:

Login gagal berulang

Percobaan akses admin tanpa izin

Delete massal

Restore database

Promote Admin

Tandai sebagai Security Event.

====================================================

API

Gunakan endpoint berikut.

Jika belum tersedia tambahkan tanpa merusak endpoint lama:

GET /api/audit

GET /api/audit/:id

GET /api/audit/export

GET /api/audit/statistics

POST /api/audit/cleanup

====================================================

STATISTICS

Total Log

Hari Ini

Minggu Ini

Bulan Ini

Top Action

Top User

Security Event

====================================================

UI

Gunakan Design System.

Glass Card

Rounded

Dark Mode

Light Mode

====================================================

LOADING

Skeleton

====================================================

EMPTY STATE

Gunakan Empty State.

====================================================

ANIMATION

Framer Motion

Fade

Slide

Drawer Animation

====================================================

RESPONSIVE

Desktop

Tablet

Mobile

====================================================

CODING STYLE

TypeScript Strict

Repository Pattern

SOLID

Reusable Components

Tidak menggunakan any

====================================================

PENTING

Audit Log harus otomatis dipanggil dari seluruh module yang sudah ada:

Authentication

Upload

Download

Files

Folders

Users

Settings

Telegram

Storage

Tidak boleh perlu memanggil manual setiap kali membuka halaman.

====================================================

OUTPUT

1. Jelaskan struktur Audit Log.

2. Jelaskan perubahan database.

3. Jelaskan endpoint baru.

4. Jelaskan integrasi dengan module yang sudah ada.

5. Pastikan:

npm install

npx prisma generate

npx prisma migrate dev

npm run build

npm run dev

berjalan tanpa error.

6. Jangan mengubah Upload Manager, Files Manager, Folder Management, Dashboard, Settings, Statistics, User Management, REST API, Bot Telegram maupun Storage Service.

7. Berhenti setelah Audit Log selesai.
```
