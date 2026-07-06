```
Jangan menambahkan fitur baru.

Jangan melakukan refactor besar.

Jangan mengubah UI.

Mulai sekarang fokus sebagai QA (Quality Assurance).

Lakukan audit end-to-end terhadap seluruh alur transaksi production.

Yang harus diperiksa:

1. Produk berasal dari Digiflazz.
2. Checkout.
3. Payment gateway.
4. Callback payment.
5. Order ke Digiflazz.
6. Callback Digiflazz.
7. Update status order.
8. Riwayat transaksi.
9. Notifikasi.
10. Recovery jika server restart.
11. Retry jika provider timeout.
12. Refund flow.

Jangan mengubah kode jika tidak ditemukan bug.

Jika menemukan bug:

- Jelaskan penyebabnya.
- Sebutkan file yang terpengaruh.
- Berikan tingkat risiko.
- Perbaiki hanya bug tersebut.

Setelah audit selesai, buat laporan:

- Bug kritis.
- Bug sedang.
- Bug ringan.
- Risiko production.
- Estimasi kesiapan production.

Jangan mengubah arsitektur yang sudah stabil.

```
