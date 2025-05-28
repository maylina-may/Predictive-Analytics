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

Pada tahap ini Univariate Analysis, dilakukan analisis distribusi fitur kategorikal (gender, race/ethnicity, parental level of education, lunch, test preparation course) dengan hitung jumlah dan presentase kategori, dan juga divisualisasikan dengan diagram batang. Untuk fitur numerik (math score, reading score, dan writing score) distribusi data divisualisasikan dengan histrogram.

- **Fitur Kategorikal**:
  - ![univariate categorical gender](https://github.com/user-attachments/assets/bd115918-10cb-4220-b3a3-85e81f5b99d2)
    
    Berdasarkan analisis, distribusi fitur gender menunjukkan female        (51,8%) dan male (48,2%), dengan female menjadi kategori yang lebih     dominan dibandingkan dengan male.

  - ![univariate categorical race(ethnicity)](https://github.com/user-attachments/assets/40d45898-d65f-4de3-bb5a-d48982fccd8d)
    
    Fitur race/ethnicity menunjukkan bahwa grup yang paling banyak adalah grup C, diikuti oleh grup D, grup B, grub E, hingga paling sedikit adalah grup A.

  - ![univariate categorical parental level of education](https://github.com/user-attachments/assets/d828e1d7-eb68-4d9b-95b3-f121a981c85b)
    
    Fitur parental level of education menunjukkan bahwa tingkat pendidikan orang tua yang paling umum adalah some college, diikuti oleh associate's degree, dan seterusnya.

  - ![univariate categorical lunch](https://github.com/user-attachments/assets/169a3474-de9f-47df-8a9c-fae01fcdc52e)

    Fitur lunch menunjukkan bahwa kategori standard memiliki jumlah sampel/persentase yang lebih tinggi dibandingkan dengan free/reduced, yang berarti mayoritas siswa memiliki tipe makan siang kategori standard.
    
  - ![univariate categorical test preparation course](https://github.com/user-attachments/assets/cdd1324f-6f0e-4e65-9b21-612731932f5d)

    Fitur test preparation course menunjukkan bahwa kategori none memiliki jumlah sampel/persentase paling tinggi dibandingkan dengan completed. Ini berarti mayoritas siswa tidak mengikuti kursus persiapan ujian.

- **Fitur Numerik**:
  - ![univariate numerik](https://github.com/user-attachments/assets/383f3d51-032d-4a81-8536-dc17cd886aac)

