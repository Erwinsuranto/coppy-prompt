```
# Telegram Drive Website - Tahap 18 : Statistics & Analytics (Professional Dashboard)

Tahap sebelumnya telah selesai.

Project saat ini telah memiliki:

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
✅ Landing Page
✅ Download Page

JANGAN mengubah fitur yang sudah berjalan.

JANGAN merusak REST API.

Gunakan seluruh Design System.

====================================================

TUJUAN

Membangun halaman Statistics & Analytics profesional.

Semua data diambil dari backend.

Tidak boleh hardcode.

====================================================

ROUTE

/admin/statistics

====================================================

OVERVIEW CARD

Tampilkan:

Total Files

Total Downloads

Total Uploads

Total Users

Total Storage

Used Storage

Free Storage

====================================================

TODAY

Upload Hari Ini

Download Hari Ini

User Aktif Hari Ini

Storage Bertambah Hari Ini

====================================================

GRAPH

Upload Harian

Download Harian

User Baru

Storage Growth

Gunakan Chart Component.

====================================================

FILTER

Hari

7 Hari

30 Hari

90 Hari

1 Tahun

Custom Date Range

====================================================

TOP FILES

Top 10 Download

Nama File

Download

Ukuran

Uploader

====================================================

TOP UPLOADER

Top User

Jumlah Upload

Total Storage

====================================================

RECENT ACTIVITY

Upload Terbaru

Download Terbaru

Login Admin

Delete File

Generate Link

====================================================

STORAGE

Storage Used

Storage Free

Persentase

Progress Bar

====================================================

DOWNLOAD ANALYTICS

Total Download

Download Hari Ini

Download Minggu Ini

Download Bulan Ini

====================================================

UPLOAD ANALYTICS

Total Upload

Upload Hari Ini

Upload Minggu Ini

Upload Bulan Ini

====================================================

FILE TYPE

Pie Chart

Photo

Video

Document

Audio

Archive

Other

====================================================

SYSTEM

Bot Status

REST API

Database

Storage

Website

====================================================

EXPORT

CSV

JSON

====================================================

REFRESH

Manual Refresh

Auto Refresh Placeholder

====================================================

LOADING

Skeleton

====================================================

EMPTY STATE

Gunakan Design System

====================================================

ANIMATION

Framer Motion

Fade

Slide

Counter Animation

Chart Animation

====================================================

RESPONSIVE

Mobile

Tablet

Desktop

====================================================

API

Gunakan endpoint backend.

Jika endpoint belum tersedia tambahkan endpoint berikut tanpa merusak endpoint lama:

GET /api/statistics

GET /api/statistics/overview

GET /api/statistics/storage

GET /api/statistics/download

GET /api/statistics/upload

GET /api/statistics/files

GET /api/statistics/users

GET /api/statistics/system

GET /api/statistics/chart

====================================================

DATABASE

Gunakan data yang sudah ada.

Jika sebagian data belum tersedia tampilkan placeholder dan beri komentar TODO.

Jangan membuat data palsu.

====================================================

DESIGN

Gunakan Design System.

Glass Card

Soft Shadow

Rounded

Dark Mode

Light Mode

====================================================

CODING STYLE

Reusable Component

TypeScript Strict

SOLID

Repository Pattern

Tidak menggunakan any

====================================================

PENTING

Belum membuat:

User Management

Premium

Folder

Category Management

Audit Log

Backup Manager

Notification Center

====================================================

OUTPUT

1. Jelaskan struktur Statistics.

2. Jelaskan endpoint yang digunakan.

3. Jelaskan chart yang dipakai.

4. Jelaskan placeholder yang digunakan bila data belum tersedia.

5. Pastikan:

npm install

npx prisma generate

npx prisma migrate dev

npm run build

npm run dev

berjalan tanpa error.

6. Jangan mengubah fitur Upload, Download, Dashboard, Files Manager, Settings Center, Authentication, REST API maupun Bot Telegram yang sudah berjalan.

7. Berhenti setelah Statistics & Analytics selesai.
```
