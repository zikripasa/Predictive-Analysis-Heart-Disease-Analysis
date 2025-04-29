# Laporan Proyek Predictive Analysis Heart Disease Analysis - Muhammad Zikri Pasa

## Domain Proyek 

Industri otomotif merupakan sektor dengan pertumbuhan signifikan di Indonesia. Salah satu aspek penting dalam proses jual-beli mobil bekas adalah penentuan harga yang sesuai berdasarkan karakteristik kendaraan. Penjual maupun pembeli seringkali kesulitan dalam menentukan nilai pasar mobil bekas secara akurat.
Masalah ini dapat diselesaikan dengan menggunakan predictive analytics berbasis machine learning untuk memprediksi harga mobil bekas dengan mempertimbangkan fitur-fitur kendaraan. Pendekatan ini akan membantu pelaku pasar otomotif mengambil keputusan yang lebih tepat, akurat, dan efisien.
Referensi:
UCI Machine Learning Repository. (n.d.). Car Data Set. Retrieved from https://archive.ics.uci.edu/


Sudharsan, N. (2020). "Predictive Analysis of Used Car Price Using Machine Learning." International Journal of Scientific Research in Computer Science, Engineering and Information Technology.



## Business Understanding
### Problem Statements
Bagaimana cara memprediksi harga jual mobil bekas secara akurat berdasarkan fitur kendaraan?


Algoritma machine learning apa yang paling sesuai untuk memprediksi harga jual mobil bekas?


### Goals
Mengembangkan model prediktif harga mobil bekas berdasarkan atribut kendaraan.


Membandingkan performa dua algoritma regresi (Linear Regression dan Lasso Regression) untuk menentukan model terbaik.


### Solution Statement
Menerapkan algoritma Linear Regression sebagai baseline model.


Melakukan perbandingan dengan Lasso Regression untuk melihat apakah regularisasi L1 dapat meningkatkan performa.


Mengukur performa model menggunakan metrik R-squared.



## Data Understanding
Dataset diambil dari file car data.csv yang berisi data mobil bekas dengan atribut-atribut berikut:
Kolom
Deskripsi
Car_Name
Nama mobil
Year
Tahun produksi
Selling_Price
Harga jual
Present_Price
Harga awal
Kms_Driven
Jarak tempuh
Fuel_Type
Jenis bahan bakar (Petrol, Diesel, CNG)
Seller_Type
Tipe penjual (Dealer, Individual)
Transmission
Tipe transmisi (Manual, Automatic)
Owner
Jumlah kepemilikan sebelumnya

Distribusi kategori:
Fuel_Type: Petrol paling banyak.


Seller_Type: Mayoritas Dealer.


Transmission: Manual paling umum.



## Data Preparation
Tahapan data preparation:
Handling Missing Values: Tidak ada missing value.


Label Encoding: Mengubah data kategorikal menjadi numerik:


Fuel_Type: Petrol=0, Diesel=1, CNG=2


Seller_Type: Dealer=0, Individual=1


Transmission: Manual=0, Automatic=1


Feature Selection: Menghapus Car_Name dan Selling_Price dari fitur (karena target prediksi).


Train-Test Split: Data dibagi 80:20.



## Modeling
### Model 1: Linear Regression
Model sederhana yang mencari hubungan linear antar fitur.


Tanpa regularisasi.


### Model 2: Lasso Regression
Menggunakan regularisasi L1 untuk mengurangi overfitting.


Dapat mengecilkan koefisien fitur yang tidak penting menjadi nol.



## Evaluation
### Metrik Evaluasi
R-squared (R²): Mengukur seberapa baik variasi dalam target bisa dijelaskan oleh fitur input.

 Formula:

### Hasil Evaluasi
Linear Regression


Training R²: ~0.88


Testing R²: ~0.84


Lasso Regression


Training R²: ~0.84


Testing R²:~0.84

### Berikut adalah analisis hasil evaluasi model Linear Regression dan Lasso Regression berdasarkan metrik R² (R-squared / Koefisien Determinasi):

Analisis Linear Regression
Training R²: 0.88


Testing R²: 0.84


### Interpretasi:
R² sebesar 0.88 pada data training berarti 88% variasi dalam target (risiko penyakit jantung) dapat dijelaskan oleh fitur-fitur input dalam model.


Testing R² yang juga tinggi (0.84) dan tidak terlalu jauh dari training R² menunjukkan bahwa model tidak overfitting, serta memiliki generalisasi yang baik pada data baru.
Analisis Lasso Regression
Training R²: 0.84


Testing R²: 0.84


### Interpretasi:
Nilai R² yang konsisten antara training dan testing menunjukkan stabilitas model.


Meskipun sedikit lebih rendah dibanding Linear Regression, Lasso Regression memiliki kelebihan dalam regularisasi, yaitu membantu mengurangi overfitting dan juga bisa mengecilkan koefisien fitur yang tidak penting menjadi nol (feature selection secara otomatis).



### Perbandingan Linear vs Lasso Regression
Aspek
Linear Regression
Lasso Regression
Training R²
0.88
0.84
Testing R²
0.84
0.84
Overfitting Risiko
Rendah
Lebih Rendah
Interpretability
Biasa
Lebih baik (fitur yang tidak penting bisa dieliminasi)


### Kesimpulan dan Rekomendasi
Jika tujuan utama adalah prediksi dengan akurasi tinggi, Linear Regression sedikit lebih unggul.


Jika kamu juga mempertimbangkan kesederhanaan model dan ingin mengetahui fitur mana yang paling berkontribusi, Lasso Regression lebih disarankan karena memberikan model yang lebih ramping dan tahan terhadap overfitting.


Dalam proyek kesehatan seperti ini, Lasso bisa sangat berguna untuk fokus pada fitur-fitur penting yang benar-benar relevan terhadap risiko penyakit jantung.


### Visualisasi
Grafik scatter antara nilai aktual dan prediksi menunjukkan model cukup baik meskipun ada beberapa deviasi.

### Kesimpulan
Model Linear Regression memberikan performa prediksi yang baik dan sederhana.


Lasso Regression dapat digunakan untuk seleksi fitur, namun sedikit menurunkan akurasi.


Untuk pengembangan ke depan, dapat dilakukan:


Hyperparameter tuning Lasso


Penambahan fitur penting lain (misalnya nilai depresiasi tahunan)


Cross-validation untuk validasi yang lebih akurat




