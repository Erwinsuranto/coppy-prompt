```
Saat ini terjadi bug pada fitur upload Website Telegram Drive.

Gejalanya:

- File berhasil diupload ke Telegram.
- File sudah tersimpan di channel Telegram.
- Progress upload mencapai 100%.
- Metadata kemungkinan sudah tersimpan.
- Namun frontend menampilkan:

Request failed with status code 400

Akibatnya UI menampilkan "Upload gagal", padahal upload sebenarnya berhasil.

Lakukan audit seluruh alur upload end-to-end.

Periksa:

1. Frontend
- Axios/fetch upload request.
- Error handling.
- Validasi response.
- Status code yang dianggap sukses.
- Pastikan response 200/201 diproses sebagai sukses.
- Jangan menampilkan "Upload gagal" jika backend sebenarnya sudah berhasil.

2. Backend
- Audit endpoint upload.
- Pastikan semua langkah setelah upload Telegram mengembalikan status yang benar.
- Jangan mengembalikan HTTP 400 jika file sudah berhasil dikirim.
- Gunakan HTTP 400 hanya untuk request yang memang tidak valid.
- Jika upload Telegram sukses dan metadata berhasil disimpan, kembalikan HTTP 200 atau 201.

3. Database
- Pastikan transaksi konsisten.
- Jangan menyimpan file lalu mengembalikan error.

4. Telegram Service
- Jika Telegram berhasil mengembalikan message_id dan file_id, proses harus dianggap sukses.

5. Response API
Pastikan format konsisten, misalnya:

{
  "success": true,
  "message": "Upload berhasil",
  "data": {
    "id": "...",
    "downloadToken": "...",
    "telegramFileId": "...",
    "telegramMessageId": "...",
    "filename": "..."
  }
}

6. Frontend
- Setelah response sukses:
  - tampilkan toast "Upload berhasil"
  - status menjadi Completed
  - hilangkan pesan error
  - file langsung muncul di My Files
  - file langsung muncul di Admin Files

7. Audit semua kemungkinan penyebab HTTP 400:
- Validasi schema
- Zod
- Prisma
- Multipart parser
- Rename file
- Metadata
- DownloadToken
- Response serializer

8. Tambahkan logging detail pada endpoint upload:
- request diterima
- upload Telegram berhasil
- metadata tersimpan
- response yang dikirim
- alasan jika mengembalikan HTTP 400

Jangan hanya memperbaiki gejalanya. Temukan akar penyebab HTTP 400 dan pastikan alur upload benar-benar selesai tanpa false error.

Setelah selesai:
- Jalankan build frontend dan backend.
- Pastikan upload file menghasilkan HTTP 200/201.
- Pastikan tidak ada lagi pesan "Request failed with status code 400" ketika upload sebenarnya berhasil.

```
