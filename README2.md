```
Saat ini upload video berhasil tetapi frontend menampilkan:

timeout of 15000ms exceeded

Fakta:

- File berhasil upload ke Telegram.
- Progress mencapai 100%.
- Telegram menerima file.
- Masalah terjadi karena frontend timeout menunggu response backend.

Lakukan audit penuh terhadap upload API.

Target:

1. Cari seluruh Axios timeout.
2. Cari timeout pada fetch.
3. Cari timeout Express.
4. Cari timeout upload Telegram.

Perbaiki agar upload file besar tidak gagal hanya karena timeout.

Gunakan strategi berikut:

- Response upload dikirim segera setelah Telegram selesai menerima file.
- Proses tambahan (thumbnail, metadata, indexing, search, cache, dsb.) dijalankan di background jika memungkinkan.
- Jangan menunggu proses yang tidak wajib sebelum mengembalikan HTTP 200/201.

Frontend:

- Jangan menggunakan timeout tetap 15000 ms untuk upload.
- Gunakan timeout yang dapat dikonfigurasi.
- Untuk upload file besar gunakan minimal 5 menit atau tanpa timeout selama upload masih aktif.

Backend:

- Audit seluruh async/await.
- Cari proses yang memblokir response.
- Pastikan response dikirim segera setelah upload sukses.

Tambahkan logging durasi:

- Mulai upload
- Upload Telegram selesai
- Simpan database selesai
- Response dikirim

Cetak waktu setiap langkah.

Output:

- Sebutkan penyebab timeout.
- Sebutkan file yang diubah.
- Pastikan upload video 100 MB tetap berhasil.
- Pastikan frontend tidak lagi menampilkan:

timeout of 15000ms exceeded

- Jalankan build frontend dan backend hingga sukses.

```

