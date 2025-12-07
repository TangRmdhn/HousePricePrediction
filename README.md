# 🏠 House Price Prediction (King County)

Proyek ini bertujuan untuk memprediksi harga rumah di wilayah King County, USA (termasuk Seattle) menggunakan algoritma Machine Learning. Proyek ini mencakup tahapan *end-to-end* mulai dari eksplorasi data, pembersihan data, rekayasa fitur (*feature engineering*), hingga evaluasi model.

## 📊 Tentang Dataset

Dataset yang digunakan adalah **King County House Sales** yang diperoleh dari Kaggle. Data ini memuat informasi penjualan rumah antara bulan Mei 2014 hingga Mei 2015.

**Link Dataset:** [Kaggle - House Sales in King County, USA](https://www.kaggle.com/datasets/harlfoxem/housesalesprediction)

### Fitur Utama:
* `price`: Harga jual rumah (Target Variable).
* `sqft_living`: Luas bangunan (dalam kaki persegi).
* `bedrooms` & `bathrooms`: Jumlah kamar tidur dan kamar mandi.
* `grade`: Nilai kualitas konstruksi dan desain (skala 1-13).
* `yr_built`: Tahun rumah dibangun.
* `waterfront` & `view`: Indikator pemandangan air atau view bagus.
* Dan fitur lainnya seperti `floors`, `condition`, `zipcode`, dll.

## 🛠️ Alur Kerja (Workflow)

1.  **Data Loading & Exploration:** Mengunduh dataset menggunakan `kagglehub` dan memeriksa struktur data serta korelasi antar variabel.
2.  **Data Cleaning:** Menghapus kolom yang tidak relevan (`id`) dan menangani *missing values*.
3.  **Feature Engineering:**
    * **Date Parsing:** Memecah kolom `date` menjadi `year_sold` dan `month_sold`.
    * **House Age:** Menghitung umur rumah saat terjual (`year_sold - yr_built`).
    * **Renovation Status:** Mengubah `yr_renovated` menjadi fitur biner `is_renovated` (1 jika pernah renovasi, 0 jika tidak).
4.  **Modeling:** Melatih model menggunakan dua algoritma berbeda untuk membandingkan performa.
5.  **Evaluation:** Menggunakan metrik **R-Squared ($R^2$)** dan **RMSE (Root Mean Squared Error)**.

## 📈 Hasil Evaluasi Model

Berikut adalah perbandingan performa antara model Linear Regression dan Random Forest:

| Model | R-Squared (Akurasi) | RMSE (Rata-rata Error) |
| :--- | :--- | :--- |
| **Linear Regression** | ~0.70 (70%) | ~$212,539 |
| **Random Forest** | **~0.85 (85%)** | **~$150,601** |

**Kesimpulan:** Model **Random Forest Regressor** bekerja jauh lebih baik dibandingkan Linear Regression karena mampu menangkap pola non-linear pada data harga rumah.

## 🔍 Insight Penting

Berdasarkan analisis *Feature Importance* dari model Random Forest, faktor-faktor yang paling mempengaruhi harga rumah di King County adalah:
1.  **Grade:** Kualitas konstruksi bangunan.
2.  **Sqft Living:** Luas area bangunan.
3.  **Lat (Latitude):** Lokasi geografis (posisi utara/selatan wilayah).

## 💻 Cara Menjalankan

1.  **Persiapan Library**
    Pastikan Anda memiliki library berikut:
    ```bash
    pip install pandas numpy scikit-learn matplotlib seaborn kagglehub
    ```

2.  **Jalankan Notebook**
    Buka file `House_Price_Prediction.ipynb` menggunakan Jupyter Notebook, Google Colab, atau VS Code, lalu jalankan semua sel secara berurutan.

---
*Project dikembangkan oleh Bintang Ramadhan sebagai portofolio Data Science & Machine Learning.*
