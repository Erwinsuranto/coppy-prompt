```
Lanjutkan penyempurnaan sistem Notifikasi Digital Cell hingga benar-benar production-ready.

Target:
- Skor keamanan minimal 95/100.
- Tidak ada fitur notifikasi yang setengah jadi.
- Tidak mengubah UI maupun alur transaksi yang sudah selesai.

Pekerjaan yang harus diselesaikan:

1. Buat halaman penuh /notifications.
   - Daftar seluruh notifikasi.
   - Pagination.
   - Search.
   - Filter:
     * Semua
     * Belum dibaca
     * Order
     * Deposit
     * Wallet
     * Refund
     * Sistem
   - Relative time.
   - Infinite scroll atau pagination.
   - Empty state.
   - Loading.
   - Retry.

2. Migrasikan seluruh event lama agar menggunakan Event Bus.
   Tidak boleh ada lagi pemanggilan DB.Notifications.create() secara langsung dari modul lain.

3. Audit seluruh source code.
   Cari semua pemanggilan notification lama.
   Ganti menjadi NotificationService + EventBus.

4. Pastikan semua event berikut menghasilkan notifikasi:
   - Order dibuat
   - Waiting payment
   - Payment success
   - Payment failed
   - Processing
   - Success
   - Failed
   - Refund
   - Deposit
   - Wallet debit
   - Wallet credit
   - Maintenance
   - Provider offline
   - Provider online
   - Recovery
   - Admin login
   - Admin error

5. Klik notifikasi harus membuka halaman yang sesuai:
   Order → Detail Order
   Deposit → Detail Deposit
   Refund → Detail Refund
   Wallet → Riwayat Wallet

6. Audit keamanan:
   - Tidak boleh membaca notification user lain.
   - Tidak boleh ada IDOR.
   - Admin dan user benar-benar terpisah.
   - Semua endpoint wajib login.

7. Uji:
   - Spam klik.
   - Double callback.
   - Restart server.
   - Reconnect.
   - Provider timeout.
   - Recovery.
   - Multi tab browser.

8. Jalankan:
   npm run lint
   npm run build

9. Setelah selesai tampilkan laporan:
   - File yang diubah.
   - Hasil audit.
   - Risiko tersisa.
   - Skor keamanan.
   - Production readiness.

Jangan membuat fitur baru sebelum seluruh sistem notifikasi benar-benar selesai dan siap production.
```
