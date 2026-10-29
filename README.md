# PROGRAM REKAP DAN ANALISIS NILAI MATEMATIKA KELAS

**Nama:** Siti Nurhasanah  
**NIM:** 2225250073  
**Kelas:** 3B

---

## 1. Tentang Program

Program ini dibuat untuk membantu proses pengolahan data nilai siswa dengan memanfaatkan bahasa pemrograman Python. Data nilai yang tersimpan dalam file teks akan dibaca, diperiksa validitasnya, kemudian diolah menjadi informasi yang lebih mudah dipahami.

Melalui program ini, pengguna dapat mengetahui jumlah data yang valid, rata-rata nilai, nilai tertinggi, nilai terendah, serta jumlah siswa yang memenuhi maupun belum memenuhi kriteria ketuntasan belajar.

Selain digunakan sebagai solusi sederhana dalam pengolahan data nilai, proyek ini juga menjadi sarana penerapan materi Algoritma dan Pemrograman yang telah dipelajari selama perkuliahan.

---

## 2. Tujuan Pengembangan

Program dirancang dengan tujuan sebagai berikut:

1. Membaca data nilai siswa dari file teks secara otomatis.
2. Memastikan hanya data yang valid yang diproses oleh sistem.
3. Menghasilkan statistik dasar dari data nilai yang tersedia.
4. Mengelompokkan siswa berdasarkan status ketuntasan belajar.
5. Menyajikan hasil analisis dalam bentuk yang mudah dibaca.
6. Melatih penerapan konsep fungsi, modularisasi, validasi data, dan file I/O pada Python.

---

## 3. Kemampuan Program

Beberapa kemampuan yang dimiliki program ini antara lain:

- Mengambil data dari file teks.
- Mengecek kesesuaian format data.
- Memastikan nilai berada pada rentang yang diperbolehkan.
- Mengabaikan data yang tidak memenuhi syarat.
- Menghitung jumlah data yang berhasil diproses.
- Menghitung total dan rata-rata nilai.
- Menentukan nilai tertinggi dan nilai terendah.
- Mengidentifikasi siswa yang tuntas dan belum tuntas.
- Menampilkan hasil analisis pada terminal.
- Menyimpan laporan hasil pengolahan ke file.

---

## 4. Struktur Proyek

```text
proyek-nilai-siswa/
├── main.py
├── input_data.py
├── data_io.py
├── analisis.py
├── proses.py
├── utilitas.py
├── output.py
├── proposal.md
├── test_case.md
├── README.md
├── .gitignore
├── data/
│   └── nilai_contoh.txt
└── output/
    └── .gitkeep
```

### Penjelasan File

| File | Kegunaan |
|--------|----------|
| `main.py` | Mengatur jalannya program secara keseluruhan |
| `input_data.py` | Mengelola data masukan |
| `data_io.py` | Menangani proses baca dan tulis file |
| `analisis.py` | Melakukan pengolahan dan perhitungan statistik |
| `proses.py` | Memproses dan memvalidasi data |
| `utilitas.py` | Menyimpan fungsi-fungsi pendukung |
| `output.py` | Menampilkan hasil kepada pengguna |
| `nilai_contoh.txt` | Sumber data yang akan dianalisis |
| `test_case.md` | Dokumentasi pengujian |
| `proposal.md` | Dokumen rancangan proyek |

---

## 5. Bentuk Data Masukan

Program menggunakan file teks sebagai sumber data. Setiap baris berisi kode siswa dan nilai yang dipisahkan dengan tanda koma.

Contoh:

```text
A001,85
A002,78
A003,92
A004,abc
A005,60
A006,50
A007,75
A008,88
A009,45
A010,100
```

Data `A004,abc` sengaja disertakan untuk memastikan bahwa program dapat mengenali dan menangani data yang tidak sesuai format.

---

## 6. Aturan Pengolahan Data

Agar hasil analisis tetap konsisten, program menggunakan aturan berikut:

1. Nilai harus berupa angka.
2. Rentang nilai yang diperbolehkan adalah 0–100.
3. Kode siswa tidak boleh kosong.
4. Kode siswa yang sama tidak diproses lebih dari satu kali.
5. Nilai minimal 60 dikategorikan **Tuntas**.
6. Nilai di bawah 60 dikategorikan **Belum Tuntas**.
7. Data yang tidak memenuhi ketentuan tidak disertakan dalam perhitungan.
8. Jika file tidak tersedia, program akan menampilkan informasi kesalahan.

---

## 7. Menjalankan Program

Pastikan Python sudah terinstal pada komputer.

Buka terminal pada folder proyek, kemudian jalankan:

```bash
python main.py
```

Apabila menggunakan Linux atau macOS, dapat menggunakan:

```bash
python3 main.py
```

Pastikan file data berada pada lokasi yang sesuai dengan path yang digunakan dalam program.

---

## 8. Contoh Hasil Analisis

Berdasarkan data contoh yang digunakan, terdapat satu data yang tidak valid sehingga hanya sembilan data yang diproses.

| Komponen | Hasil |
|-----------|-------:|
| Data valid | 9 |
| Total nilai | 673 |
| Rata-rata | 74,78 |
| Nilai tertinggi | 100 |
| Nilai terendah | 45 |
| Siswa tuntas | 7 |
| Siswa belum tuntas | 2 |
| Data tidak valid | 1 |

Dari hasil tersebut dapat diketahui bahwa sebagian besar siswa telah mencapai batas ketuntasan yang digunakan dalam program.

---

## 9. Pengujian Sistem

Program diuji menggunakan beberapa kondisi yang berbeda untuk memastikan seluruh fitur dapat berjalan dengan baik.

| No | Kondisi Uji | Hasil yang Diharapkan |
|----|-------------|----------------------|
| 1 | Nilai valid | Data diproses dengan benar |
| 2 | Nilai tepat 60 | Status Tuntas |
| 3 | Nilai di bawah 60 | Status Belum Tuntas |
| 4 | Nilai berupa teks | Data diabaikan |
| 5 | Nilai di atas 100 | Data ditolak |
| 6 | Kode siswa duplikat | Tidak diproses |
| 7 | File tidak ditemukan | Pesan kesalahan muncul |
| 8 | Menyimpan laporan | File laporan berhasil dibuat |

Dokumen lengkap pengujian dapat dilihat pada file `test_case.md`.

---

## 10. Gambaran Efisiensi Program

Jika jumlah data siswa dinyatakan sebagai **n**, maka:

- Waktu proses sekitar **O(n)** karena setiap data diperiksa dan diolah satu kali.
- Kebutuhan memori sekitar **O(n)** karena data yang valid disimpan selama proses analisis berlangsung.

Untuk data kelas dengan jumlah siswa normal, pendekatan ini sudah cukup efisien.

---

## 11. Penutup

Program ini dikembangkan sebagai contoh penerapan konsep pemrograman dalam menyelesaikan permasalahan sederhana di bidang pendidikan. Melalui proses membaca data, melakukan validasi, menghitung statistik, dan menyajikan laporan, program dapat membantu pengguna memperoleh informasi nilai dengan lebih cepat dan terstruktur.

Selain menghasilkan sebuah aplikasi sederhana, proyek ini juga menjadi latihan dalam memahami penggunaan fungsi, modul, pengolahan file, validasi data, dan penanganan kesalahan menggunakan Python.