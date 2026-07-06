```
Tambahkan fitur Deposit Saldo Otomatis ke website Digital Cell.

PENTING:

- Jangan mengubah UI yang sudah ada.
- Jangan merusak sistem checkout produk.
- Gunakan arsitektur transaksi yang sama dengan sistem order yang sudah di-hardening.
- Semua transaksi deposit harus atomic, idempotent, dan production-ready.

==================================================
TUJUAN
==================================================

Member dapat melakukan deposit saldo melalui payment gateway.

Setelah pembayaran berhasil:

Saldo otomatis bertambah.

Tidak perlu admin mengisi saldo secara manual.

==================================================
ALUR
==================================================

Member Login

↓

Menu Deposit Saldo

↓

Input nominal

↓

Pilih metode pembayaran

↓

Gateway membuat invoice

↓

User bayar

↓

Callback gateway

↓

Verifikasi signature

↓

Verifikasi amount

↓

Verifikasi invoice

↓

Verifikasi status

↓

MongoDB Transaction

↓

Saldo bertambah

↓

Riwayat deposit tersimpan

↓

Notifikasi berhasil

==================================================
DATABASE
==================================================

Buat collection:

wallets

- user_id
- balance
- created_at
- updated_at

deposit_transactions

- id
- invoice_id
- payment_gateway
- payment_reference
- payment_method
- nominal
- fee
- total
- status
- callback_status
- user_id
- created_at
- updated_at
- paid_at

wallet_ledger

- id
- wallet_id
- user_id
- deposit_id
- type
- amount
- balance_before
- balance_after
- description
- created_at

==================================================
STATUS
==================================================

created

waiting_payment

paid

processing

success

failed

expired

cancelled

==================================================
ATOMIC TRANSACTION
==================================================

Saat callback berhasil

Mongo Transaction:

1 insert ledger

2 update wallet balance

3 update deposit status

4 commit

Jika gagal

rollback semuanya.

==================================================
IDEMPOTENT
==================================================

Callback dua kali

Saldo tidak boleh bertambah dua kali.

Gunakan:

invoice_id

payment_reference

callback_id

unique index

==================================================
VALIDASI CALLBACK
==================================================

Verifikasi:

signature

merchant

invoice

amount

payment_reference

status

timestamp

==================================================
ANTI MANIPULASI
==================================================

Frontend hanya mengirim:

nominal

payment_method

Backend menghitung ulang.

Nominal tidak boleh berasal dari frontend saat callback.

==================================================
LEDGER
==================================================

Semua perubahan saldo WAJIB masuk ledger.

Tidak boleh ada update balance tanpa ledger.

==================================================
RIWAYAT
==================================================

User hanya dapat melihat deposit miliknya.

Admin dapat melihat seluruh deposit.

==================================================
ADMIN
==================================================

Tambah menu:

Deposit

Berisi:

Pending

Berhasil

Expired

Gagal

Cari invoice

Cari user

Filter gateway

==================================================
NOTIFIKASI
==================================================

Saat deposit sukses

Kirim:

Website

Telegram

WhatsApp (jika aktif)

==================================================
AUDIT
==================================================

Simulasikan:

Double callback

Double payment

Spam deposit

Nominal dimanipulasi

Invoice expired

Gateway timeout

Server restart

Mongo restart

==================================================
VALIDASI
==================================================

npm run lint

npm run build

==================================================
LAPORAN
==================================================

Setelah selesai tampilkan:

- File yang diubah
- Collection baru
- Endpoint baru
- UI baru
- Risiko tersisa
- Skor keamanan deposit
- Kesiapan production
```
