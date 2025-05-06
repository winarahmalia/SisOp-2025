# Sistem Operasi

**Nama**: Wina Rahmalia  
**NRP**: 3124500052  
**Dosen Pengajar**: Ferry Astika Saputra  

**PROGRAM STUDI D3 TEKNIK INFORMATIKA**  
**POLITEKNIK ELEKTRONIKA NEGERI SURABAYA (PENS)**  
**TAHUN 2024**

---

## 1. Perbedaan Multiprogramming dan Multitasking

### ➤ Multiprogramming
- Bentuk dasar dari pemrosesan paralel.
- Banyak proses berjalan bersamaan pada satu prosesor.
- Digunakan oleh banyak pengguna secara bersamaan dengan satu CPU.
- Memaksimalkan pemanfaatan CPU untuk mengurangi waktu idle.

### ➤ Multitasking
- Kemampuan OS menjalankan banyak tugas secara bersamaan.
- Menggunakan dua atau lebih CPU.
- Mengalokasikan tugas ke berbagai sumber daya seperti CPU dan memori.

---

## 2. Fungsi Sistem Operasi

Sistem operasi memiliki fungsi utama sebagai manajer sumber daya komputer (hardware dan software) serta penghubung antara pengguna dan perangkat keras. Beberapa fungsi utama:

- **Mengolah komponen hardware**  
  Memastikan software dapat mengakses perangkat hardware.

- **Mengolah operasi aplikasi**  
  Menyediakan akses pemrosesan di CPU dan memori untuk aplikasi.

- **Mode UI (User Interface)**  
  Mengaktifkan UI agar pengguna dapat berinteraksi dengan sistem.

- **Mengatur proses**  
  Mengelola pembuatan, penjadwalan, dan penghentian proses.

- **Mengelola memori**  
  Mengalokasikan memori secara efisien untuk program.

- **Menjamin keamanan data**  
  Menyediakan mekanisme perlindungan terhadap akses ilegal dan ancaman.

- **Menyediakan layanan jaringan**  
  Memungkinkan komunikasi antar komputer.

- **Deteksi error**  
  Mendeteksi kesalahan dan memberikan respon yang sesuai.

---

## 3. Virtualisasi Container

- **Container** adalah unit perangkat lunak yang berisi kode dan semua dependensi agar aplikasi dapat berjalan di berbagai platform (lokal, server, dll).
- Virtual Container adalah bentuk containerisasi yang berjalan di atas sistem virtualisasi.
- Umumnya dikaitkan dengan teknologi seperti Docker, LXC, dan Podman.
- Menyediakan lingkungan terisolasi dengan sistem operasi host.

### Manfaat Virtualisasi Container:
- Ukuran ringan (dalam MB)
- Waktu start cepat
- Portabilitas tinggi
- Skalabilitas tinggi
