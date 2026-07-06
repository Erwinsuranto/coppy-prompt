```
# Telegram Drive Website - Tahap 17 : Settings Center (Central Configuration System)

Tahap sebelumnya telah selesai.

Project saat ini telah memiliki:

✅ Telegram Bot
✅ Upload Engine
✅ Download Engine
✅ Storage Service
✅ REST API
✅ Authentication
✅ Website Foundation
✅ Design System
✅ Landing Page
✅ Premium Download Page
✅ Dashboard
✅ Files Manager
✅ Upload Manager

JANGAN mengubah fitur yang sudah berjalan.

JANGAN merusak REST API.

JANGAN membuat duplicate logic.

Semua pengaturan harus terpusat.

====================================================

TUJUAN

Membangun Settings Center.

Settings Center menjadi pusat seluruh konfigurasi Telegram Drive.

Bot Telegram, Website, Dashboard, REST API dan Storage Service harus membaca konfigurasi dari database yang sama.

Tidak boleh ada konfigurasi yang tersebar.

====================================================

ROUTE

/admin/settings

====================================================

DATABASE

Gunakan tabel Settings.

Jika sudah ada gunakan tabel tersebut.

Jika belum ada buat tabel baru.

Gunakan key-value configuration.

Contoh:

site_name

site_description

site_logo

site_favicon

maintenance_mode

force_join

allow_upload

allow_download

max_upload_size

theme

telegram_channel

api_base_url

jwt_expire

default_language

====================================================

LAYOUT

Sidebar:

General

Website

Telegram

Upload

Download

Security

Storage

SEO

Appearance

System

====================================================

GENERAL

Website Name

Website Description

Website Version

Footer Text

Save Button

====================================================

WEBSITE

Upload Logo

Upload Favicon

Maintenance Mode

Contact Email

Website URL

====================================================

TELEGRAM

Force Join ON/OFF

Tambah Channel

Hapus Channel

Daftar Channel

Aktif/Nonaktif Channel

Bot Username

====================================================

UPLOAD

Enable Upload

Allow Multiple Upload

Rename Before Upload

Maximum Upload Size

Generate Token Otomatis

====================================================

DOWNLOAD

Enable Download

Enable Copy Link

Enable Share Button

Default Link Status

Expired Link (placeholder)

====================================================

SECURITY

JWT Expire

Session Timeout

Max Login Attempt

Password Policy

API Key Placeholder

====================================================

STORAGE

Total File

Total Storage

Used Storage

Free Storage

Telegram Storage Status

====================================================

SEO

Meta Title

Meta Description

Meta Keywords

Open Graph Image

Twitter Card

====================================================

APPEARANCE

Light

Dark

System

Primary Color

Accent Color

====================================================

SYSTEM

Node Version

REST API Status

Telegram Bot Status

Database Status

Storage Service Status

====================================================

BUTTON

Save

Reset

Cancel

====================================================

CONFIRMATION

Sebelum Reset

Tampilkan dialog konfirmasi.

====================================================

AUTO SAVE

Optional.

Jika belum memungkinkan gunakan Save Button.

====================================================

VALIDATION

Gunakan Zod.

====================================================

API

Gunakan REST API yang sudah ada.

Jika endpoint belum tersedia tambahkan endpoint berikut tanpa merusak endpoint lama:

GET /api/settings

PUT /api/settings

GET /api/settings/system

GET /api/settings/storage

POST /api/settings/channel

DELETE /api/settings/channel/:id

====================================================

BOT

Bot Telegram harus membaca Force Join dan Channel dari database Settings.

Website juga membaca dari database yang sama.

Tidak boleh ada dua konfigurasi berbeda.

====================================================

RESPONSIVE

Mobile

Tablet

Desktop

====================================================

ANIMATION

Gunakan Framer Motion.

Fade

Slide

Card Animation

Toast Success

Loading Skeleton

====================================================

DESIGN

Gunakan seluruh komponen dari Design System.

Tidak membuat style baru jika sudah ada.

====================================================

CODING STYLE

Clean Architecture

Reusable Components

TypeScript Strict

SOLID

Repository Pattern

Tidak menggunakan any

====================================================

PENTING

Belum membuat:

Statistics

User Management

Premium

Folder

Category Management

Audit Log

Backup Manager

====================================================

OUTPUT

1. Jelaskan perubahan database.

2. Jelaskan endpoint baru.

3. Jelaskan struktur Settings Center.

4. Pastikan Bot Telegram dan Website menggunakan konfigurasi yang sama.

5. Pastikan:

npm install

npx prisma generate

npx prisma migrate dev

npm run build

npm run dev

berjalan tanpa error.

6. Jangan mengubah fitur Upload, Download, Dashboard, Landing Page, Download Page, Files Manager, Authentication, maupun REST API yang sudah berjalan.

7. Berhenti setelah Settings Center selesai.
```
