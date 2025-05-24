# Laporan Proyek Machine Learning - Ferdita Lusiana

## Domain Proyek (Kesehatan)

Kanker adalah penyakit akibat pertumbuhan sel yang tumbuh tidak normal dan tidak terkendali di dalam tubuh. Pertumbuhan sel abnormal ini dapat merusak sel normal di sekitarnya dan di bagian tubuh yang lain. Kanker merupakan penyebab kematian kedua terbanyak di seluruh dunia. Kanker sering menyebabkan kematian karena penyakit ini umumnya tidak menimbulkan gejala pada awal perkembangannya. Kanker baru terdeteksi dan ditangani setelah mencapai stadium lanjut. Skrining atau cek kesehatan secara berkala dapat mendeteksi kanker sejak dini. Untuk mencegah kondisi ini, jalani pola hidup sehat, misalnya dengan mengonsumsi makanan bergizi seimbang, rajin berolahraga, tidak merokok, dan tidak mengonsumsi minuman beralkohol.

Pada zaman sekarang, teknologi telah berkembang pesat, salah satunya adalah teknologi *machine learning*. *machine learning* telah digunakan ke dalam berbagai bidang, salah satunya bidang kesehatan. *machine learning* mampu mendeteksi berbagai macam penyakit dengan berbagai parameter maupun faktor yang diberikan, salah satunya adalah mendeteksi cancer. Oleh sebab itu, pada proyek ini, penulis ingin memanfaatkan *machine learning* untuk mendeteksi terkena cancer pada seseorang. Penulis ingin memprediksi penyakit cancer pada responden menggunakan 6 model, yaitu *Extreme Gradient Boosting* (XGBoost), *Logistic Regression*, *K-Nearest Neighbors* (KNN),*Catboosting*,*Decision Tree*, dan *Random Forest*. Penulis menggunakan dataset dari Kaggle yang dapat diakses pada link [berikut](https://www.kaggle.com/datasets/rabieelkharoua/cancer-prediction-dataset).

## Business Understanding

### Problem Statements
Rumusan masalah dari masalah latar belakang diatas adalah:
1.  Dari berbagai faktor yang ada, Faktor apa saja yang paling mempengaruhi seseorang di diagnosis menderita cancer?
2.  Bagaimana mengetahui seseorang terkena kanker berdasarkan rekam medis ?
3.  Bagaimana mengetahui seseorang terkena kanker berdasarkan riwayat kesehatan dan aktivitas yang dilakukan?

### Goals
Berdasarkan problem statements, berikut tujuan yang ingin dicapai pada proyek ini.
1. Mengetahui  faktor tiga faktor yang paling berpengaruh terhadap terkena seseorang terkena cancer.
2. Mengetahui faktor-faktor yang terkena penyakit cancer berdasarkan rekam medis.
3. Menemukan model terbaik berdasarkan akurasi tertinggi untuk memprediksi penyakit cancer pada responden.

### Solution Statement

1.   analisis pada data untuk memahami fitur-fitur yang mempengaruhi orang terkena cancer, dengan menerapkan teknik visualisasi data dan deskripsi statistik data mengetahui korelasi antar fitur dan memahami hubungan antara data target (label) dan fitur lainnya.
2.   Menggunakan algoritma machine learning untuk membandingkan performa model untuk mendapatkan model atau algoritma yang memiliki akurasi prediksi terbaik dalam memprediksi seseorang terkena cardiovascular berdasarkan riwayat kesehatan dan aktivitas yang dilakukan. Menggunakan 6 model *machine learning* untuk memprediksi penyakit cancer pada responden, yaitu *Extreme Gradient Boosting* (XGBoost), *Logistik Regression*, *Decision Tree*, *K-Nearest Neighbors* (KNN), *Catboosting*, dan *Random Forest*.
3. Menggunakan confusion matrix dan f1 score pada masing-masing model *machine learning* untuk menemukan model terbaik berdasarkan akurasi tertinggi.

## Data Understanding


### Informasi Keterangan variabel pada data
Dataset ini memiliki 9 variabel dengan keterangan sebagai berikut.
| Nama Variabel      | Keterangan                                                                   |
| ------------------ | ----------------------------------------------------------------------- |
| `Age`              | Usia responden (dalam tahun).                                           |
| `Gender`           | Jenis kelamin responden (0 = Perempuan, 1 = Laki-laki).                 |
| `BMI`              | Indeks Massa Tubuh (Body Mass Index), indikator status berat badan.     |
| `Smoking`          | Status merokok (0 = Tidak merokok, 1 = Merokok).                        |
| `GeneticRisk`      | Risiko genetik terhadap kanker (0 = Tidak ada, 1 = Rendah, 2 = Tinggi). |
| `PhysicalActivity` | Tingkat aktivitas fisik harian (dalam jam atau skor kuantitatif).       |
| `AlcoholIntake`    | Konsumsi alkohol (dalam satuan tertentu, kemungkinan skor/level).       |
| `CancerHistory`    | Riwayat kanker dalam keluarga (0 = Tidak ada, 1 = Ada).                 |
| `Diagnosis`        | Hasil diagnosis kanker (0 = Negatif, 1 = Positif).                      |

| Jumlah Baris | Jumlah Kolom 
| ------ | ------ 
| 1500 | 9 

data yang digunakan diawal sebanyak 1500 data dengan 9 kolom

#### mengecek data duplicate
"C:\Users\Lenovo\Downloads\Submission-Prediktive-Analytic\Gambar\cek_data_duplicate.jpg"


