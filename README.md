# UTS-Datmin-2304020017_KhansaHanunNabilah
# Prediksi Kualitas Anggur Menggunakan Model Klasifikasi

Repository ini berisi proses analisis dan pemodelan untuk memprediksi kualitas anggur berdasarkan karakteristik kimiawi yang terdapat pada dataset Wine Quality. Model klasifikasi digunakan untuk mempelajari pola dari data training, kemudian digunakan untuk memperkirakan kualitas anggur pada data testing.

## Deskripsi Data

Dataset yang digunakan terdiri dari dua file, yaitu data training dan data testing. Data training digunakan untuk membangun dan mengevaluasi model klasifikasi, sedangkan data testing digunakan untuk menghasilkan prediksi kualitas anggur.

Pada data training terdapat kolom `quality` sebagai variabel target. Variabel ini menunjukkan kualitas anggur dalam bentuk angka. Selain itu, terdapat beberapa fitur kimiawi yang digunakan sebagai variabel prediktor, seperti `fixed acidity`, `volatile acidity`, `citric acid`, `residual sugar`, `chlorides`, `free sulfur dioxide`, `total sulfur dioxide`, `density`, `pH`, `sulphates`, dan `alcohol`.

Data testing memiliki fitur yang sama seperti data training, tetapi tidak memiliki kolom `quality`. Oleh karena itu, nilai kualitas pada data testing perlu diprediksi menggunakan model yang dibangun dari data training.

Secara umum, dataset ini digunakan untuk melihat bagaimana karakteristik kimiawi anggur dapat membantu dalam memprediksi kualitas anggur. Setiap baris data merepresentasikan satu sampel anggur, sedangkan setiap kolom merepresentasikan informasi kimiawi atau identitas dari sampel tersebut.

## Tujuan Analisis

Tujuan dari analisis ini adalah membuat model klasifikasi untuk memprediksi nilai `quality` pada data testing. Data training digunakan untuk melatih dan mengevaluasi model, sedangkan data testing digunakan untuk menghasilkan prediksi akhir.

## Tahapan Analisis

Tahapan analisis yang dilakukan dalam notebook adalah sebagai berikut:

1. Import library yang dibutuhkan.
2. Memuat data training dan data testing.
3. Memeriksa struktur data, tipe data, missing value, dan duplikasi.
4. Melakukan eksplorasi data, terutama distribusi variabel target `quality`.
5. Memisahkan fitur dan target.
6. Membagi data training menjadi data latih dan data validasi.
7. Membandingkan beberapa model klasifikasi.
8. Melakukan evaluasi awal menggunakan data validasi.
9. Melakukan cross validation untuk memperoleh evaluasi yang lebih stabil.
10. Memilih model terbaik berdasarkan hasil evaluasi.
11. Mengevaluasi model menggunakan classification report dan confusion matrix.
12. Melihat feature importance dari model terbaik.
13. Melatih model akhir menggunakan seluruh data training.
14. Memprediksi nilai `Quality` pada data testing.

## Model yang Digunakan

Beberapa model klasifikasi yang dibandingkan adalah:

- Logistic Regression
- K-Nearest Neighbors
- Support Vector Machine RBF
- Random Forest
- Extra Trees
- Gradient Boosting

Berdasarkan hasil evaluasi awal, Gradient Boosting memperoleh akurasi tertinggi pada data validasi. Namun, setelah dilakukan cross validation, Random Forest menunjukkan performa rata-rata terbaik dan lebih stabil, sehingga dipilih sebagai model akhir.

## Interpretasi Hasil

Hasil evaluasi menunjukkan bahwa model lebih baik dalam mengenali kelas `quality` yang jumlah datanya dominan, terutama quality 5 dan 6. Sementara itu, kelas dengan jumlah data yang lebih sedikit memiliki performa prediksi yang relatif lebih terbatas. Hal ini dapat terjadi karena distribusi target pada data training tidak seimbang.

Berdasarkan feature importance, fitur yang paling berkontribusi dalam prediksi model Random Forest adalah `volatile acidity`, `sulphates`, dan `alcohol`. Ketiga fitur tersebut menjadi fitur yang paling banyak dipertimbangkan oleh model dalam memprediksi kualitas anggur.

## Kesimpulan

Berdasarkan seluruh tahapan analisis, model Random Forest dipilih sebagai model terbaik karena memiliki performa cross validation paling baik dan sesuai untuk data tabular numerik seperti dataset Wine Quality. Model ini mampu menangkap hubungan non-linear antar fitur kimiawi anggur dan digunakan untuk memprediksi kualitas anggur pada data testing.
