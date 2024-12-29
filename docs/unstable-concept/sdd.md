# Dokumen Desain Sistem (System Design Document - SDD)

## 1. Pendahuluan
### 1.1 Tujuan
Dokumen ini bertujuan untuk memberikan panduan teknis lengkap untuk pengembangan web pers dan pemberitaan. Sistem ini akan dirancang berdasarkan arsitektur Domain-Driven Design (DDD) menggunakan framework NestJS, yang dirancang untuk memenuhi kebutuhan pengguna sesuai dengan dokumen SRS.

Web ini memiliki dua bagian utama:
1. Web Admin: Untuk mengelola pengguna, berita, kategori, tag, dan pengaturan sistem.
2. Web Publik: Untuk pengguna terdaftar (member), tamu (guest), dan admin.

Setiap pengguna terdaftar dapat membuat halaman berita mereka sendiri dengan fitur mirip blog.

### 1.2 Ruang Lingkup
Desain ini mencakup:
- Arsitektur sistem berbasis DDD.
- Desain komponen dan modul dalam NestJS.
- Diagram proses bisnis.
- Desain antarmuka pengguna (UI).
- Model data dan relasi entitas.
- Keamanan dan standar pengembangan web terbaik.

### 1.3 Referensi
- Dokumen SRS Web Pers.
- Standar pengembangan aplikasi web menggunakan NestJS.
- Panduan keamanan OWASP.

---

## 2. Desain Sistem

### 2.1 Arsitektur Sistem
Arsitektur berbasis Domain-Driven Design (DDD) digunakan untuk memastikan modularitas, skalabilitas, dan maintainability. Berikut adalah elemen utama:

1. Frontend:
   - Dibangun menggunakan Vue.js dengan Vuetify sebagai framework UI.
   - Berkomunikasi dengan backend melalui REST API dan WebSocket.

2. Backend:
   - Framework: NestJS dengan pendekatan modular berbasis domain.
   - Komponen utama meliputi modul untuk pengguna, berita, kategori, tag, dan komentar.

3. Database:
   - PostgreSQL sebagai database utama.
   - Redis untuk caching dan session management.

4. Keamanan:
   - Menggunakan JWT (JSON Web Token) untuk autentikasi.
   - Data pengguna dilindungi dengan enkripsi AES-256.

5. DevOps:
   - CI/CD pipeline menggunakan GitHub Actions.
   - Deployment ke AWS dengan Docker dan Kubernetes.

6. Cloud Hosting:
   - Penyimpanan media menggunakan AWS S3.

### 2.2 Diagram Arsitektur
```plaintext
Browser (Vue.js)
     |
     v
API Gateway (NestJS)
     |
     v
Domain Services
     |
     v
PostgreSQL <--> Redis
     |
     v
AWS S3 (Media Storage)
```

---

### 2.3 Komponen Backend (NestJS)

#### 2.3.1 Struktur Modular
Modul utama:
- UserModule: Mengelola pengguna, peran, dan otentikasi.
- NewsModule: Mengelola berita, termasuk CRUD berita.
- CategoryModule: Mengelola kategori berita.
- TagModule: Mengelola tag berita.
- CommentModule: Mengelola komentar pada berita.
- AdminModule: Mengelola fitur khusus admin.

#### 2.3.2 Contoh Struktur Direktori
```plaintext
src/
  |-- modules/
  |     |-- user/
  |     |-- news/
  |     |-- category/
  |     |-- tag/
  |     |-- comment/
  |-- shared/
  |     |-- services/
  |     |-- interceptors/
  |     |-- guards/
  |-- app.module.ts
```

---

### 2.4 Model Data dan Relasi

#### 2.4.1 Desain Entitas
- User:
  - id: UUID
  - name: string
  - email: string
  - password: string (hashed)
  - role: enum (Admin/Member)

- News:
  - id: UUID
  - title: string
  - content: text
  - authorId: UUID (relation to User)
  - categoryId: UUID (relation to Category)
  - tags: many-to-many relation with Tag

- Category:
  - id: UUID
  - name: string

- Tag:
  - id: UUID
  - name: string

- Comment:
  - id: UUID
  - content: string
  - newsId: UUID (relation to News)
  - userId: UUID (relation to User)

#### Relasi
- User dapat memiliki banyak berita.
- Berita dapat memiliki banyak tag dan satu kategori.
- Setiap berita dapat memiliki banyak komentar.

---

### 2.5 Diagram Proses Bisnis

#### 2.5.1 Proses Pembuatan Berita oleh Member
1. Login: Member login menggunakan JWT.
2. Navigasi ke Dashboard: Member diarahkan ke dashboard pribadi.
3. Buat Berita:
   - Member mengisi form (judul, konten, kategori, tag).
   - Sistem memvalidasi data.
   - Data disimpan ke database.
4. Publikasi: Berita dipublikasikan dan tersedia di halaman utama.

#### 2.5.2 Moderasi Konten oleh Admin
1. Login: Admin login menggunakan JWT.
2. Moderasi:
   - Admin melihat daftar berita dan komentar.
   - Admin dapat menghapus atau menandai konten yang melanggar.

#### 2.5.3 Pembacaan oleh Guest
1. Guest mengakses halaman utama.
2. Guest mencari berita berdasarkan kategori atau tag.
3. Guest membaca berita tanpa login.

---

### 2.6 Keamanan
1. JWT digunakan untuk autentikasi.
2. Rate Limiting untuk mencegah serangan brute force.
3. Validasi input dengan class-validator di NestJS.
4. Enkripsi data sensitif menggunakan AES-256.
5. Implementasi HTTPS.

---

### 2.7 Lingkungan Implementasi
1. Backend: NestJS dengan Node.js v18.
2. Frontend: Vue.js v3.
3. Database: PostgreSQL v14.
4. Containerization: Docker.
5. CI/CD: GitHub Actions.
6. Hosting: AWS (EC2, S3, RDS).

---

## 3. Penutup
Dokumen ini disusun untuk memastikan pengembangan web pers sesuai dengan standar terbaik. Jika terdapat revisi atau tambahan, dokumen ini akan diperbarui sesuai kebutuhan.
