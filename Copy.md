# 
```
# Prompt: Telegram Share Link Bot (Force Subscribe Multi Channel & Group Management)

## Project Overview

Saya sedang membangun Telegram Bot yang berfungsi sebagai Telegram Drive dan File Sharing.

Tambahkan sistem **Force Subscribe (Force Join)** yang fleksibel.

Administrator harus dapat menambah atau menghapus Channel maupun Group langsung dari Bot Telegram tanpa membuka database atau mengedit file konfigurasi.

Gunakan struktur modular, clean code, dan scalable.

---

# Tujuan

Sebelum user bisa menggunakan bot:

* wajib join seluruh Channel yang diwajibkan
* wajib join Group yang diwajibkan
* jika belum join maka bot menolak semua command selain /start

Bot harus bisa mengecek status member menggunakan Telegram Bot API.

---

# Database

Gunakan database.

Contoh tabel:

## required_channels

* id
* chat_id
* username
* title
* invite_link
* enabled
* created_at

---

## required_groups

* id
* chat_id
* username
* title
* invite_link
* enabled
* created_at

---

# Admin Command

Hanya Admin yang boleh menggunakan command berikut.

---

## Tambah Channel

/addchannel

Flow:

Admin kirim

/addchannel

Bot membalas:

Silakan forward satu pesan dari channel yang ingin ditambahkan.

atau

Masukkan Username Channel.

Bot otomatis mengambil:

* Chat ID
* Username
* Nama Channel

Simpan ke database.

Balasan:

✅ Channel berhasil ditambahkan.

Nama:
Username:
Chat ID:

---

## Tambah Group

/addgroup

Flow sama seperti channel.

Bot otomatis menyimpan:

* Chat ID
* Username
* Nama Group

---

## Hapus Channel

/removechannel

Bot menampilkan daftar.

Contoh

1. Digital Cell
2. Promo
3. Backup

Admin klik.

Bot meminta konfirmasi.

Ya
Tidak

Jika Ya

hapus dari database.

---

## Hapus Group

/removegroup

Flow sama.

---

## List Channel

/listchannel

Menampilkan

Nama

Username

Status

Chat ID

Invite Link

---

## List Group

/listgroup

Menampilkan

Nama

Username

Status

Chat ID

Invite Link

---

## Enable

/channel enable

Pilih Channel.

Status menjadi aktif.

---

## Disable

/channel disable

Pilih Channel.

Status menjadi nonaktif.

---

## Enable Group

/group enable

---

## Disable Group

/group disable

---

# Force Subscribe

Saat user menjalankan

/start

Bot harus:

1.

Ambil seluruh channel aktif.

2.

Ambil seluruh group aktif.

3.

Loop semuanya.

4.

Gunakan getChatMember.

Jika status

left

kicked

restricted

anggap belum join.

---

Jika ada yang belum join

Bot mengirim pesan:

━━━━━━━━━━━━━━

Anda harus bergabung terlebih dahulu.

Silakan Join semua Channel dan Group berikut.

━━━━━━━━━━━━━━

Button

📢 Channel 1

📢 Channel 2

📢 Channel 3

👥 Group 1

👥 Group 2

👥 Group 3

────────────────

✅ Saya Sudah Join

---

Saat tombol

Saya Sudah Join

ditekan

Bot mengecek ulang semuanya.

Jika masih belum join

tampilkan lagi.

Jika semua sudah join

lanjut masuk menu utama.

---

# Auto Detect Invite Link

Jika channel memiliki username

gunakan

https://t.me/username

Jika private

gunakan invite link yang disimpan.

---

# Multiple Channel

Harus support

1 Channel

5 Channel

20 Channel

100 Channel

Tanpa perubahan kode.

---

# Multiple Group

Harus support

1 Group

10 Group

100 Group

Tanpa perubahan kode.

---

# Admin Panel Telegram

Semua pengelolaan dilakukan dari Bot Telegram.

Menu:

⚙ Force Subscribe

↓

Tambah Channel

Tambah Group

Daftar Channel

Daftar Group

Hapus Channel

Hapus Group

Enable

Disable

Kembali

Gunakan Inline Keyboard.

---

# Error Handling

Jika bot belum menjadi admin channel

Tampilkan

Bot belum menjadi Admin pada Channel tersebut.

Jika bot belum memiliki izin melihat anggota

Tampilkan

Bot belum memiliki izin memeriksa member.

Jika Channel tidak ditemukan

Tampilkan pesan error yang jelas.

---

# Security

Semua command admin hanya bisa digunakan oleh ADMIN_ID.

Semua validasi harus dilakukan di server.

User tidak boleh bisa bypass Force Subscribe.

---

# Performance

Gunakan async.

Gunakan Promise.all() saat mengecek banyak Channel atau Group.

Optimalkan query database.

Jangan hardcode daftar channel.

---

# Logging

Catat:

Admin menambah channel

Admin menghapus channel

Admin menambah group

Admin menghapus group

User gagal Force Subscribe

User berhasil lolos Force Subscribe

Semua log memiliki timestamp.

---

# Folder Structure

modules/

forceSubscribe/

service/

repository/

database/

telegram/

middlewares/

handlers/

config/

utils/

---

# Coding Standard

* Clean Architecture
* SOLID
* Modular
* Reusable
* Type Safe (jika TypeScript)
* Mudah ditambah fitur baru
* Tidak ada hardcode
* Semua konfigurasi melalui database

---

# Acceptance Criteria

✔ Admin dapat menambah Channel dari Bot.

✔ Admin dapat menghapus Channel dari Bot.

✔ Admin dapat menambah Group dari Bot.

✔ Admin dapat menghapus Group dari Bot.

✔ Force Subscribe mendukung banyak Channel.

✔ Force Subscribe mendukung banyak Group.

✔ Tombol "Saya Sudah Join" melakukan pengecekan ulang otomatis.

✔ Semua data tersimpan di database.

✔ Tidak perlu restart bot saat menambah atau menghapus Channel/Group.

✔ Aman, modular, scalable, dan siap production.

```


