# Pertemuan 12 — File I/O dan Error Handling

## Deskripsi

Praktikum Pertemuan 12 membahas penggunaan File I/O dan Error Handling pada Python. Pada tugas ini, program digunakan untuk membaca data nilai mahasiswa dari file `data/nilai.txt`, memproses data yang valid, menghitung statistik nilai, dan menyimpan hasil rekap ke file `data/hasil_rekap.txt`.

Program ini juga menerapkan penanganan kesalahan menggunakan `try-except` agar program dapat menangani file yang tidak ditemukan dan data nilai yang tidak valid.

## Struktur Folder

```text
pertemuan-12-file-io-2225250050/
├── README.md
├── .gitignore
├── data/
│   ├── catatan.txt
│   ├── nilai.txt
│   └── hasil_rekap.txt
├── latihan/
│   ├── 01_tulis_file.py
│   ├── 02_baca_file.py
│   ├── 03_append_file.py
│   ├── 04_proses_baris.py
│   ├── 05_file_not_found.py
│   └── 06_value_error.py
└── tugas/
    └── rekap_nilai_file.py
```

## Cara Menjalankan Program

1. Buka folder proyek melalui Visual Studio Code.
2. Buka terminal pada folder utama proyek.
3. Pastikan file `data/nilai.txt` tersedia.
4. Jalankan perintah berikut:

```bash
python tugas/rekap_nilai_file.py
```

Program akan membaca data dari `data/nilai.txt`, memproses data yang valid, lalu menuliskan hasil rekap ke `data/hasil_rekap.txt`.

## Format Data

File `data/nilai.txt` berisi NIM dan nilai mahasiswa yang dipisahkan dengan tanda koma. Setiap data ditulis pada baris yang berbeda.

Contoh:

```text
A001,80
A002,70
A003,90
```

## Hasil Pengujian (Test Case)

Pengujian dilakukan menggunakan lima kondisi untuk memeriksa kemampuan program dalam memproses data dan menangani kesalahan.

### 1. Semua Data Valid

**Kondisi pengujian:** File berisi tiga data nilai yang valid.

```text
A001,80
A002,70
A003,90
```

**Hasil pengujian:**

```text
Jumlah data valid: 3
Rata-rata: 80.00
Minimum: 70.00
Maximum: 90.00
Jumlah lulus: 3
```

**Kesimpulan:** Program berhasil membaca semua data valid dan menghitung jumlah data, rata-rata, nilai minimum, nilai maksimum, serta jumlah mahasiswa yang lulus.

### 2. File Tidak Ditemukan

**Kondisi pengujian:** File `data/nilai.txt` sementara diubah namanya sehingga tidak ditemukan pada lokasi yang dibaca program.

**Hasil pengujian di terminal:**

```text
File tidak ditemukan: data/nilai.txt
```

**Kesimpulan:** Program berhasil menangani kesalahan `FileNotFoundError` dengan menampilkan pesan bahwa file tidak ditemukan. Ketika file masukan tidak tersedia, program tidak membuat rekap baru sehingga file hasil sebelumnya tetap tidak berubah.

### 3. Nilai Tidak Valid

**Kondisi pengujian:** File berisi dua nilai valid dan satu nilai yang tidak dapat dikonversi menjadi angka.

```text
A001,80
A002,abc
A003,90
```

**Hasil pengujian di terminal:**

```text
Baris 2 dilewati: A002,abc
Rekap ditulis ke data/hasil_rekap.txt
```

**Hasil rekap:**

```text
Jumlah data valid: 2
Rata-rata: 85.00
Minimum: 80.00
Maximum: 90.00
Jumlah lulus: 2
```

**Kesimpulan:** Program berhasil melewati data dengan nilai tidak valid dan tetap memproses data valid lainnya. Kesalahan konversi ditangani menggunakan `ValueError`.

### 4. Terdapat Baris Kosong

**Kondisi pengujian:** File berisi dua data valid yang dipisahkan oleh satu baris kosong.

```text
A001,80

A002,70
```

**Hasil pengujian di terminal:**

```text
Rekap ditulis ke data/hasil_rekap.txt
```

**Hasil rekap:**

```text
Jumlah data valid: 2
Rata-rata: 75.00
Minimum: 70.00
Maximum: 80.00
Jumlah lulus: 2
```

**Kesimpulan:** Program berhasil melewati baris kosong dan hanya menghitung data yang valid.

### 5. Nilai Batas Kelulusan

**Kondisi pengujian:** File berisi nilai di bawah, tepat pada, dan di atas batas kelulusan.

```text
A001,59
A002,60
A003,61
```

**Hasil pengujian di terminal:**

```text
Rekap ditulis ke data/hasil_rekap.txt
```

**Hasil rekap:**

```text
Jumlah data valid: 3
Rata-rata: 60.00
Minimum: 59.00
Maximum: 61.00
Jumlah lulus: 2
```

**Kesimpulan:** Program berhasil menentukan kelulusan menggunakan kondisi `nilai >= 60`. Nilai 60 dan 61 dihitung lulus, sedangkan nilai 59 tidak dihitung lulus.

## Konsep yang Dipelajari

- **File I/O:** Membaca data dari file dan menuliskan hasil ke file.
- **`open()`:** Membuka file untuk dibaca atau ditulis.
- **`with`:** Mengelola file agar ditutup secara otomatis setelah blok program selesai.
- **Mode file:** Mode `r` untuk membaca, `w` untuk menulis ulang, dan `a` untuk menambahkan data.
- **`encoding="utf-8"`:** Menentukan pengodean teks saat file dibuka.
- **`strip()`:** Menghapus whitespace di awal dan akhir teks.
- **`split(",")`:** Memisahkan data NIM dan nilai berdasarkan tanda koma.
- **`float()`:** Mengonversi teks nilai menjadi bilangan.
- **`try-except`:** Menangani kesalahan yang dapat terjadi saat program dijalankan.
- **`FileNotFoundError`:** Menangani kondisi ketika file tidak ditemukan.
- **`ValueError`:** Menangani kesalahan seperti konversi nilai yang tidak valid.
- **Git dan GitHub:** Mengelola perubahan program dan dokumentasi menggunakan `git add`, `git commit`, dan `git push`.

## Kesimpulan

Berdasarkan hasil pengujian terhadap lima test case, program rekap nilai berhasil dijalankan sesuai dengan hasil yang diharapkan. Program dapat memproses data valid, menangani file yang tidak ditemukan, melewati data dengan nilai tidak valid, mengabaikan baris kosong, serta menentukan jumlah mahasiswa yang lulus berdasarkan batas nilai minimal 60.

Melalui praktikum Pertemuan 12, saya memahami penggunaan File I/O dalam Python, pemrosesan data teks, dan penanganan kesalahan menggunakan `try-except`. Pengujian pada berbagai kondisi juga membantu saya memahami pentingnya memastikan program dapat menangani data normal maupun kondisi kesalahan dengan baik.
