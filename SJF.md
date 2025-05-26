# LAPORAN SISTEM OPERASI

## TUGAS CODING UNTUK SJF DAN SRTF

**Disusun oleh:**

- Fandra Salsabilla Oktorasari (3124500040)  
- Wina Rahmalia (3124500052)  
- Virda Septina Putri (3124500058)

**Dosen Pengajar:** Dr Ferry Astika Saputra ST, M.Sc

**PROGRAM STUDI D3 TEKNIK INFORMATIKA**  
**POLITEKNIK ELEKTRONIKA NEGERI SURABAYA (PENS)**  
**TAHUN 2025**

---

## SJF Scheduling Without Arrival Time

![image](https://github.com/user-attachments/assets/0cc44ecb-9ab5-43e8-a073-42f8b7c19c67)

![image](https://github.com/user-attachments/assets/791a5dc3-d21d-47ce-a5b2-39a8689b672f)


### Penjelasan:
- **Non-Preemptive** → Setelah suatu proses mulai dieksekusi, maka tidak akan dihentikan hingga selesai.
- Karena tidak ada waktu kedatangan (arrival time), maka semua proses dianggap tiba secara bersamaan.

### Langkah-langkah:
1. P4 (BT=1) → paling kecil → jalan pertama.
2. P2 (BT=3) dan P5 (BT=3) → tie (sama besar), urutan berdasarkan input (P2 duluan).
3. P5 (BT=3)
4. P3 (BT=4)
5. P1 (BT=7) → terakhir.

### Waktu Eksekusi:
- Completion Time (CT): waktu saat proses selesai dieksekusi.
- Turnaround Time (TAT): (1 + 4 + 7 + 11 + 18) / 5 = **8.2**
- Waiting Time (WT): (0 + 1 + 4 + 7 + 11) / 5 = **4.6**

**Catatan:**  
Algoritma SJF Non-Preemptive memberikan waktu tunggu dan turnaround time yang optimal jika arrival time tidak diperhitungkan. Namun, jika proses kecil datang terlambat, maka proses besar harus menunggu lebih lama, sehingga **SJF dapat menyebabkan starvation**.

---

## SJF Scheduling With Arrival Time

![image](https://github.com/user-attachments/assets/673e3a8b-1faf-4e2a-8f1f-c2f593d6dba3)

![image](https://github.com/user-attachments/assets/051606d9-f7d2-4c69-a969-4f9176386cf8)


### Proses dan Eksekusi:
- **P3 (AT=0, BT=3)** → CT = 3, TAT = 3, WT = 0  
- Proses selanjutnya: P1 (AT=2), P2 (AT=1)  
  - P1 (BT=5) vs P2 (BT=6) → Pilih P1  
  - CT = 8, TAT = 6, WT = 1  
- Berikutnya: P2 (AT=1), P4 (AT=5), P5 (AT=8)  
  - Pilih P4 (BT=4) → CT = 12, TAT = 7, WT = 3  
- Selanjutnya: P2 (BT=6), P5 (BT=7)  
  - Pilih P2 → CT = 18, TAT = 17, WT = 11  
- Terakhir: P5 → CT = 25, TAT = 17, WT = 10

---

## SRTF Scheduling Algorithm

![image](https://github.com/user-attachments/assets/895cdbef-347e-44f1-9fa2-d78d72d55a5d)

### Data Awal:

| Proses | AT | BT |
|--------|----|----|
| P1     | 0  | 6  |
| P2     | 2  | 3  |
| P3     | 6  | 9  |
| P4     | 4  | 1  |
| P5     | 8  | 2  |

### Timeline Eksekusi:

| Waktu | Proses Berjalan | Keterangan |
|-------|------------------|------------|
| 0     | P1               | Hanya P1 hadir |
| 2     | P2               | BT < sisa P1, preempt |
| 5     | P4               | BT=1, lebih kecil dari sisa P1 |
| 6     | P1               | P3 datang, tapi P1 lebih pendek |
| 8     | P1               | P5 datang, seharusnya preempt P1 |
| 10    | P5               | Jalankan P5 (BT=2) |
| 12    | P3               | Sisa proses |

### Diagram Gantt:
0–2: P1
2–5: P2
5–6: P4
6–10: P1
10–12: P5
12–21: P3


### Perhitungan Metrik:
![WhatsApp Image 2025-05-26 at 13 36 38_3a8cc9ad](https://github.com/user-attachments/assets/00dc7f03-1e41-400c-9b36-516ddad5f59c)

#### Completion Time (CT):

| Proses | CT  |
|--------|-----|
| P1     | 10  |
| P2     | 5   |
| P3     | 21  |
| P4     | 6   |
| P5     | 12  |

#### Turnaround Time (TAT):

| Proses | AT | CT | TAT = CT–AT |
|--------|----|----|-------------|
| P1     | 0  | 10 | 10          |
| P2     | 2  | 5  | 3           |
| P3     | 6  | 21 | 15          |
| P4     | 4  | 6  | 2           |
| P5     | 8  | 12 | 4           |

#### Waiting Time (WT):

| Proses | TAT | BT | WT = TAT–BT |
|--------|-----|----|-------------|
| P1     | 10  | 6  | 4           |
| P2     | 3   | 3  | 0           |
| P3     | 15  | 9  | 6           |
| P4     | 2   | 1  | 1           |
| P5     | 4   | 2  | 2           |

### Rata-Rata:
- **Average TAT** = 34 / 5 = **6.8**
- **Average WT** = 13 / 5 = **2.6**

### Catatan:
Idealnya, pada waktu 8 proses P5 (BT=2) memiliki sisa waktu lebih pendek dibanding P1 (sisa=3), sehingga **P1 seharusnya di-preempt dan P5 dijalankan terlebih dahulu**. Namun dalam simulasi, P1 tetap berjalan—kemungkinan karena implementasi hanya memeriksa preemption saat proses datang, bukan secara terus-menerus.

Jika dioptimalkan, urutan setelah t=8 akan menjadi **P5 → P1**, yang sedikit menurunkan average waiting time.
