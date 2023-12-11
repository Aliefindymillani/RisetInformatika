# RisetInformatika
Mata kuliah riset informatika adalah mata kuliah yang mempelajari tentang berbagai metode penelitian, teknik eksperimen, analisis data, dan pendekatan penelitian lainnya yang digunakan dalam ilmu komputer. Mereka juga akan diajak untuk memahami perkembangan terbaru dalam bidang tersebut dan belajar cara menghasilkan kontribusi penelitian baru.

# Perbandingan Penggunaan Metode LTSM dan SVM dalam Kit ITCLAB Pendeteksi Suhu
Pengembangan teknologi sensor suhu telah memainkan peran krusial dalam berbagai aplikasi, termasuk pengawasan lingkungan, kendali iklim, dan sistem pemantauan suhu pada perangkat elektronik. Dalam konteks ini, kit ITCLAB Pendeteksi Suhu menawarkan solusi yang andal untuk pemantauan suhu yang akurat dan responsif. Namun, dalam mengimplementasikan sistem pendeteksian suhu, pemilihan metode analisis data menjadi langkah kritis. Dua pendekatan yang sering digunakan, yaitu Long Short-Term Memory (LSTM) dan Support Vector Machine (SVM), menawarkan keunggulan masing-masing. LSTM, sebagai model jaringan saraf rekuren, memungkinkan pengolahan informasi sepanjang deret waktu, sesuai dengan fluktuasi suhu yang dinamis. Di sisi lain, SVM, sebuah metode pembelajaran mesin yang solid, menawarkan kemampuan klasifikasi yang kuat untuk mengenali pola dalam data suhu. Oleh karena itu, perbandingan antara penggunaan LSTM dan SVM dalam konteks kit ITCLAB Pendeteksi Suhu memerlukan pemahaman mendalam terhadap karakteristik fluktuasi suhu, kompleksitas pola, keakuratan, dan kebutuhan sumber daya. Dengan merinci pertimbangan ini, penelitian ini bertujuan untuk mengevaluasi kinerja relatif dari kedua metode tersebut, membuka peluang untuk pemilihan metode yang optimal dalam mencapai tujuan pemantauan suhu yang efisien dan responsif.

# SVM
Dalam rangka mengimplementasikan kit ITCLAB Pendeteksi Suhu, metode Support Vector Machine (SVM) dipilih sebagai salah satu pendekatan utama dalam menganalisis dan mengolah data suhu. SVM, sebagai model klasifikasi dalam pembelajaran mesin, memiliki kemampuan untuk memetakan data suhu ke dalam ruang berdimensi tinggi dan menemukan hyperplane terbaik yang memisahkan kelas-kelas suhu yang berbeda. Dalam konteks ini, SVM dapat digunakan untuk mengidentifikasi pola dan tren dalam data suhu yang bersifat non-linear, sehingga memberikan ketepatan yang baik dalam klasifikasi dan deteksi anomali. Kelebihan SVM terletak pada kemampuannya menangani data yang kompleks tanpa mengalami overfitting, sehingga dapat diandalkan untuk mendeteksi perubahan suhu yang signifikan atau perilaku anomali. Selain itu, SVM dapat diadaptasi dengan baik untuk pengolahan data waktu nyata, memungkinkan respons cepat terhadap perubahan suhu mendadak yang dapat terjadi di lingkungan aplikasi sensor suhu. 

# LSTM (Long Short Term Memory)
LSTM, sebagai salah satu jenis arsitektur jaringan saraf rekuren (RNN), menonjol karena kemampuannya dalam menangkap dependensi jangka panjang dalam data deret waktu suhu. Melalui pemrosesan sekuensial data, LSTM dapat mengenali pola, tren, dan hubungan temporal yang kompleks, yang sering kali sulit ditangkap oleh metode konvensional. Dengan demikian, dalam konteks pemantauan suhu, LSTM dapat digunakan untuk mengantisipasi perubahan suhu yang terjadi sepanjang waktu, memungkinkan deteksi dini dan respons yang efektif terhadap perubahan kondisi suhu. Keunggulan utama LSTM terletak pada kemampuannya mengatasi masalah vanishing gradient, sehingga mampu memodelkan konteks sepanjang sejarah data dengan baik. Dengan menerapkan metode LSTM dalam kit ITCLAB Pendeteksi Suhu, diharapkan dapat meningkatkan kemampuan sistem dalam menghadapi dinamika fluktuasi suhu secara efisien dan akurat.








