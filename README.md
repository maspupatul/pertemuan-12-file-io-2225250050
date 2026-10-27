## Pengujian Program

Pengujian dilakukan pada program `tugas/rekap_nilai_file.py` untuk memastikan program dapat membaca data nilai dari file, menangani data yang tidak valid, dan menghasilkan rekap nilai dengan benar.

### Test Case 1: Semua Data Valid

- **Kondisi pengujian:** File `data/nilai.txt` berisi `A001,80`, `A002,70`, dan `A003,90`.
- **Hasil yang diharapkan:** Program menghasilkan 3 data valid, rata-rata 80.00, nilai minimum 70.00, nilai maksimum 90.00, dan jumlah lulus 3.
- **Hasil aktual:** [Isi sesuai hasil pengujian.]
- **Status:** [Berhasil/Gagal.]

### Test Case 2: File Tidak Ditemukan

- **Kondisi pengujian:** File `data/nilai.txt` sementara diubah namanya sehingga tidak ditemukan.
- **Hasil yang diharapkan:** Program menampilkan pesan `File tidak ditemukan: data/nilai.txt` dan tidak menghasilkan rekap baru.
- **Hasil aktual:** [Isi sesuai hasil pengujian.]
- **Status:** [Berhasil/Gagal.]

### Test Case 3: Nilai Tidak Valid

- **Kondisi pengujian:** File berisi `A001,80`, `A002,abc`, dan `A003,90`.
- **Hasil yang diharapkan:** Baris kedua dilewati, sedangkan dua data valid tetap direkap. Rata-rata 85.00, nilai minimum 80.00, nilai maksimum 90.00, dan jumlah lulus 2.
- **Hasil aktual:** [Isi sesuai hasil pengujian.]
- **Status:** [Berhasil/Gagal.]

### Test Case 4: Terdapat Baris Kosong

- **Kondisi pengujian:** File berisi dua data valid yang dipisahkan oleh satu baris kosong.
- **Hasil yang diharapkan:** Baris kosong dilewati dan dua data valid direkap. Rata-rata 75.00, nilai minimum 70.00, nilai maksimum 80.00, dan jumlah lulus 2.
- **Hasil aktual:** [Isi sesuai hasil pengujian.]
- **Status:** [Berhasil/Gagal.]

### Test Case 5: Nilai Batas Kelulusan

- **Kondisi pengujian:** File berisi nilai 59, 60, dan 61.
- **Hasil yang diharapkan:** Ketiga data dihitung valid, rata-rata 60.00, nilai minimum 59.00, nilai maksimum 61.00, dan jumlah lulus 2.
- **Hasil aktual:** [Isi sesuai hasil pengujian.]
- **Status:** [Berhasil/Gagal.]

### Kesimpulan Pengujian

[Isi kesimpulan setelah kelima test case dijalankan. Jelaskan apakah program telah menghasilkan keluaran sesuai dengan hasil yang diharapkan.]
