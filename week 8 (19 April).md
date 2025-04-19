
# Konsep Single Thread dan Multithread

### Single Thread

Konsep *single thread* mengacu pada model eksekusi di mana hanya terdapat satu thread (utas) yang menangani seluruh tugas dari awal hingga akhir dalam suatu program. Thread adalah unit terkecil dari pemrosesan yang dapat dijadwalkan oleh sistem operasi. Dalam sistem *single-threaded*, semua instruksi diproses secara berurutan. Jika terdapat operasi yang memakan waktu lama, maka seluruh program akan berhenti sejenak menunggu operasi tersebut selesai, baru kemudian melanjutkan ke langkah berikutnya.

Kelebihan dari *single thread* adalah kesederhanaannya. Karena hanya ada satu jalur eksekusi, tidak ada risiko konflik antar thread seperti *race condition* atau *deadlock*. Ini membuat proses *debugging* lebih mudah. Namun, kekurangannya cukup signifikan terutama dalam hal performa dan efisiensi karena tidak dapat memanfaatkan kemampuan prosesor modern yang memiliki banyak inti (*cores*).

### Multithread

Sebaliknya, *multithreading* adalah pendekatan di mana sebuah program dapat membuat dan menjalankan beberapa thread secara bersamaan (paralel atau semi-paralel). Setiap thread dapat menjalankan bagian berbeda dari program pada waktu yang sama. Contohnya, dalam aplikasi web server, satu thread bisa menangani permintaan pengguna pertama, sementara thread lain melayani pengguna kedua. Ini membuat program menjadi lebih cepat, efisien, dan responsif.

Multithreading sangat bermanfaat dalam aplikasi seperti game, pemrosesan data besar, dan aplikasi real-time. Namun, juga menimbulkan tantangan seperti *race condition* dan *deadlock*. Untuk itu dibutuhkan teknik sinkronisasi seperti `mutex`, `semaphore`, atau `lock`.

---

# Programming Exercise

## a. Penerapan Thread pada `SumTask.java`

Langkah:

1. Cek instalasi JDK:
   ```bash
   java -version
   javac -version
   ```
2. Buat folder dan file:
   ```bash
   D:
   cd D:/Java
   ```
3. Kompilasi:
   ```bash
   javac SumTask.java
   java SumTask
   ```

### Penjelasan

Program `SumTask.java` menunjukkan bagaimana Java menjalankan *thread* untuk menghitung total secara paralel. Setelah JDK terinstal, file Java dikompilasi dan dijalankan. Output menunjukkan proses multithread berjalan bersamaan dengan program utama.

## b. Penerapan `thrd-posix.c` di Linux

Langkah:

1. Buat file:
   ```bash
   nano thrd-posix.c
   ```
2. Masukkan kode, lalu kompilasi:
   ```bash
   gcc thrd-posix.c -o thrd-posix -pthread
   ./thrd-posix 10
   ```

### Penjelasan

Program menghitung jumlah 1 hingga n. Menggunakan pustaka POSIX thread (`pthread`), proses dijalankan paralel dengan thread tambahan untuk efisiensi.

## c. Penerapan `thrd-win32.c` di Windows

Langkah:

1. Clone repo:
   ```bash
   git clone https://github.com/ferryastika/osc10e.git
   cd osc10e/ch4
   ```
2. Kompilasi dan jalankan:
   ```bash
   gcc thrd-win32.c -o thrd-win32.exe
   .\thrd-win32.exe 4
   ```

### Penjelasan

Program menghitung jumlah dari 1 sampai 4 menggunakan *Windows thread*. Perintah di atas menghasilkan output dari eksekusi thread.

---

# Evolusi Teknologi Processor Intel

> Gunakan referensi: [YouTube Video](https://www.youtube.com/watch?v=PT787d9odKk)

Silakan buat presentasi (PPT) berdasarkan video tersebut, meliputi:
- Tahun rilis prosesor
- Teknologi utama
- Evolusi arsitektur
- Performa dan efisiensi daya

---

# Exercise Chapter 4

### 1. Contoh Multithreading vs Single-threaded

- **Web Server**: Menangani banyak klien secara paralel.
- **Pengolahan Gambar**: Paralelisasi per-area.
- **Kompresi File**: Memproses blok file secara bersamaan.

### 2. Amdahl’s Law

Rumus:
```
Speedup = 1 / ( (1 - P) + P / N )
```

Dengan `P = 0.6`:

a) Dua core:
```
Speedup = 1 / (0.4 + 0.3) ≈ 1.43
```

b) Empat core:
```
Speedup = 1 / (0.4 + 0.15) ≈ 1.82
```

### 3. Web Server: Task vs Data Parallelism

Jawaban: **Task Parallelism**, karena setiap thread menangani tugas berbeda (permintaan klien berbeda).

### 4. User-level Threads vs Kernel-level Threads

| Aspek | User-Level | Kernel-Level |
|-------|------------|--------------|
| Pengelolaan | Library user-space | Kernel |
| Kecepatan switching | Cepat | Lebih lambat |

**User-level lebih baik** untuk switching cepat.  
**Kernel-level lebih baik** saat terjadi blocking I/O.

### 5. Kernel Context-Switch (Kernel Threads)

- Simpan konteks thread lama.
- Perbarui scheduler.
- Muat konteks thread baru.
- Atur program counter.
- Lanjutkan eksekusi.
