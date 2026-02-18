# Laporan Relasi Database & Implementasi CRUD Mata Kuliah

## 1. Skema Database (ERD)

Berikut adalah representasi logis dari skema database yang dibangun menggunakan Laravel Migrations:

### Tabel: `mata_kuliahs`
- `id` (PK, BigInt, Auto Increment)
- `kode_mk` (String, Unique) - Kode identifikasi mata kuliah.
- `nama_mk` (String) - Nama mata kuliah.
- `sks` (Integer) - Jumlah SKS (Validasi: 1-6).
- `timestamps` (`created_at`, `updated_at`)

### Tabel: `mahasiswas`
- `id` (PK, BigInt, Auto Increment)
- `nim` (String, Unique) - Nomor Induk Mahasiswa.
- `nama` (String) - Nama Lengkap.
- `prodi` (String) - Program Studi.
- `angkatan` (Integer) - Tahun Angkatan.
- `mata_kuliah_id` (FK, Nullable) - Menghubungkan ke `mata_kuliahs.id`.
- `timestamps` (`created_at`, `updated_at`)

## 2. Alur Relasi (One-to-Many / hasMany)

Dalam proyek ini, relasi diimplementasikan menggunakan arsitektur **One-to-Many**:
- **Model `MataKuliah`**: Memiliki relasi `hasMany(Mahasiswa)`. Artinya, satu mata kuliah dapat diambil oleh banyak mahasiswa.
- **Model `Mahasiswa`**: Memiliki relasi `belongsTo(MataKuliah)`. Artinya, satu mahasiswa (dalam penyederhanaan tugas ini) terdaftar pada satu mata kuliah utama.

### Alur Kerja AI dalam Pengembangan:
1.  **Analisis Struktur**: AI menyarankan penggunaan relasi `hasMany` untuk memenuhi instruksi tugas spesifik.
2.  **Migrasi**: AI membantu membuat migrasi baru untuk menambahkan `mata_kuliah_id` ke tabel `mahasiswas` dan menghapus tabel pivot sebelumnya untuk beralih dari *Many-to-Many* ke *One-to-Many*.
3.  **Integrasi Controller**: AI memodifikasi `MahasiswaController` agar menyimpan `mata_kuliah_id` secara langsung dan `MataKuliahController` untuk menampilkan data relate menggunakan *Eager Loading* (`with('mahasiswas')`).
4.  **UI/UX**: AI merancang dropdown seleksi pada form Mahasiswa dan tabel dinamis pada halaman detail Mata Kuliah untuk menampilkan daftar mahasiswa secara otomatis.

## 3. Fitur CRUD Mata Kuliah
- **Create**: Input Kode, Nama, dan SKS dengan validasi ketat.
- **Read**: Daftar Mata Kuliah dengan tombol navigasi ke detail mahasiswa.
- **Update**: Memperbarui data mata kuliah tanpa merusak relasi yang ada.
- **Delete**: Menghapus mata kuliah (mahasiswa yang terkait akan diset menjadi `null` pada kolom `mata_kuliah_id` berkat `onDelete('set null')`).

---
**Penyusun:** Meli Kurniyah
**Teknologi:** Laravel 12, SQLite, Antigravity AI
