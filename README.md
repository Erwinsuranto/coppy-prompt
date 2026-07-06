```
TUGAS: SELESAIKAN PONDASI TRANSAKSI PRODUCTION DIGITAL CELL

JANGAN mengubah UI.
JANGAN mengubah layout.
JANGAN mengubah desain.
JANGAN mengubah alur pembelian yang sudah berjalan.

Fokus hanya menyelesaikan seluruh pekerjaan yang masih tersisa agar sistem siap production.

==================================================
TARGET
==================================================

Saya ingin seluruh alur transaksi benar-benar production ready.

Setelah tahap ini selesai, website harus siap diuji dengan transaksi uang asli dalam lingkungan production.

==================================================
PEKERJAAN YANG HARUS DISELESAIKAN
==================================================

1. PAYMENT GATEWAY PRODUCTION

Audit seluruh sistem pembayaran.

Pastikan:

- tidak ada sandbox
- tidak ada placeholder
- tidak ada demo key
- tidak ada fake callback
- tidak ada payment dummy
- seluruh payment gateway menggunakan credential production

Verifikasi:

- callback
- signature
- timestamp
- merchant
- amount
- reference
- order id

==================================================

2. CALLBACK

Periksa seluruh callback.

Pastikan callback:

- idempotent
- tidak bisa diproses dua kali
- tidak bisa mengubah status terminal
- tidak bisa menerima callback palsu
- mencatat audit log

==================================================

3. RETRY

Jika provider timeout:

- jangan langsung gagal
- cek status provider
- retry sesuai aturan
- update status dengan aman

==================================================

4. REFUND SYSTEM

Bangun sistem refund production.

Refund hanya boleh jika:

payment berhasil

provider gagal permanen

belum pernah refund

tidak ada callback sukses

Refund harus:

atomic

idempotent

memiliki audit log

memiliki approval admin jika diperlukan

tidak boleh refund dua kali

==================================================

5. ADMIN REFUND

Tambahkan backend:

refund request

refund approval

refund reject

refund history

refund audit

Tidak perlu mengubah UI.

==================================================

6. AUDIT LOG

Semua aktivitas harus dicatat.

create order

payment

callback

provider request

provider response

refund

retry

timeout

admin action

login

==================================================

7. RECOVERY

Jika server mati:

order processing harus lanjut

payment pending harus dicek

callback terlambat tetap diproses

provider timeout harus dicek ulang

==================================================

8. MONGODB

Pastikan:

seluruh transaksi memakai MongoDB

tidak ada transaksi production memakai local_db.json

local_db.json hanya untuk development

==================================================

9. VALIDASI

Backend tidak boleh percaya frontend.

Harga

Provider

Status

Nama produk

Kategori

Subtotal

Total

Semua wajib diambil ulang dari database.

==================================================

10. TEST

Setelah selesai lakukan simulasi:

spam klik beli

double callback

callback terlambat

provider timeout

payment timeout

server restart

provider gagal

refund

double refund

network error

==================================================

11. BUILD

Jalankan:

npm run lint

npm run build

Perbaiki seluruh error.

==================================================

12. AUDIT AKHIR

Setelah semuanya selesai,

buat laporan lengkap:

✔ tingkat keamanan

✔ status refund

✔ status payment

✔ status callback

✔ status MongoDB

✔ status recovery

✔ status retry

✔ status provider

✔ status Digiflazz

✔ status transaksi

✔ status production

Berikan skor keamanan 0-100.

Jika masih ada risiko sekecil apa pun, jelaskan secara rinci.

Jangan membuat fitur baru.

Jangan mengubah UI.

Jangan mengubah desain.

Fokus hanya menyelesaikan pondasi transaksi hingga benar-benar siap production.
```
