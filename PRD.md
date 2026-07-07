# 🎮 Product Requirements Document (PRD)

# XKOTAKBUNDER

> **Tagline:** *Game Jalan, Sholat Jangan Ketinggalan.*

**Status:** Draft Final v2.0

**Platform:** Website (PHP Native + MySQL)

**Target Platform:** Desktop & Mobile Responsive

---

# 1. Ringkasan Produk

XKOTAKBUNDER adalah website booking rental PlayStation yang memungkinkan pelanggan melakukan reservasi unit PlayStation secara online tanpa harus datang langsung ke lokasi. Pelanggan dapat melihat informasi rental, harga sewa, memilih unit yang tersedia, menentukan jadwal bermain, serta memilih metode pembayaran.

Website juga menyediakan dashboard admin untuk mengelola unit PlayStation, booking pelanggan, pembayaran, serta status ketersediaan unit secara real-time.

---

# 2. Latar Belakang

Banyak usaha rental PlayStation masih menggunakan pencatatan manual sehingga pelanggan harus datang langsung atau menghubungi admin hanya untuk menanyakan ketersediaan unit.

Hal tersebut sering menyebabkan:

- Jadwal bentrok.
- Kesalahan pencatatan.
- Sulit mengetahui unit yang masih tersedia.
- Pengelolaan booking kurang efisien.

Melalui XKOTAKBUNDER, proses booking menjadi lebih praktis, cepat, dan terorganisir.

---

# 3. Permasalahan

Permasalahan yang ingin diselesaikan:

- Booking masih dilakukan secara manual.
- Pelanggan tidak mengetahui unit yang tersedia.
- Sering terjadi double booking.
- Admin kesulitan mengelola data booking.
- Status unit tidak berubah secara otomatis setelah dipesan.

---

# 4. Tujuan Produk

Website ini bertujuan untuk:

- Mempermudah pelanggan melakukan booking PlayStation.
- Menampilkan informasi rental secara menarik.
- Mengurangi double booking.
- Membantu admin mengelola penyewaan.
- Menampilkan status ketersediaan unit secara real-time.

---

# 5. Non Goals

Versi pertama **tidak mencakup**:

- Membership
- Voucher & Promo
- Payment Gateway Otomatis
- Login Google
- Multi Cabang
- Notifikasi WhatsApp
- Penyewaan dibawa pulang
- Review & Rating

---

# 6. Target Pengguna

## Customer

Pelanggan yang ingin melakukan booking PlayStation secara online.

Kebutuhan:

- Melihat informasi rental.
- Melakukan booking.
- Memilih metode pembayaran.
- Mengetahui status booking.

---

## Admin

Pemilik atau pengelola rental.

Kebutuhan:

- Mengelola unit PlayStation.
- Mengelola booking.
- Mengonfirmasi pembayaran.
- Melihat statistik sederhana.

---

# 7. Fitur Customer

## Landing Page

Landing page terdiri dari:

- Hero Slider Game
- Tentang Rental
- Mengapa Memilih Kami
- Jenis PlayStation & Harga
- Cara Booking
- Lokasi Rental (Google Maps)
- Kontak
- Footer

---

## Hero Slider

Hero slider menampilkan game populer.

Contoh:

- GTA V
- God of War Ragnarök
- EA Sports FC 26
- Resident Evil 4
- Naruto Storm 4

Fitur:

- Autoplay
- Previous / Next Button
- Indicator
- Responsive

---

## Informasi PlayStation

Menampilkan informasi:

### PlayStation 5

Harga:

Rp15.000 / Jam

---

### PlayStation 4

Harga:

Rp10.000 / Jam

Disertai gambar PlayStation.

---

## Booking Online

Customer mengisi form:

- Nama
- Nomor HP
- Pilih Unit PlayStation
- Tanggal Bermain
- Jam Mulai
- Lama Bermain
- Metode Pembayaran

Pilihan pembayaran:

- QRIS
- Bayar di Tempat

---

## Status Booking

Setelah booking berhasil:

### Jika QRIS

Status Booking:

- Menunggu Konfirmasi

### Jika Bayar di Tempat

Status Booking:

- Pending

Status Unit otomatis berubah menjadi:

**Dibooking**

Sehingga tidak dapat dipilih oleh pelanggan lain sampai admin menyelesaikan transaksi.

---

# 8. Dashboard Admin

Admin Login.

Dashboard menampilkan:

- Total Unit
- Total Booking
- Booking Hari Ini
- Pendapatan

---

# 9. Kelola Unit PlayStation

Admin dapat:

- Menambah Unit
- Mengubah Unit
- Menghapus Unit

Data Unit:

- Gambar PlayStation
- Nama Unit
- Harga / Jam
- Status

Contoh:

- PS5 - Bilik 1
- PS5 - Bilik 2
- PS4 - Bilik 1
- PS4 - Bilik 2

---

# 10. Kelola Booking

Admin dapat:

- Melihat seluruh booking.
- Melihat detail booking.
- Mengubah status booking.
- Menghapus booking.

---

# 11. Konfirmasi Pembayaran

## QRIS

Customer mengunggah bukti pembayaran.

Admin dapat:

- Melihat bukti pembayaran.
- Mengonfirmasi pembayaran.

Status berubah menjadi:

**Dikonfirmasi**

---

## Bayar di Tempat

Status awal:

**Pending**

Setelah pelanggan datang dan pembayaran dilakukan:

Status menjadi:

**Selesai**

Status Unit otomatis kembali menjadi:

**Tersedia**

---

# 12. Alur Sistem

```text
Landing Page
      ↓
Klik "Booking Sekarang"
      ↓
Isi Form Booking
      ↓
Pilih Unit PlayStation
      ↓
Pilih Metode Pembayaran
(QRIS / Bayar di Tempat)
      ↓
Simpan Booking
      ↓
Status Unit = Dibooking
      ↓
Admin Login
      ↓
Konfirmasi Booking
      ↓
Status Unit = Tersedia (setelah selesai)
```

---

# 13. Database

## users

- id
- username
- password
- role

---

## playstations

- id
- nama_unit
- tipe
- harga
- gambar
- status

---

## bookings

- id
- nama_customer
- no_hp
- playstation_id
- tanggal
- jam_mulai
- durasi
- total_harga
- metode_pembayaran
- status

---

## payments

- id
- booking_id
- bukti_pembayaran
- status

---

# 14. UI & Desain

Tema:

- Gaming Modern
- Dark Theme
- Neon Blue Accent

Framework:

- Bootstrap 5

Karakteristik:

- Modern
- Clean
- Responsive
- Mudah digunakan

---

# 15. Scope MVP

## Customer

- Landing Page
- Hero Slider
- Informasi PlayStation
- Booking Online
- Upload Bukti QRIS
- Status Booking

---

## Admin

- Login
- Dashboard
- CRUD Unit PlayStation
- CRUD Booking
- Konfirmasi Pembayaran

---

# 16. Catatan Implementasi

- Booking hanya berlaku untuk bermain di tempat.
- Unit yang telah dibooking tidak dapat dipilih oleh pelanggan lain.
- Status unit akan kembali menjadi **Tersedia** setelah admin menyelesaikan transaksi.
- Seluruh tampilan menggunakan tema gaming modern dengan dominasi warna gelap dan aksen biru neon.