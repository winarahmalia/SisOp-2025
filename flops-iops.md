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
![image](https://github.com/user-attachments/assets/5488a9d6-0686-4683-aefc-19bb12c97f75)

 Berdasarkan gambar diatas terdapat error pada perintah $make, ini terjadi
karena tidak sesuai dengan direktori . maka dari itu, solusi untuk menjalankan
$make yaitu harus memasuki direktori yang sesuai .

---

### 2. Membersihkan Build
Jalankan code dibawah ini:

```bash
$ make clean
```

![image](https://github.com/user-attachments/assets/f5e59d08-595c-46df-b9c0-2f78b17ef573)
 berdasarkan gambar diatas Perintah `make clean` berfungsi untuk membersihkan file yang dihasilkan selama proses build.
---

### 3. Instalasi Program
 ketik perintah $sudo make intall s

```bash
$ sudo make install
```
![image](https://github.com/user-attachments/assets/0a933b48-fd69-4b31-86fb-c80659c50297)

`sudo make install` berfungsi untuk memasang atau membangun perangkat lunak.

---

### 4. Uninstall Program
Jalankan:
![image](https://github.com/user-attachments/assets/f9a7f7a8-88f8-4b12-8456-401c790f898c)


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
![image](https://github.com/user-attachments/assets/caedfafe-17cc-4c8d-912c-59f66697bb94)

sesuai pada gambar diatas menunjukkan bahwa code diatas berfungsi untuk melihat performa operasi bilangan bulat.
---

### 6. Benchmarking CPU
Untuk menampilkan benchmarking CPU yang sedang dijalankan gunakan perintah:
```bash
$ ./flops64 8
$ ./iops64 8
```
![image](https://github.com/user-attachments/assets/812f2950-27e3-4251-a67d-b58e7bb809da)

