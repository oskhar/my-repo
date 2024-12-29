# Dokumen Wireframe dan Mockup (MMD)

## 1. **Pendahuluan**

### 1.1 Tujuan
Dokumen ini bertujuan untuk memberikan panduan visual yang lengkap mengenai tata letak dan desain antarmuka web pers dan pemberitaan. Dokumen ini akan mencakup wireframe dan mockup untuk semua halaman utama, termasuk halaman admin, pengguna terdaftar (member), dan tamu (guest).

### 1.2 Lingkup
Dokumen ini mencakup:
- Wireframe: Sketsa sederhana dari tata letak halaman untuk memberikan gambaran awal.
- Mockup: Desain antarmuka yang lebih mendetail dengan elemen visual seperti warna, ikon, dan tipografi.

Wireframe dan mockup disesuaikan dengan konsep arsitektur **Domain-Driven Design (DDD)** serta mengutamakan **UX/UI best practices** agar web layak jual dan mudah digunakan.

---

## 2. **Desain Wireframe**

### 2.1 Wireframe Halaman Publik

#### 2.1.1 Halaman Utama (Guest)
- **Header**:
  - Logo di kiri atas.
  - Navigasi utama: Home, Kategori, Tentang Kami, Login.
- **Hero Section**:
  - Gambar banner.
  - Pencarian berita dengan input field.
- **Daftar Berita**:
  - List berita terbaru dengan gambar thumbnail, judul, dan deskripsi singkat.
- **Footer**:
  - Informasi kontak dan tautan media sosial.

#### 2.1.2 Halaman Detail Berita
- **Header**: Sama dengan halaman utama.
- **Konten Berita**:
  - Judul berita di atas.
  - Gambar utama.
  - Konten berita dalam format paragraf.
- **Komentar**:
  - Form untuk menambahkan komentar (jika member).
  - Daftar komentar dari pengguna lain.
- **Sidebar**:
  - Daftar berita terkait.

#### 2.1.3 Halaman Login/Registrasi
- **Form Login**:
  - Input untuk email dan password.
  - Tombol login.
- **Form Registrasi**:
  - Input untuk nama, email, dan password.
  - Tombol registrasi.

---

### 2.2 Wireframe Halaman Admin

#### 2.2.1 Dashboard Admin
- **Header**:
  - Logo di kiri atas.
  - Menu dropdown untuk profil admin.
- **Sidebar Navigasi**:
  - Menu: Berita, Pengguna, Kategori, Tag, Komentar, Pengaturan.
- **Konten Utama**:
  - Statistik singkat (jumlah berita, pengguna, komentar).
  - Tabel daftar berita yang dapat dimoderasi.

#### 2.2.2 Halaman Pengguna
- **Daftar Pengguna**:
  - Tabel dengan kolom: Nama, Email, Role, Tindakan (Edit/Hapus).
- **Form Tambah/Edit Pengguna**:
  - Input untuk nama, email, password, dan role.

#### 2.2.3 Halaman Moderasi Berita
- **Daftar Berita**:
  - Tabel dengan kolom: Judul, Penulis, Status, Tindakan (Edit/Hapus).
- **Form Edit Berita**:
  - Input untuk judul, konten, kategori, dan tag.

---

## 3. **Desain Mockup**

### 3.1 Mockup Halaman Publik

#### 3.1.1 Halaman Utama
- **Warna**:
  - Header: Biru tua (#002D62).
  - Background: Putih (#FFFFFF).
  - Teks: Hitam (#333333).
- **Tipografi**:
  - Judul: Montserrat, Bold, 24px.
  - Konten: Roboto, Regular, 16px.
- **Ikon**:
  - Pencarian: Ikon kaca pembesar.
  - Media sosial: Ikon Facebook, Twitter, Instagram di footer.

#### 3.1.2 Halaman Detail Berita
- **Konten**:
  - Gambar utama dengan rasio 16:9.
  - Komentar dengan avatar pengguna.

### 3.2 Mockup Halaman Admin

#### 3.2.1 Dashboard Admin
- **Warna**:
  - Sidebar: Abu-abu gelap (#2D2D2D).
  - Konten: Putih.
- **Grafik Statistik**:
  - Menggunakan chart pie dan bar sederhana dengan warna biru dan hijau.

#### 3.2.2 Halaman Pengguna
- **Tabel**:
  - Header tabel dengan background abu-abu muda (#F2F2F2).
  - Teks tabel: Hitam (#000000).

---

## 4. **Spesifikasi UI**

### 4.1 Komponen Utama
- **Button**:
  - Primary: Biru (#0056D2), teks putih.
  - Secondary: Abu-abu (#6C757D), teks putih.
- **Form Input**:
  - Border abu-abu terang.
  - Placeholder dengan teks abu-abu (#B0B0B0).

### 4.2 Interaksi Pengguna
- **Hover Effects**:
  - Tombol: Warna lebih gelap saat hover.
  - Tautan: Garis bawah saat hover.
- **Responsif**:
  - Mobile: Navigasi collapse menjadi ikon hamburger.
  - Tablet/Desktop: Navigasi horizontal penuh.

---

## 5. **Kesimpulan**
Dokumen ini menyediakan panduan lengkap mengenai tata letak dan desain antarmuka web pers. Wireframe dan mockup dirancang sesuai dengan standar terbaik untuk memastikan pengalaman pengguna yang optimal. Desain ini siap digunakan untuk pengembangan frontend dengan framework seperti **Vue.js** atau lainnya sesuai kebutuhan.
