```
Lanjutkan implementasi sesuai hasil audit.

Kerjakan hanya Tahap 1 terlebih dahulu.

Prioritas utama adalah menjadikan alur transaksi benar-benar aman.

Target:

1. Produk hanya berasal dari Digiflazz.
2. Hilangkan seluruh mock, dummy, seed, fallback production.
3. Checkout hanya mengirim product_id, buyer_sku_code, customer_number, payment_method, quantity, notes, client_request_id.
4. Backend wajib mengambil ulang seluruh data produk dari database.
5. Harga, provider, nama produk, dan kategori dari frontend tidak boleh dipercaya.
6. Terapkan state machine transaksi.
7. Terapkan idempotency createOrder.
8. Verifikasi callback Digiflazz.
9. Tambahkan retry dan recovery jika timeout.
10. Semua perubahan harus tetap kompatibel dengan UI yang sekarang.

JANGAN mengubah tampilan website.

JANGAN mengubah layout.

JANGAN menghapus fitur yang sudah berjalan.

JANGAN membuat file baru jika fungsi masih bisa menggunakan struktur yang ada.

Setelah implementasi selesai:

- Jalankan npm run lint.
- Jalankan npm run build.
- Perbaiki semua error.
- Lakukan audit ulang.
- Berikan laporan file yang diubah.
- Berikan daftar risiko yang masih tersisa.

Jangan lanjut ke sistem refund sebelum Tahap 1 benar-benar selesai dan lolos audit.
















```
