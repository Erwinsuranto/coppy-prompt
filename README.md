```

Tahap Final Production Hardening (Target 100/100)

Jangan mengubah UI.
Jangan mengubah desain.
Jangan mengubah flow pengguna.

Lanjutkan hanya hardening production.

Target akhir:
Website benar-benar siap menerima transaksi uang asli.

Kerjakan semua poin berikut.

==================================================
1. Audit Semua Gateway Payment
==================================================

Audit seluruh adapter payment.

Contoh:

Tripay
Midtrans
iPaymu
Duitku
Xendit

Pastikan setiap gateway memiliki:

- callback verification
- signature verification
- polling status
- timeout recovery
- duplicate callback protection
- idempotent payment

Jika gateway tidak mendukung polling,
beri fallback yang aman.

==================================================
2. Unified Payment Recovery
==================================================

Buat satu RecoveryService.

RecoveryService harus:

- scan payment pending
- scan processing
- cek gateway
- update state machine
- retry callback
- retry provider
- retry notification

Jangan ada recovery berbeda-beda tiap gateway.

==================================================
3. Atomic Notification
==================================================

Pastikan:

Status berubah
↓

Mongo transaction commit

↓

Notification Queue

↓

Send notification

Jika notification gagal

Jangan rollback transaksi.

Masukkan retry queue.

==================================================
4. Provider Recovery
==================================================

Jika provider timeout

cek status provider

Jika success

ubah menjadi success

Jika failed

ubah failed

Jika unknown

tetap processing

jangan pernah langsung gagal.

==================================================
5. Production Config Audit
==================================================

Cari seluruh project.

Pastikan tidak ada lagi:

sandbox

dummy

mock

placeholder

localhost

example.com

yourdomain

dev-key

testing credential

Jika ditemukan

hapus dari production path.

==================================================
6. Security Audit
==================================================

Audit:

JWT

Session

Cookie

CORS

Rate limit

CSRF

Helmet

Admin endpoint

History endpoint

Payment endpoint

Provider endpoint

Pastikan tidak ada endpoint tanpa auth.

==================================================
7. Privacy Audit
==================================================

Pastikan user tidak dapat:

melihat order user lain

refund user lain

payment user lain

callback user lain

history user lain

==================================================
8. MongoDB Production
==================================================

Audit:

index

compound index

TTL

transaction

replica set

write concern

read concern

optimistic locking

==================================================
9. Recovery Test
==================================================

Simulasikan:

- restart server
- payment callback terlambat
- provider timeout
- provider success setelah timeout
- callback datang dua kali
- refund dua kali
- payment spam
- checkout spam
- network error
- Mongo restart

==================================================
10. Final Report
==================================================

Berikan laporan:

✔ skor keamanan

✔ production readiness

✔ daftar file berubah

✔ risiko tersisa

✔ apakah sudah layak transaksi uang asli

✔ apakah sudah layak menerima ribuan transaksi per hari

✔ apakah ada kemungkinan kehilangan saldo

✔ apakah masih ada kemungkinan double payment

✔ apakah masih ada kemungkinan double refund

✔ apakah masih ada kemungkinan order nyangkut

Jika masih ada risiko,

jelaskan secara rinci.

Jangan mengubah UI.

Jangan mengubah desain.

Fokus hanya keamanan dan stabilitas production.
```
