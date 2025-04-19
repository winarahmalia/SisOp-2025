Jelaskan dalam 2 pargraph disertai dengan gambar tentang konsep single thread dan multithread!
Jawaban:

 Konsep single thread mengacu pada model eksekusi Dimana hanya terdapat satu thread(utas) yang menangani seluruh tugas dari awal hingga akhir dalam suati program. Thread adalah unit terkecil dari pemrosesan yang dapat dijadwalkan oleh system operasi. Dalam system single -threaded, semua intruksi diproses secara berurutan, dari atas ke bawah.Jadi, jika terdapat operasi yang memakan waktu lama makaseluruh program akan berhenti sejenak menunh=ggu operasi tersebut selesai, baru melanjutkan ke langkah berikutnya.

 Kelebihan dari single thread adalah kesederhanaan. Karena hanya ada satu jalur ekseskusi, kita tidak perlu khawatir tentang konflik antar thread seperti race condition atau deadlock. Ini membuat debugging menjadi lebih mudah. Namun, kekurangannya cukup signifikan , terutama pada performa dan efisiensi. Pada prosesor modern yang memiliki banyak core, program single-threaded tidak bisa memanfaatkan kemampuan komputasi parallel secara optimal.



 Sebaliknya, multithreading adalah pendekatan di mana sebuah program dapat membuat dan menjalankan beberapa thread secara bersamaan (paralel atau semi-paralel). Setiap thread dapat menjalankan bagian berbeda dari program pada waktu yang sama. Contohnya, dalam sebuah aplikasi web server, satu thread bisa menangani permintaan dari pengguna pertama, sementara thread lain melayani pengguna kedua. Ini membuat program menjadi lebih cepat, efisien, dan responsif, karena beberapa pekerjaan bisa dilakukan secara paralel, tanpa harus menunggu pekerjaan lain selesai terlebih dahulu.

 Multithreading sangat bermanfaat dalam berbagai aplikasi seperti game, pemrosesan data besar, aplikasi real-time, dan server. Namun, multithreading juga membawa tantangan baru. Karena thread berbagi memori dan sumber daya yang sama, pengembang harus berhati-hati untuk mencegah race condition (dua thread mengakses dan mengubah data yang sama secara bersamaan) dan deadlock (dua atau lebih thread saling menunggu satu sama lain sehingga tidak ada yang bisa melanjutkan). Untuk itu, diperlukan teknik sinkronisasi seperti mutex, semaphore, atau lock.




Kerjakan Programming Exercise a. Penerapan thread pada contoh SumTask.java b. penerapan Thread di Linux (thrd-posix.c) dan penerapan thread di Microsoft Windows (thrd-win32.c) . Beri penjelasan dalam bentuk esay. Gunakan Link 

Penerapan thread pada contoh SumTask.java 

Untuk menjalankan ch4/SumTask.java pertama cek instalasi JDK (Java development Kit) dengan cara ketik perintah pada command promt:

java -version
javac -version

jika tidak terjadi error dan mengeluarkan versi java berarti JDK telah terinstall.
Setelah terintall lanjut membuat file java dan letakkan ke Alamat yang di inginkan seperti D:/Java.
Untuk ingin memasuki Alamat D:/Java gunakan perintah:

D:
Cd D:/Java

Setelah memasuki alamat cd D:/Java buat file SumTask.java dengan perintah:

Javac SumTask.jave

setelah itu isi file dengan code yang sesuai pada ch4/SumTask.java.

Untuk menjalankan hasil code pada file SumTask.java dengan menggunakan perintah:

Java SumTask.java

Gambar diatas merupakan hasil dari thread pada contoh SumTask.java
 penjelasan dalam bentuk esay:

Thread adalah bagian dari program yang memungkinkan beberapa proses berjalan secara paralel dalam satu aplikasi. Java menyediakan fitur multithreading yang sangat efisien, dan salah satu contoh penerapannya dapat dilihat dalam program SumTask.java.

Sebelum menjalankan program tersebut, langkah awal yang perlu dilakukan adalah memastikan bahwa Java Development Kit (JDK) telah terinstal pada sistem. Hal ini bisa dicek melalui Command Prompt dengan mengetikkan perintah java -version dan javac -version. Jika keduanya berhasil menampilkan versi yang terinstal, maka JDK sudah siap digunakan.

Langkah berikutnya adalah membuat file SumTask.java. File ini bisa diletakkan di direktori mana saja, misalnya di D:/Java. Untuk membuatnya, pengguna perlu masuk ke direktori tersebut melalui Command Prompt menggunakan perintah D: lalu cd D:/Java.

Setelah berada di dalam direktori tujuan, pengguna bisa menuliskan kode program ke dalam file SumTask.java sesuai isi dari contoh ch4/SumTask.java. Setelah file selesai ditulis, program perlu dikompilasi menggunakan perintah javac SumTask.java. Jika tidak ada kesalahan dalam kode, proses kompilasi akan menghasilkan file bytecode SumTask.class.

Langkah terakhir adalah menjalankan program tersebut dengan perintah java SumTask. Hasil dari program akan menampilkan output dari proses yang dijalankan oleh thread. Ini menunjukkan bahwa Java mampu menjalankan proses dalam thread terpisah yang berjalan secara paralel dengan program utama, sebuah konsep dasar dari multithreading.


 penerapan Thread di Linux (thrd-posix.c)
Untuk menerapkan (thrd-posix.c) di Linux yang pertama buat file dengan perintah:

nano thread-posfix.c

lalu masukkan code thrd-posix.c kedalam file thrd-posix.c.
lalu compile manggunakan perintah:

gcc thred-posix.c -o thrs-posix -pthread

untuk menjalankannya gunakan perintah ./thrd-posix 

Code diatas merupakan hasil dari perintah yang telah dijelaskan sebelumnya, mengapa jika mengunakan perintah ./thrd-posix 10 hasil outputnya adalah sum = 55? Karena code pada thrd-posix.c brfungsi untuk meghitung menhitung jumlah 1 sampai n(1+2+3+4+5+6+7+8+9+10).

 penjelasan dalam bentuk esay:

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


penerapan thread di Microsoft Windows (thrd-win32.c) 
penerapan thread di Microsoft Windows hamper sama dengan menerapkan thread pada linux yaitu dengan, tetapi saya akan mengclone link yang telah disediakan. Jadi lebih simple tanpa membuat file dan memindah code.

Yang dapat dilakukan yang pertama adalah clone repository dari github dengan cara menjalankan perintah di bawah pada command promt:

git clone 

lalu masuk ke folder program

cd osc10e
cd ch4

compale dengan menggunakan perintah

gcc thrd-win32.c -o thrd-win32.exe

setelah selesai jalankan perintah 

.\thrd-win32.exe 4

Gambar diatas merupakan hasil dari langkah langkah yang sudah dijelaskan sebelumnya.
 
penjelasan dalam bentuk esay:

Langkah pertama dalam proses ini adalah mengunduh repository dari GitHub menggunakan perintah git clone https://github.com/ferryastika/osc10e.git. Perintah ini akan menyalin seluruh isi repository ke dalam folder lokal bernama osc10e. Setelah selesai, pengguna berpindah ke direktori osc10e dan selanjutnya ke dalam subdirektori ch4, yang berisi file kode program thrd-win32.c.

Selanjutnya, file thrd-win32.c dikompilasi menggunakan GCC (GNU Compiler Collection) dengan perintah gcc thrd-win32.c -o thrd-win32.exe. Perintah ini akan mengubah file kode sumber .c menjadi file executable .exe yang dapat dijalankan di sistem operasi Windows.

Setelah proses kompilasi selesai tanpa error, program dijalankan menggunakan perintah .\thrd-win32.exe 4. Angka 4 di sini merupakan argumen yang diteruskan ke program. Program ini kemudian akan menjalankan thread yang menghitung penjumlahan dari angka 1 sampai 4, dan mencetak hasilnya ke layar, yaitu sum = 10.


Buat PPT tentang evolusi teknilogi processor Intel dengan menggunakan referensi : 


Jawab pertanyaan exercise pada chater 4 !
Provide three programming examples in which multithreading provides better performance than a single-threaded solution.

Tiga contoh pemrograman Dimana multithreding memberikan peforma lebih baik disbanding Solusi single-threaded:
 Web server: Permintaan client dapat ditangani oleh thread yang berbeda. Ini meningkatkan performa dan throughput secara signifikan karena banyak koneksi yang dapat diproses secara parallel.
Pengolaan gambar:Operasi seperti filter atau transformasi pada gambar besar dapat dibagi ke beberapa thread berdasarkan area gambar yang diproses.
Kompresi file:File besar dapat dipecah ke beberapa begian dan masing masing bagian dikompresi oleh thread yang berbeda secara parallel.


Using Amdahl’s Law, calculate the speedup gain of an application that has a 60 percent parallel component for (a) two processing cores and (b) four processing cores

Rumus Amdahl’s Law:
Speedup=1(1−P)+PN\text{Speedup} = \frac{1}{(1 - P) + \frac{P}{N}}Speedup=(1−P)+NP​1​ 
dengan:
P=0.6P = 0.6P=0.6 (60% dari program dapat diparalelkan),
N=N =N= jumlah core.

a) Dua core:
Speedup=1(1−0.6)+0.62=10.4+0.3=10.7≈1.43\text{Speedup} = \frac{1}{(1 -0.6) + \frac{0.6}{2}} = \frac{1}{0.4 + 0.3} = \frac{1}{0.7} \approx1.43Speedup=(1−0.6)+20.6​1​=0.4+0.31​=0.71​≈1.43 

b) Empat core:
Speedup=1(1−0.6)+0.64=10.4+0.15=10.55≈1.82\text{Speedup} = \frac{1}{(1 - 0.6) + \frac{0.6}{4}} = \frac{1}{0.4 + 0.15} = \frac{1}{0.55} \approx 1.82Speedup=(1−0.6)+40.6​1​=0.4+0.151​=0.551​≈1.82 




Does the multithreaded web server described in Section 4.1 exhibit task or data parallelism?
web server multithreaded pada Section 4.1 menunjukkan task Parallelism, karena setiap thread menagani permintaan klien yang berbeda/berbagai tugas, bukan data yang sama dibagi-bagi untuk diproses secara paralel.


What are two differences between user-level threads and kernel-level threads? Under what circumstances is one type better than the other?

User-level akan lebih baik Ketika switching antar thread sangat sering dan tidak perlu melibatkan kernel.

Kernel-level lebih baik saat terjadi blocking I/O, karena kernel bisa menjadwalkan thread lain saat satu thread diblok.
 

Describe the actions taken by a kernel to context-switch between kernel-level threads. 
Menyimpan konteks (register, program counter, stack pointer) dari thread yang sedang berjalan.
Memperbarui data struktur scheduler.
Memuat konteks dari thread yang akan dijalankan berikutnya.
Mengatur program counter ke posisi terakhir thread tersebut.
Melanjutkan eksekusi dari thread yang baru dijadwalkan.

 



 



