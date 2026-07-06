```
# Tahap Selanjutnya - Backup & Restore Center

Jangan mengubah seluruh fitur yang sudah selesai.

Semua module harus tetap berjalan:

- Telegram Bot
- Upload Telegram
- Download Page
- REST API
- Login Admin
- Dashboard
- Upload Manager
- Files Manager
- Folder Manager
- User Manager
- Statistics
- Audit Log
- Notification Center
- Settings
- Force Join

==================================================

Buat Backup & Restore Center.

Route:

/admin/backup

==================================================

Sidebar

Backup

Restore

Schedule

History

Storage

==================================================

Dashboard Backup

Card:

Last Backup

Next Backup

Database Size

Total Backup

Storage Used

==================================================

Backup Type

✓ Database

✓ Uploaded Metadata

✓ Settings

✓ Folder

✓ User

✓ Notification

✓ Audit

✓ Statistics

✓ Configuration

Checkbox bebas dipilih.

==================================================

Button

Backup Now

Download Backup

Delete Backup

Restore Backup

==================================================

Backup Format

ZIP

JSON

SQL

==================================================

History

Tanggal

Ukuran

Jenis

Status

Durasi

Download

Restore

Delete

==================================================

Schedule

Manual

Daily

Weekly

Monthly

Auto Cleanup

Retention:

7 hari

30 hari

90 hari

365 hari

==================================================

Storage

Total Backup

Used

Free

Largest Backup

Latest Backup

==================================================

Restore

Upload backup

Validasi

Preview isi backup

Konfirmasi Restore

Progress Restore

Rollback jika gagal

==================================================

API

GET /api/backup

POST /api/backup/create

POST /api/backup/restore

DELETE /api/backup/:id

GET /api/backup/download/:id

GET /api/backup/history

==================================================

Security

Hanya OWNER

Audit Log otomatis

Notification otomatis

==================================================

UI

Glassmorphism

Framer Motion

Progress

Loading

Toast

Responsive Desktop Tablet Mobile

==================================================

Output

Jelaskan:

1. File baru

2. File diubah

3. Database

4. API

5. UI

6. Integrasi

7. Verifikasi:

npm install

npx prisma generate

npx prisma migrate dev

npm run build

npm run dev

Jangan mengubah module lain.

Berhenti setelah Backup & Restore selesai.
```

