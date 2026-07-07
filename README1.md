```
Perbaiki layout halaman Upload Manager pada website Telegram Drive.

Masalah saat ini:

- Halaman upload terus bertambah panjang setiap selesai upload atau saat memilih file baru.
- Card upload terus ditambahkan ke bawah sehingga halaman menjadi sangat panjang.
- Setelah upload selesai atau gagal, item lama tetap menumpuk.
- UX di mobile menjadi buruk karena harus scroll sangat jauh.

Lakukan audit menyeluruh pada halaman:

website/src/app/admin/upload/page.tsx

dan seluruh komponen upload yang digunakan.

Target perbaikan:

1. Jangan membuat card upload baru setiap kali memilih file jika file yang sama masih ada.
2. Gunakan satu Upload Queue yang benar.
3. Setelah upload selesai:
   - status berubah menjadi Completed
   - item tetap satu kali
   - jangan membuat duplikat.
4. Setelah Retry:
   - update item yang sama
   - jangan membuat item baru.
5. Setelah Reset:
   - kosongkan queue.
6. Setelah Delete:
   - hapus item dari queue.
7. Tinggi daftar upload harus memakai area scroll sendiri (overflow-y: auto), bukan membuat seluruh halaman semakin panjang.
8. Pisahkan layout menjadi:
   - Folder
   - Area Drag & Drop
   - Upload Queue (scroll)
   - Progress Summary
   - Tombol Upload/Cancel/Reset tetap di bagian bawah.
9. Pastikan responsive di Android, iPhone, tablet, dan desktop.
10. Jangan ada re-render yang membuat item upload bertambah sendiri.
11. Audit seluruh penggunaan:
    - setState
    - useState
    - useEffect
    - Array.map
    - key
    - id upload
    Pastikan tidak ada item yang ter-push dua kali.
12. Pastikan setelah upload berhasil:
    - queue menjadi Completed
    - file muncul di My Files
    - tidak ada card upload baru yang muncul.
13. Jalankan:
    - npm run lint
    - npm run build
    Pastikan tidak ada warning maupun error.

Output:
- Jelaskan penyebab halaman bertambah panjang.
- Sebutkan file yang diubah.
- Jelaskan perubahan pada state management upload queue.
- Pastikan halaman upload memiliki tinggi yang stabil dan tidak terus memanjang setelah beberapa kali upload.
```
