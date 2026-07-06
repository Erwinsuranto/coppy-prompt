```
# Telegram Drive Website - Tahap 11 : Landing Page (Homepage)

Tahap 10 (Design System) telah selesai.

Gunakan seluruh komponen dari Design System.

Jangan membuat komponen baru jika sudah tersedia.

====================================================

TUJUAN

Membuat Homepage Telegram Drive yang modern, profesional, cepat, responsif, dan siap diintegrasikan dengan REST API yang sudah dibuat.

Homepage harus menjadi identitas produk, bukan sekadar halaman daftar file.

====================================================

Gunakan:

Next.js App Router

Tailwind CSS

shadcn/ui

Framer Motion

TanStack Query

Axios Client yang sudah ada

Lucide Icons

====================================================

Layout Homepage

1. Hero Section
- Logo
- Nama Telegram Drive
- Subtitle singkat
- Search Box besar di tengah
- Tombol Search
- Statistik (Files, Users, Downloads)
- Background gradient modern
- Floating cards dengan animasi

2. Recent Files
- Ambil data dari REST API
- Tampilkan maksimal 12 file terbaru
- Card berisi thumbnail/icon file, nama, ukuran, jenis, tanggal upload

3. Popular Files
- Ambil data berdasarkan download terbanyak
- Grid responsif

4. Categories
- PDF
- Video
- Audio
- ZIP
- APK
- Image
- Document
- Masing-masing berupa card dengan ikon

5. Feature Section
- Telegram Cloud Storage
- Download Cepat
- Aman
- Mobile Friendly
- Dark Mode
- Multi Platform

6. FAQ
- Accordion
- Pertanyaan umum tentang Telegram Drive

7. Footer
- Copyright
- Version
- Telegram
- GitHub
- Privacy Policy
- Terms of Service

====================================================

ANIMASI

Gunakan Framer Motion.

- Hero Fade In
- Floating Cards
- Counter Animation
- Scroll Reveal
- Hover Animation
- Search Glow
- Smooth Transition

====================================================

RESPONSIVE

Mobile First

Tablet

Desktop

====================================================

API

Gunakan endpoint REST API yang sudah ada.

Jangan hardcode data.

Gunakan TanStack Query.

Loading gunakan Skeleton.

====================================================

PENTING

Belum membuat:

Download Page

Dashboard

Upload

Login

Premium

Settings

Admin

====================================================

OUTPUT

1. Jelaskan struktur halaman.
2. Jelaskan API yang dipakai.
3. Pastikan npm run build berhasil.
4. Pastikan npm run dev berhasil.
5. Berhenti setelah Homepage selesai.
```
