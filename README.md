```
Lanjutkan pengembangan Digital Cell.

Jangan mengubah UI yang sudah ada.

Jangan mengubah sistem checkout.

Tambahkan fitur pembayaran menggunakan Saldo Member (Wallet Payment).

==================================================

TUJUAN

==================================================

Member dapat membeli seluruh produk menggunakan saldo wallet.

Jika saldo cukup:

Tidak perlu membuka payment gateway.

Order langsung diproses.

==================================================

ALUR

==================================================

Member Login

↓

Pilih Produk

↓

Checkout

↓

Metode Pembayaran

↓

Saldo Member

↓

Validasi saldo

↓

MongoDB Transaction

↓

Potong saldo

↓

Buat Ledger

↓

Create Order

↓

Kirim ke Digiflazz

↓

Success / Failed

==================================================

VALIDASI

==================================================

Jika saldo kurang

tolak transaksi.

Jika saldo cukup

lanjut.

==================================================

ATOMIC

==================================================

Gunakan Mongo Transaction.

Urutan:

1 Lock Wallet

2 Potong saldo

3 Ledger

4 Create Order

5 Commit

Jika Digiflazz gagal permanen

Refund saldo otomatis.

Jika timeout

Saldo jangan langsung dikembalikan.

Status processing.

==================================================

LEDGER

==================================================

Catat:

Order ID

User

Saldo sebelum

Saldo sesudah

Nominal

Jenis

Tanggal

==================================================

REFUND

==================================================

Jika provider gagal permanen

Tambah saldo kembali.

Ledger Refund.

Notifikasi user.

==================================================

SECURITY

==================================================

Double klik checkout

Tidak boleh memotong saldo dua kali.

Gunakan:

client_request_id

idempotency

unique index

==================================================

ADMIN

==================================================

Tambah menu:

Riwayat Wallet Payment

Filter:

Pending

Processing

Success

Refund

Failed

==================================================

USER

==================================================

Tambah:

Riwayat pembayaran saldo.

Riwayat refund.

==================================================

NOTIFIKASI

==================================================

Potong saldo

Refund

Order berhasil

Order gagal

==================================================

SIMULASI

==================================================

Saldo kurang

Saldo pas

Double klik

Server restart

Mongo restart

Digiflazz timeout

Digiflazz success

Digiflazz failed

Refund

==================================================

VALIDASI

==================================================

npm run lint

npm run build

==================================================

LAPORAN

==================================================

Tampilkan:

- File yang diubah
- Endpoint baru
- Ledger baru
- Wallet Payment Flow
- Refund Flow
- Risiko tersisa
- Skor keamanan Wallet Payment
- Production Readiness
```
