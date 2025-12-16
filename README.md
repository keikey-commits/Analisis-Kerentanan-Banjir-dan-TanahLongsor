# Analisis Kerentanan Banjir dan Tanah Longsor
Project Mata Kuliah Data Wrangling Sains Data UNESA X Statistika UNJ


### Anggota Kelompok 4
1. Ananda Keissa Az Zahra (24031554051), Sains Data UNESA 2024C
2. Anggi Nur Zavira (1314622009), Statistika UNJ
   
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

<img width="445" height="316" alt="Image" src="https://github.com/user-attachments/assets/bde27601-603b-4ed4-9fc1-13102a886634" />

Dari histogram distribusi Total_Kejadian, terlihat bahwa pola kejadian bencana di Indonesia sangat tidak merata. Ketimpangan paling besar terlihat pada kelompok provinsi dengan kejadian lebih dari 60 kali. Hanya beberapa provinsi yang masuk kategori ini, dan dua di antaranya  Aceh dan Sumatera Utara yang muncul sebagai provinsi dengan jumlah kejadian tertinggi, masing-masing mencapai sekitar 97 dan 112 kejadian.

### Histogram Total Meninggal

<img width="467" height="316" alt="Image" src="https://github.com/user-attachments/assets/ab546595-d65b-4c93-aa30-99dd7a2f5301" />

Distribusi korban meninggal menunjukkan bahwa sebagian besar provinsi tidak mencatat fatalitas atau hanya mencatat satu sampai dua korban meninggal. Kelompok dengan nilai 0–1 korban merupakan kelompok yang paling dominan, mencakup lebih dari separuh provinsi. Hanya satu provinsi yang mencapai angka tertinggi, yakni sekitar 10 korban meninggal, sehingga terlihat jelas sebagai outlier. Hal ini menunjukkan bahwa meskipun banjir cukup sering terjadi, fatalitas tinggi bukanlah kondisi umum di sebagian besar wilayah Indonesia.

### Histogram Total Luka

<img width="454" height="316" alt="Image" src="https://github.com/user-attachments/assets/6395a263-9eb0-4336-a67a-cf73250de349" />

Sebaran korban luka jauh lebih ekstrem. Hampir semua provinsi memiliki korban luka rendah, berada pada rentang 0–50 orang, namun terdapat satu provinsi dengan lebih dari 4.000 korban luka, menarik distribusi ke kanan. Hal ini mengindikasikan adanya satu kejadian besar di wilayah tertentu yang berdampak luar biasa besar pada populasi.

### Histogram Total Rumah Terendam

<img width="487" height="316" alt="Image" src="https://github.com/user-attachments/assets/13c87e20-25eb-4cd1-9a7a-c8ab4471f9c8" />

Pada variabel Total_Rumah_Terendam, sebarannya juga sangat bervariasi. Sekitar 18–20 provinsi berada pada rentang 0–20.000 rumah terendam, yang berarti mayoritas wilayah mengalami dampak banjir yang relatif masih terkendali.
Namun, terdapat satu provinsi yang mengalami dampak jauh lebih besar dengan lebih dari 100.000 rumah terendam. Nilai yang sangat tinggi ini merupakan indikasi adanya kejadian banjir besar, kemungkinan berkaitan dengan curah hujan ekstrim atau kondisi hidrologis yang buruk pada wilayah tersebut.

### Heatmap Korelasi Kejadian Banjir

<img width="970" height="730" alt="Image" src="https://github.com/user-attachments/assets/392c5cde-0dee-4ed5-af3f-c8fed411f9d1" />

Kejadian banjir berkorelasi kuat dengan rumah terendam, kerusakan fasum, dan korban meninggal, sehingga frekuensi banjir sangat berpengaruh pada tingkat kerusakan. Variabel luka menunjukkan korelasi rendah.

### Scatter Plot

<img width="597" height="455" alt="Image" src="https://github.com/user-attachments/assets/5472fc9a-f89d-4bb2-8d6a-1a0452bb9399" />

Scatter plot di atas menunjukkan hubungan antara total kejadian banjir dan total rumah terendam menunjukkan pola kecenderungan yang jelas bahwa semakin tinggi frekuensi banjir pada suatu wilayah, semakin besar pula jumlah rumah yang terdampak. Meskipun sebaran titik data terlihat variatif, terdapat tren peningkatan yang konsisten terutama pada wilayah yang mengalami lebih dari 50 kejadian banjir, di mana jumlah rumah terendam dapat mencapai puluhan ribu hingga lebih dari seratus ribu unit. Kehadiran beberapa outlier dengan dampak yang sangat besar mengindikasikan bahwa karakteristik fisik wilayah—seperti kepadatan permukiman, kondisi topografi dataran rendah, dan minimnya infrastruktur penanganan banjir—berperan penting dalam memperparah skala kerusakan. Secara keseluruhan, grafik ini memperkuat bahwa frekuensi banjir memiliki keterikatan kuat dengan besarnya dampak fisik yang dialami masyarakat.

### Total Kejadian per provinsi

<img width="850" height="578" alt="Image" src="https://github.com/user-attachments/assets/05b949bb-6ba0-4b06-b4c9-780c5b5a8d1c" />

Grafik batang di atas,  menampilkan jumlah kejadian banjir per provinsi menunjukkan variasi yang cukup signifikan di seluruh Indonesia. Provinsi seperti Sumatera Utara, Jawa Barat, dan Jawa Tengah menjadi wilayah dengan jumlah kejadian banjir tertinggi, masing-masing mencatat lebih dari 90 hingga lebih dari 110 kejadian. 

### Pie Chart Kerentanan

<img width="520" height="504" alt="Image" src="https://github.com/user-attachments/assets/583d75f1-7d28-42ca-9798-7348cf1c06e3" />

Grafik pie di atas, menunjukkan persentase kategori kerentanan terhadap banjir, dan terlihat bahwa sebagian besar wilayah berada pada kategori rendah, yaitu mencapai sekitar 94,1% dari total wilayah yang dianalisis. Angka ini menunjukkan bahwa mayoritas wilayah memiliki tingkat risiko banjir yang relatif kecil berdasarkan parameter penilaian yang digunakan, seperti frekuensi kejadian, tingkat kerusakan, dan karakteristik geografis. Sementara itu, kategori sedang dan tinggi masing-masing hanya mencakup sekitar 2,9%, mengindikasikan bahwa hanya sebagian kecil wilayah yang teridentifikasi memiliki potensi terdampak banjir secara signifikan. Komposisi ini menunjukkan bahwa secara umum tingkat kerentanan banjir berada pada kategori aman atau terkendali, meskipun wilayah-wilayah kecil dalam kategori sedang dan tinggi tetap memerlukan perhatian khusus karena potensi dampaknya yang bisa lebih besar

## Grafik Tanah Longsor
### Histogram Total Kejadian

<img width="454" height="316" alt="Image" src="https://github.com/user-attachments/assets/6424a0e0-dcb2-4f20-b8e3-6746181a1385" />

Hasil visualisasi distribusi Total_Kejadian menunjukkan bahwa sebagian besar wilayah hanya mengalami kejadian longsor dalam jumlah yang relatif kecil, yaitu pada rentang 0–20 kejadian. Distribusi ini tampak sangat miring ke kanan karena terdapat beberapa wilayah yang menjadi outlier dengan jumlah kejadian mencapai lebih dari 100 hingga mendekati 200. Hal ini menunjukkan bahwa meskipun longsor terjadi di banyak wilayah, hanya sedikit wilayah yang mengalami kejadian dalam skala yang jauh lebih tinggi dibanding wilayah lainnya.

### Histogram Total Meninggal

<img width="454" height="316" alt="Image" src="https://github.com/user-attachments/assets/dfdf2513-e508-46a2-bce5-7785f640a37a" />

Pada variabel Total_Meninggal, sebagian besar wilayah tercatat tidak mengalami korban jiwa atau hanya memiliki 1–5 korban. Distribusinya juga sangat skewed ke kanan karena terdapat beberapa kasus ekstrim dengan jumlah korban meninggal mencapai 30–40 orang. Artinya, kejadian longsor yang menimbulkan korban jiwa besar merupakan kejadian yang jarang terjadi, namun memberikan kontribusi signifikan terhadap ketidakseimbangan distribusi data

### Histogram Total Luka

<img width="454" height="316" alt="Image" src="https://github.com/user-attachments/assets/46364246-3ad2-4696-bd00-1a0dc2ce50b7" />

Distribusi Total_Terluka menunjukkan pola yang serupa, di mana mayoritas wilayah mencatat korban luka dalam jumlah kecil, umumnya di bawah 50 orang. Namun terdapat satu outlier ekstrim dengan korban luka mencapai sekitar 600 orang, yang menunjukkan adanya satu kejadian longsor besar yang tidak lazim dibandingkan wilayah lainnya. Kondisi ini mengindikasikan bahwa meskipun sebagian besar longsor berdampak ringan, terdapat kejadian tertentu yang menimbulkan dampak besar.

### Histogram Total Rumah Rusak

<img width="454" height="316" alt="Image" src="https://github.com/user-attachments/assets/a94eb4f0-9d36-468d-86b3-a05927d2d565" />

Pada variabel Total_Rumah_Rusak, sebagian besar wilayah mengalami kerusakan rumah pada rentang 0–100 unit. Meski demikian, terdapat beberapa wilayah yang mencatat kerusakan dalam skala ratusan rumah, serta satu outlier yang mencapai hampir 800 unit. Hal ini menunjukkan bahwa kerusakan rumah akibat longsor umumnya tidak besar, tetapi sesekali terjadi bencana dengan dampak kerusakan yang sangat signifikan.

### Heatmap Korelasi Kejadian Tanah Longsor

<img width="970" height="730" alt="Image" src="https://github.com/user-attachments/assets/d6b97453-9216-475b-b88b-2d2ce0b626be" />

Kejadian longsor menunjukkan korelasi sangat kuat dengan kerusakan rumah dan fasilitas umum, sehingga semakin banyak kejadian maka semakin besar dampaknya. Variabel luka memiliki hubungan yang lemah dengan variabel lain.

### Scatter Plot

<img width="571" height="455" alt="Image" src="https://github.com/user-attachments/assets/d1b22551-5e3c-45a0-b7b2-eb8a44fe1df9" />

Berdasarkan scatter plot di atas, menunjukkan hubungan antara total kejadian tanah longsor dan total rumah rusak menggambarkan pola hubungan yang lebih kompleks dan tidak sekuat pada kasus banjir. Sebagian besar wilayah mengalami kejadian longsor dalam jumlah kecil dengan dampak kerusakan rumah yang relatif rendah. Namun, terdapat beberapa titik data yang menjadi outlier, yaitu wilayah yang mengalami kejadian longsor sangat tinggi atau menghasilkan kerusakan rumah dalam jumlah besar, bahkan mencapai lebih dari 800 unit. Hal ini menunjukkan bahwa intensitas kerusakan akibat longsor tidak selalu bergantung pada jumlah kejadiannya, melainkan lebih dipengaruhi oleh kondisi geografis seperti kemiringan lereng, kualitas bangunan, serta kedekatan permukiman dengan tebing atau area rawan longsor. Dengan demikian, hubungan antara frekuensi longsor dan kerusakan rumah bersifat tidak linear dan sangat bergantung pada tingkat kerentanan wilayah.

### Total Kejadian per provinsi

<img width="850" height="578" alt="Image" src="https://github.com/user-attachments/assets/287046a9-9027-43da-9ae3-7df988f46def" />

Grafik batang di atas, menunjukkan distribusi jumlah kejadian tanah longsor per provinsi, dan pola yang muncul tampak lebih mencolok dibanding grafik banjir. Jawa Barat mendominasi secara signifikan dengan jumlah kejadian longsor yang melampaui 200 kejadian, menjadikannya provinsi dengan tingkat kerentanan tertinggi terhadap longsor di Indonesia.

### Pie Chart Kerentanan

<img width="504" height="504" alt="Image" src="https://github.com/user-attachments/assets/37e4bfa6-df0e-42fe-a4b9-cfcdf095e5f0" />

Grafik pie di atas, menunjukkan persentase kategori kerentanan terhadap tanah longsor. Secara keseluruhan, pola sebarannya serupa dengan banjir, di mana kategori rendah mendominasi hingga 87,5% wilayah. Hal ini menunjukkan bahwa mayoritas daerah yang dianalisis memiliki tingkat risiko longsor yang relatif kecil dan cenderung stabil. Namun, berbeda dengan banjir, proporsi kategori sedang relatif lebih besar, yaitu sekitar 9,4%, menunjukkan bahwa terdapat lebih banyak wilayah yang berada pada tingkat kewaspadaan menengah terhadap potensi longsor. Adapun kategori tinggi berada pada angka 3,1%, yang meskipun kecil, tetap menunjukkan adanya wilayah tertentu yang sangat rentan terhadap longsor, kemungkinan akibat kondisi lereng curam, jenis tanah rawan gerakan, serta intensitas hujan tinggi. Grafik ini menegaskan bahwa meskipun sebagian besar wilayah aman, mitigasi bencana tetap diperlukan terutama pada kategori sedang dan tinggi yang memiliki potensi risiko lebih besar.


