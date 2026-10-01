# Tugas Mandiri Data Wrangling - Pertemuan 2

**Nama:** Virgio Arwa Sandhika  
**NIM:** 25200016  

## Studi Kasus
Analisis kampanye kupon diskon akhir bulan di PT Nusantara Retail Mandiri: berapa total transaksi yang memakai kupon, bagaimana profil loyalitas pelanggannya, dan apakah pesanan sudah terkirim oleh mitra logistik.

## Isi Repositori
| File | Keterangan |
|---|---|
| `Tugas1_DW_25200016.ipynb` | Notebook utama (Bagian A, B, C) beserta output |
| `kamus_data_hasil.csv` | Kamus data otomatis dari `df_master_analisis` |
| `transaksi_pos.csv` | Dataset dummy transaksi kasir (CSV) |
| `crm_loyalty.db` | Database SQLite dummy data pelanggan (CRM) |
| `mock_logistik.json` | Mock respons REST API logistik (JSON nested) |
| `requirements.txt` | Daftar library Python |

## Ringkasan Pengerjaan
- **Bagian A:** Pemetaan kebutuhan bisnis ke kebutuhan teknis data dan matriks RACI.
- **Bagian B:** Ingestion dari CSV (pandas), SQL (SQLite + SQLAlchemy, `WHERE is_active = 1`), dan REST API (`requests` + `pd.json_normalize`), lalu merge dengan *left join* menjadi `df_master_analisis`.
- **Bagian C:** Fungsi kamus data otomatis dan assertion kualitas data (PK unik, `total_amount` tidak negatif, tidak ada future date).

## Cara Menjalankan
```bash
pip install -r requirements.txt
jupyter notebook Tugas1_DW_25200016.ipynb
```
Jalankan semua cell dari atas ke bawah (*Run All*). Jika endpoint API tidak dapat diakses, notebook otomatis memakai `mock_logistik.json`.
