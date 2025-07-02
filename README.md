# Belajar Membangun Machine Learning Project
Submission kelas Membangun Proyek Machine Learning (Laskar AI &amp; Dicoding)
Proyek ini merupakan bagian dari submission akhir untuk kelas Belajar Membangun Machine Learning Project (BMLP). 
Proyek ini bertujuan untuk memahami pola pengeluaran masyarakat Indonesia melalui dua pendekatan utama:

Clustering  — Untuk mengelompokkan masyarakat berdasarkan karakteristik pengeluaran mereka.

Classification — Untuk membangun model prediktif yang dapat mengklasifikasikan data baru ke dalam segmen yang telah terbentuk.

📊 1. Analisis & Clustering Data Pengeluaran
🔹 Dataset Awal
Data bersumber dari Kaggle - Indonesia Household Expenditure. Fitur yang digunakan meliputi:

prov: Provinsi

pengeluaran: Total pengeluaran

tahun: Tahun pengeluaran

peng_log: Log dari pengeluaran (untuk normalisasi distribusi)

🔹 Preprocessing
Cleaning: Memastikan tidak ada missing values.

Transformasi log pada fitur pengeluaran agar distribusi lebih normal.

Encoding data kategorikal.

🔹 Clustering
Metode clustering yang digunakan adalah K-Means.

Preprocessing: Menggunakan PowerTransformer untuk mengurangi skewness.

Penentuan jumlah cluster optimal dilakukan dengan:

Elbow Method (Inertia)

Silhouette Score

🔹 Hasil Clustering
Terbentuk tiga segmen masyarakat berdasarkan pola pengeluaran.

Segmentasi mencerminkan kelompok dengan:

Pengeluaran rendah

Pengeluaran sedang

Pengeluaran tinggi

🔹 Analisis Tiap Klaster
Dilakukan eksplorasi terhadap:

Distribusi numerik (pengeluaran, tahun)

Distribusi berdasarkan provinsi

Rata-rata pengeluaran per cluster

🤖 2. Klasifikasi Hasil Cluster
Setelah segmentasi terbentuk, kita membangun model klasifikasi untuk memprediksi klaster berdasarkan fitur numerik.

🔹 Dataset
Dataset hasil_clustering.csv yang merupakan hasil akhir dari proses clustering.

🔹 Fitur yang digunakan:
peng (pengeluaran)

tahun

peng_log (pengeluaran log)

Target: Cluster (hasil dari K-Means)

🔹 Preprocessing:
StandardScaler digunakan untuk penyesuaian skala fitur numerik.

SelectKBest digunakan untuk feature selection berbasis ANOVA F-score.

🔹 Algoritma yang digunakan:
Logistic Regression

K-Nearest Neighbors (KNN)

🔹 Evaluasi Model Awal:
Model	Train Accuracy	Test Accuracy	Train F1	Test F1
Logistic Regression	0.9928	0.9934	0.9928	0.9934
KNN (k=15)	0.9953	0.9956	0.9953	0.9956

Logistic Regression: Stabil, cepat, dan akurat tanpa tuning ekstrem.

KNN: Akurat namun memerlukan tuning n_neighbors agar tidak overfit.

🔹 Tuning Model:
Dilakukan GridSearchCV dan RandomizedSearchCV untuk optimasi hyperparameter:

Logistic Regression: C, solver, max_iter

KNN: n_neighbors, p, weights

🔹 Evaluasi Setelah Tuning:
Model	Train Accuracy	Test Accuracy	Train F1	Test F1
Logistic Regression	0.9986	0.9967	0.9986	0.9967
KNN (tuned)	0.9953	0.9945	0.9953	0.9945

🔹 Learning Curve:
Learning curve digunakan untuk memvisualisasikan kestabilan model seiring bertambahnya data latih.

🔍 Analisis Perbandingan Model
Logistic Regression:

Kelebihan: Stabil, cepat, dan hasil sangat akurat.

Kelemahan: Kurang fleksibel untuk data non-linear.

KNN:

Kelebihan: Sangat akurat jika parameter optimal.

Kelemahan: Rentan overfitting dan lambat saat inferensi data besar.

📈 Visualisasi Tambahan
Confusion matrix untuk kedua model.

Learning curve untuk masing-masing algoritma.

Distribusi klaster berdasarkan fitur numerik dan kategorikal.

✅ Rekomendasi Lanjutan
Coba model lain: SVM, Random Forest, XGBoost untuk membandingkan performa.

Tambahkan fitur baru (feature engineering) untuk meningkatkan daya prediksi model.

Lakukan validasi silang dengan data tahun berbeda untuk uji generalisasi.

Kembangkan model klasifikasi menjadi API untuk digunakan secara real-time.
