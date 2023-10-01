# RisetInformatika
Mata kuliah riset informatika adalah mata kuliah yang mempelajari tentang berbagai metode penelitian, teknik eksperimen, analisis data, dan pendekatan penelitian lainnya yang digunakan dalam ilmu komputer. Mereka juga akan diajak untuk memahami perkembangan terbaru dalam bidang tersebut dan belajar cara menghasilkan kontribusi penelitian baru.

# Tugas 1 : Mencari Topik Penelitian
Judul : Pendeteksi Tawuran Dalam Satu Wilayah Menggunakan Metode Convolutional Neural Network.

Pendeteksi tawuran dalam satu wilayah menggunakan metode Convolutional Neural Network (CNN) adalah sebuah sistem yang memanfaatkan teknik deep learning untuk mengidentifikasi potensi tawuran atau kejadian kekerasan berdasarkan data visual seperti gambar atau video dalam wilayah tertentu. CNN adalah jenis jaringan saraf tiruan yang sangat cocok untuk tugas pengenalan pola dalam data gambar.

# Persoalan Praktis
Dalam judul "Pendeteksi Tawuran Dalam Satu Wilayah Menggunakan Metode Convolutional Neural Network" ada beberapa persoalan praktis yang mungkin dihadapi dalam pengembangan sistem ini. Berikut beberapa persoalan yang perlu diperhatikan:
1. Ketersediaan Data yang Cukup: Salah satu tantangan utama adalah mendapatkan dataset yang mencukupi untuk melatih model CNN. Pengumpulan data tawuran yang valid dan cukup besar bisa menjadi sulit, terutama jika tawuran merupakan peristiwa yang jarang terjadi.
2. Labeling Data: Proses pelabelan data (annotasi) memerlukan waktu dan sumber daya yang signifikan. Menentukan gambar atau video mana yang berisi tawuran dan mana yang tidak bisa menjadi pekerjaan yang memakan waktu.
3. Akurasi Deteksi: Meskipun CNN dapat digunakan untuk pengenalan gambar dengan baik, akurasi deteksi tawuran dalam konteks yang kompleks seperti wilayah publik mungkin tidak selalu 100%. Meningkatkan akurasi deteksi adalah tantangan utama.
4. Keterbatasan Sumber Daya Komputasi: Implementasi real-time dari model CNN memerlukan sumber daya komputasi yang kuat. Tidak semua wilayah memiliki akses ke infrastruktur komputasi yang memadai untuk menjalankan model CNN dengan cepat dan efisien.
5. False Positives dan False Negatives: Model CNN dapat menghasilkan false positives (mendeteksi tawuran ketika sebenarnya tidak ada) dan false negatives (gagal mendeteksi tawuran yang sebenarnya terjadi). Mengurangi angka false positives sambil meminimalkan false negatives adalah tantangan penting.
6. Privasi dan Etika: Menggunakan kamera CCTV untuk pemantauan dapat menimbulkan masalah privasi dan etika. Hal ini memerlukan pertimbangan dan kebijakan yang baik dalam mengimplementasikan teknologi ini.
7. Integrasi dengan Sistem Keamanan yang Ada: Jika Anda mengintegrasikan sistem ini dengan sistem keamanan yang sudah ada, Anda perlu memastikan bahwa integrasi tersebut berjalan lancar dan dapat berkoordinasi dengan sistem lainnya.
8. Regulasi dan Kebijakan Hukum: Penggunaan teknologi pemantauan seperti ini seringkali tunduk pada regulasi dan hukum yang ketat. Perlu memahami dan mematuhi semua peraturan yang berlaku.
9. Perawatan dan Pemeliharaan: Sistem ini memerlukan pemeliharaan rutin dan perawatan agar tetap berfungsi dengan baik. Ini termasuk memeriksa kamera CCTV, perangkat keras, dan perangkat lunak.
10. Efektivitas dalam Kondisi Variabel: Sistem ini harus efektif dalam berbagai kondisi, termasuk perubahan cuaca, pencahayaan yang berbeda, dan situasi yang kompleks seperti kerumunan besar.
    
# Research Question
Berikut beberapa pertanyaan penelitian (research questions) yang dapat menjadi dasar untuk penelitian mengenai "Pendeteksi Tawuran Dalam Satu Wilayah Menggunakan Metode Convolutional Neural Network":
1. Apakah mungkin mengembangkan model Convolutional Neural Network (CNN) yang efektif untuk mendeteksi tawuran dalam gambar atau video dari satu wilayah tertentu?
2. Bagaimana pengaruh ukuran dataset pelatihan terhadap akurasi dan kinerja model CNN dalam mendeteksi tawuran?
3. Bagaimana cara yang paling efektif untuk mengatasi keterbatasan dalam labeling data tawuran untuk melatih model CNN?
4. Sejauh mana akurasi model CNN dalam mendeteksi tawuran di berbagai kondisi pencahayaan, cuaca, dan situasi yang kompleks?
5. Bagaimana cara mengurangi angka false positives dan false negatives dalam pendeteksian tawuran menggunakan model CNN?
6. Bagaimana implementasi model CNN dalam skenario waktu nyata pada wilayah publik dapat mempengaruhi keamanan dan respons terhadap tawuran?
7. Bagaimana perbandingan performa model CNN dengan metode deteksi lain yang digunakan dalam konteks keamanan wilayah publik?
8. Bagaimana implikasi privasi dan etika terkait penggunaan sistem pemantauan ini dalam wilayah publik?
9. Bagaimana pengaruh regulasi dan kebijakan hukum terhadap penggunaan sistem pendeteksi tawuran dengan teknologi CNN dalam wilayah publik?
10. Apakah ada cara untuk mengintegrasikan sistem ini dengan sistem keamanan yang ada untuk meningkatkan respons terhadap tawuran dalam satu wilayah?

# Teori yang berkaitan : 
Dalam penelitian mengenai pendeteksi tawuran dalam satu wilayah menggunakan metode Convolutional Neural Network (CNN), terdapat beberapa teori dan konsep yang berkaitan. Berikut adalah beberapa teori yang relevan dengan topik ini:
Convolutional Neural Network (CNN): Ini adalah teori dasar yang menjadi landasan pengembangan model. CNN adalah jenis jaringan saraf tiruan yang terutama digunakan untuk pengolahan citra dan pengenalan pola dalam data gambar.
1. Deep Learning: CNN adalah salah satu komponen dari deep learning, yang merupakan cabang dari machine learning yang menggunakan jaringan saraf tiruan dengan banyak lapisan (deep neural networks) untuk memahami fitur-fitur hierarkis dalam data.
2. Pengolahan Citra: Teori pengolahan citra mencakup berbagai teknik untuk memproses gambar, termasuk normalisasi, augmentasi data, deteksi tepi, pemilihan fitur, dan teknik lain yang relevan untuk meningkatkan kualitas data masukan dan hasil pendeteksian.
3. Pendeteksian Objek: Pendeteksian tawuran dapat dikaitkan dengan teori pendeteksian objek dalam pengolahan citra. Ini melibatkan identifikasi dan pelokalan objek tertentu dalam gambar atau video.
4. Labeling Data dan Anotasi: Teori ini berkaitan dengan cara yang efisien dan akurat untuk memberikan label (anotasi) kepada dataset, yaitu menentukan gambar mana yang berisi tawuran dan mana yang tidak.
5. Transfer Learning: Teori ini mencakup teknik-teknik yang memungkinkan penggunaan model CNN yang telah dilatih sebelumnya (pre-trained) untuk tugas pendeteksian tawuran dengan fine-tuning.
6. Evaluasi Model: Teori evaluasi model melibatkan metrik-metrik seperti akurasi, presisi, recall, F1-score, dan ROC-AUC yang digunakan untuk mengukur kinerja model CNN dalam mendeteksi tawuran.
7. Kecerdasan Buatan dan Machine Learning: Penelitian ini sangat terkait dengan konsep-konsep dasar kecerdasan buatan dan machine learning, termasuk pembelajaran supervised, unsupervised, dan reinforcement learning.
8. Pemrosesan Real-Time: Bagian dari teori ini melibatkan strategi dan teknik untuk mengimplementasikan model CNN agar dapat berjalan secara real-time dalam situasi pemantauan wilayah publik.
9. Etika dan Privasi: Teori etika dan privasi berperan penting dalam pengembangan sistem pendeteksi tawuran, khususnya terkait dengan penggunaan teknologi pemantauan dalam wilayah publik dan perlindungan privasi individu.
10. Regulasi dan Kebijakan: Terkait dengan pemahaman tentang peraturan dan kebijakan yang berlaku terhadap penggunaan teknologi pendeteksi tawuran dalam wilayah publik.

