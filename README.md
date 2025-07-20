# DISTRIBUSI TAKSI YANG EFISIEN  
Pemetaan Keramaian Spatio-Temporal Taksi di New York City  

---

## Daftar Isi

1. [Deskripsi Proyek](#deskripsi-proyek)  
2. [Executive Summary](#executive-summary)  
3. [Latar Belakang & Tujuan](#latar-belakang--tujuan)  
4. [Dataset & Sumber Data](#dataset--sumber-data)  
5. [Metode Analisis](#metode-analisis)  
6. [Visualisasi & Insight Utama](#visualisasi--insight-utama)  
7. [Kesimpulan & Rekomendasi](#kesimpulan--rekomendasi)  
8. [Struktur Folder](#struktur-folder)   
9. [Lisensi](#lisensi)  

---

## Deskripsi Proyek

Proyek ini bertujuan untuk memetakan dan menganalisis distribusi permintaan taksi di New York City secara spasial dan temporal pada Januari 2023. Hasilnya digunakan untuk merumuskan strategi penempatan armada yang lebih efisien, meminimalkan idle time, dan mengurangi waktu tunggu pelanggan.

---

## Executive Summary

Pada Januari 2023 tercatat 3,07 juta perjalanan Green Taxi. Temuan kunci:

- Permintaan tertinggi terjadi antara pukul 13:00–19:00 pada hari Selasa–Kamis.  
- Zona paling sibuk: East Elmhurst (bandara LaGuardia), East Harlem North, dan Flushing.  
- Manhattan (50,8%) dan Queens (44,5%) mendominasi permintaan, sedangkan Staten Island hanya 4,7%.  
- 34,6% drop-off berada di zona ‘Unknown’, mengindikasikan data zona belum lengkap.  

---

## Latar Belakang & Tujuan

Distribusi armada taksi di NYC saat ini belum optimal. Banyak taksi menumpuk di zona dengan permintaan rendah sehingga:

- Idle time meningkat  
- Pelanggan potensial hilang  
- Efisiensi operasional menurun  

Tujuan analisis:

- Mengidentifikasi pola permintaan berdasarkan zona, hari, dan jam  
- Mengevaluasi ketidakseimbangan distribusi armada  
- Memberikan rekomendasi alokasi armada yang lebih efektif  

---

## Dataset & Sumber Data

**Data utama:**  
NYC TLC Green Taxi Trip Records – Januari 2023 (.csv)  

Kolom utama yang digunakan:  
- `lpep_pickup_datetime` (waktu penjemputan)  
- `PU Zone` & `DO Zone` (zona jemput dan turun)  
- `PU Borough` (borough penjemputan)  
- `passenger_count`  
- `PU Longitude` & `PU Latitude`  

Sumber:  
NYC Taxi & Limousine Commission Open Data (https://www.nyc.gov)  

---

## Metode Analisis

- Descriptive statistics untuk merangkum distribusi dasar  
- Agregasi per zona dan per jam/hari  
- Visualisasi geospasial menggunakan GeoMap/Tableau  
- Heatmap untuk mengungkap jam dan lokasi tersibuk  
- Analisis spatio-temporal untuk pola jam sibuk tiap zona  

---

## Visualisasi & Insight Utama

### 1. Pola Temporal

- Puncak permintaan sore hari (15:00–19:00)  
- Hari kerja (Selasa–Kamis) lebih padat daripada weekend  

### 2. Top Zona Pick-up & Drop-off

| Zona Pick-up Teratas | Jumlah Penumpang | Zona Drop-off Teratas | Jumlah Penumpang |
|----------------------|------------------|-----------------------|------------------|
| East Elmhurst        | 16.860           | Unknown Zone          | 14.952           |
| East Harlem North    | 12.360           | East Harlem North     | 4.612            |
| Flushing             | 4.934            | East Elmhurst         | 4.363            |
| Stuyvesant Town/PCV  | 4.924            | Yorkville West        | 3.448            |
| Central Harlem       | 4.822            | Central Harlem        | 3.321            |

### 3. Distribusi per Borough

- Manhattan: 50,8%  
- Queens: 44,5%  
- Staten Island: 4,7%  

### 4. Spatio-Temporal Zona Pilihan

- East Elmhurst sibuk pagi (07:00–09:00) dan sore (18:00)  
- East Harlem North sibuk sore (15:00–17:00)  
- Flushing sibuk siang hingga sore  

---

## Kesimpulan & Rekomendasi

### Kesimpulan

- Armada taksi tidak merata: menumpuk di zona sepi, kekurangan di zona padat  
- Data zona masih incomplete (“Unknown” sebesar 34,6%)  
- Pola jam sibuk berbeda tiap wilayah  

### Rekomendasi

1. Penjadwalan dinamis armada berdasarkan zona & jam puncak  
2. Integrasi peta zona resmi (shapefile NYC Taxi Zone / OpenStreetMap)  
3. Insentif bagi driver yang berpindah ke zona kekurangan taksi  
4. Kembangkan sistem prediksi permintaan per zona (machine learning)  
5. Audit dan validasi ulang data `Unknown Zone`  

---

## Struktur Folder

```
├── README.md  
├── data/  
│   ├── raw/               # Data CSV asli  
│   └── processed/         # Data setelah pembersihan  
├── notebooks/             # Jupyter notebooks analisis  
├── tableau_dashboard/     # File Tableau workbook  
└── images/                # Grafik dan peta  
```

---

## Lisensi

MIT License © 2025 Alvin Zyafi Yanto  
Berbagi data dan analisis ini untuk meningkatkan efisiensi transportasi di NYC.
