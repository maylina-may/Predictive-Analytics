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
  - Terdeteksi outlier pada kolom **reading score** dan  
    **writing score** 🧐

### 🔍 Variabel pada 1000 Students Performance in Exams adalah sebagai berikut:

- **gender:** Jenis kelamin siswa (categorical).
- **race/ethnicity:** Kelompok ras atau etnis siswa (categorical).
- **parental level of education:** Tingkat pendidikan orang tua siswa (categorical).
- **lunch:** Tipe makan siang yang didapat siswa (standard atau free/reduced) (categorical).
- **test preparation course:** Apakah siswa mengikuti kursus persiapan ujian (completed atau none) (categorical).
- **math score:** Skor matematika siswa (numerical).
- **reading score:** Skor membaca siswa (numerical).
- **writing score:** Skor menulis siswa (numerical).

### 📝 Exploratory Data Analysis (EDA)

#### 1. Univariate Analysis:
- **Fitur Kategorikal**:

Distribusi sampel pada fitur kategorikal gender menunjukkan female (51,8%) dan male (48,2%), dengan female menjadi kategori yang lebih dominan dibandingkan dengan male. ![![univariate categorical](https://github.com/user-attachments/assets/44f3c499-0bce-41cb-bb91-467b033d44cb)
]




- **Fitur Numerik**:
