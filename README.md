```
# Telegram Drive Website - Tahap 20 : Folder Management (Professional File Organization)

Tahap User Management telah selesai.

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
✅ Statistics
✅ User Management

JANGAN mengubah fitur yang sudah berjalan.

JANGAN merusak REST API.

Gunakan seluruh Design System.

====================================================

TUJUAN

Membangun Folder Management profesional.

Folder digunakan untuk mengelola ribuan file agar terorganisir.

Upload Manager harus bisa memilih Folder.

Files Manager harus bisa difilter berdasarkan Folder.

====================================================

ROUTE

/admin/folders

====================================================

DATABASE

Gunakan tabel Folder.

Jika belum ada buat schema berikut:

Folder

id

parentId

name

slug

description

icon

color

sortOrder

visibility

status

createdAt

updatedAt

====================================================

SUPPORT

Unlimited Folder

Unlimited Sub Folder

====================================================

TREE VIEW

Sidebar kiri seperti File Explorer.

Folder

Sub Folder

Expand

Collapse

====================================================

CONTENT

Saat klik Folder tampilkan:

Nama Folder

Jumlah File

Jumlah Sub Folder

Storage

Tanggal Dibuat

====================================================

ACTION

Create Folder

Rename

Move

Duplicate

Delete

Change Icon

Change Color

====================================================

DRAG DROP

Support Drag & Drop Folder.

Jika belum memungkinkan beri TODO.

====================================================

MOVE FILE

File dapat dipindahkan ke Folder lain.

====================================================

UPLOAD

Upload Manager wajib memiliki dropdown Folder.

Folder terakhir disimpan sebagai default.

====================================================

FILES MANAGER

Tambahkan:

Filter Folder

Breadcrumb

====================================================

BREADCRUMB

Contoh:

Home

>

Film

>

Action

====================================================

SEARCH

Cari Folder.

====================================================

SORT

Nama

Tanggal

Jumlah File

====================================================

STATUS

Active

Hidden

Locked

====================================================

VISIBILITY

Public

Private

Premium

====================================================

DETAIL DRAWER

Nama

Slug

Parent Folder

Jumlah File

Jumlah Download

Storage

Owner

Tanggal Dibuat

====================================================

ICON

Gunakan Icon Library.

Folder

Video

Music

Photo

Archive

Application

Document

Game

Movie

====================================================

COLOR

Blue

Green

Purple

Orange

Red

Gray

====================================================

EMPTY STATE

Gunakan Design System.

====================================================

LOADING

Skeleton.

====================================================

ANIMATION

Framer Motion.

Expand Animation

Collapse Animation

Fade

Hover

====================================================

RESPONSIVE

Desktop

Tablet

Mobile

====================================================

API

Gunakan endpoint backend.

Jika belum tersedia tambahkan endpoint berikut tanpa merusak endpoint lama:

GET /api/folders

GET /api/folders/tree

GET /api/folders/:id

POST /api/folders

PUT /api/folders/:id

DELETE /api/folders/:id

POST /api/folders/:id/move

POST /api/folders/:id/icon

POST /api/folders/:id/color

GET /api/folders/:id/files

====================================================

DATABASE RELATION

Folder

↓

Many Files

Folder

↓

Many Child Folder

Parent Folder

↓

Many Sub Folder

====================================================

SECURITY

Semua endpoint wajib menggunakan Admin Authentication.

====================================================

DESIGN

Gunakan seluruh komponen Design System.

Glass Card

Rounded

Light

Dark

====================================================

CODING STYLE

Reusable Components

TypeScript Strict

Repository Pattern

SOLID

Tidak menggunakan any

====================================================

PENTING

Belum membuat:

Category Management

Audit Log

Backup Manager

Notification Center

Premium System

Production Ready

====================================================

OUTPUT

1. Jelaskan struktur Folder Management.

2. Jelaskan relasi database.

3. Jelaskan endpoint yang digunakan.

4. Pastikan Upload Manager dan Files Manager telah terintegrasi dengan Folder.

5. Pastikan:

npm install

npx prisma generate

npx prisma migrate dev

npm run build

npm run dev

berjalan tanpa error.

6. Jangan mengubah Upload Manager, Files Manager, Dashboard, Settings, Statistics, User Management, REST API, Bot Telegram maupun Storage Service.

7. Berhenti setelah Folder Management selesai.
```
