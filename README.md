### Nama : Alief Indy Millani
### NPM :  20081010013

# Riset Informatika
<div style="text-align: justify"> Mata kuliah riset informatika adalah mata kuliah yang mempelajari tentang berbagai metode penelitian, teknik eksperimen, analisis data, dan pendekatan penelitian lainnya yang digunakan dalam ilmu komputer. Mereka juga akan diajak untuk memahami perkembangan terbaru dalam bidang tersebut dan belajar cara menghasilkan kontribusi penelitian baru. </div>

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
Dalam hasil evaluasi PID Deep Learning menggunakan SVM dan LSTM, metrik yang diukur termasuk Rising Time, Settling Time, dan Overshoot. Analisis perbandingan hasil masing-masing metrik memberikan pemahaman lebih mendalam tentang kinerja kedua metode tersebut.

### SVM

![PID_Result](https://github.com/Aliefindymillani/RisetInformatika/assets/89888415/340ce2de-0251-4558-8831-d77e532a3aae)

PID Result

![SVM_Result](https://github.com/Aliefindymillani/RisetInformatika/assets/89888415/01b62c82-051f-48ff-ada3-037833372aa8)

SVM Result

### LSTM

![HEAT with (PID DL)](https://github.com/Aliefindymillani/RisetInformatika/assets/89888415/ac293d8c-2451-48ec-b530-957d4707f79f)

PID Result

![HEAT with (LSTM)](https://github.com/Aliefindymillani/RisetInformatika/assets/89888415/4c5f147e-3624-4eac-910c-3ae60fdc5826)

LSTM Result


### Perbandingan
![image](https://github.com/Aliefindymillani/RisetInformatika/assets/89888415/3c2d77d8-524d-4ad0-aac0-f2e521381464)

### PID Deep Learning (SVM vs. LSTM):

Dalam evaluasi performa PID Deep Learning menggunakan metode SVM dan LSTM pada berbagai metrik, terdapat perbedaan yang mencolok dalam ketiga kategori pengukuran kinerja: Rising Time, Settling Time, dan Overshoot. Pertama, pada aspek Rising Time, nilai yang lebih rendah pada LSTM (55,89) dibandingkan dengan SVM (86,45) menunjukkan bahwa PID Deep Learning dengan LSTM mampu merespons perubahan input dengan lebih cepat. Dengan selisih 30,56, dapat disimpulkan bahwa waktu yang dibutuhkan untuk mencapai nilai setpoint lebih efisien pada LSTM.

Kedua, dalam kategori Settling Time, SVM menunjukkan performa yang signifikan lebih baik dengan nilai 27,82 dibandingkan dengan LSTM yang memiliki nilai 237,62. Dengan selisih -209,8, SVM dapat mencapai nilai yang mendekati setpoint secara stabil dalam waktu yang lebih singkat, menandakan keunggulan dalam stabilitas Settling Time.

Terakhir, evaluasi pada Overshoot menunjukkan bahwa SVM memiliki nilai lebih rendah (6,42%) dibandingkan dengan LSTM (18,52%), dengan selisih 12,10. Hal ini menandakan bahwa SVM memiliki respons yang lebih stabil dan mendekati setpoint tanpa melebihi nilai yang diinginkan, memberikan kestabilan yang lebih besar dalam sistem pengendalian suhu.

Dengan demikian, analisis metrik-metrik tersebut menggambarkan keunggulan masing-masing metode dalam konteks pengendalian suhu, di mana LSTM lebih cocok untuk situasi yang membutuhkan respons cepat, sementara SVM menonjol dalam mencapai kestabilan yang lebih baik dalam waktu yang lebih singkat. Evaluasi ini memberikan wawasan yang berguna untuk pemilihan metode yang paling sesuai dengan kebutuhan spesifik sistem yang diinginkan.

### Perbandingan dengan metode yang berbeda (SVM vs. LSTM):

Dalam evaluasi perbandingan antara PID Deep Learning menggunakan metode SVM dan PID Deep Learning pada metrik kinerja yang berbeda, terlihat bahwa keduanya memiliki keunggulan dan kelemahan spesifik. Pertama, dalam hal Rising Time, PID Deep Learning dengan nilai 86,45 menunjukkan performa lebih baik dibandingkan dengan SVM yang memiliki nilai 101,59. Dengan selisih -15,14, dapat disimpulkan bahwa PID Deep Learning mampu mengurangi waktu yang diperlukan untuk mencapai nilai setpoint, menandakan respons yang lebih efisien terhadap perubahan input.

Kedua, dalam kategori Settling Time, SVM menunjukkan performa yang lebih baik dengan nilai 26,87 dibandingkan dengan PID Deep Learning yang memiliki nilai 27,82. Meskipun perbedaan kecil, selisih 0,95 menandakan bahwa SVM lebih efektif dalam mencapai nilai yang mendekati setpoint secara stabil dalam waktu yang lebih singkat dibandingkan dengan PID Deep Learning.

Terakhir, evaluasi terhadap Overshoot menunjukkan bahwa PID Deep Learning memiliki nilai lebih baik (6,42%) dibandingkan dengan SVM (7,23%), meskipun perbedaan yang kecil dengan selisih -0,81. Meskipun perbedaan kecil, PID Deep Learning menunjukkan respons yang sedikit lebih stabil dan mendekati setpoint tanpa melebihi nilai yang diinginkan.

Secara keseluruhan, analisis metrik-metrik tersebut menggarisbawahi bahwa pemilihan metode harus didasarkan pada prioritas spesifik aplikasi, apakah lebih mengutamakan kecepatan respon (Rising Time), stabilitas (Settling Time), atau kelebihan nilai (Overshoot). Evaluasi ini memberikan pandangan holistik untuk mempertimbangkan keunggulan dan kelemahan masing-masing metode, memandu penggunaan metode yang paling sesuai dengan kebutuhan sistem yang diinginkan.

## Evaluasi
Berdasarkan perbandingan hasil antara PID Deep Learning menggunakan SVM dan LSTM, serta perbandingan dengan metode SVM, dapat disimpulkan bahwa kedua metode memiliki kelebihan dan kekurangan masing-masing. Dalam konteks PID Deep Learning, LSTM menunjukkan keunggulan dalam hal Rising Time dengan selisih yang signifikan, menandakan kemampuan merespons perubahan input dengan lebih efisien. Di sisi lain, SVM unggul dalam Settling Time, menunjukkan stabilitas yang lebih baik dalam mencapai nilai setpoint secara stabil. Meskipun LSTM memiliki Overshoot yang lebih tinggi, hal ini dapat diatasi dengan pertimbangan kecepatan respon yang lebih baik.

Ketika membandingkan PID Deep Learning dengan SVM, dapat dilihat bahwa PID Deep Learning, terutama dengan penggunaan LSTM, menunjukkan performa lebih baik dalam hal waktu rising yang lebih singkat. Sementara itu, SVM memberikan keunggulan dalam Settling Time, menunjukkan kestabilan yang lebih baik dalam mencapai nilai yang mendekati setpoint.

Kesimpulannya, pemilihan antara SVM dan LSTM dalam konteks PID Deep Learning harus didasarkan pada prioritas spesifik aplikasi, apakah lebih mengutamakan kecepatan respon atau stabilitas settling time. Evaluasi yang cermat perlu dilakukan dengan mempertimbangkan kriteria kinerja yang paling relevan dan mengoptimalkan penggunaan metode yang paling sesuai untuk memenuhi kebutuhan sistem pengendalian suhu yang bersangkutan.

# Referensi
Berikut merupakan referensi yang digunakan :

[1-s2.0-S0022169423013227-main.pdf](https://github.com/Aliefindymillani/RisetInformatika/files/13644441/1-s2.0-S0022169423013227-main.pdf)<br />
[1-s2.0-S2405844022006879-main.pdf](https://github.com/Aliefindymillani/RisetInformatika/files/13644444/1-s2.0-S2405844022006879-main.pdf)<br />
[1-s2.0-S0950705123010389-main.pdf](https://github.com/Aliefindymillani/RisetInformatika/files/13644447/1-s2.0-S0950705123010389-main.pdf)<br />
[1-s2.0-S0308814623018538-main.pdf](https://github.com/Aliefindymillani/RisetInformatika/files/13644445/1-s2.0-S0308814623018538-main.pdf)<br />

# Coding

(https://github.com/Aliefindymillani/RisetInformatika/blob/main/SVM_ITCLAB.ipynb)
(https://github.com/Aliefindymillani/RisetInformatika/blob/main/LSTM_ITCLAB.ipynb)

# Paper








