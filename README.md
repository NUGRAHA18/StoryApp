# StoryShare - Dicoding Submission Project

StoryShare adalah aplikasi web Single-Page Application (SPA) yang dirancang sebagai platform bagi pengguna (khususnya siswa/alumni Dicoding) untuk berbagi cerita atau momen berharga mereka, lengkap dengan foto, deskripsi, dan lokasi opsional. Aplikasi ini dibangun sebagai bagian dari submission kelas "Menjadi Front-End Web Developer Expert" di Dicoding Academy.

Project ini memanfaatkan Dicoding Story API sebagai backend dan di-bundle menggunakan Webpack.

*(Disarankan: Tambahkan screenshot atau link demo GIF aplikasi Anda di sini)*

## ✨ Fitur Utama

* **Autentikasi Pengguna:** Registrasi dan Login pengguna.
* **Lihat Cerita:** Menampilkan daftar cerita terbaru dari API.
* **Tambah Cerita Baru:**
    * Upload foto dari perangkat atau ambil langsung dari kamera.
    * Menulis deskripsi cerita.
    * Memilih lokasi cerita (opsional) dengan klik pada peta interaktif.
    * Validasi input form dan pesan status (sukses/gagal).
* **Peta Interaktif:**
    * Visualisasi lokasi cerita pada peta Leaflet.
    * Marker dengan popup detail cerita.
    * Sinkronisasi antara daftar cerita dan peta (highlight marker saat hover/klik/fokus keyboard pada kartu cerita).
    * Kontrol untuk memilih *tile layer* peta (Street Map, Satellite, Topographic).
    * Layout peta dinamis pada halaman utama saat di-scroll (desktop).
* **Single-Page Application (SPA):** Navigasi antar halaman menggunakan *hash routing* tanpa *reload* halaman penuh.
* **Transisi Halaman Kustom:** Menggunakan View Transitions API dengan animasi kustom (scale & fade).
* **Tema:** Pilihan mode Terang (Light) dan Gelap (Dark).
* **Desain Responsif:** Tampilan optimal pada berbagai ukuran layar (Mobile, Tablet, Desktop).
* **Aksesibilitas:**
    * Penggunaan HTML semantik (`header`, `nav`, `main`, `footer`, `article`, dll.).
    * Teks alternatif (`alt`) pada gambar.
    * Label yang sesuai untuk elemen formulir.
    * Fitur "Skip to content".
    * Navigasi keyboard untuk elemen interaktif (termasuk kartu cerita).

## 💻 Tumpukan Teknologi

* **Front-end:** HTML, CSS, JavaScript
* **Bundler:** Webpack
* **Transpiler:** Babel
* **Library Peta:** LeafletJS
* **Arsitektur:** Single-Page Application (SPA) dengan pola Model-View-Presenter (MVP)
* **API:** View Transitions API (untuk animasi halaman)

## 🚀 Memulai

### Prasyarat

* [Node.js](https://nodejs.org/) (disarankan versi LTS terbaru)
* [npm](https://www.npmjs.com/) (biasanya terinstal bersama Node.js)

### Instalasi

1.  **Clone repository ini:**
    ```bash
    git clone <URL_REPOSITORY_ANDA>
    cd <NAMA_FOLDER_PROYEK>
    ```
    *(Atau jika Anda mengunduh sebagai ZIP, ekstrak file tersebut)*

2.  **Instal dependensi:**
    ```bash
    npm install
    ```
   

3.  **Buat file `.env`:**
    * Buat file baru bernama `.env` di *root* direktori proyek.
    * Salin isi dari file `STUDENT.txt` ke dalam `.env`.
    * Sesuaikan nilainya jika diperlukan (saat ini belum wajib). Contoh isi `.env`:
        ```dotenv
        APP_URL=http://localhost:3000
        MAP_SERVICE_API_KEY=
        ```
    * File `.env` sudah diabaikan oleh Git.

## 🛠️ Skrip yang Tersedia

* **Menjalankan Server Pengembangan:**
    ```bash
    npm run start-dev
    ```
   
    Membuka aplikasi di `http://localhost:3000` (atau port lain jika 3000 sudah terpakai) dengan *hot reload*.

* **Build untuk Produksi:**
    ```bash
    npm run build
    ```
   
    Menghasilkan *build* aplikasi yang teroptimasi di dalam direktori `dist/`.

* **Menjalankan Build Produksi Secara Lokal:**
    ```bash
    npm run serve
    ```
   
    Menjalankan server HTTP sederhana untuk menyajikan konten dari direktori `dist/`. Berguna untuk menguji *build* produksi sebelum *deploy*.

## 📂 Struktur Proyek

```text
storyshare-app/
├── dist/                   # File hasil build untuk produksi
├── src/
│   ├── public/             # Aset statis (favicon, images, manifest, etc.)
│   ├── scripts/            # Kode JavaScript
│   │   ├── components/     # Komponen UI (StoryCard, StoryList, etc.)
│   │   ├── data/           # Repositori data (interaksi API)
│   │   ├── models/         # Model (logika bisnis data)
│   │   ├── pages/          # Komponen halaman (HomePage, LoginPage, etc.)
│   │   ├── presenters/     # Presenter (penghubung View & Model)
│   │   ├── routes/         # Pengaturan routing SPA
│   │   ├── utils/          # Fungsi/kelas utilitas (MapHandler, AuthGuard, etc.)
│   │   └── index.js        # Entry point utama JavaScript
│   ├── styles/             # Kode CSS
│   │   ├── components.css  # Styling komponen
│   │   ├── main.css        # Reset & gaya dasar
│   │   ├── pages.css       # Styling spesifik halaman
│   │   ├── responsive.css  # Aturan media query
│   │   ├── themes.css      # Variabel tema (dark/light)
│   │   ├── transitions.css # Styling View Transitions
│   │   └── styles.css      # Entry point utama CSS (impor file lain)
│   └── index.html          # Template HTML utama
├── .env                    # Variabel lingkungan (dibuat manual)
├── .gitignore              # File/folder yang diabaikan Git
├── package.json            # Metadata proyek & dependensi
├── package-lock.json       # Kunci versi dependensi
├── README.md               # Dokumentasi proyek (file ini)
├── STUDENT.txt             # Informasi (bisa dihapus/diubah)
├── webpack.common.js       # Konfigurasi Webpack umum
├── webpack.dev.js          # Konfigurasi Webpack untuk development
└── webpack.prod.js         # Konfigurasi Webpack untuk produksi
