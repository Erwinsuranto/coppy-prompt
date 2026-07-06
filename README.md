```
# Telegram Drive - Tahap Final : Production Optimization

Semua fitur sebelumnya sudah selesai.

JANGAN mengubah UI maupun fitur yang sudah ada.

==================================================

TARGET

Membuat Telegram Drive Production Ready.

==================================================

1. PERFORMANCE

Optimasi seluruh API.

Response cache.

Compression gzip/brotli.

Pagination optimization.

Lazy loading.

Image optimization.

Database query optimization.

Index Prisma bila diperlukan.

==================================================

2. SECURITY

Helmet.

Rate Limit.

CORS whitelist.

CSRF Protection bila diperlukan.

XSS Protection.

Sanitize input.

SQL Injection protection.

Upload validation.

JWT expiration.

Refresh token support.

Secret validation.

==================================================

3. STORAGE

Automatic cleanup temp file.

Failed upload cleanup.

Restore cleanup.

Expired token cleanup.

Expired download link cleanup.

==================================================

4. HEALTH CHECK

Endpoint

GET /health

GET /ready

GET /live

Menampilkan:

REST API

Telegram Bot

Database

Storage

Memory

CPU

Version

Uptime

==================================================

5. LOGGING

Request log.

Error log.

Performance log.

Slow query log.

Startup log.

Shutdown log.

==================================================

6. ENV VALIDATION

BOT_TOKEN

DATABASE_URL

ADMIN_ID

CHANNEL_ID

JWT_SECRET

PORT

APP_URL

Semua wajib divalidasi saat startup.

==================================================

7. DOCKER READY

Dockerfile

Docker Compose

.env.example

README deployment

==================================================

8. NGINX READY

Reverse Proxy

HTTPS

Websocket Support

Large Upload

Compression

==================================================

9. PM2 READY

ecosystem.config.js

Restart otomatis

Memory limit

Log rotate

==================================================

10. CLOUD READY

VPS

Railway

Render

DigitalOcean

Oracle Cloud

Hetzner

Ubuntu Server

==================================================

11. CLOUDFLARE READY

Proxy

SSL

Cache Header

Security Header

==================================================

12. AUTO START

Systemd Service

PM2

Auto Restart

==================================================

13. VERSION

Tambahkan halaman:

/admin/system

Menampilkan:

Version

Build Time

Node Version

Prisma Version

Telegram Bot Status

REST API Status

Database Status

Website Status

Storage Status

Memory Usage

CPU Usage

Disk Usage

==================================================

14. FINAL AUDIT

Audit seluruh project.

Cari:

Duplicate code

Unused file

Unused API

Unused package

Unused component

Unused env

Broken import

Broken route

Broken API

Memory leak

Security issue

Performance bottleneck

Berikan rekomendasi tetapi JANGAN menghapus kode yang masih dipakai.

==================================================

15. VERIFIKASI

npm install

npm audit

npm run lint

npm run build

npm run dev

Backend berjalan.

Frontend berjalan.

Bot berjalan.

Semua endpoint berjalan.

==================================================

OUTPUT

Jelaskan:

1. File baru.

2. File diubah.

3. Optimasi.

4. Security.

5. Performance.

6. Production checklist.

7. Deployment checklist.

8. Hasil audit.

Berhenti setelah tahap Production Optimization selesai.
```

