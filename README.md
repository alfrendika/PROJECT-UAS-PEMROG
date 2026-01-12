Sistem Manajemen Data Mahasiswa
 Aplikasi berbasis teks untuk mengelola data mahasiswa dengan arsitektur Model-View-Controller (MVC). Aplikasi ini dirancang untuk mendemonstrasikan prinsip-prinsip pemrograman berorientasi objek dan validasi data yang ketat.
 
 <img width="128" height="21" alt="image" src="https://github.com/user-attachments/assets/ba59bc7d-5a20-4caf-9de8-ebdc04900a6d" />
<img width="104" height="24" alt="image" src="https://github.com/user-attachments/assets/cad1f00b-6a5c-43b2-bf03-81bdd7b24fee" />
<img width="109" height="21" alt="image" src="https://github.com/user-attachments/assets/e773d992-b630-4d69-98f6-b9c00452b777" />

Fitur Utama

✅ Tambah Data Mahasiswa - Menambahkan mahasiswa baru dengan validasi otomatis
✅ Tampilkan Semua Data - Menampilkan semua data mahasiswa dalam format tabel
✅ Cari Mahasiswa - Mencari data mahasiswa berdasarkan NIM
✅ Hapus Data - Menghapus data mahasiswa berdasarkan NIM
✅ Validasi Ketat - Validasi untuk NIM, Nama, Jurusan, dan IPK

Cara Menggunakan
1. Clone Repository
bashgit clone https://github.com/username/sistem-manajemen-mahasiswa.git
cd sistem-manajemen-mahasiswa
2. Jalankan Program
bashpython main.py
3. Pilih Menu
Setelah program berjalan, Anda akan melihat menu utama:
Menu:
1. Tambah Data Mahasiswa
2. Tampilkan Semua Data Mahasiswa
3. Cari Mahasiswa
4. Hapus Data Mahasiswa
5. Keluar
Masukkan angka (1-5) untuk memilih menu yang diinginkan.

📖 Panduan Penggunaan
Menambah Data Mahasiswa (Menu 1)

Pilih menu "1"
Masukkan NIM (9 digit, harus numeric)

   NIM (9 digit): 123456789

Masukkan Nama (minimal 3 karakter, hanya huruf dan spasi)

   Nama: john doe

Pilih Jurusan (1-3)

   Pilihan Jurusan:
   1. Teknik Informatika
   2. Sistem Informasi
   3. Ilmu Komputer
   Pilih jurusan (1-3): 1

Masukkan IPK (0.0 - 4.0)

   IPK (0.0 - 4.0): 3.85
Pesan Sukses:
✓ Data mahasiswa berhasil ditambahkan!
Tampilkan Semua Data (Menu 2)

Pilih menu "2"
Sistem akan menampilkan tabel semua mahasiswa:

----------------------------------------------------------------------
NIM         Nama                 Jurusan                   IPK
----------------------------------------------------------------------
123456789   John Doe             Teknik Informatika        3.85
987654321   Jane Smith           Sistem Informasi          3.50
----------------------------------------------------------------------
Total: 2 mahasiswa
Cari Mahasiswa (Menu 3)

Pilih menu "3"
Masukkan NIM yang dicari

   Masukkan NIM yang dicari: 123456789

Sistem akan menampilkan data mahasiswa jika ditemukan

Hapus Data Mahasiswa (Menu 4)

Pilih menu "4"
Masukkan NIM mahasiswa yang akan dihapus

   Masukkan NIM mahasiswa yang akan dihapus: 123456789

Data akan dihapus jika NIM ditemukan

Keluar (Menu 5)
Pilih menu "5" untuk menutup aplikasi

✅ Validasi Data
Aplikasi ini melakukan validasi ketat untuk setiap input:
FieldAturan ValidasiContoh ValidContoh InvalidNIM9 digit numeric, tidak duplikat12345678912345678, 12345678ANamaMinimal 3 karakter, hanya huruf & spasiJohn DoeAb, John123JurusanHarus salah satu dari 3 pilihanTeknik InformatikaTeknik ElektroIPKDesimal 0.0 - 4.03.85, 4.05.0, abc

🏗️ Struktur Kode
├── main.py                    # File utama, berisi keseluruhan aplikasi
│
├── Class Mahasiswa           # Model data mahasiswa
│   ├── __init__()           # Inisialisasi atribut
│   └── __str__()            # Representasi string
│
├── Class ProsesMahasiswa    # Business Logic (Controller)
│   ├── validasi_nim()       # Validasi NIM
│   ├── validasi_nama()      # Validasi Nama
│   ├── validasi_jurusan()   # Validasi Jurusan
│   ├── validasi_ipk()       # Validasi IPK
│   ├── tambah_mahasiswa()   # Tambah data
│   ├── hapus_mahasiswa()    # Hapus data
│   ├── cari_mahasiswa()     # Cari data
│   └── get_semua_mahasiswa()# Ambil semua data
│
├── Class ViewMahasiswa      # Presentation (View)
│   ├── tampilkan_header()           # Tampilkan header
│   ├── tampilkan_menu()             # Tampilkan menu
│   ├── input_mahasiswa_baru()       # Form input
│   ├── tampilkan_tabel_mahasiswa()  # Tampilkan tabel
│   ├── cari_dan_tampilkan()         # Cari dan tampilkan
│   └── hapus_mahasiswa_view()       # Hapus melalui UI
│
└── def main()               # Program utama
    └── Loop menu utama

🎓 Arsitektur MVC
Aplikasi ini menggunakan pola Model-View-Controller untuk memisahkan tanggung jawab:
┌─────────────────────────────────────────────┐
│         USER INTERFACE (View)               │
│    - Menampilkan menu                       │
│    - Menerima input user                    │
│    - Menampilkan output/laporan             │
└────────────────┬────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────┐
│      BUSINESS LOGIC (Controller)            │
│    - Validasi data                          │
│    - Operasi CRUD (Create, Read, Update)   │
│    - Proses logika aplikasi                 │
└────────────────┬────────────────────────────┘
                 │
                 ▼
┌─────────────────────────────────────────────┐
│      DATA MODEL (Model)                     │
│    - Struktur data Mahasiswa                │
│    - Penyimpanan data dalam memory          │
└─────────────────────────────────────────────┘

💡 Contoh Kasus Penggunaan
Kasus 1: Registrasi Mahasiswa Baru
User memilih Menu 1
→ Input data mahasiswa
→ Sistem validasi semua field
→ Data disimpan jika valid
→ Pesan sukses ditampilkan
Kasus 2: Melihat Daftar Mahasiswa
User memilih Menu 2
→ Sistem mengambil semua data
→ Ditampilkan dalam format tabel
→ Menampilkan jumlah total mahasiswa
Kasus 3: Pencarian Data
User memilih Menu 3
→ Input NIM yang dicari
→ Sistem mencari di database
→ Menampilkan hasil pencarian
→ "Tidak ditemukan" jika tidak ada

🐛 Penanganan Error
Aplikasi ini menyediakan pesan error yang informatif untuk setiap kasus:
python# Contoh error yang ditangani:

✗ NIM harus numeric dan terdiri dari 9 digit!
✗ NIM 123456789 sudah terdaftar!
✗ Nama minimal harus 3 karakter!
✗ Nama hanya boleh mengandung huruf dan spasi!
✗ Jurusan harus: Teknik Informatika, Sistem Informasi, Ilmu Komputer
✗ IPK harus antara 0.0 hingga 4.0!
✗ IPK harus berupa angka desimal!
✗ Mahasiswa dengan NIM 123456789 tidak ditemukan!
✗ Pilihan tidak valid! Silakan coba lagi.

🔄 Flow Diagram

START
  │
  ├─→ Display Header
  │
  ├─→ LOOP: Display Menu
  │    │
  │    ├─→ Menu 1: Input & Tambah Data
  │    │    ├─→ Validasi NIM
  │    │    ├─→ Validasi Nama
  │    │    ├─→ Validasi Jurusan
  │    │    ├─→ Validasi IPK
  │    │    ├─→ Simpan ke Database
  │    │    └─→ Tampilkan Pesan Sukses
  │    │
  │    ├─→ Menu 2: Tampilkan Semua Data
  │    │    └─→ Tampilkan dalam Tabel
  │    │
  │    ├─→ Menu 3: Cari Mahasiswa
  │    │    ├─→ Input NIM
  │    │    └─→ Tampilkan Hasil
  │    │
  │    ├─→ Menu 4: Hapus Mahasiswa
  │    │    ├─→ Input NIM
  │    │    └─→ Hapus dari Database
  │    │
  │    └─→ Menu 5: Keluar
  │         └─→ END
  │
  └─→ Kembali ke LOOP (jika belum exit)
