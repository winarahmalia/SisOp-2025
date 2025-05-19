# SJF Scheduling Without Arrival Time

![image](https://github.com/user-attachments/assets/24b16433-cbdf-4190-a282-4c5488f5e78a)

## Penjelasan:
- **Non-Preemptive** → Setelah suatu proses mulai dieksekusi, maka tidak akan dihentikan hingga selesai.
- Karena **tidak ada waktu kedatangan**, maka semua proses dianggap tiba secara bersamaan.

## Langkah-langkah Eksekusi:
1. **P4 (BT=1)** → Paling kecil → jalan pertama.
2. **P2 (BT=3)** dan **P5(BT=3)** → *tie* (sama besar), urutan berdasarkan input (P2 terlebih dahulu).
3. **P5 (BT=3)**
4. **P3 (BT=4)**
5. **P1 (BT=7)** → Paling terakhir.

### Penjelasan Parameter:
- **Completion Time (CT):** Waktu saat proses selesai dieksekusi.
- **Turnaround Time (TAT):** Total waktu dari datang hingga selesai = CT - Arrival Time.
- **Waiting Time (WT):** TAT - Burst Time.

### Rata-rata:
- **Turnaround Time** = (1+4+7+11+18)/5 = **8.2**
- **Waiting Time** = (0+1+4+7+11)/5 = **4.6**

### Kesimpulan:
Algoritma SJF Non-Preemptive menghasilkan **waktu tunggu dan turnaround time yang optimal** jika arrival time tidak dipertimbangkan. Namun, jika banyak proses kecil datang terlambat, mereka harus menunggu, sehingga **SJF dapat menyebabkan starvation** untuk proses dengan burst time besar.

---
