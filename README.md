# 🏥 Emergency Room (IGD) Queue Management System

> 🚀 **Aplikasi Sistem Manajemen Antrean IGD Berbasis Skala Triase Medis Otomatis**
> Pengembangan portofolio implementasi Struktur Data Lanjut (*Linked List*) dan Basis Data Relasional Terapan untuk optimalisasi alur kerja layanan kesehatan gawat darurat.


## 📌 Sekilas Tentang Proyek

Sistem Manajemen Antrean IGD ini dirancang khusus untuk memprioritaskan penanganan medis pasien secara objektif menggunakan kalkulasi tanda-tanda vital secara otomatis. Aplikasi ini memisahkan peran secara rapi (*Separation of Concerns*) antara backend manajemen data dan antarmuka pengguna grafis desktop yang interaktif.


## 🚀 Fitur Utama & Keunggulan Teknis

* ### 🧠 Automated Triage Classifier
    Sistem mengkalkulasi kombinasi nilai klinis seperti **tensi sistolik**, **denyut nadi**, dan **suhu badan** pasien secara *real-time* untuk mengklasifikasikan tingkat kegawatan triase secara objektif (Level 1 hingga Level 5).

* ### ⛓️ Priority Queue via Custom Linked List
    Menggunakan struktur data kustom **Single Linked List Non-Circular (SLLNC)** yang dimodifikasi. Setiap ada pasien baru, sistem otomatis menyisipkan node (*auto-restructuring*) langsung di posisi yang sesuai dengan hierarki kegawatannya, bukan sekadar waktu kedatangan (*FIFO*).

* ### 🚨 Emergency Override (Jalur Resusitasi)
    Menyediakan tombol pintas darurat untuk memotong seluruh proses input tanda vital reguler. Fitur ini menempatkan pasien berkondisi kritis (Level 1) langsung di urutan paling depan antrean untuk penanganan tanpa penundaan.

* ### ⏳ Dynamic Aging Mechanism (Anti-Starvation)
    Dilengkapi algoritma penuaan antrean otomatis. Pasien dengan tingkat triase rendah yang sudah mengantre terlalu lama akan dinaikkan tingkat prioritasnya secara berkala guna menghindari kendala *starvation* (tidak pernah dilayani).

* ### 📊 Interactive Analytics Dashboard
    Menyajikan visualisasi data analitik dalam bentuk grafik **Donut Chart** untuk distribusi kategori triase pasien dan **Bar Chart** untuk status penanganan aktual menggunakan library *Matplotlib* yang dirender langsung ke kanvas UI.

* ### 🔐 Data Accountability & Shift Log
    Mengintegrasikan database relasional lokal **SQLite3** untuk merekam penanggung jawab medis secara akurat, mendata nama perawat penginput, serta dokter pemeriksa pada setiap siklus pelayanan pasien.

* ### 📦 Secure Session Archive & Reset Sequence
    Menyediakan mekanisme penutupan sesi harian yang aman. Seluruh antrean aktif otomatis disalin ke dalam tabel arsip riwayat jangka panjang sebelum tabel utama dibersihkan dan nomor urut ID diatur ulang kembali ke angka awal (1).


## 🛠️ Tech Stack & Arsitektur Sistem

Aplikasi ini dibangun menggunakan ekosistem teknologi modern Python:

* **Core Language:** 🐍 Python 3
* **GUI Framework:** 🎨 Kivy & KivyMD (Material Design UI components)
* **Database Engine:** 🗄️ SQLite3 (Relational Local Database)
* **Data Visualization:** 📉 Matplotlib Engine
* **Data Structure Core:** 🛠️ Custom Single Linked List (`NodePasien` & `SistemAntreanIGD`)


## 📁 Struktur Modul Berkas

* 📦 **`igd.py` (Core Logic & Data):** Mengatur blueprint basis data SQLite, rumus klasifikasi nilai triase, metode penanganan simpul berprioritas (*Linked List*), fungsi *aging*, serta fungsi penanganan tabel arsip.
* 📦 **`main.py` (User Interface & Controller):** Mengelola transisi antar halaman (*Screen Manager*), validasi form login, rendering visual grafik Matplotlib, serta manajemen tabel data interaktif (*MDDataTable*).
* 📦 **`bg.jpg` (Visual Asset):** Berkas latar belakang grafis utama yang terintegrasi secara harmonis dengan tema komponen gelap aplikasi.


## 💻 Panduan Instalasi & Pengoperasian

Ikuti langkah-langkah berikut untuk menjalankan proyek ini di lingkungan lokal Anda:
1. **Instalasi Dependensi Utama**
   ```bash
   pip install kiwi kivymd matplotlib
2. Pastikan file gambar `bg.jpg` berada di direktori yang sama dengan kode program.
3. Jalankan aplikasi melalui terminal atau command prompt:
   ```bash
python main.py
