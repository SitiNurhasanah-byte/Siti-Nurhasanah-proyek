## Program Rekap dan Analisis Nilai Matematika Kelas

**Nama:** Siti Nurhasanah  
**NIM:** 2225250073  
**Kelas:** 3B

---

## 1. Latar Belakang Pengujian

Pengujian dilakukan untuk memastikan bahwa setiap fitur pada program dapat berjalan sesuai dengan tujuan yang telah direncanakan. Proses pengujian tidak hanya berfokus pada hasil perhitungan, tetapi juga mencakup kemampuan program dalam membaca file, memeriksa validitas data, melakukan analisis nilai, serta menangani kesalahan input yang mungkin terjadi selama program digunakan.

---

## 2. Aturan yang Digunakan

Dalam proses pengolahan data nilai, program menerapkan beberapa aturan sebagai berikut:

- Nilai yang dapat diproses berada pada rentang 0 sampai 100.
- Nilai minimum ketuntasan ditetapkan sebesar 60.
- Siswa dengan nilai 60 atau lebih dikategorikan sebagai **Tuntas**.
- Siswa yang memperoleh nilai di bawah 60 dikategorikan sebagai **Belum Tuntas**.
- Data yang tidak memenuhi format akan diabaikan dan tidak disertakan dalam analisis.
- Jika tidak ditemukan data yang valid, program akan memberikan informasi kepada pengguna.

---

## 3. Sumber Data Uji

File yang digunakan dalam pengujian adalah `data/nilai_contoh.txt` dengan isi sebagai berikut:

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

Pada data tersebut terdapat satu baris yang sengaja dibuat tidak valid, yaitu `A004,abc`, untuk menguji apakah program mampu mengenali data yang tidak sesuai format.

---

## 4. Rincian Skenario Pengujian

Berikut adalah berbagai kondisi yang digunakan untuk menguji fungsi-fungsi dalam program.

| ID | Kondisi yang Diuji | Input | Hasil yang Diharapkan |
|----|-------------------|--------|----------------------|
| TC01 | Nilai berada di atas batas ketuntasan | 85 | Status Tuntas |
| TC02 | Nilai sama dengan batas ketuntasan | 60 | Status Tuntas |
| TC03 | Nilai berada di bawah batas ketuntasan | 45 | Status Belum Tuntas |
| TC04 | Nilai valid terendah | 0 | Diterima sistem |
| TC05 | Nilai valid tertinggi | 100 | Diterima sistem |
| TC06 | Nilai negatif | -5 | Ditolak sistem |
| TC07 | Nilai melebihi batas maksimum | 110 | Ditolak sistem |
| TC08 | Nilai berupa teks | abc | Tidak diproses |
| TC09 | Format data benar | NIM,nilai | Data terbaca |
| TC10 | Format tanpa tanda pemisah | A011 80 | Data diabaikan |
| TC11 | Terdapat baris kosong | Baris kosong | Tidak diproses |
| TC12 | File tidak tersedia | Nama file salah | Muncul pesan error |
| TC13 | Seluruh data tidak valid | Data salah semua | Pesan tidak ada data |
| TC14 | Perhitungan rata-rata | 80,70,90 | Rata-rata = 80 |
| TC15 | Penentuan nilai tertinggi | 80,70,90 | Nilai tertinggi = 90 |
| TC16 | Penentuan nilai terendah | 80,70,90 | Nilai terendah = 70 |
| TC17 | Perhitungan siswa tuntas | 60,75,50 | 2 siswa tuntas |
| TC18 | Perhitungan siswa belum tuntas | 60,75,50 | 1 siswa belum tuntas |
| TC19 | Menampilkan hasil analisis | Data valid | Ringkasan muncul |
| TC20 | Menyimpan hasil analisis | Data valid | File laporan berhasil dibuat |

---

## 5. Hasil yang Diperkirakan

Berdasarkan data pengujian yang digunakan, terdapat sembilan data yang memenuhi syarat untuk diproses dan satu data yang tidak valid.

| Komponen | Hasil |
|-----------|-------:|
| Jumlah data valid | 9 siswa |
| Total seluruh nilai | 673 |
| Nilai rata-rata | 74,78 |
| Nilai tertinggi | 100 |
| Nilai terendah | 45 |
| Jumlah siswa tuntas | 7 siswa |
| Jumlah siswa belum tuntas | 2 siswa |
| Data tidak valid | 1 data |

---

## 6. Pengujian Fungsi Pendukung

Selain menguji program secara keseluruhan, beberapa fungsi pendukung juga diuji secara terpisah agar hasilnya lebih akurat.

| ID | Fungsi | Input | Output yang Diharapkan |
|----|---------|--------|------------------------|
| UT01 | `validasi_nilai()` | 80 | `True` |
| UT02 | `validasi_nilai()` | 120 | `False` |
| UT03 | `validasi_nilai()` | `"abc"` | `False` |
| UT04 | `status_ketuntasan()` | 85 | `"Tuntas"` |
| UT05 | `status_ketuntasan()` | 60 | `"Tuntas"` |
| UT06 | `status_ketuntasan()` | 45 | `"Belum Tuntas"` |
| UT07 | `format_nilai()` | 85 | `"85.00"` |
| UT08 | `format_nilai()` | `"abc"` | `"Tidak valid"` |

---

## 7. Pengujian Modul Analisis

Pengujian berikut dilakukan untuk memastikan bahwa proses analisis nilai dapat menghasilkan informasi yang benar.

| ID | Fungsi | Data Uji | Hasil yang Diharapkan |
|----|---------|-----------|----------------------|
| AN01 | `analisis_nilai()` | 80,70,90 | Rata-rata = 80 |
| AN02 | `analisis_nilai()` | Data kosong | Menghasilkan `None` |
| AN03 | `analisis_nilai()` | 60 dan 50 | 1 tuntas dan 1 belum tuntas |
| AN04 | `analisis_nilai()` | 100 dan 0 | Maksimum 100, minimum 0 |

---

## 8. Indikator Keberhasilan

Program dianggap memenuhi kebutuhan apabila:

1. Data dari file dapat dibaca tanpa kendala.
2. Kesalahan format data dapat ditangani tanpa menghentikan program.
3. Nilai di luar batas yang ditentukan dapat ditolak.
4. Hasil perhitungan statistik sesuai dengan data yang diberikan.
5. Status ketuntasan ditentukan berdasarkan batas nilai yang berlaku.
6. Program mampu menangani kondisi file tidak ditemukan maupun data kosong.
7. Laporan hasil analisis dapat ditampilkan serta disimpan dengan baik.

---

## 9. Penutup

Dokumen pengujian ini digunakan sebagai acuan untuk mengevaluasi apakah seluruh fungsi dalam Sistem Pengolahan Nilai Matematika telah berjalan sesuai kebutuhan. Program dinyatakan berhasil apabila setiap skenario pengujian menghasilkan keluaran yang sesuai dengan perencanaan. Hasil aktual dari pengujian nantinya dapat digunakan sebagai bahan evaluasi dan pengembangan program pada tahap berikutnya.