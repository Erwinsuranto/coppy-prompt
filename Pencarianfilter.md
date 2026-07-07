```


Perbaiki layout halaman Admin Files khusus tampilan mobile.

Jangan ubah fungsi filter, hanya ubah UI/UX.

Targetnya seperti Google Drive atau Dropbox.

Perubahan:

1. Search Box
- Tinggi maksimal 44px.
- Jangan full tinggi seperti sekarang.
- Placeholder: "Cari file..."
- Sticky di bagian atas saat scroll.

2. Filter
- Semua dropdown jangan langsung ditampilkan.
- Ganti menjadi satu tombol:

⚙️ Filter

Saat ditekan baru membuka:
- Bottom Sheet (mobile)
atau
- Modal.

Di dalam modal baru ada:
- Jenis
- Status
- Folder
- Uploader
- Sort

3. Halaman default

Yang langsung terlihat hanya:

Search Box
Tombol Filter
Tabel/Card File

Bukan semua dropdown.

4. Desktop

Desktop tetap seperti sekarang.

Hanya mobile yang diubah.

5. Tambahkan badge

Jika filter aktif tampil:

Filter (3)

Jika tidak ada:

Filter

6. Responsive

Search + Filter berada dalam satu baris.

Contoh:

[ 🔍 Cari file........ ][⚙️]

Bukan bertumpuk.

7. Spacing

Kurangi tinggi card Filter.

Kurangi margin atas.

Daftar file harus langsung terlihat tanpa scroll panjang.

8. Jangan mengubah API.

Jangan mengubah backend.

Hanya refactor UI frontend.

Pastikan:
- npm run lint
- npm run build

harus sukses tanpa warning maupun error.

```
