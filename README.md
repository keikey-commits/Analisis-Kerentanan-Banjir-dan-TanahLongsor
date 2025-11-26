# Analisis-Kerentanan-Banjir
Project Mata Kuliah Data Wrangling Sains Data UNESA X Statistika UNJ
Anggota Kelompok 2
Ananda Keissa Az Zahra (24031554051), Sains Data UNESA
Anggi Nur Zavira (1314622009), Statistika UNJ

## Tujuan Proyek:
1. Mengevaluasi tingkat kerentanan bencana di Indonesia secara menyeluruh dengan menggabungkan data kerusakan, korban bencana, data penduduk, kejadian bencana, dan jumlah topografi suatu daerah.
2. Memetakan tingkat kerentanan bencana di tingkat wilayah terkecil, sehingga mengatasi kekurangan penelitian sebelumnya yang sering kali hanya fokus pada satu jenis risiko bencana atau daerah tertentu.
3. Mengidentifikasi pola dan tren tingkat kerentanan bencana di Indonesia, terutama peningkatan risiko bencana hidrometeorologi seperti banjir dan longsor, untuk mendukung penentuan prioritas intervensi di wilayah yang berisiko tinggi dan memiliki kemampuan mitigasi rendah.

## Sumber Data:
- Data Kejadian dan Dampak Bencana: Diperoleh dari https://gis.bnpb.go.id/databencana/tabel/pencarian.php, berisi frekuensi kejadian dan total dampak fisik (korban, kerusakan) per Kabupaten/Kota.
- Data Topografi: Diperoleh dari https://www.bps.go.id/id/statistics-table/3/TTBSVFJsVnNjMDFEYnpsbmFrRjRaMGgyVHpoSlFUMDkjMw==/jumlah-desa-sup-1-2--sup--kelurahan-menurut-provinsi-dan-topografi-wilayah.html?year=2021,  berisi jumlah desa/kelurahan di kategori dataran, lereng/puncak dan lembah.
- Data Jumlah Penduduk: Diperoleh dari https://pelita.kemendagri.go.id/kemendagri/dataset/262/tabel-data, berisi data jumlah penduduk tiap provinsi di Indonesia tahun 2018-2023.

## Tahapan

<img width="1772" height="1181" alt="Image" src="https://github.com/user-attachments/assets/595e7b4d-7d6c-40c1-88df-488bfeceaab5" />

1. Pengambilan Data
2. Data Cleaning
3. Integrasi Data
4. Eksplorasi Data (EDA)
5. Data Publishing

## Hasil
### Heatmap Korelasi Kejadian Banjir

<img width="959" height="730" alt="Image" src="https://github.com/user-attachments/assets/4660a332-39bd-4ff9-af79-cc85585bea7a" />

Kejadian banjir berkorelasi kuat dengan rumah terendam, kerusakan fasum, dan korban meninggal, sehingga frekuensi banjir sangat berpengaruh pada tingkat kerusakan. Variabel luka menunjukkan korelasi rendah.

### Heatmap Korelasi Kejadian Tanah Longsor

<img width="959" height="730" alt="Image" src="https://github.com/user-attachments/assets/46c7b71d-a30b-4fe6-98b2-f5eb4ab9da92" />

Kejadian longsor menunjukkan korelasi sangat kuat dengan kerusakan rumah dan fasilitas umum, sehingga semakin banyak kejadian maka semakin besar dampaknya. Variabel luka memiliki hubungan yang lemah dengan variabel lain.
