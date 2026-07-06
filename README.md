```
Tahap 2 - Migrasi Database Production

JANGAN mengubah UI website.

JANGAN mengubah alur transaksi yang sudah selesai.

Fokus hanya pada migrasi database agar siap production.

Target:

1. Hilangkan ketergantungan local_db.json sebagai penyimpanan utama transaksi.

2. Gunakan MongoDB sebagai database production.

3. Semua transaksi harus menggunakan MongoDB.

4. Buat collection:

products
orders
payments
refunds
provider_attempts
audit_logs
notifications
users

5. Tambahkan unique index yang diperlukan.

6. Pastikan createOrder menggunakan transaksi atomic.

7. Pastikan update status transaksi tidak race condition.

8. Semua callback wajib update database secara aman.

9. Jangan ada data transaksi yang hanya tersimpan di memory atau JSON.

10. local_db.json hanya boleh dipakai sebagai data migrasi atau development, bukan storage production.

11. Tambahkan migration script apabila diperlukan.

12. Pastikan seluruh endpoint tetap kompatibel dengan frontend saat ini.

13. Jalankan:

npm run lint

npm run build

14. Audit ulang seluruh alur transaksi.

15. Laporkan:

- file yang diubah
- struktur database baru
- index yang dibuat
- collection baru
- risiko yang masih tersisa

Jangan mengubah tampilan website.

Jangan mengubah layout.

Jangan mengubah fitur frontend.

Fokus menjadikan sistem siap production menggunakan MongoDB.

```
