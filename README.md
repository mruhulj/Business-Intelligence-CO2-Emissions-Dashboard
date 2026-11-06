# Global CO2 Emissions Business Intelligence Dashboard

Proyek akhir mata kuliah Kecerdasan Bisnis, IF-A, UPN "Veteran" Yogyakarta 2025. Proyek ini menganalisis tren emisi CO2 global dan hubungannya dengan pertumbuhan ekonomi (GDP) memakai pendekatan Business Intelligence, dari data warehouse sampai rekomendasi strategis.

## Tim (Kelompok 5)

| Nama | NIM |
|---|---|
| Muhammad Ruhul Jadid | 123230046 |
| Arsyila Saduwarti | 123230120 |
| Mufidah Shofi Aqilah | 123230133 |
| Gita Ristya | 123230152 |

Dosen pengampu: Andrey Ferriyan, S.T., M.Cs., Ph.D.

## Rumusan Masalah

1. Bagaimana mengolah dataset emisi CO2 global agar mendukung operasi OLAP (pivot, slice, dice)?
2. Bagaimana tren historis emisi dan sektor kontributor utamanya?
3. Bagaimana proyeksi emisi jika tidak ada intervensi kebijakan?
4. Strategi apa yang dapat mencapai decoupling antara pertumbuhan ekonomi dan emisi?

## Dataset

[CO2 Emissions Across Countries, Regions, and Sectors](https://www.kaggle.com/datasets/shreyanshdangi/co-emissions-across-countries-regions-and-sectors) (Kaggle), 198 negara, 1850 sampai 2023. Dataset tidak disertakan di repository ini, silakan unduh dari Kaggle.

## Pendekatan

- **Data warehouse:** dataset berformat lebar diubah menjadi tabel fakta berformat long (dimensi lokasi, waktu, dan sektor; metrik emisi, GDP, populasi, emisi per kapita, intensitas emisi) memakai Python dan Pandas di Google Colab.
- **OLAP:** pivot table dengan heatmap (negara x sektor) dan slice berdasarkan rentang tahun.
- **Empat pilar analitik** dalam satu dashboard Looker Studio:
  - *Deskriptif:* scorecard KPI dan time series 1850 sampai 2023.
  - *Diagnostik:* stacked area chart per sektor (batu bara dan minyak penyumbang terbesar).
  - *Prediktif:* regresi linear (OLS) sebagai proyeksi business as usual.
  - *Preskriptif:* scatter plot GDP vs emisi untuk membandingkan efisiensi antarnegara.
- **Rekomendasi:** kurangi batu bara di pembangkit listrik, elektrifikasi transportasi, dan tetapkan target emisi per unit GDP (decoupling), bukan hanya penurunan absolut.

## Isi Repository

| Folder | Isi |
|---|---|
| `laporan/` | Laporan proyek akhir (PDF) |
| `orange/` | Workflow Orange (File, Impute, Select Columns, Data Table) dan laporan HTML untuk persiapan data awal |

## Keterbatasan

- Proyeksi memakai trendline regresi linear tanpa validasi lanjutan (pembagian data latih dan uji, ukuran kesalahan).
- Hubungan GDP dan emisi bersifat korelasi, bukan sebab-akibat.
- Dashboard Looker Studio perlu dicek ulang karena sebagian grafik gagal dimuat dari akun pengunjung. Tangkapan layar ada di laporan PDF.

## Lampiran

- Video presentasi: https://youtu.be/r5Dh7dBBDV8
