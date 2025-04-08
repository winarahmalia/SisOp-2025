# Sistem Operasi

## Tugas Minggu ke-6

### Nama: Wina Rahmalia  
### NRP: 3124500052  
### Dosen Pengajar: Ferry Astika Saputra  

### PROGRAM STUDI D3 TEKNIK INFORMATIKA  
### POLITEKNIK ELEKTRONIKA NEGERI SURABAYA (PENS)  
### TAHUN 2024  

---

## Compile Thread 3

```c
#include <stdio.h>
#include <pthread.h>

pthread_cond_t cond1 = PTHREAD_COND_INITIALIZER;
pthread_cond_t cond2 = PTHREAD_COND_INITIALIZER;
pthread_cond_t cond3 = PTHREAD_COND_INITIALIZER;
pthread_mutex_t lock = PTHREAD_MUTEX_INITIALIZER;
int done = 1;

void *foo(void *arg) {
    int thread_num = *(int *)arg;
    while (1) {
        pthread_mutex_lock(&lock);
        while (done != thread_num) {
            if (thread_num == 1) {
                pthread_cond_wait(&cond1, &lock);
            } else if (thread_num == 2) {
                pthread_cond_wait(&cond2, &lock);
            } else {
                pthread_cond_wait(&cond3, &lock);
            }
        }

        printf("%d ", thread_num);
        fflush(stdout);

        if (done == 3) {
            done = 1;
            pthread_cond_signal(&cond1);
        } else if (done == 1) {
            done = 2;
            pthread_cond_signal(&cond2);
        } else if (done == 2) {
            done = 3;
            pthread_cond_signal(&cond3);
        }

        pthread_mutex_unlock(&lock);
    }

    return NULL;
}

int main() {
    pthread_t tid1, tid2, tid3;
    int n1 = 1, n2 = 2, n3 = 3;

    pthread_create(&tid1, NULL, foo, &n1);
    pthread_create(&tid2, NULL, foo, &n2);
    pthread_create(&tid3, NULL, foo, &n3);

    pthread_join(tid1, NULL);
    pthread_join(tid2, NULL);
    pthread_join(tid3, NULL);

    return 0;
}
```

### Cara Menjalankan Kode:
1. Buka terminal Linux.
2. Ketik perintah `nano 123.c` untuk memasukkan kode ke dalam file `123.c`.
3. Simpan dengan `Ctrl+X`, lalu tekan `Y` dan `Enter` untuk kembali ke terminal.
4. Compile menggunakan perintah `gcc -pthread 123.c -o 123`.
5. Jalankan dengan perintah `./123`.

Output dari program ini adalah:
```
123123123... (terus berjalan hingga dihentikan dengan Ctrl+C)
```

### Analisa:
Program ini menggunakan **multithreading** dengan **mutex** dan **condition variable** untuk sinkronisasi antara tiga thread yang bergantian mencetak angka mereka.

---

## Forking

**Forking** adalah proses dalam sistem operasi yang digunakan untuk membuat salinan dari proses yang sedang berjalan. Forking memungkinkan satu proses menjadi dua, yaitu **parent process** dan **child process**.

### Contoh Kode Forking:
```c
#include <stdio.h>
#include <unistd.h>
#include <sys/types.h>

int main() {
    pid_t pid = fork(); 

    if (pid < 0) {
        perror("Fork gagal");
        return 1;
    }

    if (pid == 0) {
        printf("Ini adalah proses anak dengan PID: %d
", getpid());
    } else {
        printf("Ini adalah proses induk dengan PID: %d, dan PID anak: %d
", getpid(), pid);
    }    

    return 0;
}
```

### Analisa Kode:
- **`fork()`** digunakan untuk membuat proses anak.
- Jika **`pid < 0`**, fork gagal.
- Jika **`pid == 0`**, proses anak berjalan.
- Jika **`pid > 0`**, proses induk berjalan dan mengetahui PID anak.

Ketika dijalankan, hasilnya bisa seperti ini:
```
Ini adalah proses induk dengan PID: 1234, dan PID anak: 1235
Ini adalah proses anak dengan PID: 1235
```

---

## Manfaat Time Quantum Berbeda dalam Multilevel Queue:

1. **Optimasi Penggunaan CPU**:  
   - Proses cepat mendapatkan time quantum kecil untuk respons cepat.
   - Proses panjang mendapatkan time quantum besar untuk mengurangi switching.

2. **Meningkatkan Responsifitas**:  
   - Proses interaktif mendapat prioritas tinggi dengan time quantum kecil.

3. **Mengurangi Overhead Switching**:  
   - Proses panjang bisa berjalan lebih lama tanpa sering berpindah.

4. **Menyeimbangkan Beban Kerja**:  
   - Proses cepat selesai lebih dulu, proses batch dieksekusi di level lebih rendah.

---

## Diagram Eksekusi Proses dengan Berbagai Algoritma Penjadwalan

| Proses | Burst Time | Prioritas |
|--------|-----------|----------|
| P1     | 10        | 3        |
| P2     | 1         | 1        |
| P3     | 2         | 2        |
| P4     | 1         | 4        |
| P5     | 5         | 2        |

1. **First Come First Serve (FCFS)**
```
| P1 | P2 | P3 | P4 | P5 |
0    10   11   13   14   19
```

2. **Shortest Job First (SJF) - Non-preemptive**
```
| P2 | P4 | P3 | P5 | P1 |
0    1    2    4    9    19
```

3. **Prioritas Non-preemptive**
```
| P2 | P3 | P5 | P1 | P4 |
0    1    3    8   18   19
```

4. **Round Robin (Quantum = 2)**
```
| P1 | P2 | P3 | P5 | P1 | P4 | P5 | P1 | P1 |
0    2    3    5    7    9    10   12   14   16   18   19
```

---

**Selesai** ✅

