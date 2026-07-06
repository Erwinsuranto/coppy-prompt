```
# Telegram Drive - Tahap 22 : Notification Center (Real Time)

Semua modul sebelumnya sudah selesai.

JANGAN mengubah fitur yang sudah berjalan.

Gunakan seluruh REST API, Database, Authentication, Dashboard, Settings, Audit Log, Statistics, Folder Management, Upload Manager, Files Manager yang sudah ada.

====================================================

TUJUAN

Membangun Notification Center profesional.

Semua aktivitas penting menghasilkan notifikasi.

====================================================

ROUTE

/admin/notifications

====================================================

DATABASE

Jika belum ada buat tabel:

Notification

id

title

message

type

icon

priority

isRead

userId (nullable)

targetRole

actionUrl

metadata JSON

createdAt

====================================================

TYPE

Info

Success

Warning

Error

Security

System

====================================================

PRIORITY

Low

Medium

High

Critical

====================================================

NOTIFIKASI OTOMATIS

Upload berhasil

Upload gagal

Download tinggi

Storage hampir penuh

Login berhasil

Login gagal

User baru

Admin baru

Role berubah

Folder dibuat

Folder dihapus

Generate Link

Disable Link

Force Join ON

Force Join OFF

Tambah Channel

Hapus Channel

Backup selesai

Restore selesai

Error Telegram API

REST API Error

====================================================

HEADER

Tambahkan Bell Notification.

Badge unread.

Klik membuka Notification Drawer.

====================================================

DRAWER

Latest Notification

Infinite Scroll

Load More

Mark Read

Mark All Read

Delete Read

====================================================

HALAMAN

/admin/notifications

Filter

Search

Sort

Priority

Type

Date

Status

====================================================

CARD

Icon

Title

Description

Time Ago

Priority Badge

Action Button

====================================================

REALTIME

Auto Refresh

Polling

30 detik

Tanpa websocket.

====================================================

API

GET /api/notifications

GET /api/notifications/unread

POST /api/notifications/read/:id

POST /api/notifications/read-all

DELETE /api/notifications/read

====================================================

SETTING

Settings Center sekarang memiliki:

Enable Notification

Desktop Notification

Sound Notification

Email Placeholder

Telegram Placeholder

====================================================

ANIMATION

Framer Motion

Slide

Fade

Bell Shake

Counter Animation

====================================================

RESPONSIVE

Desktop

Tablet

Mobile

====================================================

OUTPUT

Jelaskan:

1. Database

2. API

3. UI

4. Integrasi otomatis

5. Verifikasi:

npm install

npx prisma generate

npx prisma migrate dev

npm run build

npm run dev

6. Jangan mengubah module lain.

Berhenti setelah Notification Center selesai.
```
