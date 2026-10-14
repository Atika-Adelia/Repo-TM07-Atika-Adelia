# Repo-TM07-Atika-Adelia

# Replikasi Parsial: Gradient-Boosted Tree untuk Prediksi Penyakit Kardiovaskular dengan Apache Spark

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<USERNAME>/<REPO>/blob/main/Replikasi_Parsial_GBT_Cardiovascular_Spark.ipynb)

Tugas Eksplorasi Mandiri, mata kuliah **Mahadata / Big Data (IF25-40402)**, Institut Teknologi Sumatera.

| | |
|---|---|
| **Nama / NIM** | **Atika Adelia** / **123140172** |
| **Kelas** | **Mahadata** |
| **Tingkat replikasi** | Parsial: satu model (Gradient-Boosted Tree), Spark mode lokal di Google Colab |


## Ringkasan

Repositori ini berisi notebook yang mereplikasi sebagian eksperimen pada artikel di bawah: membangun pengklasifikasi **Gradient-Boosted Tree (GBT)** dengan **PySpark MLlib** untuk memprediksi ada atau tidaknya penyakit kardiovaskular (`cardio` = 1/0), lalu membandingkan hasilnya (AUC-ROC, accuracy, precision, recall, F1) dengan angka yang dilaporkan artikel.

Empat model lain pada artikel (Logistic Regression, Decision Tree, SVM, Random Forest) **tidak** direplikasi. Alur kerja, hiperparameter baseline, dan metrik dibuat sama dengan artikel; bagian yang tidak dirinci artikel ditandai sebagai asumsi di dalam notebook.

## Artikel acuan

Gupta, Y. K., & Kumari, S. (2021). Performance evaluation of distributed machine learning for cardiovascular disease prediction in Spark. In *2021 5th International Conference on Trends in Electronics and Informatics (ICOEI)* (pp. 1506–1512). IEEE. https://doi.org/10.1109/ICOEI51242.2021.9452955

## Dataset

Ulianova, S. (n.d.). *Cardiovascular disease dataset* [Data set]. Kaggle. https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset

Dataset **tidak disertakan** dalam repositori ini. Notebook mengunduhnya otomatis dengan `kagglehub` (cadangan: unggah manual berkas `cardio_train.csv`). Ikuti ketentuan lisensi yang tertera pada halaman dataset.

## Struktur repositori

```
.
├── icoei51242.2021.9452955.pdf # file .pdf artikel
├── TugasMandiri_Atika_Adelia_123140172.ipynb     # notebook utama
├── README.md
└── tugasmandiri_atika_adelia_123140172.py        # eksplorasi versi python                                            
                          
```

## Cara menjalankan

Notebook dirancang untuk **Google Colab** (menggunakan perintah `!apt-get`, `!pip`, dan `google.colab.files`).

1. Buka notebook melalui badge **Open In Colab** di atas, atau unggah berkas `.ipynb` ke Colab.
2. Pakai runtime CPU/GPU.
3. Pilih **Runtime → Run all**. Sel pertama memasang Java 17 dan pustaka Python (sekitar 1–2 menit).
4. Bila unduhan Kaggle otomatis gagal, notebook akan menampilkan kotak unggah. Unduh `cardio_train.csv` dari halaman dataset, lalu unggah pada kotak tersebut.
5. Setelah selesai, berkas hasil berada di `/content/results` (panel *Files* di Colab). Unduh folder itu bila ingin menyimpannya ke repositori.


## Alur notebook

| Tahap pada artikel | Bagian notebook |
|---|---|
| Loading dataset | 4. Memuat dataset |
| Eksplorasi data | 5. EDA |
| Data cleaning | 6. Pembersihan data |
| Data pre-processing (`VectorAssembler` + `StandardScaler`) | 7. Praproses data |
| Pembagian latih/uji 70/30 | 8. Pembagian data |
| GBT `maxIter=75`, `maxDepth=3` (Gambar 7 artikel) | 9. Model baseline, 10. Evaluasi |
| `ParamGridBuilder` + `CrossValidator` 5-fold | 11. Tuning, 12. Evaluasi hasil tuning |
| Perbandingan dengan artikel | 13. Perbandingan |
| Analisis tambahan | 14. Kepentingan fitur, 15. Catatan dan inkonsistensi artikel |


## Lisensi

Digunakan untuk keperluan akademik. Dataset tunduk pada lisensi di halaman Kaggle.
