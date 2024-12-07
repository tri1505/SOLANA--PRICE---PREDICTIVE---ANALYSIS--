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
Berdasarkan kondisi yang telah diuraikan sebelumnya, proyek ini akan mengembangkan sebuah sistem prediksi harga Solana berdasarkan data historis yaitu harga tertinggi, harga terendah, harga pembukaan, harga penutupan, dimana masing masing faktor memiliki peran penting dalam pergerakan harga Solana seperti:

Harga Tertinggi: Mencerminkan titik harga tertinggi yang dicapai Solana dalam periode tertentu. Faktor ini penting karena menunjukkan batas atas kekuatan beli di pasar dan sering kali menjadi patokan untuk menentukan apakah harga sedang mendekati titik resistensi.
Harga Terendah: Menunjukkan titik terendah harga Solana dalam periode tertentu. Ini membantu mengidentifikasi titik dukungan dimana tekanan jual mungkin telah memudar, memberikan gambaran mengenai batas bawah dari volatilitas pasar.
Harga Pembukaan: Adalah harga awal dari Solana di awal periode perdagangan. Perbandingan antara harga pembukaan dan harga penutupan bisa memberikan indikasi tentang tren pasar yang sedang terjadi, apakah tren naik (bullish) atau turun (bearish).
Harga Penutupan: Harga pada akhir periode perdagangan merupakan salah satu indikator kunci yang sering digunakan untuk melihat kecenderungan harga secara keseluruhan. Perubahan harga penutupan dari waktu ke waktu membantu dalam memahami pola tren harga di masa depan.

Bagaimana cara memanfaatkan data historis harga Solana seperti harga pembukaan, harga penutupan, harga tertinggi, harga terendah, untuk memprediksi harganya di masa depan?
Bagaimana cara mengoptimalkan kinerja algoritma XGBoost untuk memprediksi harga Solana melalui parameter-parameter penting seperti learning rate, max_depth, subsample, dan n_estimators?

### Goal
Untuk menjawab problem statement tersebut, akan dibuat predictive modelling dengan tujuan atau goals sebagai berikut:

Membuat model machine learning yang dapat memprediksi harga Solana untuk 10 hari ke depan berdasarkan parameter yang ditetapkan.
Mencari nilai optimal untuk learning rate, max_depth, subsample, dan n_estimators pada algoritma XGBoost melalui proses hyperparameter tuning, dengan tujuan memaksimalkan akurasi prediksi harga Solana.

### Solution Statement
Untuk mencapai goals tersebut, ada 2 pendekatan yang akan digunakan yaitu:

Menggunakan Algoritma XGBoost: XGBoost merupakan algoritma ensemble yang sangat cocok untuk tugas prediksi, terutama pada data yang kompleks dan nonlinear seperti data harga Solana. XGBoost bekerja dengan membangun banyak pohon keputusan (decision tree) secara berurutan, dengan setiap pohon belajar dari kesalahan pohon sebelumnya. Struktur ensemble ini memungkinkan XGBoost menangkap pola yang kompleks dalam data dan menghasilkan prediksi yang lebih akurat.
Menentukan Nilai Optimal untuk Hyperparameter XGBoost: Untuk mengoptimalkan kinerja model XGBoost, kita akan melakukan hyperparameter tuning. Hyperparameter adalah parameter yang tidak dipelajari oleh model selama pelatihan, melainkan diatur sebelum pelatihan dimulai. Beberapa hyperparameter penting pada XGBoost antara lain:
learning_rate: Mengontrol tingkat di mana model belajar dari setiap iterasi. Nilai yang terlalu besar dapat menyebabkan overfitting, sedangkan nilai yang terlalu kecil dapat memperlambat konvergensi.
max_depth: Mengontrol kedalaman maksimum pohon keputusan. Nilai yang terlalu besar dapat menyebabkan overfitting, sedangkan nilai yang terlalu kecil dapat menghambat kemampuan model untuk menangkap pola yang kompleks.
subsample: Mengontrol proporsi data yang digunakan untuk membangun setiap pohon keputusan. Subsampling dapat membantu mengurangi overfitting.
n_estimators: Menentukan jumlah pohon keputusan yang akan dibangun. Jumlah pohon yang terlalu sedikit dapat menyebabkan underfitting, sedangkan jumlah pohon yang terlalu banyak dapat menyebabkan overfitting.

### Data Understanding
Dataset yang di gunakan pada proyek machine learning ini merupakan Dataset yang menyediakan riwayat harga harian Solana dari tahun 2020 - 2022. Dataset tersebut dapat di unduh di website kaggle: **[Solana Data]([https://www.investing.com/crypto/solana/historical-data])**

Setelah dilakukan analisa pada data, didapatkan informasi bahwa:

-Format dataset yaitu CSV (Comma-Seperated Values)

-Jumlah kolom data yang terdapat didalam dataset berjumla 7 kolom, antara lain: Date, Open, High, Low, Close, Adj Close, Volume

-Terdapat 715 jumlah sample yang terdapat didalam dataset.

-Terdapat 5 kolom data yang memiliki tipe data Float yaitu (High, Low, Open, Close, adj close).

-Terdapat 1 kolom data yang memiliki tipe data Integer yaitu (Volume)

-Terdapat 2 kolom data yang memiliki tipe data Object atau String yaitu (Date)

-Tidak terdapat missing value pada dataset

### Variabel-variabel pada dataset adalah sebagai berikut:

-Date: Tanggal pencatatan data

-High : Harga tertinggi pada hari tertentu

-Adj High : Copy harga tertinggi pada hari tertentu

-Low : Harga terendah pada hari tertentu

-Open : Harga pembukaan pada hari tertentu

-Close : Harga penutupan pada hari tertentu

-Volume : Volume transaksi pada hari tertentu

Sebelum melakukan pemrosesan data untuk pelatihan, perlu dilakukan analisa pada data untuk mengetahui keadaan pada data seperti korelasi antar fitur dan outlier pada data. Berikut visualisasi data yang menunjukkan korelasi atar fitur dan outlier pada data:

1.Menangani Oulier
Jika dilihat divisualisasi outlier dibawah hampir semua data numeric memiliki data outlier. Terdapat beberapa teknik untuk mengatasi outlier pada data. Pada proyek ini akan menerapkan teknik IQR Method yaitu dengan menghapus data yang berada diluar interquartile range. Interquartile merupakan range diantara kuartil pertama(25%) dan kuartil ketiga(75%).
	![alt text](VIZ/outlier.png)
 
2.Multivariate Analysis
Jika di lihat dari visualisasi data dibawah. Fitur Close pada sumbu y memiliki korelasi dengan data pada fitur High, Low, Open, dan adj_close. Korelasi yang terdapat pada data-data tersebut merupakan korelas yang tinggi, sedangkan untuk fitur Volume terlihat memiliki korelasi yang cukup lemah karena sebaran datanya tidak membentuk pola
![alt text](VIZ/multivariate.png)

## Data Preparation

Berikut merupakan tahapan dalam mempersiapkan data untuk keperluan pelatihan model:

### Menghapus data yang tidak diperlukan dan merubah nama column
Kolom data seperti (Date, Adj Close, Value) tidak diperlukan untuk pelatihan, karena data tersebut akan mengganggu model dalam mempelajari data. Karena isi dari data tersebut tidak memiliki value yang berarti untuk dipelajari oleh model. Lalu, mengubah nama kolom High, Low, Open, Close menjadi nama kolom yang dapat lebih dipahami
| From        | to	    |
| ----------- | ----------- |
| High        | High_Price  |
| Low	      | Low_Price   |
| Open        | Open_Price  |
| Close	      | Close_Price |

## Split dataset
Membagi dataset menjadi data latih (train) dan data uji (test) merupakan hal yang harus kita lakukan sebelum membuat model.Data latih adalah sekumpulan data yang akan digunakan oleh model untuk melakukan pelatihan. Sedangkan, data uji adalah sekumpulan data yang akan digunakan untuk memvalidasi kinerja pada model yang telah dilatih. Karena data uji berperan sebagai data baru yang belum pernah dilihat oleh model, maka cara ini efektif untuk memeriksa performa model setelah proses pelatihan dilakukan. Proporsi pembagian dataset pada proyek ini menggunakan proporsi pembagian 80:20 yang berarti sebanyak 80% merupakan data latih dan 20% persen merupakan data uji.

## Normalisasi data
Melakukan transformasi pada data fitur fitur yang akan dipelajari oleh model menggunakan library MinMaxScaler. MinMaxScaler mentransformasikan fitur dengan menskalakan setiap fitur ke rentang tertentu. Library ini menskalakan dan mentransformasikan setiap fitur secara individual sehingga berada dalam rentang yang diberikan pada set pelatihan, pada library ini memiliki range default antara 0 dan 1. Dengan merenapkan teknik normalisasi data, model akan dengan lebih mudah mengenali pola-pola yang terdapat pada data sehingga akan menghasilkan prediksi yang lebih baik daripada tidak menggunakan teknik normalisasi.

## Modeling
Algoritma machine learning yang digunakan pada proyek ini yaitu Support Vector Regression, K-Nearest Neighbours, Random Forest, XGBoost.

## Support Vector Regression (SVR)

Support Vector Regression (SVR) menggunakan prinsip yang sama dengan SVM pada kasus klasifikasi. Perbedaannya adalah jika pada kasus klasifikasi, SVM berusaha mencari ‘jalan’ terbesar yang bisa memisahkan sampel-sampel dari kelas berbeda, maka pada kasus regresi SVR berusaha mencari jalan yang dapat menampung sebanyak mungkin sampel di ‘jalan’. Pada pembuatan model ini dilakukan dengan menggunakan modul yang tersedia di library scikit-learn dengan menggunakan beberapa parameter sebagai berikut:

-kernel = rbf. Parameter ini merupakan metode yang digunakan untuk mengambil data sebagai input dan mengubahnya menjadi bentuk pemrosesan data yang diperlukan.

-gamma = 0.003. Secara intuitif, parameter gamma menentukan seberapa jauh pengaruh satu contoh pelatihan mencapai, dengan nilai rendah berarti 'jauh' dan nilai tinggi berarti 'dekat'. Parameter gamma dapat dilihat sebagai kebalikan dari radius pengaruh sampel yang dipilih oleh model sebagai vektor pendukung.

-C (parameter Regularisasi) = 100000. Parameter C menukar klasifikasi yang benar dari contoh pelatihan terhadap maksimalisasi margin fungsi keputusan. Untuk nilai C yang lebih besar, margin yang lebih kecil akan diterima jika fungsi keputusan lebih baik dalam mengklasifikasikan semua titik pelatihan dengan benar. C yang lebih rendah akan mendorong margin yang lebih besar, oleh karena itu fungsi keputusan yang lebih sederhana, dengan mengorbankan akurasi pelatihan. Dengan kata lain C berperilaku sebagai parameter regularisasi dalam SVR.

## K-Nearest Neighbours
K-nearest neighbor adalah salah satu algoritma machine learning dengan pendekatan supervised learning yang bekerja dengan mengkelaskan data baru menggunakan kemiripan antara data baru dengan sejumlah data (k) pada lokasi yang terdekat yang telah tersedia. Algoritma ini menerapkan lazy learning” atau “instant based learning” dan merupakan algoritma non parametrik. Algoritma KNN digunakan untuk klasifikasi dan regresi. Pada pembuatan model ini akan menggunaka modul KNN yang terlah di sediakan oleh library scikit-learn .Pada model ini hanya akan menggunakan 1 parameter yaitu n_neighbours (Jumlah tetangga). Jumlah neighbours yang di gunakan yaitu sejumlah 5 neighbours. Kemudian, untuk menentukan titik mana dalam data yang paling mirip dengan input baru, KNN menggunakan perhitungan ukuran jarak. Metrik ukuran jarak yang digunakan secara default pada library sklearn adalah Minkowski distance. Setelah menentukan nilai-nilai pada parameter model melakukan pelatihan menggunakan data latih setelah itu model akan melakukan prediksi terhadap data yang belum pernah dilihat dengan menggunakan data uji. Namun algoritma ini memiliki keunggulan dan kekurangan.

## Random Forest
Algoritma ini merupakan sekumpulan algoritma decision tree. Konsep dasar decision tree adalah mengubah data menjadi aturan-aturan keputusan. Kombinasi dari masing–masing decision tree yang baik kemudian dikombinasikan ke dalam satu model. Random Forest bergantung pada sebuah nilai vector random dengan distribusi yang sama pada semua pohon yang masing masing decision tree memiliki kedalaman yang maksimal. Algoritma ini bisa menyelesaikan permasalahan klasifikasi dan regresi. Pada kasus klasifikasi, prediksi akhir diambil dari prediksi terbanyak pada seluruh pohon. Sedangkan, pada kasus regresi, prediksi akhir adalah rata-rata prediksi seluruh pohon. Untuk pembuatan model Random Forest, akan menggunakan beberapa parameter, antara lain:

-n_estimator: jumlah trees (pohon) di forest. Di sini kita set n_estimator=50.

-max_depth: kedalaman atau panjang pohon. Ia merupakan ukuran seberapa banyak pohon dapat membelah (splitting) untuk membagi setiap node ke dalam jumlah pengamatan yang diinginkan.

## XGBoost (Extreme Gradient Boosting)
XGBoost (Extreme Gradient Boosting) adalah algoritma machine learning berbasis ensemble learning yang dirancang untuk menangani tugas regresi dan klasifikasi. XGBoost dikembangkan untuk memberikan solusi yang cepat, fleksibel, dan akurat dengan memperluas metode gradient boosting.

Parameter pada parameters XGBoost (Extreme Gradient Boosting)
1.n_estimators (Jumlah Pohon Keputusan)

 -Menentukan jumlah pohon yang akan digunakan dalam ensemble.
 
 -Nilai lebih tinggi dapat meningkatkan akurasi, tetapi risiko overfitting juga meningkat.
 
 -Contoh nilai: [100, 200, 300].

2.max_depth (Kedalaman Maksimum Pohon)

 -Mengontrol kompleksitas setiap pohon.
 
 -Nilai kecil mendorong generalisasi lebih baik, sedangkan nilai besar memungkinkan model mempelajari hubungan yang lebih kompleks.
 
 -Contoh nilai: [3, 5, 7].

3.learning_rate (Rate Belajar atau Shrinkage)

 -Menentukan langkah pembaruan bobot setelah setiap iterasi boosting.
 
 -Nilai kecil (misalnya 0.01) membuat pembelajaran lebih lambat tetapi stabil, sedangkan nilai besar (misalnya 0.1) memungkinkan model belajar lebih cepat.
 
 -Contoh nilai: [0.1, 0.01, 0.001].

4.subsample (Subsampling Data)

 -Menentukan proporsi sampel data yang digunakan untuk melatih setiap pohon.

 -Nilai kecil membantu mengurangi overfitting dengan membuat model lebih robust.

 -Contoh nilai: [0.8, 0.9, 1.0].

5.colsample_bytree (Sampling Kolom)

 -Mengontrol proporsi fitur (kolom) yang digunakan saat membangun pohon keputusan.

 -Membantu menangani overfitting, terutama pada dataset dengan banyak fitur.

 -Contoh nilai: [0.8, 0.9, 1.0].

## Evaluation
Pada proyek machine learning ini, metrik evaluasi yang digunakan yaitu mean squared error (MSE) yang mana metrik ini merupakan ukuran seberapa dekat garis pas dengan titik data. Untuk setiap titik data, model mengambil jarak secara vertikal dari titik ke nilai y yang sesuai pada kecocokan kurva (kesalahan), dan kuadratkan nilainya.


**Rumus MSE:**

![alt text](VIZ/rumusMSE.jpg)

dimana:

At = Nilai Aktual permintaan

Ft = Nilai hasil prediksi

n = banyaknya data

Setelah melakukan evaluasi menggunakan metrik mean squared error pada model dengan menggunakan data uji didapatkan hasil seperti berikut:

![alt text](VIZ/mse.png)

Dapat dilihat dari visualisasi diatas bahwa MSE pada model SVR merupakan MSE yang paling rendah dari kedua model lainnya, selain itu jumlah error pada saat pengujian tidak berbeda jauh dengan error pada saat pelatihan.

![alt text](VIZ/prediksi.png)

Dapat juga dilihat melalui visualisasi diatas bahwa angka prediksi pada model SVR yang paling mendekati dengan angka sebenarnya.
