# LAPORAN PROYEK MACHINE LEARNING - TRI RAMDHANY
## Latar Belakang
 Pasar cryptocurrency telah mengalami pertumbuhan pesat dalam beberapa tahun terakhir, dengan semakin banyaknya jenis aset digital yang diperkenalkan dan diperdagangkan. Salah satu aset yang menonjol adalah Solana (SOL), sebuah cryptocurrency yang dikenal dengan kemampuan skalabilitas tinggi dan kecepatan transaksi yang unggul. Sebagai salah satu dari 10 besar cryptocurrency berdasarkan kapitalisasi pasar, Solana menarik perhatian baik dari investor ritel maupun institusional.
 
Namun, volatilitas tinggi yang menjadi ciri khas cryptocurrency, termasuk Solana, membuat proses pengambilan keputusan investasi menjadi tantangan. Fluktuasi harga yang signifikan sering kali dipengaruhi oleh berbagai faktor, seperti sentimen pasar, adopsi teknologi, kebijakan pemerintah, dan dinamika pasar global. Dalam konteks ini, kemampuan untuk memprediksi harga Solana secara akurat menjadi sangat berharga bagi investor, pedagang, dan analis pasar.

Teknologi kecerdasan buatan dan pembelajaran mesin (machine learning) telah terbukti menjadi alat yang efektif dalam menganalisis data kompleks dan memprediksi tren masa depan. Dengan memanfaatkan algoritma prediktif, model dapat dilatih untuk mengidentifikasi pola-pola yang tersembunyi dalam data historis dan memberikan estimasi harga di masa depan. Pendekatan ini tidak hanya membantu mengurangi risiko dalam perdagangan, tetapi juga memberikan wawasan berharga tentang faktor-faktor utama yang memengaruhi pergerakan harga Solana.

Proyek ini bertujuan untuk mengembangkan model prediktif harga Solana menggunakan data historis pasar, termasuk harga, volume perdagangan, serta indikator teknis dan fundamental. Hasil penelitian ini diharapkan dapat memberikan kontribusi signifikan dalam pemahaman dan pengelolaan risiko dalam investasi cryptocurrency, khususnya Solana, di tengah dinamika pasar yang terus berkembang.

### Referensi
-**[Survey on Cryptocurrency Price Prediction Using Machine Learning](https://www.ijres.org/papers/Volume-10/Issue-2/Ser-3/G10124247.pdf)**

## Business Understanding
### Problem Statement
Pasar cryptocurrency, termasuk Solana (SOL), memiliki sifat yang sangat volatil dan kompleks dengan pola pergerakan harga yang dipengaruhi oleh berbagai faktor seperti sentimen pasar, tren keuangan global, dan indikator teknikal. Kompleksitas ini menyulitkan prediksi harga yang akurat, padahal prediksi yang andal sangat penting bagi para investor dan trader untuk membuat keputusan yang tepat.

Meskipun terdapat data historis yang melimpah mengenai pergerakan harga Solana, pendekatan prediksi yang ada sering kali gagal menangkap pola rumit dan sifat non-stasioner dari pasar cryptocurrency. Model statistik tradisional cenderung kurang mampu menggeneralisasi hubungan yang kompleks, sementara penerapan model machine learning yang lebih canggih pada pasar Solana masih terbatas atau kurang dioptimalkan

### Goal
Penelitian ini bertujuan untuk mengembangkan model prediktif berbasis machine learning yang mampu memprediksi harga Solana (SOL) secara akurat dengan cara berikut:
1. Membangun Model Prediksi yang Optimal

Menggunakan algoritma machine learning seperti Support Vector Regression (SVR), Random Forest (RF), k-Nearest Neighbors (KNN), dan XGBoost untuk membangun model prediksi.
Melakukan tuning hyperparameter menggunakan metode seperti Grid Search untuk meningkatkan akurasi prediksi.

2. Mengevaluasi Performa Model

Membandingkan performa model dengan metrik evaluasi seperti Mean Squared Error (MSE

### Solution Statement
Solusi yang dapat diterapkan agar goals diatas terpenuhi adalah sebagai berikut:

Melakukan analisa pada data untuk dapat memahami data yang ada dengan menerapkan teknik visualisasi data. Analisa yang dapat dilakukan yaitu, Memeriksa korelasi antar data penting untuk memahami hubungan data target dan data fitur.

Melakukan pemrosesan pada data seperti:

1.Mengatasi outlier pada data dengan menerapkan IQR method.

2.Normalisasi data pada fitur numerik.

Membangun model regresi yang dapat memprediksi bilangan kontinu sesuai dengan permasalahan yang ingin di selesaikan. Beberapa algoritma yang akan digunakan pada model regresi proyek ini yaitu, sebagai berikut:

-Support Vector Machine

-K-Nearest Neighbours

-Random Forest

-XGBoost

Menerapkan teknik Grid Search untuk mendapatkan parameter-parameter dengan performa terbaik pada masing-masing model.

### Data Understanding
Dataset yang di gunakan pada proyek machine learning ini merupakan Dataset yang menyediakan riwayat harga harian Solana dari tahun 2020 - 2022. Dataset tersebut dapat di unduh di website kaggle: **[Solana Data](https://www.kaggle.com/datasets/varpit94/solana-data)**

Setelah dilakukan analisa pada data, didapatkan informasi bahwa:

-Format dataset yaitu CSV (Comma-Seperated Values)

-Jumlah kolom data yang terdapat didalam dataset berjumla 7 kolom, antara lain: Date, Open, High, Low, Close, Adj Close, Volume

-Terdapat 715 jumlah sample yang terdapat didalam dataset.

-Terdapat 5 kolom data yang memiliki tipe data Float yaitu (High, Low, Open, Close, adj close).

-Terdapat 1 kolom data yang memiliki tipe data Integer yaitu (Volume)

-Terdapat 2 kolom data yang memiliki tipe data Object atau String yaitu (Date)

-Tidak terdapat missing value pada dataset

### Variabel-variabel pada dataset adalah sebagai berikut:
Name: Nama mata uang kripto
Symbol: Simbol mata uang kripto
Date: Tanggal pencatatan data
High : Harga tertinggi pada hari tertentu
Low : Harga terendah pada hari tertentu
Open : Harga pembukaan pada hari tertentu
Close : Harga penutupan pada hari tertentu
Volume : Volume transaksi pada hari tertentu
Mastercap : Kapitalisasi pasar dalam USD

