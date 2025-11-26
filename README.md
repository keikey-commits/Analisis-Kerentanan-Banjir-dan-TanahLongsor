# Analisis Kerentanan Banjir dan Tanah Longsor
Project Mata Kuliah Data Wrangling Sains Data UNESA X Statistika UNJ
Anggota Kelompok 2
Ananda Keissa Az Zahra (24031554051), Sains Data UNESA 2024C
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

## Grafik Banjir
### Histogram Total Kejadian
<img width="445" height="316" alt="Image" src="https://github.com/user-attachments/assets/241b9360-e851-49d6-8030-4a5ea1dc95e2" />
### Histogram Total Meninggal
<img width="467" height="316" alt="Image" src="https://github.com/user-attachments/assets/d2456463-66dd-4576-9cfe-d0201a3ab029" />
### Histogram Total Luka
<img width="454" height="316" alt="Image" src="https://github.com/user-attachments/assets/c77c7590-98ec-4a4c-926a-15086a6372ca" />
### Histogram Total Rumah Terendam
<img width="487" height="316" alt="Image" src="https://github.com/user-attachments/assets/8948a406-1829-4b6f-845d-a78746a92de6" />
### Heatmap Korelasi Kejadian Banjir

<img width="959" height="730" alt="Image" src="https://github.com/user-attachments/assets/4660a332-39bd-4ff9-af79-cc85585bea7a" />

Kejadian banjir berkorelasi kuat dengan rumah terendam, kerusakan fasum, dan korban meninggal, sehingga frekuensi banjir sangat berpengaruh pada tingkat kerusakan. Variabel luka menunjukkan korelasi rendah.
### Scatter Plot
<img width="597" height="455" alt="Image" src="https://github.com/user-attachments/assets/c28973f1-3c86-4d48-8e82-694c1c39b046" />
### Total Kejadian per provinsi
<img width="597" height="455" alt="Image" src="https://github.com/user-attachments/assets/c28973f1-3c86-4d48-8e82-694c1c39b046" />
### Pie Chart Kerentanan
<img width="520" height="504" alt="Image" src="https://github.com/user-attachments/assets/583d75f1-7d28-42ca-9798-7348cf1c06e3" />


## Grafik Tanah Longsor
### Histogram Total Kejadian
### Histogram Total Meninggal
### Histogram Total Luka
### Histogram Total Rumah Rusak
### Heatmap Korelasi Kejadian Tanah Longsor

<img width="959" height="730" alt="Image" src="https://github.com/user-attachments/assets/46c7b71d-a30b-4fe6-98b2-f5eb4ab9da92" />

Kejadian longsor menunjukkan korelasi sangat kuat dengan kerusakan rumah dan fasilitas umum, sehingga semakin banyak kejadian maka semakin besar dampaknya. Variabel luka memiliki hubungan yang lemah dengan variabel lain.

### Total Kejadian per provinsi
### Pie Chart Kerentanan
### Scatter Plot
