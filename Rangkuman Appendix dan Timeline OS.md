# Sistem Operasi  
**Rangkuman Appendix dan Timeline OS**

**Nama**: Wina Rahmalia  
**NRP**: 3124500052  
**Dosen Pengajar**: Ferry Astika Saputra  
**Program Studi**: D3 Teknik Informatika  
**Politeknik Elektronika Negeri Surabaya (PENS)**  
**Tahun**: 2024

---

# Rangkuman Appendix dan Perkembangan Sistem Operasi

## Rangkuman Appendix

Sistem operasi menggunakan berbagai struktur data untuk mengelola proses, memori, dan sumber daya lainnya. Berikut adalah penjelasan beberapa struktur data yang umum digunakan:

- **Tabel Proses**: Menyimpan informasi tentang proses yang sedang berjalan.
- **Antrian (Queue)**: Digunakan untuk mengelola tugas atau proses secara berurutan.
- **Tabel Alokasi Memori**: Mencatat alokasi memori untuk aplikasi dan proses yang berjalan.
- **Struktur Data Kompleks**: Seperti pohon biner (binary tree), hash table, dan lainnya untuk pengelolaan data yang lebih efisien.

### Perintah Terminal

Appendix biasanya menyertakan daftar perintah yang tersedia di sistem operasi, seperti:

- **Perintah Sistem Dasar**: `ls`, `cd`, `mkdir`, `rm` (pada sistem berbasis Unix/Linux).
- **Perintah Administrasi**: Untuk mengelola jaringan, memori, penyimpanan, dan lainnya.
- **Utilitas Debugging dan Log**: Contohnya `top`, `ps`, `grep`.

#### Contoh Perintah:
- `ls`: Menampilkan isi direktori.
- `chmod`: Mengubah hak akses file.

### API dan System Calls

Sistem operasi menyediakan **Application Programming Interface (API)** atau **system call** untuk memungkinkan aplikasi berinteraksi dengan sistem.

#### Contoh API di Windows:
- `CreateFile()`, `ReadFile()`, `WriteFile()` → operasi file.
- `CreateProcess()` → membuat proses baru.

### Konfigurasi Sistem Lanjut

Appendix juga dapat menjelaskan konfigurasi sistem yang lebih kompleks, seperti:

- **Konfigurasi Kernel**: Mengatur kernel di sistem berbasis Unix/Linux.
- **Pengaturan Jaringan**: IP statis/dinamis, DNS, firewall, dan layanan jaringan lainnya.
- **Keamanan Sistem**: Mengatur fitur keamanan seperti SELinux, AppArmor, dan firewall.

### Contoh Kode Program

Beberapa cuplikan kode juga disertakan untuk menunjukkan implementasi sistem operasi, seperti:

- **Manajemen Proses**: Kode untuk membuat atau mengelola proses.
- **Input/Output File**: Membaca dan menulis file menggunakan system call.
- **Multithreading dan Sinkronisasi**: Mengelola thread dan penguncian (locking) dalam aplikasi paralel.

### Algoritma dalam Sistem Operasi

Appendix juga dapat memuat penjelasan algoritma penting, seperti:

- **Penjadwalan Proses**: First-Come First-Served (FCFS), Shortest Job Next (SJN), Round Robin (RR).
- **Manajemen Memori**: Paging, segmentasi, dan memori virtual.
- **Manajemen I/O**: Algoritma untuk buffer dan antrian perangkat.

### Troubleshooting, Glosarium, dan FAQ

- **Solusi Masalah Umum**: Seperti instalasi, masalah perangkat keras, dan performa sistem.
- **Glosarium Istilah**: Membantu memahami istilah-istilah teknis dalam sistem operasi.
- **FAQ (Frequently Asked Questions)**: Pertanyaan yang sering muncul dari pengguna dan jawabannya.

---

## Timeline Perkembangan Sistem Operasi

Perkembangan sistem operasi dibagi ke dalam beberapa generasi:

### Generasi ke-1: Batch Processing (1950-an)

- Tugas diproses satu per satu tanpa interaksi pengguna.
- Contoh sistem: GM-NAA I/O, IBSYS (menggunakan punch card dan printer).

### Generasi ke-2: Time-Sharing (1960-an)

- Komputer mendukung banyak pengguna secara bersamaan.
- Contoh sistem: CTSS, MULTICS.

### Generasi ke-3: Berbasis Disk (1970-an)

- Muncul sistem seperti UNIX, DOS, dan CP/M.
- Fokus pada efisiensi penyimpanan dan menjalankan program kompleks.

### Generasi ke-4: GUI dan Jaringan (1980-an)

- Sistem operasi semakin interaktif dengan antarmuka grafis (GUI).
- Contoh: Macintosh System Software, Microsoft Windows, dan Linux.
- Mendukung koneksi jaringan untuk meningkatkan produktivitas.

### Generasi ke-5: Berbasis Internet (1990-an – sekarang)

- Sistem operasi seperti Windows 10, macOS, dan distribusi Linux mendukung integrasi internet, cloud computing, dan layanan online.
- Fokus pada konektivitas global dan kolaborasi daring.

### Masa Depan: Kognitif dan Otomatis

- Akan mengandalkan kecerdasan buatan (AI) dan komputasi kuantum.
- Sistem akan lebih adaptif terhadap kebiasaan pengguna dan meningkatkan efisiensi secara otomatis.

