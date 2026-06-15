
🏥Emergency Room (IGD) Queue Management System
Aplikasi Manajemen Antrean Pasien IGD Berbasis Skala Triase Medis Otomatis
Sistem Manajemen Antrean IGD ini dirancang khusus untuk memprioritaskan penanganan medis pasien
secara objektif. Menggunakan kalkulasi data klinis tanda-tanda vital, aplikasi ini mengklasifikasikan kondisi
kegawatan secara langsung demi mengoptimalkan alur kerja tenaga kesehatan di ruang instalasi gawat
darurat.

Fitur Utama & Keunggulan Teknis
- Automated Triage Classifier: Mengkalkulasi nilai tensi sistolik, denyut nadi, dan suhu badan pasien
secara *real-time* untuk menentukan kategori prioritas triase (Level 1 sampai 5).
- Priority Queue via Custom Linked List: Menggunakan struktur data *Single Linked List Non-Circular*
(SLLNC) yang dimodifikasi. Setiap pasien baru otomatis disisipkan (*auto-restructuring*) sesuai hierarki
kegawatan, bukan sekadar waktu kedatangan.
- Emergency Override (Jalur Resusitasi): Menyediakan tombol pintas darurat untuk melompati seluruh
proses input reguler dan menempatkan pasien dengan kondisi kritis langsung di urutan paling depan
antrean.
- Dynamic Aging Mechanism (Anti-Starvation): Dilengkapi algoritma penuaan antrean otomatis. Pasien
dengan triase rendah yang telah menunggu lama akan dinaikkan tingkat prioritasnya agar terhindar dari
kendala penanganan yang tertunda terlalu lama.
- Data Accountability & Shift Log: Mengintegrasikan database lokal SQLite untuk mencatatkan petugas
penanggung jawab secara akurat, mendata nama perawat penginput, serta dokter pemeriksa pada setiap
siklus pemeriksaan.
- Interactive Analytics Dashboard: Menampilkan visualisasi data analitik dalam bentuk grafik *Donut
Chart* untuk distribusi triase pasien dan *Bar Chart* untuk status pelayanan menggunakan library
Matplotlib yang dirender langsung ke dalam kanvas antarmuka.
- Secure Session Archive & Sequence Reset: Menyediakan mekanisme penutupan sesi harian yang
aman. Data antrean aktif akan disalin ke tabel arsip riwayat jangka panjang sebelum tabel utama
dibersihkan dan urutan nomor ID diatur ulang kembali ke awal.

Tech Stack yang Digunakan
Bahasa Pemrograman: Python 3
Framework GUI: Kivy & KivyMD (Material Design UI komponen untuk Python)
Penyimpanan Data: SQLite3 (Relational Local Database)
Visualisasi Data: Matplotlib (Engine pembuat grafik distribusi data)
Struktur Data Inti: Custom Single Linked List (`NodePasien` & `SistemAntreanIGD`)

Panduan Instalasi & Pengoperasian
Untuk menjalankan proyek ini di lingkungan lokal Anda, ikuti langkah-langkah di bawah ini:
1. Pastikan library dependensi utama sudah terinstal
pip install kivy kivymd matplotlib
2. Letakkan igd.py, main.py, dan bg.jpg di dalam satu direktori
3. Jalankan aplikasi utama melalui terminal
python main.py
