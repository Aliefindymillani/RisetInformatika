Nama : Alief Indy Millani
NPM :  20081010013

# Riset Informatika
Mata kuliah riset informatika adalah mata kuliah yang mempelajari tentang berbagai metode penelitian, teknik eksperimen, analisis data, dan pendekatan penelitian lainnya yang digunakan dalam ilmu komputer. Mereka juga akan diajak untuk memahami perkembangan terbaru dalam bidang tersebut dan belajar cara menghasilkan kontribusi penelitian baru.

# Perbandingan Penggunaan Metode LSTM dan SVM dalam Kit ITCLAB Pendeteksi Suhu
Pengembangan teknologi sensor suhu telah memainkan peran krusial dalam berbagai aplikasi, termasuk pengawasan lingkungan, kendali iklim, dan sistem pemantauan suhu pada perangkat elektronik. Dalam konteks ini, kit ITCLAB Pendeteksi Suhu menawarkan solusi yang andal untuk pemantauan suhu yang akurat dan responsif. Namun, dalam mengimplementasikan sistem pendeteksian suhu, pemilihan metode analisis data menjadi langkah kritis. Dua pendekatan yang sering digunakan, yaitu Long Short-Term Memory (LSTM) dan Support Vector Machine (SVM), menawarkan keunggulan masing-masing. LSTM, sebagai model jaringan saraf rekuren, memungkinkan pengolahan informasi sepanjang deret waktu, sesuai dengan fluktuasi suhu yang dinamis. Di sisi lain, SVM, sebuah metode pembelajaran mesin yang solid, menawarkan kemampuan klasifikasi yang kuat untuk mengenali pola dalam data suhu. Oleh karena itu, perbandingan antara penggunaan LSTM dan SVM dalam konteks kit ITCLAB Pendeteksi Suhu memerlukan pemahaman mendalam terhadap karakteristik fluktuasi suhu, kompleksitas pola, keakuratan, dan kebutuhan sumber daya. Dengan merinci pertimbangan ini, penelitian ini bertujuan untuk mengevaluasi kinerja relatif dari kedua metode tersebut, membuka peluang untuk pemilihan metode yang optimal dalam mencapai tujuan pemantauan suhu yang efisien dan responsif.

# SVM
Dalam rangka mengimplementasikan kit ITCLAB Pendeteksi Suhu, metode Support Vector Machine (SVM) dipilih sebagai salah satu pendekatan utama dalam menganalisis dan mengolah data suhu. SVM, sebagai model klasifikasi dalam pembelajaran mesin, memiliki kemampuan untuk memetakan data suhu ke dalam ruang berdimensi tinggi dan menemukan hyperplane terbaik yang memisahkan kelas-kelas suhu yang berbeda. Dalam konteks ini, SVM dapat digunakan untuk mengidentifikasi pola dan tren dalam data suhu yang bersifat non-linear, sehingga memberikan ketepatan yang baik dalam klasifikasi dan deteksi anomali. Kelebihan SVM terletak pada kemampuannya menangani data yang kompleks tanpa mengalami overfitting, sehingga dapat diandalkan untuk mendeteksi perubahan suhu yang signifikan atau perilaku anomali. Selain itu, SVM dapat diadaptasi dengan baik untuk pengolahan data waktu nyata, memungkinkan respons cepat terhadap perubahan suhu mendadak yang dapat terjadi di lingkungan aplikasi sensor suhu. 

# LSTM (Long Short Term Memory)
LSTM, sebagai salah satu jenis arsitektur jaringan saraf rekuren (RNN), menonjol karena kemampuannya dalam menangkap dependensi jangka panjang dalam data deret waktu suhu. Melalui pemrosesan sekuensial data, LSTM dapat mengenali pola, tren, dan hubungan temporal yang kompleks, yang sering kali sulit ditangkap oleh metode konvensional. Dengan demikian, dalam konteks pemantauan suhu, LSTM dapat digunakan untuk mengantisipasi perubahan suhu yang terjadi sepanjang waktu, memungkinkan deteksi dini dan respons yang efektif terhadap perubahan kondisi suhu. Keunggulan utama LSTM terletak pada kemampuannya mengatasi masalah vanishing gradient, sehingga mampu memodelkan konteks sepanjang sejarah data dengan baik. Dengan menerapkan metode LSTM dalam kit ITCLAB Pendeteksi Suhu, diharapkan dapat meningkatkan kemampuan sistem dalam menghadapi dinamika fluktuasi suhu secara efisien dan akurat.

# Metode 
Metode penelitian adalah metode yang digunakan dalam mengumpulkan, menganalisis, dan menginterpretasi data untuk menjawab pertanyaan penelitian atau mencapai tujuan penelitian yang telah ditetapkan. Pada sub bab ini kami ingin menjelaskan metode penelitian yang digunakan dalam studi ini, yang meliputi pengumpulan data, pra proses data, pelatihan model SVM, pelatihan model LSTM, analisis, dan evaluasi.

![Metode](https://github.com/Aliefindymillani/RisetInformatika/assets/89888415/c96cf109-e815-4729-992c-7466cb544dc6)

## Pengumpulan Data
Dalam penelitian ini, data dikumpulkan menggunakan TCLab emulator. Selama tahap pengumpulan data, TCLab emulator diatur dengan frekuensi 100 kali. Selama simulasi, setpoint suhu diberikan dengan variasi yang beragam sebagai nilai target yang diinginkan dalam pengendalian suhu. Variasi setpoint ini dimaksudkan untuk memperoleh data yang dapat efektif melatih model. TCLab emulator dijalankan dalam 540 siklus atau loop, yang merujuk pada jumlah kali TCLab emulator membaca sensor suhu dan mengatur aktuator suhu untuk mencapai setpoint yang telah ditentukan. Pada setiap loop, sensor suhu membaca suhu aktual, dan aktuator disesuaikan untuk mendekati setpoint yang diinginkan. Grafik setpoint dataset yang digunakan untuk pelatihan model juga disajikan.

![Riset_Pengumpulan Data](https://github.com/Aliefindymillani/RisetInformatika/assets/89888415/7e96a208-6b96-4f25-99fb-912accfb4313)

## Praproses Data
Setelah mendapatkan data set point dan error dari tahap pengumpulan data, langkah selanjutnya dalam penelitian ini adalah pra proses data untuk menyiapkan data sebelum memasuki tahap pelatihan model. Pra proses data merupakan tahapan kritis yang melibatkan beberapa langkah untuk memastikan kualitas dan kecocokan data dengan model yang akan dibangun.

Salah satu langkah kunci dalam pra proses data adalah pemilihan fitur atau ciri yang akan digunakan. Dalam penelitian ini, fitur yang terpilih adalah set point dan error. Set point mencerminkan nilai target suhu dalam pengendalian suhu, sementara error menunjukkan perbedaan antara set point dan suhu aktual yang terukur. Pemilihan fitur ini sangat penting karena kualitas fitur yang baik dapat memberikan informasi yang relevan dan signifikan untuk pelatihan model.

Selain pemilihan fitur, pembentukan output juga menjadi aspek penting dalam pra proses data. Output yang akan diprediksi dalam penelitian ini adalah Q, yang merupakan hasil penjumlahan dari tiga komponen: P (Proporsional), I (Integral), dan D (Derivative). Komponen-komponen ini mengacu pada algoritma kontrol PID (Proporsional-Integral-Derivative) yang digunakan untuk mengendalikan suhu. Pemahaman yang baik tentang komponen-komponen ini akan membantu model dalam merespon dengan lebih baik terhadap perubahan suhu.

Tahap pra proses data juga mencakup normalisasi data. Normalisasi dilakukan untuk mengubah rentang nilai setiap fitur agar sejajar dan dapat diolah dengan baik oleh model pembelajaran mesin. Dalam penelitian ini, digunakan metode normalisasi Min-Max Scaling. Metode ini bertujuan untuk mengubah skala nilai data dari rentang nilai aktual menjadi rentang nilai antara 0 hingga 1 atau -1 hingga 1 (Naufal et al., 2023). Formula Min-Max Scaling digunakan untuk mencapai normalisasi, dengan X scaled sebagai hasil scaling data ke-i, 𝑥 sebagai nilai asli data ke-i, xmin sebagai nilai minimum dari X, dan xmax sebagai nilai maksimum dari X.

Dengan pra proses data yang cermat, diharapkan data yang disiapkan dapat memberikan kontribusi maksimal terhadap pelatihan model dan hasil prediksi yang akurat.

![Riset_PraProses Data](https://github.com/Aliefindymillani/RisetInformatika/assets/89888415/56579048-c19b-4b6e-b161-9387ed93e235)


## Pelatihan Model SVM
Pelatihan model dalam arsitektur SVM (Support Vector Machine) merujuk pada proses di mana algoritma SVM belajar dari data latihan untuk membuat model yang dapat digunakan untuk melakukan prediksi atau klasifikasi pada data baru. Dalam SVM, model yang dihasilkan bertujuan untuk memisahkan data ke dalam kelas-kelas yang berbeda dengan menemukan hyperplane (bidang pemisah) optimal. Proses pelatihan ini melibatkan dua tahap utama: pembentukan model dan penentuan parameter.

![SVM](https://github.com/Aliefindymillani/RisetInformatika/assets/89888415/4ac25895-c0f0-42ec-b2d3-5897116e922b)

Proses pelatihan model SVM ini bertujuan untuk mencapai generalisasi yang baik, di mana model dapat mengklasifikasikan data baru dengan akurasi tinggi. Penting untuk memahami karakteristik data, memilih parameter dengan bijak, dan melakukan validasi untuk memastikan kinerja model yang baik pada data yang tidak terlihat selama pelatihan.

## Pelatihan Model LSTM
Proses pelatihan model merupakan tahap krusial dalam penelitian, di mana model yang telah direncanakan akan dipelajari menggunakan data yang telah terkumpul sebelumnya. Dalam konteks penelitian ini, arsitektur model yang digunakan adalah LSTM, yang dijelaskan pada diagram berikut:

![LTSM_Model](https://github.com/Aliefindymillani/RisetInformatika/assets/89888415/1491be1c-1e62-43c4-bb67-7afc42082566)

Model yang telah direncanakan melalui proses pelatihan dilakukan sebanyak 300 epoch. Pada setiap epoch, model akan mengolah data pelatihan, menghitung loss (kesalahan) antara output yang dihasilkan oleh model dengan output yang diharapkan, dan melakukan optimalisasi terhadap bobot dan bias model.

![image](https://github.com/Aliefindymillani/RisetInformatika/assets/89888415/1bff15b0-9905-418c-8f77-4e53a0af2985)


Penting untuk dicatat bahwa proses pelatihan model melibatkan iterasi sejumlah epoch, di mana setiap iterasi membantu model untuk belajar dari data pelatihan dan meningkatkan kinerjanya. Selama proses ini, parameter model, seperti bobot dan bias, dioptimalkan untuk menghasilkan output yang semakin mendekati target yang diharapkan.

## Hasil dan Analisis
## Evaluasi

# Referensi
# Dataset
# Coding
# Cara Menjalankan
# Paper








