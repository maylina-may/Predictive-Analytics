# 🕵️‍♀️ Laporan Proyek Machine Learning - Maylina Nur'aini

---

## 📚 Domain Proyek : Pendidikan

Pendidikan merupakan pilar penting dalam pembangunan suatu bangsa. Salah satu indikator keberhasilan pendidikan adalah capaian akademik siswa, seperti skor ujian matematika. Namun, pencapaian tersebut tidak hanya dipengaruhi oleh faktor intelektual semata, melainkan juga oleh latar belakang demografis, sosial, dan dukungan lingkungan belajar.

Proyek ini memanfaatkan dataset Students Performance in Exams dari Kaggle untuk mengeksplorasi dan menganalisis faktor-faktor yang paling berpengaruh terhadap skor matematika siswa. Dengan pendekatan analitik dan pemodelan prediktif, proyek ini diharapkan dapat memberikan wawasan bagi pendidik dan pembuat kebijakan dalam meningkatkan kualitas pembelajaran dan hasil akademik siswa secara lebih tepat sasaran.

---

## 📊 Business Understanding

### ❓ Problem Statements

1. Faktor-faktor apa yang memiliki dampak paling signifikan terhadap skor matematika siswa?
2. Bagaimana kita dapat memprediksi skor matematika siswa menggunakan data yang tersedia dan model machine learning mana yang memberikan prediksi terbaik?

### 🎯 Goals

1. Mengidentifikasi faktor-faktor demografis dan pendidikan utama yang berkorelasi dengan kinerja matematika siswa dan memahami hubungannya.
2. Membangun dan mengevaluasi beberapa model machine learning untuk memprediksi skor matematika siswa dan mengidentifikasi model dengan performa terbaik berdasarkan Mean Squared Error (MSE).

### 🛠️ Solution statements

1. Menggunakan algoritma **KNeighborsRegressor**, **RandomForestRegressor**, dan **AdaBoostRegressor** untuk membandingkan kinerja setiap model dalam memprediksi kinerja finansial perusahaan berdasarkan pengeluaran di departemen R&D, Administrasi, dan Marketing.
2. Melakukan evaluasi model menggunakan **Mean Squared Error (MSE)** untuk membandingkan keakuratan prediksi setiap model, dan memilih model yang memberikan MSE terkecil sebagai model terbaik untuk memprediksi kinerja finansial perusahaan.

## 🗂️ Data Understanding

- **Sumber data**: [Kaggle - 1000 Companies Profit Dataset] https://www.kaggle.com/datasets/spscientist/students-performance-in-exams
- **Jumlah data**: 1000 baris, 8 kolom (fitur asli), yaitu R&D Spend, Administration, Marketing Spend, Profit, dan State.
- **Kondisi data**:
  - Tidak ada missing value ✅
  - Tidak terdapat data duplikat ✅
  - Berdasarkan visualisasi boxplot, terindikasi adanya beberapa nilai ekstrem pada kolom **reading score** dan **writing score**. Namun, perhitungan berdasarkan metode IQR tidak mendeteksi adanya outlier pada kolom-kolom tersebut.

### 📌 Variabel pada 1000 Students Performance in Exams adalah sebagai berikut:

- **gender:** Jenis kelamin siswa (categorical).
- **race/ethnicity:** Kelompok ras atau etnis siswa (categorical).
- **parental level of education:** Tingkat pendidikan orang tua siswa (categorical).
- **lunch:** Tipe makan siang yang didapat siswa (standard atau free/reduced) (categorical).
- **test preparation course:** Apakah siswa mengikuti kursus persiapan ujian (completed atau none) (categorical).
- **math score:** Skor matematika siswa (numerical).
- **reading score:** Skor membaca siswa (numerical).
- **writing score:** Skor menulis siswa (numerical).

### 📝 Exploratory Data Analysis (EDA)

#### 1. EDA - Univariate Analysis:

Pada tahap ini Univariate Analysis, dilakukan analisis distribusi fitur kategorikal (gender, race/ethnicity, parental level of education, lunch, test preparation course) dengan hitung jumlah dan presentase kategori, dan juga divisualisasikan dengan diagram batang. Untuk fitur numerik (math score, reading score, dan writing score) distribusi data divisualisasikan dengan histrogram.

- **Fitur Kategorikal**:

![univariate categorical gender](https://github.com/user-attachments/assets/bd115918-10cb-4220-b3a3-85e81f5b99d2)
    
Berdasarkan analisis, distribusi fitur gender menunjukkan female (51,8%) dan male (48,2%), dengan female menjadi kategori yang lebih dominan dibandingkan dengan male.

![univariate categorical race(ethnicity)](https://github.com/user-attachments/assets/40d45898-d65f-4de3-bb5a-d48982fccd8d)
    
Fitur race/ethnicity menunjukkan bahwa grup yang paling banyak adalah grup C, diikuti oleh grup D, grup B, grub E, hingga paling sedikit adalah grup A.

![univariate categorical parental level of education](https://github.com/user-attachments/assets/d828e1d7-eb68-4d9b-95b3-f121a981c85b)
    
Fitur parental level of education menunjukkan bahwa tingkat pendidikan orang tua yang paling umum adalah some college, diikuti oleh associate's degree, dan seterusnya.

![univariate categorical lunch](https://github.com/user-attachments/assets/169a3474-de9f-47df-8a9c-fae01fcdc52e)

Fitur lunch menunjukkan bahwa kategori standard memiliki jumlah sampel/persentase yang lebih tinggi dibandingkan dengan free/reduced, yang berarti mayoritas siswa memiliki tipe makan siang kategori standard.
    
![univariate categorical test preparation course](https://github.com/user-attachments/assets/cdd1324f-6f0e-4e65-9b21-612731932f5d)

Fitur test preparation course menunjukkan bahwa kategori none memiliki jumlah sampel/persentase paling tinggi dibandingkan dengan completed. Ini berarti mayoritas siswa tidak mengikuti kursus persiapan ujian.

- **Fitur Numerik**:

![univariate numerik](https://github.com/user-attachments/assets/383f3d51-032d-4a81-8536-dc17cd886aac)

- Math score: Distribusi cenderung normal, puncaknya di sekitar nilai tengah. Ada beberapa siswa dengan skor rendah.
- Reading score: Distribusi juga cenderung normal, dengan puncak di sekitar nilai tengah. Terlihat lebih sedikit siswa dengan skor sangat rendah dibandingkan math score.
- Writing score: Distribusi mirip dengan reading score, cenderung normal dengan puncak di sekitar nilai tengah.

#### 2. EDA - Multivariate Analysis:

Pada tahap Multivariate Analysis, dilakukan analisis untuk memahami hubungan antar fitur dalam dataset, khususnya terhadap kolom target yaitu math score. Analisis ini penting untuk mengidentifikasi fitur-fitur yang memiliki pengaruh signifikan terhadap skor matematika siswa.

Untuk fitur kategorikal seperti gender, race/ethnicity, parental level of education, lunch, dan test preparation course, digunakan diagram batang (bar plot) untuk menunjukkan distribusi nilai rata-rata math score pada masing-masing kategori. Visualisasi ini bertujuan untuk melihat apakah terdapat perbedaan signifikan skor matematika berdasarkan kelompok kategori tertentu.

Sementara itu, untuk fitur numerik seperti reading score dan writing score, hubungan antar fitur dianalisis menggunakan pairplot, yang memperlihatkan scatter plot serta distribusi antar pasangan fitur. Visualisasi ini membantu dalam mendeteksi pola linier atau hubungan korelatif antara skor matematika dan dua skor lainnya.

Selain itu, digunakan juga heatmap korelasi untuk menunjukkan tingkat hubungan (korelasi) antar fitur numerik dalam bentuk matriks warna. Heatmap ini memberikan gambaran seberapa kuat fitur reading score dan writing score berkorelasi dengan math score, serta hubungan antar sesama fitur numerik lainnya.

- **Categorical Features:**

![multivariate categorical](https://github.com/user-attachments/assets/303a0475-eb8d-4eda-90ee-c724a393e189)

- Pada fitur gender, terlihat bahwa siswa perempuan (female) cenderung memiliki rata-rata (math score) yang sedikit lebih rendah dibandingkan siswa laki-laki (male).
- Pada fitur race/ethnicity, rata-rata (math score) bervariasi antar grup. Grup (E) cenderung memiliki rata-rata (math score) tertinggi, sementara Grup (A) memiliki rata-rata (math score) terendah.
- Untuk parental level of education, siswa yang orang tuanya memiliki tingkat pendidikan lebih tinggi ("master's degree" dan "bachelor's degree") cenderung memiliki rata-rata 'math score' yang lebih tinggi dibandingkan siswa yang orang tuanya memiliki tingkat pendidikan lebih rendah ("high school" dan "some high school").
- Pada fitur lunch, siswa yang memiliki tipe makan siang 'standard' cenderung memiliki rata-rata 'math score' yang lebih tinggi dibandingkan siswa yang memiliki tipe makan siang 'free/reduced'.
- Fitur test preparation course menunjukkan bahwa siswa yang telah menyelesaikan kursus persiapan ujian ('completed') cenderung memiliki rata-rata 'math score' yang lebih tinggi dibandingkan siswa yang tidak mengikuti kursus ('none').

- **Numerical Features:**

![multivariate numerik](https://github.com/user-attachments/assets/0295a693-c8c3-4e30-bfd5-44f61d5fe495)

Berdasarkan visualisasi pairplot, terlihat adanya korelasi positif yang kuat antar fitur numerik yaitu math score, reading score, dan writing score. Hal ini ditunjukkan oleh pola sebaran data pada scatter plot yang membentuk pola linier naik, menandakan bahwa siswa dengan nilai tinggi pada satu mata pelajaran cenderung juga memiliki nilai tinggi pada mata pelajaran lainnya.

Sebaliknya, tidak ditemukan korelasi negatif yang signifikan antar fitur numerik dalam dataset ini. Hubungan antar fitur cenderung searah dan saling memperkuat, yang menunjukkan bahwa ketiga skor ini berkaitan erat dalam menggambarkan performa akademik siswa secara keseluruhan.

---

## 🧮 Data Preparation

- Data diperiksa untuk menghindari adanya duplikat, meskipun dataset asli tidak mengandung duplikasi.
- Outlier ditangani menggunakan metode **IQR (Interquartile Range)**.
- Fitur kategorikal `gender`, `race/ethnicity`, `parental level of education`, `lunch`, `test preparation course` diubah menjadi variabel numerik melalui **one-hot encoding**.
- Data dibagi menjadi data latih (train) dan data uji (test) menggunakan **train_test_split** dengan proporsi 80% untuk data latih dan 20% untuk data uji.
- Fitur numerik dinormalisasi dengan **StandardScaler**.

---

## 💹 Modeling

1. 🤖 **K-Nearest Neighbor Regressor:** Model K-Nearest Neighbors (KNN) untuk regresi memprediksi nilai target untuk sebuah data baru berdasarkan nilai target dari 'K' data terdekat di set pelatihan. Algoritma ini menghitung jarak antara data baru dan semua data pelatihan, kemudian memilih K data dengan jarak terpendek. Prediksi akhir untuk data baru adalah rata-rata dari nilai target K tetangga terdekat tersebut.
Pada implementasi ini, digunakan parameter n_neighbors=5, yang berarti model akan mempertimbangkan 5 tetangga terdekat untuk menentukan nilai prediksi.

2. 🌲 **Random Forest Regressor:** Random Forest Regressor adalah model ensemble yang membangun banyak Decision Tree secara independen pada subset data pelatihan dan subset fitur yang diambil secara acak. Setiap Decision Tree memprediksi nilai target secara terpisah. Hasil prediksi akhir dari Random Forest adalah rata-rata dari prediksi semua Decision Tree individual. Metode ini membantu mengurangi overfitting dan meningkatkan generalisasi.
Pada implementasi ini, digunakan parameter n_estimators=100 untuk membangun 100 pohon keputusan, serta random_state=42 untuk memastikan hasil yang konsisten dan dapat direproduksi.


3. ⚡ **AdaBoost Regressor :** AdaBoost Regressor (Adaptive Boosting) adalah algoritma ensemble boosting. Algoritma ini membangun model (disebut weak learner, biasanya Decision Tree sederhana) secara berurutan. Setiap model baru dilatih untuk memperbaiki kesalahan prediksi dari model sebelumnya dengan memberikan bobot lebih besar pada data yang sulit diprediksi. Prediksi akhir adalah kombinasi berbobot dari prediksi semua weak learner, di mana model yang lebih akurat memiliki bobot yang lebih tinggi. Pada implementasi ini, digunakan parameter learning_rate=0.05 untuk mengontrol kontribusi setiap weak learner terhadap prediksi akhir, serta random_state=55 untuk menjaga konsistensi hasil.

---

## 🤹‍♀️ Evaluasi Model

### 📉 Metrik Evaluasi

Dalam proyek ini, **Mean Squared Error (MSE)** digunakan untuk mengukur akurasi model dalam memprediksi skor matematika siswa. Model dengan MSE terendah pada data uji dianggap sebagai model terbaik.

Penjelasan MSE:   
MSE adalah salah satu metrik yang umum digunakan untuk evaluasi model regresi. Metrik ini mengukur rata-rata kuadrat selisih antara nilai prediksi dan nilai aktual (ground truth). Semakin kecil nilai MSE, semakin akurat model dalam memprediksi. 

### 🏆 Hasil Evaluasi Berdasarkan MSE

![evaluasi modell](https://github.com/user-attachments/assets/1e740c18-a8a9-4bf0-acf4-8adc7452811f)

- Random Forest: Memiliki MSE training paling rendah (5.2953) tetapi MSE testing paling tinggi (1193.5052). Ini menunjukkan overfitting parah.
- KNN: Memiliki MSE training (35.639899) yang lebih tinggi dari RF tetapi MSE testing (1165.454472) yang sedikit lebih rendah dari RF. Ini juga menunjukkan overfitting.
- Boosting: Memiliki MSE training (44.512746) tertinggi tetapi MSE testing (681.897012) paling rendah.
Jadi, Boosting adalah model yang paling baik dalam memprediksi skor matematika pada data yang belum dilihat (data test), meskipun secara keseluruhan akurasi prediksinya (dalam hal MSE) masih bisa ditingkatkan.
 
### 💡 Hasil Evaluasi Berdasarkan Data Aktual

1. **Random Forest:** 36.2
2. **K-Nearest Neighbor:** 36.0
3. **Boosting:** 50.5

Secara keseluruhan dari ketiga model yang telah diuji, Boosting adalah algoritma yang dapat dipilih untuk melakukan suatu prediksi karena, memiliki performa tinggi yang dapat memberikan hasil yang paling akurat untuk memprediksi skor matematika siswa 🔥.

---
