```
# Telegram Drive Website - Tahap 12 : Premium Download Page

Tahap Landing Page telah selesai.

Backend REST API telah selesai.

Storage Service telah selesai.

Download Engine telah selesai.

Force Join telah selesai.

Gunakan seluruh komponen Design System.

JANGAN membuat komponen baru jika sudah tersedia.

====================================================

TUJUAN

Membuat halaman Download yang sangat modern, cepat, mobile friendly, dan premium.

Halaman ini akan menjadi halaman yang paling sering dibuka user.

Desain harus setara website cloud storage modern.

====================================================

Route

/file/[token]

====================================================

Saat halaman dibuka.

Ambil data menggunakan:

GET /api/token/:token

Jangan hardcode.

====================================================

Loading

Saat membuka halaman.

Jangan langsung muncul.

Gunakan:

Skeleton

Loading Animation

Fade

Progress

====================================================

Validasi

Jika token salah.

Tampilkan halaman modern.

❌ File tidak ditemukan.

Dengan tombol

Kembali ke Home.

====================================================

Jika token disable.

Halaman:

Link telah dinonaktifkan.

====================================================

Jika Force Join aktif.

Jangan redirect.

Tampilkan Card.

━━━━━━━━━━━━━━

📢 Join Channel

━━━━━━━━━━━━━━

Daftar seluruh channel.

Button Join.

Button

✔ Saya Sudah Join

━━━━━━━━━━━━━━

Ketika user klik

Saya Sudah Join

Panggil API validasi.

Jika lolos.

Card berubah.

✔ Verification Success

Starting Download...

====================================================

Jika Force Join OFF

Langsung tampil Download Card.

====================================================

Download Card

Thumbnail

Nama File

Ukuran

Jenis

Tanggal Upload

Total Download

Uploader

====================================================

Button

Download Now

Copy Link

Share

====================================================

Saat Download

Jangan langsung download.

Animasi.

Preparing File...

████░░░░░

██████░░

████████

Starting Download...

====================================================

Download selesai.

Toast

Download Started

====================================================

Animation

Gunakan Framer Motion.

Hero Fade

Card Hover

Progress Animation

Ripple Button

Counter Animation

Page Transition

Glass Effect

Floating Background

====================================================

Background

Gradient

Glassmorphism

Blur

Floating Shapes

====================================================

Mobile

Optimalkan.

Karena mayoritas user Telegram memakai HP.

====================================================

SEO

Dynamic Metadata.

Judul mengikuti nama file.

OpenGraph.

====================================================

Share

Copy Link.

Native Share API.

====================================================

Dark Mode

Harus sempurna.

====================================================

Loading

Gunakan Skeleton.

Jangan Spinner saja.

====================================================

Accessibility

Keyboard Navigation.

ARIA.

====================================================

Performance

Gunakan Dynamic Import.

Optimalkan Rendering.

====================================================

PENTING

Belum membuat:

Dashboard

Upload

Login

Premium

Statistics

Admin

====================================================

OUTPUT

1.

Jelaskan struktur Download Page.

2.

Jelaskan API yang dipakai.

3.

Pastikan:

npm run build

npm run dev

berhasil.

4.

Pastikan responsif.

5.

Berhenti setelah Download Page selesai.




















```
