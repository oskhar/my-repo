# Spesifikasi Kebutuhan Perangkat Lunak (SRS)
## Portal Web untuk Jurnalisme dan Pelaporan Berita

### 1. Pendahuluan

#### 1.1 Tujuan
Dokumen Spesifikasi Kebutuhan Perangkat Lunak (SRS) ini menjelaskan kebutuhan fungsional dan non-fungsional yang komprehensif untuk portal web yang berfokus pada jurnalisme dan pelaporan berita. Sistem ini akan menyediakan dua antarmuka utama: satu untuk administrator, anggota terdaftar, dan tamu; dan satu lagi untuk anggota terdaftar untuk membuat dan mengelola halaman berita pribadi mereka. Sistem ini bertujuan memberikan pengalaman yang mulus seperti platform blogging populer seperti Dev.to atau Facebook sambil mempertahankan standar jurnalisme profesional.

#### 1.2 Lingkup
Portal web ini akan menyediakan:
- Platform bagi pengguna tamu untuk membaca artikel berita dan berinteraksi melalui komentar.
- Sistem yang kuat bagi anggota terdaftar untuk membuat dan mengelola halaman berita pribadi mereka, termasuk menulis artikel, menyematkan media, dan menyesuaikan profil mereka.
- Alat administratif untuk memantau konten, mengelola peran pengguna, dan memastikan kepatuhan dengan pedoman komunitas.

#### 1.3 Definisi, Akronim, dan Singkatan
- Admin: Pengguna dengan kendali penuh atas moderasi konten, manajemen pengguna, dan pengaturan platform.
- Anggota Terdaftar: Pengguna yang memiliki kemampuan untuk membuat dan menerbitkan artikel berita, mengelola profil mereka, dan berinteraksi dengan anggota lain.
- Pengguna Tamu: Pengunjung yang dapat membaca artikel yang diterbitkan dan memberikan komentar.
- CMS: Sistem Manajemen Konten, platform untuk membuat, mengelola, dan memodifikasi konten digital.

#### 1.4 Referensi
- Platform Dev.to untuk Blogging dan Keterlibatan Komunitas.
- Halaman Facebook untuk manajemen konten yang dibuat pengguna.
- Template dan panduan SRS standar (IEEE 830-1998).

---

### 2. Deskripsi Umum

#### 2.1 Perspektif Produk
Platform ini adalah aplikasi web terpusat yang dirancang untuk mendukung aktivitas jurnalisme dan berbagi berita. Platform ini akan memanfaatkan teknologi web modern untuk pengalaman pengguna yang responsif, mudah diakses, dan dapat diskalakan.

#### 2.2 Fitur Produk
1. Fitur Admin:
   - Dasbor untuk memantau aktivitas pengguna dan konten.
   - Alat untuk memoderasi artikel dan komentar.
   - Manajemen peran dan izin.
2. Fitur Anggota Terdaftar:
   - Pembuatan dan penyesuaian profil.
   - Menulis, mengedit, dan menerbitkan artikel berita.
   - Penyesuaian halaman dengan templat dan widget.
   - Fitur interaksi: menyukai, berkomentar, dan berbagi artikel.
3. Fitur Pengguna Tamu:
   - Menjelajahi dan membaca artikel berita.
   - Memberikan komentar pada artikel (dimoderasi).

#### 2.3 Kelas dan Karakteristik Pengguna
1. Pengguna Admin:
   - Literasi teknis tinggi.
   - Bertanggung jawab memastikan kualitas konten dan standar komunitas.
2. Anggota Terdaftar:
   - Beragam keterampilan teknis.
   - Tertarik pada jurnalisme, blogging, atau berbagi berita.
3. Tamu:
   - Pengguna umum dengan kebutuhan teknis minimal.
   - Tertarik pada konsumsi konten berita.

#### 2.4 Lingkungan Operasional
- Frontend: Desain web responsif yang kompatibel dengan semua browser modern.
- Backend: Dihosting pada infrastruktur cloud yang dapat diskalakan dengan dukungan untuk penyimpanan data yang aman.
- Basis Data: Basis data relasional untuk mengelola pengguna, artikel, dan aktivitas.

#### 2.5 Kendala Desain dan Implementasi
- Kepatuhan terhadap GDPR dan undang-undang perlindungan data lokal.
- Dukungan untuk volume lalu lintas tinggi tanpa penurunan kinerja.
- Kepatuhan aksesibilitas (WCAG 2.1).

#### 2.6 Asumsi dan Ketergantungan
- Konektivitas internet diperlukan untuk semua fungsi pengguna.
- Ketergantungan pada pustaka dan kerangka kerja pihak ketiga untuk pengembangan cepat (misalnya, Vue.js, Laravel).

---

### 3. Kebutuhan Fungsional

#### 3.1 Portal Admin
1. Manajemen Pengguna:
   - Membuat, memperbarui, menghapus, dan menetapkan peran kepada pengguna.
2. Moderasi Konten:
   - Menyetujui, menolak, atau menandai artikel dan komentar.
3. Analitik:
   - Melihat statistik situs (misalnya, aktivitas pengguna, lalu lintas).

#### 3.2 Fitur Anggota Terdaftar
1. Manajemen Artikel:
   - Menulis, menyimpan draf, dan menerbitkan artikel.
   - Menambahkan gambar, video, dan tautan eksternal.
2. Manajemen Profil:
   - Memperbarui informasi pribadi.
   - Menyesuaikan tata letak halaman.
3. Interaksi:
   - Berinteraksi dengan anggota lain melalui suka dan komentar.

#### 3.3 Fitur Pengguna Tamu
1. Menjelajahi Konten:
   - Mencari artikel berdasarkan kategori atau kata kunci.
   - Melihat profil penulis dan konten terkait.
2. Komentar:
   - Memposting dan membalas komentar (tergantung moderasi).

---

### 4. Kebutuhan Non-Fungsional

#### 4.1 Kebutuhan Performa
- Sistem harus menangani hingga 10.000 pengguna bersamaan.
- Waktu muat halaman tidak boleh melebihi 3 detik.

#### 4.2 Kebutuhan Keamanan
- Menerapkan kontrol akses berbasis peran.
- Memastikan HTTPS untuk transmisi data yang aman.
- Enkripsi data untuk informasi sensitif.

#### 4.3 Kebutuhan Kemudahan Penggunaan
- Navigasi intuitif dan desain yang ramah pengguna.
- Dokumentasi bantuan yang komprehensif.

#### 4.4 Pemeliharaan dan Skalabilitas
- Arsitektur modular untuk pembaruan yang mudah.
- Dapat diskalakan untuk mengakomodasi pertumbuhan pengguna.

---

### 5. Lampiran

#### A. Contoh Kasus Penggunaan
Nama Kasus Penggunaan: Membuat Artikel
Aktor: Anggota Terdaftar
Prasyarat: Pengguna harus masuk.
Langkah-langkah:
1. Buka halaman "Buat Artikel".
2. Masukkan judul dan konten.
3. Lampirkan gambar atau video.
4. Simpan sebagai draf atau langsung terbitkan.
Hasil Akhir: Artikel disimpan dan ditampilkan di profil pengguna.

#### B. Glosarium
- Artikel: Sebuah konten yang dibuat oleh anggota terdaftar.
- Widget: Komponen yang dapat digunakan kembali untuk menyesuaikan halaman.
