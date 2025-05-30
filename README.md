# Laporan Proyek Machine Learning Terapan - Ferdita Lusiana

## Domain Proyek (Kesehatan)

Kanker adalah penyakit akibat pertumbuhan sel yang tumbuh tidak normal dan tidak terkendali di dalam tubuh. Pertumbuhan sel abnormal ini dapat merusak sel normal di sekitarnya dan di bagian tubuh yang lain. Kanker merupakan penyebab kematian kedua terbanyak di seluruh dunia. Kanker sering menyebabkan kematian karena penyakit ini umumnya tidak menimbulkan gejala pada awal perkembangannya. Kanker baru terdeteksi dan ditangani setelah mencapai stadium lanjut. Skrining atau cek kesehatan secara berkala dapat mendeteksi kanker sejak dini. Untuk mencegah kondisi ini, jalani pola hidup sehat, misalnya dengan mengonsumsi makanan bergizi seimbang, rajin berolahraga, tidak merokok, dan tidak mengonsumsi minuman beralkohol.

Pada zaman sekarang, teknologi telah berkembang pesat, salah satunya adalah teknologi *machine learning*. *machine learning* telah digunakan ke dalam berbagai bidang, salah satunya bidang kesehatan. *machine learning* mampu mendeteksi berbagai macam penyakit dengan berbagai parameter maupun faktor yang diberikan, salah satunya adalah mendeteksi cancer. Oleh sebab itu, pada proyek ini, penulis ingin memanfaatkan *machine learning* untuk mendeteksi terkena cancer pada seseorang. Penulis ingin memprediksi penyakit cancer pada responden menggunakan 6 model, yaitu *Extreme Gradient Boosting* (XGBoost), *Logistic Regression*, *K-Nearest Neighbors* (KNN),*Catboosting*,*Decision Tree*, dan *Random Forest*. Penulis menggunakan dataset dari Kaggle yang dapat diakses pada link [berikut](https://www.kaggle.com/datasets/rabieelkharoua/cancer-prediction-dataset).

## Business Understanding

### Problem Statements
Rumusan masalah dari masalah latar belakang diatas adalah:
1. faktor-faktor apa saja yang paling berpengaruh dalam memprediksi risiko kanker pada seseorang?
2.  Bagaimana mengetahui seseorang terkena kanker berdasarkan riwayat kesehatan dan aktivitas yang dilakukan?

### Goals
Berdasarkan problem statements, berikut tujuan yang ingin dicapai pada proyek ini.
1. Mengetahui  faktor-faktor yang paling berpengaruh terhadap seseorang terkena cancer.
2. Menemukan model terbaik berdasarkan akurasi tertinggi untuk memprediksi penyakit cancer pada responden.

### Solution Statement
1. faktor-faktor yang paling berpengaruh dalam memprediksi risiko kanker adalah usia, aktivitas fisik, indeks massa tubuh (BMI), dan konsumsi alkohol. Hal ini menunjukkan bahwa selain faktor alami seperti usia, gaya hidup juga memainkan peran penting dalam risiko kanker. Oleh karena itu, upaya pencegahan kanker sebaiknya difokuskan pada promosi gaya hidup sehat, seperti rutin beraktivitas fisik, menjaga berat badan ideal, dan menghindari konsumsi alkohol berlebihan.
2. Menggunakan algoritma machine learning untuk membandingkan performa model untuk mendapatkan model atau algoritma yang memiliki akurasi prediksi terbaik dalam memprediksi seseorang terkena cancer berdasarkan riwayat kesehatan dan aktivitas yang dilakukan. Menggunakan 6 model *machine learning* untuk memprediksi penyakit cancer pada responden, yaitu *Extreme Gradient Boosting* (XGBoost), *Logistik Regression*, *Decision Tree*, *K-Nearest Neighbors* (KNN), *Catboosting*, dan *Random Forest*.

## Data Understanding
Dataset Cancer Prediction yang berasal dari Kaggle merupakan dataset yang berisi 1500 entri dan 9 kolom. Dataset ini dapat diunduh dari platform [kaggle](https://www.kaggle.com/datasets/rabieelkharoua/cancer-prediction-dataset) yang dipublikasikan oleh Rabie El Kharoua kumpulan dataset ini tersedia dibawah lisensi CC BY 4.0. 


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
<img src="https://github.com/user-attachments/assets/2da0765c-e430-44a4-9226-b2b52d7f468e" alt="cek_data_duplicate" width="200">

dari hasil diatas terlihat bahwa tidak ada data yang terduplikasi.

#### mengecek missing values
<img src="https://github.com/user-attachments/assets/402cd37e-d93c-473e-8a2e-1a95946f4060" alt="cek_data_missingvelue" width="200">

dari output diatas didapati bahwa tidak terdapat missing velue pada dataset.

#### mengecek outlier
<img src="https://github.com/user-attachments/assets/f2bb8ea8-8eaf-4fb6-996f-01bdbe3e5ddf" alt="boxplot_Age" width="350">
<img src="https://github.com/user-attachments/assets/277b4056-6122-4e08-9357-dd0f128cecff" alt="boxplot_AlcoholIntak" width="350">
<img src="https://github.com/user-attachments/assets/61755c61-cc2a-452d-99d8-39296bde77fb" alt="boxplot_BMI" width="350">
<img src="https://github.com/user-attachments/assets/5efe5385-9d43-4bd6-ad14-ee81604648de" alt="boxplot_PhysicalActivity" width="350">

penjelasan:
Berdasarkan keempat fitur yang dianalisis, tidak ada indikasi outlier yang perlu ditangani. Hal ini menunjukkan bahwa data numerik dalam dataset relatif bersih dan berada dalam rentang yang wajar secara statistik maupun secara logis. Dengan demikian, tidak diperlukan proses pembersihan atau transformasi khusus terhadap outlier untuk variabel-variabel ini.

Setelah dilakukan pengecekan data duplicate,missing velue dan outlier dapat disimpulkan bahwa dataset sudah bersih maka tidak perlu dilakukan cleaning data di data preparation dan bisa dilanjutkan untuk data preprocesing.

### Deskripsi Statistik dari Data

|        | Age        | Gender     | BMI        | Smoking    | GeneticRisk | PhysicalActivity | AlcoholIntake | CancerHistory | Diagnosis  |
|--------|------------|------------|------------|------------|-------------|------------------|----------------|----------------|------------|
| count  | 1500.000000 | 1500.000000 | 1500.000000 | 1500.000000 | 1500.000000 | 1500.000000      | 1500.000000    | 1500.000000    | 1500.000000 |
| mean   | 50.320000  | 0.490667   | 27.513321  | 0.269333   | 0.508667    | 4.897929         | 2.417987       | 0.144000       | 0.371333    |
| std    | 17.640968  | 0.500088   | 7.230012   | 0.443761   | 0.678895    | 2.866162         | 1.419318       | 0.351207       | 0.483322    |
| min    | 20.000000  | 0.000000   | 15.000291  | 0.000000   | 0.000000    | 0.002410         | 0.001215       | 0.000000       | 0.000000    |
| 25%    | 35.000000  | 0.000000   | 21.483134  | 0.000000   | 0.000000    | 2.434609         | 1.210598       | 0.000000       | 0.000000    |
| 50%    | 51.000000  | 0.000000   | 27.598494  | 0.000000   | 0.000000    | 4.843416         | 2.382971       | 0.000000       | 0.000000    |
| 75%    | 66.000000  | 1.000000   | 33.850837  | 1.000000   | 1.000000    | 7.409896         | 3.585624       | 0.000000       | 1.000000    |
| max    | 80.000000  | 1.000000   | 39.958688  | 1.000000   | 2.000000    | 9.994607         | 4.987115       | 1.000000       | 1.000000    |

Fungsi `describe()` memberikan informasi statistik pada masing-masing kolom, antara lain:

- `Count` adalah jumlah sampel pada data.
- `Mean` adalah nilai rata-rata.
- `Std` adalah standar deviasi.
- `Min` yaitu nilai minimum setiap kolom.
- `25%` adalah kuartil pertama. Kuartil adalah nilai yang menandai batas interval dalam empat bagian sebaran yang sama.
- `50%` adalah kuartil kedua, atau biasa juga disebut median (nilai tengah).
-` 75%` adalah kuartil ketiga.
- `Max` adalah nilai maksimum.

Dataset terdiri dari 1.500 sampel dengan fitur numerik yang mencerminkan karakteristik pasien, kemungkinan terkait data kanker. Beberapa fitur bersifat biner, sementara yang lain menunjukkan variasi lebih besar. Rentang usia pasien berkisar antara 20–80 tahun dengan median 51, menunjukkan distribusi yang cukup merata. Nilai mean dan median yang mendekati mengindikasikan distribusi data relatif simetris, meskipun analisis lanjutan diperlukan untuk memastikan normalitas dan mendeteksi outlier.


## Exploratory Data Analysis
### Univariate Analysis

Dari variabel-variabel yang diketahui, variabel dapat dibagi menjadi 2 jenis, yaitu variabel numerikal dan variabel kategorikal. Berikut merupakan kolom-kolom yang termasuk dalam variabel numerikal maupun kategorikal. <br>
Kolom-kolom numerikal: ['Age', 'BMI', 'PhysicalActivity', 'AlcoholIntake'] <br>
Kolom-kolom kategorikal: ['Gender','Smoking', 'GeneticRisk', 'CancerHistory', 'Diagnosis'] <br>
Pertama, kita akan memvisualisasikan kolom-kolom kategorikal untuk melihat jumlah-jumlah nilai kategorikal menggunakan bar plot.

![categorical_plots](https://github.com/user-attachments/assets/68507d32-10b6-482a-a202-94beff2357b8)

Gambar di atas dapat diinterpretasikan sebagai berikut.
1. Dari `Plot Jumlah dari Jenis Kelamin`, mayoritas responden adalah pria dan sisanya adalah wanita.
2. Dari `Plot Jumlah dari Merokok`, sebagian besar responden tidak merokok, sedangkan sebagian kecil merupakan perokok.
3. Dari `Plot Jumlah dari Risiko Genetik`, mayoritas responden memiliki risiko genetik rendah terhadap kanker.
4. Dari `Plot Jumlah dari Riwayat Kanker`, sebagian besar responden tidak memiliki riwayat kanker, sedangkan sisanya memiliki riwayat tersebut.
5. Dari `Plot Jumlah dari Diagnosis Kanker`, mayoritas responden tidak terdiagnosis kanker, dan sebagian lainnya terdiagnosis positif kanker.

![histogram_plot](https://github.com/user-attachments/assets/b8a71fb7-2e76-4c6e-a20b-2a807371e663)

Gambar di atas dapat diinterpretasikan sebagai berikut.
1. Plot Histogram dari `Age`, `BMI`, dan `PhysicalActivity` memiliki distribusi yang cukup merata tanpa pola lonceng yang jelas, mengindikasikan bahwa data tersebar luas di seluruh rentang nilai yang tersedia.
2. Plot Histogram dari `Gender`, `Smoking`, `GeneticRisk`, `CancerHistory`, `AlcoholIntake`, dan Diagnosis menunjukkan bahwa data merupakan data kategorikal biner, dengan nilai yang sangat dominan pada salah satu kelas (misalnya nilai 0 lebih banyak dari 1).
3. Plot Histogram dari `Age` terlihat agak miring ke kanan, yang berarti sebagian besar responden berusia di atas rata-rata, menunjukkan dominasi kelompok usia dewasa hingga lansia dalam data ini.


### Multivariate Analysis

#### 1. Membandingkan Diagnosis Kanker Berdasarkan Jenis Kelamin

![barplot_gender](https://github.com/user-attachments/assets/a5685044-acff-4a60-ac7f-30e673238130)

Dari grafik bar yang ditampilkan, dapat disimpulkan bahwa:
1. Penyakit kanker (Diagnosis = 1) lebih banyak ditemukan pada responden perempuan dibandingkan laki-laki. Hal ini terlihat dari jumlah bar perempuan yang lebih tinggi pada kategori “Diagnosis = 1”.
2. Responden yang tidak terkena kanker (Diagnosis = 0) ini artinya responde laki-laki lebih banyak ditemukan dibanding perempuan,selisihnya lumayan jauh.

#### 2. Membandingkan Diagnosis Kanker Berdasarkan Usia

![barplot_usia](https://github.com/user-attachments/assets/35e07dda-402e-4f5f-8122-a60537088337)

Dari gambar di atas, dapat disimpulkan bahwa:
1. Seluruh responden yang terdiagnosis kanker (positif) berada pada rentang usia sekitar 30 hingga 80 tahun, dengan penyebaran lebih padat di atas usia 40 tahun.
2. Responden yang tidak terdiagnosis kanker (negatif) memiliki distribusi usia yang lebih luas, mulai dari usia 20 hingga sekitar 80 tahun, dengan sebaran cukup merata.

#### 3. Membandingkan Kebiasaan Merokok Berdasarkan Diagnosis Kanker

![barplot_smoking](https://github.com/user-attachments/assets/0808199f-19a6-4c49-9c00-66051173805b)

Dari gambar di atas, disimpulkan bahwa:
1. Mayoritas individu yang tidak merokok (warna biru) lebih banyak ditemukan pada kelompok yang tidak terkena kanker (Diagnosis = 0) dibandingkan dengan kelompok yang terkena kanker.
2. Sebaliknya, individu yang merokok (warna oranye) lebih banyak muncul pada kelompok dengan diagnosis kanker (Diagnosis = 1), menunjukkan adanya korelasi antara kebiasaan merokok dan peningkatan risiko kanker.

#### 4. Membandingkan Distribusi BMI Berdasarkan Diagnosis Kanker

![barplot_bmi](https://github.com/user-attachments/assets/3f2e2423-1f12-485d-8ee7-f041b3e52a55)

Dari gambar di atas, disimpulkan bahwa:
1. Distribusi BMI pada kelompok yang tidak terkena kanker (Diagnosis = 0) cenderung memiliki median BMI yang sedikit lebih rendah dibandingkan dengan kelompok yang terkena kanker (Diagnosis = 1).
2. Variasi BMI pada kedua kelompok relatif mirip, namun terdapat beberapa nilai BMI ekstrim (outlier) di kedua kelompok, yang menunjukkan adanya individu dengan BMI sangat rendah atau sangat tinggi.
3. Secara umum, individu dengan diagnosis kanker (positif) cenderung memiliki BMI yang sedikit lebih tinggi dibandingkan dengan individu tanpa kanker (negatif).

#### 5. Membandingkan Risiko Genetik Berdasarkan Diagnosis Kanker

![barplot_resikogenetik](https://github.com/user-attachments/assets/7308fb30-fa30-42a8-a73d-35b2303a5186)

Dari gambar di atas, disimpulkan bahwa:
1. Mayoritas individu yang tidak terdiagnosis kanker (No Cancer) memiliki risiko genetik rendah (low). Hal ini menunjukkan bahwa risiko genetik yang rendah kemungkinan berasosiasi dengan tidak adanya diagnosis kanker.
2. Sebaliknya, kelompok yang didiagnosis kanker (Cancer) memiliki distribusi risiko genetik yang lebih beragam, dengan jumlah signifikan pada kategori risiko sedang (medium) dan risiko tinggi (high).
3. Individu dengan risiko genetik tinggi (high) secara proporsional lebih banyak ditemukan pada kelompok Cancer dibandingkan kelompok No Cancer. Ini menunjukkan adanya potensi korelasi positif antara risiko genetik tinggi dan kemungkinan terkena kanker.
4. Meskipun kelompok risiko rendah tetap mendominasi dalam kedua diagnosis, proporsinya jauh lebih tinggi di kelompok No Cancer dibanding kelompok Cancer.

#### 6. Melihat Korelasi Variabel dengan Menggunakan Heatmap

![colerasi_heatmap](https://github.com/user-attachments/assets/0a172a92-5e0d-4991-9100-af7566d69e86)

Kesimpulan Heatmap Korelasi:
1. Korelasi antar fitur sangat rendah
 - Hampir semua nilai korelasi antar fitur numerik seperti Age, BMI, Physical Activity, dan Alcohol Intake berada di kisaran 0.00 – 0.03.
  - Ini menunjukkan bahwa tidak terdapat hubungan linear yang signifikan antar variabel tersebut.
2. Nilai diagonal bernilai 1
  - Korelasi antara fitur dengan dirinya sendiri adalah 1.00, yang merupakan karakteristik normal dari matriks korelasi.

## Data Preparation
Pertama, akan diubah nilai-nilai kategorikal pada data menggunakan encoder sehingga menjadi nilai-nilai numerik agar dapat dilatih dengan *machine learning*.

### Data Cleaning
Data cleaning adalah proses penting dalam analisis data dan machine learning yang bertujuan untuk memperbaiki atau menghapus data yang rusak, tidak konsisten, tidak lengkap, atau tidak relevan dari dataset agar kualitas analisis atau prediksi menjadi lebih akurat dan andal.

#### Menghapus Kolom yang tidak digunakan
<img src="https://github.com/user-attachments/assets/d155cbce-2a87-4504-ae10-83102a96e90d" alt="menghapus_duplikasi" width="200">

dari hasil diatas menunjukkan bahwa dataset dengan jumlah 1500 data artinya dataset yang dipakai tidak ada data yang terduplikasi dan bisa lanjut untuk menganalisis.

### One Hot Encoding

<img src="https://github.com/user-attachments/assets/c0e6fa60-da37-4b6d-bd84-badf46678ff7" alt="one_hot_encoding" width="200">

Kode di atas melakukan proses one-hot encoding pada kolom kategorikal yaitu Gender, Smoking, CancerHistory, dan GeneticRisk. Proses ini mengubah nilai kategori menjadi format numerik (dummy variables) agar dapat digunakan dalam model machine learning. Opsi drop_first=True digunakan untuk menghindari dummy variable trap dengan menghapus satu kategori dari setiap variabel. Setelah encoding, kolom aslinya dihapus dan data hasil transformasi siap digunakan untuk proses analisis atau pemodelan lebih lanjut.

### Data Training dan Testing

Tahapan ini dilakukan untuk membagi data menjadi 2, yaitu data training dan testing. Data training digunakan untuk melatih model dengan data yang ada, sedangkan data testing digunakan untuk menguji model yang dibuat menggunakan data yang belum dilatih. Pembagian data ini dilakukan dengan perbandingan 70% : 30% untuk data training dan data testing menggunakan `train_test_split` dari library sklearn.

### Standarisasi

Tahapan ini dilakukan agar algoritma machine learning memiliki performa lebih baik dan konvergen lebih cepat ketika dimodelkan pada data dengan skala relatif sama atau mendekati distribusi normal. Proses scaling dan standarisasi membantu untuk membuat fitur data menjadi bentuk yang lebih mudah diolah oleh algoritma dengan range 0 hingga 1 dan menyeragamkan karena memiliki satuan yang berbeda pada tiap fitur.


## Modeling

Ada 6 algoritma *Machine Learning* yang digunakan untuk membuat model, yaitu sebagai berikut.
### 1. ***Extreme Gradient Boosting* (XGBoost)**.

Algoritma ini bekerja dengan mengimplementasikan *decision tree* yang kemudian ditingkatkan dengan gradien untuk meningkatkan kecepatan dan kinerja. Kelebihan dari algoritma ini adalah memiliki performa dan efisiensi tinggi, efektif untuk dataset bberukuran besar, dan memiliki parameter regularisasi yang mampu mencegah *overfitting*. Sementara itu, kekurangan dari algoritma ini adalah membutuhkan ketelitian terhadap hyperparameter tuning untuk mencegah *overfitting* dan komputasi yang mahal serta membutuhkan memori yang besar untuk dataset berukuran besar. <br>

Pada pemodelan ini, XGBoost diimplementasikan menggunakan `XGBClassifier` dari library `xgboost` dengan memasukkan `X_train` dan `y_train` untuk melatih model, lalu menggunakan `X_test` dan `y_test` untuk menguji model dengan data testing yang tidak ada di data training. Parameter yang digunakan pada model ini adalah `max_depth` yaitu kedalaman maksimum setiap tree, `n_estimators` yaitu jumlah tree yang akan dibuat, `random_state` yaitu mengontrol seed acak yang diberikan pada setiap iterasi, `learning rate` yaitu mengatur langkah setiap iterasi ketika meminimumkan *loss function*, dan `n_jobs` yaitu mengatur jumlah CPU threads untuk menjalankan XGBoost. Pada proyek ini, parameter yang digunakan adalah `max_depth = 4`, `n_estimators = 134`, `random_state = 854`, `learning_rate = 0.01593435842863771`, `n_jobs = -1`.

### 2. ***Logistik Regresion***

Logistic Regression adalah metode statistik yang digunakan untuk memprediksi probabilitas suatu hasil biner (dua kategori) berdasarkan satu atau lebih variabel independen. Meskipun mengandung kata "regression," metode ini digunakan untuk klasifikasi, bukan regresi seperti pada linear regression. Logistic regression sering digunakan dalam pembelajaran mesin dan statistik untuk memodelkan hubungan antara variabel input (fitur) dan hasil biner. <br>

Pada pemodelan ini, *Logistik Regression* diimplementasikan menggunakan `LogisticRegression` dari library `sklearn.liniear_model` dengan memasukkan `X_train` dan `y_train` untuk melatih model, lalu menggunakan `X_test` dan `y_test` untuk menguji model dengan data testing yang tidak ada di data training. Parameter yang digunakan pada model ini adalah  `solver:sag` untuk menemukan parameter terbaik (koefisien) dalam model dengan data yang besar dan sparseness tinggi dan `n_jobs=-1` diatur ke -1, model akan menggunakan semua inti yang tersedia, sehingga mempercepat proses pelatihan.

### 3. ***Decission Tree***

Decision Tree adalah algoritma pembelajaran mesin yang digunakan untuk tugas klasifikasi dan regresi. Decision tree membagi dataset menjadi subset yang lebih kecil berdasarkan aturan keputusan yang diterapkan pada fitur input. Proses ini diulang secara rekursif, menghasilkan struktur seperti pohon. memiliki kelebihan yaitu Dapat Menangani Data Kategorikal dan Numerik,algoritma dapat bekerja dengan baik untuk berbagai jenis data tanpa perlu transformasi kompleks, cepat untuk Pelatihan dan Prediksi, dan dapat Menangkap Interaksi Non-Linear, sedangkan mempunya kelemahan yaitu Bias terhadap Fitur dengan Banyak Kategori (misalnya, kode pos) dan tidak Menangani Pola Kompleks Secara Efisien. <br>

Pada pemodelan ini, *Decision Tree* diimplementasikan menggunakan `DecisionTreeClassifier` dari library `sklearn.tree` dengan memasukkan `X_train` dan `y_train` untuk melatih model, lalu menggunakan `X_test` dan `y_test` untuk menguji model dengan data testing yang tidak ada di data training. Parameter yang digunakan pada model ini adalah `min_samples_split =14`, `max_features = None`, `max_depth = 40`, `min_samples_leaf = 30`.


### 4. ***K-Nearest Neighbors* (KNN)**

Algoritma ini bekerja dengan mengklasifikasikan titik data berdasarkan kelas mayoritas dari sejumlah k tetangga terdekatnya. Kelebihan dari algoritma ini adalah mudah dan simple untuk digunakan, tidak ada fase *lazy learning* sehingga cepat, dan efektif. Sementara itu, kekurangan dari algoritma ini adalah sensitif terhadap pemilihan k dan metrik jarak serta memiliki performa buruk untuk data berdimensi tinggi (*curse of dimensionality*). <br>

Pada pemodelan ini, KNN diimplementasikan menggunakan `KNeighborsClassifier` dari library `sklearn.neighbors` dengan memasukkan `X_train` dan `y_train` untuk melatih model, lalu menggunakan `X_test` dan `y_test` untuk menguji model dengan data testing yang tidak ada di data training. Parameter yang digunakan pada model ini adalah `n_neighbors` yaitu jumlah k tetangga. Pada proyek ini, parameter yang digunakan adalah `n_neighbors = 20`.

### 5. ***Random Forest***

Algoritma ini bekerja dengan membentuk decision trees, lalu menggunakan sampiing dengan penggantian (*bootstrapping*) dan pemilihan fitur acak untuk setiap pohon agar pohon-pohon menjadi beragam. Kelebihan dari algoritma ini adalah memiliki akurasi tinggi karena menggunakan pendekatan ensemble, mencegah *overfitting* dengan jumlah pohon yang banyak, dan mampu menangani dataset berukuran besar dan multi dimensi. Sedangkan kekurangan dari algoritma ini adalah komputasi yang besar untuk jumlah pohon yang besar dan membutuhkan memori yang besar untuk menyimpan seluruh pohon. <br>

Pada pemodelan ini, *Random Forest* diimplementasikan menggunakan `RandomForestClassifier` dari library `sklearn.ensemble` dengan memasukkan `X_train` dan `y_train` untuk melatih model, lalu menggunakan `X_test` dan `y_test` untuk menguji model dengan data testing yang tidak ada di data training. Parameter yang digunakan pada model ini adalah `n_estimators` yaitu jumlah tree yang akan dibuat, `criterion` yaitu fungsi untuk menentukan kualitas *splitting data*, `max_depth` yaitu kedalaman maksimum setiap tree, dan `random_state` yaitu mengontrol seed acak yang diberikan pada setiap iterasi. Pada proyek ini, parameter yang digunakan adalah `n_estimators = 100`, `criterion = "entropy"`, `max_depth = 10`, `random_state = 50`.

### 6. ***CatBoosting***
CatBoost mencoba memprediksi probabilitas kelas target berdasarkan fitur input dengan cara membangun model pohon keputusan secara iteratif, di mana setiap iterasi bertujuan untuk memperbaiki kesalahan model sebelumnya. Memiliki kelebihan yaitu Mengurangi Overfitting dengan Regularisasi Unik dan performa tinggi ,sedangkan memiliki kekurangan yaitu waktu training lebih lama dan memori lebih tinggi.<br>

Pada pemodelan ini, *CatBoosting* diimplementasikan menggunakan `CatBoostClassifier` dari library `catboost` dengan memasukkan `X_train` dan `y_train` untuk melatih model, lalu menggunakan `X_test` dan `y_test` untuk menguji model dengan data testing yang tidak ada di data training. Parameter yang digunakan pada model ini adalah `depth = 4`, `learning_rate = 0.0563827883242152`, `iterations = 161`, `random_strength = 7`.

### 7. Pemilihan Model

Setelah semua model dijalankan, penulis memilih algoritma *Catboosting* sebagai model terbaik yang akan digunakan sebagai solusi untuk memprediksi penyakit kanker karena model ini memiliki akurasi dan skor f1 tertinggi dibandingkan model lainnya, serta kesalahan klasifikasi pada matriks confusion yang lebih kecil dibanding model lainnya. Penjelasan lebih lengkap mengenai alasan ini ada di bagian selanjutnya, yaitu **evaluation**.

## Evaluation

Pada proyek ini, penilaian model menggunakan confusion matrix, akurasi, dan f1 score sebagai metrik evaluasi untuk masing-masing model. Akan dijelaskan terlebih dahulu bagaimana cara menggunakan confusion matrix.

### Sekilas Tentang Matriks Confusion, Akurasi, dan Skor f1

Matriks Confusion merupakan sebuah tabel untuk mengukur akurasi dari model klasifikasi. Contoh dari Matriks Confusion beserta labelnya dapat dilihat pada gambar di bawah ini. 

![confusian matrik](https://github.com/user-attachments/assets/02f6da7a-969c-4b40-bb78-9a99f2dcd2ba) <br>

Setiap baris pada matriks confusion merepresentasikan nilai sesungguhnya, sedangkan setiap kolom pada matriks confusion merepresentasikan nilai yang diprediksi. Terdapat 4 label pada matriks confusion seperti yang terlihat di gambar, yaitu TP, TN, FP, dan FN.
1. *True Positive* (TP) merupakan jumlah data pada positif yang ditebak dengan benar.
2. *True Negative* (TN) merupakan jumlah data pada negatif yang ditebak dengan benar.
3. *False Positive* (FP) merupakan jumlah data yang ditebak dengan salah karena diprediksi positif, sedangkan aslinya adalah negatif. Kesalahan ini sering disebut Error Tipe 1.
4. *False Negative* (FN) merupakan jumlah data yang ditebak dengan salah karena diprediksi negatif, sedangkan aslinya adalah positif. Kesalahan ini sering disebut Error Tipe 2.

Selanjutnya, metrik evaluasi yang digunakan berdasarkan label-label yang diketahui dari matriks confusion ada 4, yaitu sebagai berikut.
1. Akurasi (*Accuracy*) merupakan proporsi data yang berhasil diprediksi dengan benar dari seluruh data yang diprediksi. Akurasi dirumuskan sebagai <br>
![Rumus_Akurasi](https://github.com/user-attachments/assets/790eeb4f-01a9-455c-927e-e14328677eec) <br>

2. *Precision* merupakan proporsi data positif yang berhasil diprediksi dengan benar dari seluruh data yang diprediksi positif. *Precision* dirumuskan sebagai <br>
![Rumus_Precision](https://github.com/user-attachments/assets/046dc13c-5ba2-4de7-bf22-8e5c4afd031a) <br>

3. *Recall* merupakan proporsi data positif yang berhasil diprediksi dengan benar dari seluruh data yang aslinya positif. *Recall* dirumuskan sebagai <br>
![Rumus_Recall](https://github.com/user-attachments/assets/c0353cdf-08a8-452d-b218-a3fef1ac3e12) <br>

4. Skor F1 (F1 *score*) merupakan rata-rata harmonik dari *precision* dan *recall* untuk mendapatkan sebuah metrik yang seimbang. Skor F1 dirumuskan sebagai <br>
![Rumus_SkorF1](https://github.com/user-attachments/assets/9dfa59db-b969-4255-aa75-3d178a110705) <br>

### Penerapan Matriks Confusion, Akurasi, dan Skor f1

#### 1. Model XGBoost

Berikut merupakan matriks confusion, akurasi, dan skor f1 dari model XGBoost

<img src="https://github.com/user-attachments/assets/a4645924-8f56-47b9-bc58-3ae76b04393e" alt="algoritma_XGBoost" width="350">

Dari gambar di atas, terdapat 98 data diklasifikasikan salah sebagai responden cancer 
dan 32 data diklasifikasikan salah sebagai responden noncancer. Diperoleh skor F1 nya adalah 0.73 dengan akurasi ≈ 73.31%.

#### 2. Model Logisitik Regression

Berikut merupakan matriks confusion, akurasi, dan skor f1 dari model SVM

<img src="https://github.com/user-attachments/assets/2db847a5-6976-4c3f-99d5-11ff29a117ff" alt="Algoritma_logistik" width="350">

Dari gambar di atas, terdapat 130 data diklasifikasikan salah sebagai responden cancer 
dan 17 data diklasifikasikan salah sebagai responden noncancer. Diperoleh skor F1 nya adalah 0.67 dengan akurasi ≈ 67.33%.

#### 3. Model *Decision Tree*

Berikut merupakan matriks confusion, akurasi, dan skor f1 dari model*Decision Tree*

<img src="https://github.com/user-attachments/assets/c9dd59fc-70cb-4a75-b443-29cdec8f4607" alt="Algoritma_decision_tree" width="350">

Dari gambar di atas, terdapat 87 data diklasifikasikan salah sebagai responden cancer 
dan 48 data diklasifikasikan salah sebagai responden noncancer. Diperoleh skor F1 nya adalah 0.70 dengan akurasi ≈ 70.00%.

#### 4. Model KNN

Berikut merupakan matriks confusion, akurasi, dan skor f1 dari model KNN

<img src="https://github.com/user-attachments/assets/d81ed2a9-ec10-4351-87f4-a2103505a165" alt="algoritma_knn" width="350">

Dari gambar di atas, terdapat 123 data diklasifikasikan salah sebagai responden cancer 
dan 44 data diklasifikasikan salah sebagai responden noncancer. Diperoleh skor F1 nya adalah 0.63 dengan akurasi ≈ 62.89%.

#### 5. Model *Random Forest*

Berikut merupakan matriks confusion, akurasi, dan skor f1 dari model *Random Forest*

<img src="https://github.com/user-attachments/assets/0225c335-45a8-48e4-b40f-bc5ddab24542" alt="algoritma-randomforest" width="350">

Dari gambar di atas, terdapat 98 data diklasifikasikan salah sebagai responden cancer 
dan 41 data diklasifikasikan salah sebagai responden noncancer. Diperoleh skor F1 nya adalah 0.69 dengan akurasi ≈ 69.11%.

#### 6. Model *CatBoosting**

Berikut merupakan matriks confusion, akurasi, dan skor f1 dari model *Catboosting*

<img src="https://github.com/user-attachments/assets/020a60c5-cd59-4573-b2f7-81c77a274150" alt="algoritma_catboost" width="350">

Dari gambar di atas, terdapat 97 data diklasifikasikan salah sebagai responden cancer 
dan 29 data diklasifikasikan salah sebagai responden noncancer. Diperoleh skor F1 nya adalah 0.72 dengan akurasi ≈ 72.00%.

#### Hasil Evaluasi
Dari seluruh akurasi yang diketahui dari keenam model, dibentuk bar plot untuk melihat perbandingan nilai akurasi model sebagai berikut. 

![hasil_evaluasi](https://github.com/user-attachments/assets/93c7fb3b-3342-49b6-87b8-e9d507984151) <br>

Berdasarkan visualisasi dan hasil evaluasi masing-masing model, Catboost menunjukkan performa terbaik. Hal ini ditunjukkan oleh skor akurasi dan skor F1 yang tertinggi, serta jumlah kesalahan klasifikasi yang paling rendah, khususnya dalam mendeteksi kasus Cancer.

![catboost_diagnosa_kanker](https://github.com/user-attachments/assets/fb0abd44-e236-45f5-95df-567bf61b4d5a) <br>

Berdasarkan hasil analisis menggunakan model CatBoost, faktor-faktor yang paling berpengaruh dalam memprediksi risiko kanker adalah usia, aktivitas fisik, indeks massa tubuh (BMI), dan konsumsi alkohol. Hal ini menunjukkan bahwa selain faktor alami seperti usia, gaya hidup juga memainkan peran penting dalam risiko kanker. Oleh karena itu, upaya pencegahan kanker sebaiknya difokuskan pada promosi gaya hidup sehat, seperti rutin beraktivitas fisik, menjaga berat badan ideal, dan menghindari konsumsi alkohol berlebihan.

## Kesimpulan: 
1. Berdasarkan data yang diperoleh, menunjukan bahwa faktor-faktor yang paling berpengaruh dalam memprediksi risiko kanker seseorang adalah usia, aktivitas fisik, indeks massa tubuh (BMI), dan konsumsi alkohol. Hal ini menunjukkan bahwa selain faktor alami seperti usia, gaya hidup juga memainkan peran penting dalam risiko kanker. Oleh karena itu, upaya pencegahan kanker sebaiknya difokuskan pada promosi gaya hidup sehat, seperti rutin beraktivitas fisik, menjaga berat badan ideal, dan menghindari konsumsi alkohol berlebihan.
2. Setelah menguji data menggunakan 6 model *machine learning*, yaitu ***Extreme Gradient Boosting* (XGBoost)**, ***Logistik Regression***,***Decision Tree*** , ***K-Nearest Neighbors* (KNN)**, ***CatBoosting*** dan ***Random Forest*** untuk mendeteksi cancer, diperoleh model ***CatBoosting*** merupakan model terbaik dibandingkan model lainnya berdasarkan skor akurasi, skor F1 , dan jumlah kesalahan klasifikasi yang paling sedikit yaitu 72.00%.

# Referensi
1. Penjelasan mengenai penyakit kanker diambil dari website alodokter https://www.alodokter.com/penyakit-kanker








