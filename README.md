# Belajar Membangun Machine Learning Project
Submission kelas Membangun Proyek Machine Learning (Laskar AI &amp; Dicoding)
Proyek ini merupakan bagian dari submission akhir untuk kelas Belajar Membangun Machine Learning Project (BMLP). Terdiri dari dua bagian utama:

✅ Klasifikasi — Membangun model prediksi untuk memecahkan permasalahan klasifikasi.

✅ Clustering — Melakukan segmentasi pelanggan dengan teknik unsupervised learning.

🧠 1. Klasifikasi: Prediksi Dropout Mahasiswa
Deskripsi
Proyek klasifikasi ini bertujuan untuk memprediksi apakah seorang mahasiswa akan dropout berdasarkan berbagai fitur akademik dan demografis.

Alur Pengerjaan
Data Understanding & EDA

Menampilkan distribusi dropout, persebaran nilai akademik, dan korelasi antar fitur.

Preprocessing

Encoding kategorikal (LabelEncoder), normalisasi numerikal.

Penanganan missing values.

Modeling

Model yang digunakan: RandomForestClassifier.

Pipeline scikit-learn dibangun secara end-to-end.

Evaluasi

Menggunakan metrik: accuracy, precision, recall, F1-score, confusion matrix.

Deployment

Pipeline disimpan sebagai file .pkl menggunakan joblib.

Label encoder disimpan secara terpisah.

Output
final_model_pipeline.pkl

label_encoder.pkl

📈 2. Clustering: Segmentasi Pelanggan
Deskripsi
Proyek ini bertujuan untuk membagi pelanggan menjadi beberapa segmen berdasarkan perilaku pembelian menggunakan metode Unsupervised Learning (K-Means Clustering).

Alur Pengerjaan
Data Preparation & EDA

Menyusun RFM (Recency, Frequency, Monetary).

Visualisasi distribusi dan outlier handling.

Preprocessing

Menggunakan PowerTransformer untuk normalisasi.

Clustering

Menentukan jumlah klaster optimal menggunakan Elbow Method & Silhouette Score.

Algoritma: KMeans.

Interpretasi Klaster

Analisis segmentasi berdasarkan nilai RFM.

Output
Visualisasi hasil klaster (scatter plot dan pairplot).

Penamaan segmen berdasarkan profil pelanggan.
