# Proyek melitugas03pwl 🚀

Proyek ini adalah sistem manajemen data mahasiswa dan mata kuliah yang dibangun menggunakan **Laravel 12**. Sistem ini memiliki fitur CRUD lengkap dengan desain modern (Glassmorphism & Dark Mode) dan sistem relasi antar data.

## ✨ Fitur Utama
1.  **CRUD Mahasiswa**: Pengelolaan data mahasiswa (NIM, Nama, Prodi, Angkatan).
2.  **CRUD Mata Kuliah**: Pengelolaan data akademik dengan **Validasi SKS (1-6)**.
3.  **Relasi Many-to-Many**: Mahasiswa dapat memilih beberapa mata kuliah, dan detail mata kuliah menampilkan daftar mahasiswa yang mengambilnya.
4.  **Log Konsultasi AI**: Dokumentasi proses pengembangan aplikasi bersama Antigravity AI.
5.  **Desain Premium**: Menggunakan Google Fonts (Outfit & Plus Jakarta Sans) dengan efek visual modern.

## 🛠️ Persyaratan
-   PHP >= 8.2
-   Laravel 12
-   SQLite (Database default)

## 🚀 Cara Instalasi
1.  Clone repository:
    ```bash
    git clone https://github.com/kurniyahmeli/melitugas03pwl.git
    ```
2.  Install dependensi:
    ```bash
    composer install
    ```
3.  Siapkan environment:
    ```bash
    cp .env.example .env
    php artisan key:generate
    ```
4.  Jalankan migrasi:
    ```bash
    php artisan migrate
    ```
5.  Jalankan server:
    ```bash
    php artisan serve
    ```

## 📝 Log Konsultasi AI
Log lengkap konsultasi selama pengerjaan tugas ini dapat diakses melalui link di footer aplikasi atau langsung di file `LOG_KONSULTASI_AI.md`.

---
© 2026 STMIK IKMI Cirebon - Dibuat oleh Meli Kurniyah
