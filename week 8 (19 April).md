
# 1. Jelaskan dalam 2 pargraph disertai dengan gambar tentang konsep single thread dan multithread!

### Single Thread

Konsep *single thread* mengacu pada model eksekusi di mana hanya terdapat satu thread (utas) yang menangani seluruh tugas dari awal hingga akhir dalam suatu program. Thread adalah unit terkecil dari pemrosesan yang dapat dijadwalkan oleh sistem operasi. Dalam sistem *single-threaded*, semua instruksi diproses secara berurutan. Jika terdapat operasi yang memakan waktu lama, maka seluruh program akan berhenti sejenak menunggu operasi tersebut selesai, baru kemudian melanjutkan ke langkah berikutnya.

Kelebihan dari *single thread* adalah kesederhanaannya. Karena hanya ada satu jalur eksekusi, tidak ada risiko konflik antar thread seperti *race condition* atau *deadlock*. Ini membuat proses *debugging* lebih mudah. Namun, kekurangannya cukup signifikan terutama dalam hal performa dan efisiensi karena tidak dapat memanfaatkan kemampuan prosesor modern yang memiliki banyak inti (*cores*).
![image](https://github.com/user-attachments/assets/cb3416ba-a914-4c91-be60-21148575448d)

### Multithread

Sebaliknya, *multithreading* adalah pendekatan di mana sebuah program dapat membuat dan menjalankan beberapa thread secara bersamaan (paralel atau semi-paralel). Setiap thread dapat menjalankan bagian berbeda dari program pada waktu yang sama. Contohnya, dalam aplikasi web server, satu thread bisa menangani permintaan pengguna pertama, sementara thread lain melayani pengguna kedua. Ini membuat program menjadi lebih cepat, efisien, dan responsif.

Multithreading sangat bermanfaat dalam aplikasi seperti game, pemrosesan data besar, dan aplikasi real-time. Namun, juga menimbulkan tantangan seperti *race condition* dan *deadlock*. Untuk itu dibutuhkan teknik sinkronisasi seperti `mutex`, `semaphore`, atau `lock`.
![image](https://github.com/user-attachments/assets/ad5200e2-8b47-41e8-9ca3-bba2c9ffea9a)

---

# 2.	Kerjakan Programming Exercise a. Penerapan thread pada contoh SumTask.java b. penerapan Thread di Linux (thrd-posix.c) dan penerapan thread di Microsoft Windows (thrd-win32.c) . Beri penjelasan dalam bentuk esay. Gunakan Link 
**Referensi:**  
[https://github.com/ferryastika/osc10e/tree/master/ch4](https://github.com/ferryastika/osc10e/tree/master/ch4)
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

![image](https://github.com/user-attachments/assets/0f64001a-d5b6-4e12-9e2c-aa6e87de851b)

### Penjelasan dalam bentuk esay:

Thread adalah bagian dari program yang memungkinkan beberapa proses berjalan secara paralel dalam satu aplikasi. Java menyediakan fitur multithreading yang sangat efisien, dan salah satu contoh penerapannya dapat dilihat dalam program SumTask.java.

Sebelum menjalankan program tersebut, langkah awal yang perlu dilakukan adalah memastikan bahwa Java Development Kit (JDK) telah terinstal pada sistem. Hal ini bisa dicek melalui Command Prompt dengan mengetikkan perintah java -version dan javac -version. Jika keduanya berhasil menampilkan versi yang terinstal, maka JDK sudah siap digunakan.

Langkah berikutnya adalah membuat file SumTask.java. File ini bisa diletakkan di direktori mana saja, misalnya di D:/Java. Untuk membuatnya, pengguna perlu masuk ke direktori tersebut melalui Command Prompt menggunakan perintah D: lalu cd D:/Java.

Setelah berada di dalam direktori tujuan, pengguna bisa menuliskan kode program ke dalam file SumTask.java sesuai isi dari contoh ch4/SumTask.java. Setelah file selesai ditulis, program perlu dikompilasi menggunakan perintah javac SumTask.java. Jika tidak ada kesalahan dalam kode, proses kompilasi akan menghasilkan file bytecode SumTask.class.

Langkah terakhir adalah menjalankan program tersebut dengan perintah java SumTask. Hasil dari program akan menampilkan output dari proses yang dijalankan oleh thread. Ini menunjukkan bahwa Java mampu menjalankan proses dalam thread terpisah yang berjalan secara paralel dengan program utama, sebuah konsep dasar dari multithreading.


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
![image](https://github.com/user-attachments/assets/167c1a88-4a3c-4345-bc37-4417ef780cc6)

### Penjelasan dalam bentuk esay:

Untuk mempraktikkan multithreading di Linux, pengguna dapat membuat file program bernama thrd-posix.c. Proses pertama yang dilakukan adalah membuat file C baru menggunakan teks editor di terminal, misalnya dengan perintah:
bash
Copy code
nano thrd-posix.c
Setelah itu, pengguna akan masuk ke editor nano, dan dapat menuliskan atau menyalin kode program dari thrd-posix.c. Kode ini biasanya berisi fungsi main yang membuat thread baru, serta fungsi runner() yang akan dijalankan oleh thread tersebut untuk menghitung jumlah bilangan bulat dari 1 hingga angka yang diberikan sebagai argumen.
Setelah selesai menulis kode, file disimpan dan ditutup. Langkah berikutnya adalah melakukan proses kompilasi. Karena program menggunakan fitur thread POSIX, maka diperlukan flag tambahan -pthread saat melakukan kompilasi menggunakan gcc:
bash
Copy code
gcc thrd-posix.c -o thrd-posix -pthread
Perintah ini akan menghasilkan file output bernama thrd-posix yang dapat dieksekusi. Flag -pthread digunakan untuk memberi tahu compiler dan linker agar menyertakan pustaka pthread yang diperlukan agar fungsi thread bisa digunakan.
Setelah program berhasil dikompilasi, pengguna dapat menjalankan program dengan perintah:
bash
Copy code
./thrd-posix 5
Argumen 5 di sini berarti program akan menghitung jumlah dari angka 1 hingga 5, dan mencetak hasilnya di terminal, seperti sum = 15.


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

![image](https://github.com/user-attachments/assets/54dcad94-1af5-44a7-a2c6-08c21202e896)

### Penjelasan dalam bentuk esay:

Langkah pertama dalam proses ini adalah mengunduh repository dari GitHub menggunakan perintah git clone https://github.com/ferryastika/osc10e.git. Perintah ini akan menyalin seluruh isi repository ke dalam folder lokal bernama osc10e. Setelah selesai, pengguna berpindah ke direktori osc10e dan selanjutnya ke dalam subdirektori ch4, yang berisi file kode program thrd-win32.c.

Selanjutnya, file thrd-win32.c dikompilasi menggunakan GCC (GNU Compiler Collection) dengan perintah gcc thrd-win32.c -o thrd-win32.exe. Perintah ini akan mengubah file kode sumber .c menjadi file executable .exe yang dapat dijalankan di sistem operasi Windows.

Setelah proses kompilasi selesai tanpa error, program dijalankan menggunakan perintah .\thrd-win32.exe 4. Angka 4 di sini merupakan argumen yang diteruskan ke program. Program ini kemudian akan menjalankan thread yang menghitung penjumlahan dari angka 1 sampai 4, dan mencetak hasilnya ke layar, yaitu sum = 10.


---

# 3.	Buat PPT tentang evolusi teknilogi processor Intel dengan menggunakan 
> Gunakan referensi: [YouTube Video](https://www.youtube.com/watch?v=PT787d9odKk)


---

# 4.	Jawab pertanyaan exercise pada chater 4 !

### 4.1. Contoh Multithreading vs Single-threaded

- **Web Server**: Menangani banyak klien secara paralel.
- **Pengolahan Gambar**: Paralelisasi per-area.
- **Kompresi File**: Memproses blok file secara bersamaan.

### 4.2. Amdahl’s Law

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

### 4.3. Web Server: Task vs Data Parallelism

Jawaban: **Task Parallelism**, karena setiap thread menangani tugas berbeda (permintaan klien berbeda).

### 4.4. User-level Threads vs Kernel-level Threads

| Aspek | User-Level | Kernel-Level |
|-------|------------|--------------|
| Pengelolaan | Library user-space | Kernel |
| Kecepatan switching | Cepat | Lebih lambat |

**User-level lebih baik** untuk switching cepat.  
**Kernel-level lebih baik** saat terjadi blocking I/O.

### 4.5. Kernel Context-Switch (Kernel Threads)

- Simpan konteks thread lama.
- Perbarui scheduler.
- Muat konteks thread baru.
- Atur program counter.
- Lanjutkan eksekusi.
