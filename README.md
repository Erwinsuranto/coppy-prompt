```
Lanjutkan Tahap Final Hardening Production.

Jangan mengubah UI.
Jangan mengubah desain.
Jangan mengubah alur pengguna.

Fokus hanya pada keamanan transaksi production.

Target akhir:
- Seluruh perubahan status transaksi hanya boleh melalui Transaction State Machine.
- Tidak boleh ada service lain yang mengubah status order secara langsung.

Kerjakan poin berikut:

1. Cari seluruh update status order di project.
   Contoh:
   - order.status =
   - updateOrder()
   - updateOne()
   - findByIdAndUpdate()
   - ProviderService
   - OrderEngine
   - PaymentService
   - CallbackService

2. Semua update status harus melalui satu fungsi resmi:
   TransactionStateMachine.transition()

3. Hapus seluruh direct status update yang masih ada.

4. Payment Gateway Recovery
   Jangan hanya menunggu callback.
   Tambahkan scheduled polling:
   - pending > cek gateway
   - processing > cek gateway
   - timeout > cek gateway
   - recovery setelah restart server

5. Callback Gateway
   Pastikan:
   - Signature valid
   - Merchant valid
   - Amount valid
   - Payment ID valid
   - Ref ID valid
   - Timestamp valid
   - Idempotent

6. Endpoint Riwayat Order
   Pastikan:
   - User hanya dapat melihat order miliknya sendiri.
   - Admin memiliki endpoint terpisah.
   - Tidak boleh ada IDOR.

7. Notification
   Jadikan atomic.
   Status berhasil berubah
   ↓
   Commit transaksi
   ↓
   Notification Queue

   Jangan kirim notifikasi sebelum commit berhasil.

8. Audit kembali:
   - Double callback
   - Double payment
   - Restart server
   - Timeout provider
   - Provider gagal
   - Payment gagal
   - Recovery
   - Refund eligibility

9. Jalankan:
   npm run lint
   npm run build

10. Setelah selesai tampilkan laporan:

- File yang diubah
- Direct status update yang berhasil dihapus
- Hasil audit baru
- Risiko production tersisa
- Skor keamanan terbaru
- Persentase kesiapan production

Jangan membuat fitur baru.

Jangan mengubah UI.

Jangan mengubah database tanpa alasan.

Fokus hanya pada hardening transaksi production.

```
