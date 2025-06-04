# Sistem Operasi  
## Flops-iops

**Nama**: Wina Rahmalia  
**NRP**: 3124500052  
**Dosen Pengajar**: Ferry Astika Saputra  

**PROGRAM STUDI D3 TEKNIK INFORMATIKA**  
**POLITEKNIK ELEKTRONIKA NEGERI SURABAYA (PENS)**  
**TAHUN 2024**

---

### 1. Clone Repository dan Build
Buka terminal Linux lalu clone repository `flops-iops`:

```bash
git clone https://github.com/ferryastika/flops-iops.git
```

Masuk ke direktori `flops-iops`, kemudian jalankan:

```bash
$ make
```

> ⚠️ Jika terjadi error pada perintah `$make`, kemungkinan karena direktori yang aktif tidak sesuai. Solusinya adalah pastikan Anda berada di direktori `flops-iops`.

---

### 2. Membersihkan Build
Jalankan:

```bash
$ make clean
```

Perintah `make clean` berfungsi untuk membersihkan file yang dihasilkan selama proses build.

---

### 3. Instalasi Program
Jalankan:

```bash
$ sudo make install
```

`sudo make install` berfungsi untuk memasang atau membangun perangkat lunak.

---

### 4. Uninstall Program
Jalankan:

```bash
$ sudo make uninstall
```

Perintah ini berfungsi untuk menghapus perangkat lunak yang telah terinstal.

---

### 5. Melihat Performa Operasi
Jalankan perintah-perintah berikut:

```bash
$ iops32 $(nproc)
$ iops64 $(nproc)
$ flops32 $(nproc)
$ flops64 $(nproc)
```

Perintah-perintah ini digunakan untuk melihat performa operasi bilangan bulat.

---

### 6. Benchmarking CPU
Untuk menampilkan benchmarking CPU yang sedang dijalankan:

```bash
$ ./flops64 8
$ ./iops64 8
```
