
LAPORAN SISTEM OPERASI
TUGAS CODING UNTUK SJF DAN SRTF
 


 

 
Disusun oleh:
Fandra Salsabilla Oktorasari (3124500040)
Wina Rahmalia   (3124500052)
Virda Septina Putri  (3124500058)
Dosen Pengajar  	: Dr Ferry Astika Saputra ST, M.Sc
 
 
PROGRAM STUDI D3 TEKNIK INFORMATIKA
POLITEKNIK ELEKTRONIKA NEGERI SURABAYA (PENS)
TAHUN 2025

SJS Sceduling Without Arrival Time


Penjelasan:
Non-Preemptive → setelah suatu proses memulai dieksekusi maka tidak akan di hentikan hingga selesai.
 Karena tidak ada waktu kedatangan maka semua proses akan dianggap tiba secara bersamaan 
Langkah langkah:
P4 (BT=1) → Paling kecil → jalan pertama kali.
P2 (BT=3) dan P5(BT=3) →  tie(sama besar), urutan bisa berdasarkan input (P2 terlebih dahulu).
P5(BT=3)
P3(BT=4)
P1(BT=7) → paling terakhir.
Completion Time(CT): Waktu saat proses selesai dieksekusi.
Turnaround Time = (1+4+7+11+18)/5=8.2
Waiting Time = (0+1+4+7+11)/5=4.6

Algoritma SJF Non-Preemptive menghasilkan waktu tunggu dan turnaund time yang optimal jika arrival time tidak dipertimbangkan. Jika banyak proses kecil datang terlambat maka harus menunggu, sehingga SJF dapat menyebabkan starvation untuk proses dengan burst time besar.

SJF Scheduling Algorithms With Arrival Time


Penjelasan:
P3 (AT=0, BT=3)
Selesai pada waktu 3 (CT=3)
TAT = 3-0 = 3
Witing time = 0
Proses setelah P3 (Waktu = 3)
P1 (AT = 2), P2 (AT = 1), P4 (AT = belum tiba)
Memilih proses dengan BT terkecil antara P1 (BT=5) dan P2 (BT=6)
P1 dieksekusi
Selesai pada waktu 8 (CT = 3+5 = 8)
TAT = 8-2 = 6
Waiting time = 6-5 = 1 
Proses berikutnya dengan waktu = 8
P2 (AT = 1), P4 (AT = 5), P5 (AT = 8)
Memilih proses dengan BT terkecil: P4 (BT = 4)
Selesai pada waktu 12 (CT = 8+4 = 12)
TAT = 12 -5 = 7
Waiting time = 7-4 = 3
Proses berikutnya dengan waktu = 12
P2 (BT = 6), P5 (BT = 7)
Pilih P2 (BT=6)
Selesai pada waktu 18 (CT = 12+6 = 18)
TAT = 18-1 = 17
Waiting time = 17 - 6 = 11
Proses terakhir dengan waktu = 18
P5 (BT = 7)
Selesai pada waktu 25 (CT = 18+7 = 25)
TAT = 25 - 8 = 17
Waiting time = 17 - 7 = 10


SRTF Scheduling Algorithms

Data Awal
AT = waktu kedatangan proses
BT = lama eksekusi proses
Timeline Eksekusi
Kita susun langkah demi langkah pada setiap waktu diskrit:



Diagram Gantt (ASCII)

0–2: P1
2–5: P2
5–6: P4
6–10: P1 (lanjutan)
10–12: P5
12–21: P3

Perhitungan Metrik
Completion Time (CT)
Waktu saat proses benar-benar selesai dieksekusi.



Turnaround Time (TAT)
TAT=CT−AT

Waiting Time (WT)
WT=TAT−BT
Rata-Rata
Average Turnaround Time (Rata-rata TAT)
(10 + 3 + 15 + 2 + 4)/5 = 34/5 = 6,8

Average Waiting Time (Rata-rata WT)
(4 + 0 + 6 + 1 + 2)/5 = 13/5 = 2,6

Catatan
Idealnya pada waktu 8 proses P5 (BT=2) memiliki sisa waktu lebih pendek daripada P1 (sisa=3), sehingga seharusnya P1 di-preempt dan P5 dijalankan terlebih dahulu. Namun hasil simulasi menunjukkan P1 tetap berjalan hingga selesai—mungkin karena implementasi hanya memeriksa preemption pada momen kedatangan terjadinya proses baru, bukan secara terus-menerus.

Jika dioptimalkan sepenuhnya, urutan setelah t=8 akan menjadi P5 → P1, yang akan menurunkan sedikit average waiting time.


