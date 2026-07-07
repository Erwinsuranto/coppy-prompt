```

# ROLE

Kamu adalah Senior Full Stack Engineer, Senior Next.js Engineer, Senior Node.js Engineer, Senior Prisma Engineer, dan Senior Telegram Bot Engineer.

Jangan hanya memperbaiki error yang terlihat. Lakukan audit menyeluruh terhadap seluruh sistem Upload Website Telegram Drive sampai benar-benar siap dipakai production.

Project ini menggunakan:

- Frontend: Next.js 15 + React + TypeScript
- Backend: Node.js + Express + TypeScript
- Database: Prisma + SQLite
- Telegram Bot API
- Folder frontend: /website
- Folder backend: root project (/src)

==================================================
TARGET
==================================================

Perbaiki seluruh fitur Upload Website Telegram Drive sampai 100% berfungsi.

Saat ini halaman:

/admin/upload

mengalami error:

Runtime TypeError

crypto.randomUUID is not a function

Lokasi:

src/app/admin/upload/page.tsx

Tetapi jangan hanya mengganti randomUUID.

Lakukan audit seluruh alur upload.

==================================================
STEP 1
Audit Source Code
==================================================

Cari seluruh penggunaan:

crypto.randomUUID()

window.crypto.randomUUID()

crypto.randomUUID

di seluruh project.

Jika ada gunakan solusi yang kompatibel dengan semua browser.

Gunakan salah satu:

uuid package

atau

Date.now()+Math.random()

atau helper util yang aman.

Jangan sampai ada runtime error lagi.

==================================================
STEP 2
Audit Upload Page
==================================================

Periksa seluruh file upload page.

Pastikan fitur berikut bekerja:

✔ Drag and Drop

✔ Browse File

✔ Multiple Upload

✔ Rename File

✔ Description

✔ Progress Bar

✔ Cancel Upload

✔ Retry Upload

✔ Delete sebelum upload

✔ Preview file

✔ Validasi ukuran file

✔ Validasi file kosong

✔ Validasi extension

✔ Error handling

==================================================
STEP 3
Audit Frontend API
==================================================

Pastikan frontend memanggil backend yang benar.

Periksa:

.env.local

BACKEND_API_URL

NEXT_PUBLIC_API_URL

Proxy API

Axios BaseURL

Fetch URL

Semua endpoint harus mengarah ke backend VPS.

Tidak boleh ada localhost yang salah.

==================================================
STEP 4
Audit Backend Upload API
==================================================

Periksa endpoint upload.

Pastikan endpoint:

- menerima multipart/form-data

- menerima multiple file

- rename file

- generate token

- generate file id

- menyimpan metadata

- upload file ke Telegram

- mendapatkan file_id Telegram

- menyimpan ke database

- mengembalikan response sukses

==================================================
STEP 5
Audit Telegram Upload
==================================================

Pastikan:

Bot mengirim file ke Channel Telegram.

Bot mendapatkan:

message_id

file_id

chat_id

Semua tersimpan di database.

Jika upload Telegram gagal:

Jangan crash server.

Harus mengembalikan pesan error yang jelas.

==================================================
STEP 6
Audit Database
==================================================

Periksa Prisma Schema.

Pastikan metadata upload tersimpan:

id

filename

originalName

mimeType

size

telegramFileId

telegramMessageId

downloadToken

description

createdAt

updatedAt

Semua migration harus sinkron.

==================================================
STEP 7
Audit Download
==================================================

Pastikan setelah upload selesai:

File langsung muncul di:

My Files

Admin Files

Search

Download

Preview

Token download harus sama antara:

Bot Telegram

Website

API

Tidak boleh ada dua sistem token.

Gunakan satu downloadToken untuk semuanya.

==================================================
STEP 8
Audit Frontend Error
==================================================

Tidak boleh ada:

Unhandled Promise

Runtime Error

Hydration Error

TypeError

ReferenceError

Console Error

Warning React

Next Warning

==================================================
STEP 9
Audit TypeScript
==================================================

Hilangkan seluruh:

any

ts-ignore

eslint-disable

Jika tidak diperlukan.

Perbaiki typing.

==================================================
STEP 10
Audit Build
==================================================

Pastikan berhasil menjalankan:

npm install

npm run lint

npm run build

Frontend

Backend

Semuanya tanpa error.

==================================================
STEP 11
Audit Production
==================================================

Pastikan project berjalan pada:

Frontend

npm run build

npm run start

Backend

npm run build

npm run start

Tanpa runtime error.

==================================================
STEP 12
Audit Security
==================================================

Validasi:

Nama file

Ukuran file

Mime type

Path traversal

Duplicate upload

Token

Authentication

Authorization

==================================================
STEP 13
Audit UX
==================================================

Jika upload berhasil:

✔ Progress mencapai 100%

✔ Toast sukses

✔ File muncul otomatis

✔ Tidak perlu refresh

Jika gagal:

✔ Toast error

✔ Retry

✔ Tidak crash

==================================================
STEP 14
Output
==================================================

Setelah selesai:

1. Sebutkan semua bug yang ditemukan.

2. Sebutkan semua file yang diubah.

3. Jelaskan alasan perubahan.

4. Pastikan seluruh fitur upload bekerja.

5. Jalankan build sampai sukses.

6. Pastikan tidak ada runtime error lagi.

Jangan berhenti setelah memperbaiki satu bug.

Lanjutkan audit sampai seluruh sistem Upload Telegram Drive benar-benar siap digunakan pada production.
```
