# **Tokopedia Seblak Sales Scraping and Data Cleaning using Python**

---

## Overview
Project ini berfokus pada pengambilan data penjualan produk seblak di Tokopedia menggunakan Selenium sebagai web automation dan BeautifulSoup untuk parsing HTML. Data produk seperti nama, harga, penjual, kota toko, jumlah terjual, dan rating disimpan ke DataFrame lalu diekspor ke CSV. Setelah itu dilakukan proses data cleaning pada kolom harga dan jumlah terjual agar dapat dianalisis secara kuantitatif.

---

## File Description
- data_Penjualan_Seblak.csv: Hasil scraping mentah sebelum dibersihkan.
- web_scraping_seblak.ipynb: Script utama untuk scraping halaman Tokopedia menggunakan Selenium dan BeautifulSoup.

---

## Steps
1. Web Scraping dengan Selenium
- Inisialisasi webdriver.Chrome()
- Buka URL pencarian Tokopedia (q=seblak)
- Tambahkan time.sleep() untuk menunggu halaman load
- Ambil page_source dan parsing dengan BeautifulSoup
- Ekstrak elemen produk:
- Nama Produk
- Harga Produk
- Penjual
- Kota Toko
- Banyaknya Terjual
- Rating Produk
- Simpan data ke DataFrame
- Export ke data_Penjualan_Seblak.csv

2. Load Data & Explorasi
- Import CSV hasil scraping
- Tampilkan 5 data teratas (head())
- Cek tipe data (info())

3. Data Cleaning & Type Conversion
- Harga Produk
   - Hapus string "Rp" dan titik .
	- Konversi ke int
- Banyaknya Terjual
   Mengubah format seperti:
	- “Terjual 750+” → 750
	- “Terjual 1 rb” → 1000
   Langkah:
	- Hapus kata "terjual"
	- Jika mengandung "rb" dikali 1000
	- Jika angka biasa → konversi integer
	- Jika kosong → 0

---

## Final Dataset Structure
| Kolom | Tipe Data |
|:-------|:-----------|
| Nama Produk | object |
| Harga Produk | int |
| Penjual | object |
| Kota Toko | object |
| Banyaknya Terjual | int |
| Rating Produk | float|

---

## Tools & Libraries
- Python
- Selenium (web automation)
- BeautifulSoup (HTML parsing)
- Pandas (dataframe dan cleaning)
- Time (delay loading)

---

## 👤 Author
Rifqi Nadhir Aziz
