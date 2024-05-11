
## PCD_UTS_202231032_2024_ITPLN

Nama : Desi Fitriani Ramadan

NIM  : 202231032

## Laporan Praktikum UTS PCD C
# A. Tahapan cara menyelesaikan projek

## 1. Deteksi warna pada citra. 
Analisislah apa yang terjadi pada citra. 
Proyek ini memuat sebuah citra yang disebut 'Nama.jpg' menggunakan fungsi matplotlib.image.imread(). Citra tersebut kemudian ditampilkan menggunakan matplotlib.pyplot.imshow(). Setelah itu, kanal warna (merah, hijau, dan biru) dari citra tersebut dipisahkan menggunakan indexing NumPy. Proses pemisahan ini memungkinkan untuk menganalisis dan memahami kontribusi masing-masing warna terhadap citra secara terpisah.

Selanjutnya, citra yang telah dipisahkan menjadi kanal warna tersebut divisualisasikan dalam bentuk subplot menggunakan matplotlib.pyplot.subplots(). Ini memungkinkan untuk membandingkan kontribusi warna merah, hijau, dan biru secara visual. Dalam visualisasi ini, setiap kanal warna ditampilkan dalam bentuk citra grayscale untuk menyoroti intensitas piksel dalam masing-masing kanal.

Langkah berikutnya adalah perhitungan dan visualisasi histogram untuk masing-masing kanal warna menggunakan cv2.calcHist(). Histogram digunakan untuk memahami distribusi intensitas piksel dalam setiap kanal warna. Ini membantu dalam mengevaluasi sebaran warna dalam citra serta menyoroti kemungkinan ketidakseimbangan warna atau kejenuhan dalam gambar.

Selain itu, citra juga diproses dalam ruang warna HSV (Hue, Saturation, Value) untuk melakukan deteksi warna. Rentang warna untuk biru, merah, dan hijau ditentukan dalam ruang warna HSV dengan menentukan ambang bawah dan atas untuk masing-masing kanal (H, S, V) menggunakan np.array(). Hal ini memungkinkan untuk menangkap piksel dengan nilai warna yang berada dalam rentang yang ditentukan.

Terakhir, dilakukan deteksi warna menggunakan masker HSV untuk menangkap piksel biru, merah, dan hijau dalam citra. Masker tersebut kemudian digabungkan menggunakan operasi bitwise OR (cv2.bitwise_or()) untuk menciptakan masker gabungan yang menyoroti piksel yang sesuai dengan rentang warna yang telah ditentukan sebelumnya. Hasil deteksi warna kemudian divisualisasikan untuk memperoleh pemahaman yang lebih baik tentang kontribusi warna pada citra.

Melalui langkah-langkah tersebut, proyek berhasil melakukan analisis detil terhadap citra, baik dari sudut pandang kontribusi warna maupun distribusi intensitas piksel dalam kanal warna. Teknik-teknik pemrosesan citra dan analisis warna yang digunakan memberikan wawasan yang mendalam tentang sifat-sifat visual dari citra yang diamati.

## 2. Buat Histogram dan Analisis histogram. 
Proyek ini adalah membuat histogram untuk masing-masing kanal warna (merah, hijau, biru) dari citra. Histogram adalah representasi grafis dari distribusi intensitas piksel dalam citra. Histogram dapat memberikan informasi tentang sebaran warna dalam citra, termasuk kecerahan dan kontrasnya. Histogram yang dihasilkan dari masing-masing kanal warna digunakan untuk menganalisis sebaran intensitas piksel dalam rentang nilai yang berbeda.

Histogram biru, histogram hijau, dan histogram merah masing-masing menunjukkan distribusi intensitas piksel dalam kanal warna yang sesuai. Pada histogram, sumbu x mewakili nilai intensitas piksel (dari 0 hingga 255), sedangkan sumbu y mewakili jumlah piksel dengan intensitas tertentu. Dari histogram tersebut, dapat dianalisis distribusi intensitas piksel dalam citra, misalnya apakah ada ketimpangan warna atau apakah terdapat kecenderungan tertentu dalam sebaran warna.

Histogram warna merupakan gabungan dari ketiga kanal warna (RGB) dan memberikan gambaran tentang distribusi intensitas piksel secara keseluruhan dalam citra. Dengan menganalisis histogram warna, dapat dipahami distribusi intensitas piksel untuk semua warna yang ada dalam citra. Hal ini membantu untuk memahami secara keseluruhan kontribusi warna dalam citra dan dapat digunakan sebagai dasar untuk proses pengolahan citra lebih lanjut.

Selain itu, histogram juga dapat digunakan untuk mengevaluasi kontras citra. Kontras mengacu pada perbedaan antara tingkat kecerahan piksel yang berdekatan. Dengan melihat histogram, dapat dianalisis apakah citra memiliki kontras yang baik atau apakah ada area dengan kontras yang rendah yang memerlukan penyesuaian lebih lanjut.

Dalam proyek ini, histogram digunakan sebagai alat analisis untuk memahami distribusi intensitas piksel dalam citra dan untuk mengevaluasi kontras citra. Analisis histogram memberikan wawasan tentang karakteristik visual citra, yang dapat digunakan untuk membuat keputusan tentang teknik pengolahan citra yang tepat.

## 3. Mencari dan mengurutkan ambang batas terkecil sampai dengan terbesar.
Proyek ini melibatkan pencarian dan pengurutan ambang batas dari yang terkecil hingga yang terbesar untuk menentukan rentang warna yang ingin diisolasi dalam citra. Pada tahap ini, nilai-nilai ambang batas ditentukan untuk warna biru, merah, dan hijau dalam format HSV. Ambang batas ini penting karena mereka menentukan rentang warna yang akan diekstraksi dari citra menggunakan masker.

Untuk warna biru, nilai ambang batas yang ditentukan adalah:

Ambang bawah: [100, 50, 50]

Ambang atas: [130, 255, 255]

Ini dipilih karena mencakup rentang nilai hue, saturation, dan value yang khas dari warna biru. Rentang ini dipilih setelah eksperimen dan observasi terhadap citra untuk memastikan bahwa warna biru dapat diisolasi secara efektif.

Sementara untuk warna merah, karena hue merah melintasi nilai 0/180 dalam format HSV, kami menggunakan dua rentang untuk menangkap warna merah yang mungkin terbagi di sekitar ambang 0/180. Nilai ambang batas untuk merah adalah:

Ambang bawah 1: [0, 50, 50]

Ambang atas 1: [10, 255, 255]

Ambang bawah 2: [170, 50, 50]

Ambang atas 2: [180, 255, 255]

Hal ini memungkinkan kami untuk menangkap warna merah yang terletak di kedua sisi rentang hue yang melintasi nilai 0/180.

Terakhir, untuk warna hijau, nilai ambang batas yang ditentukan adalah:

Ambang bawah: [50, 50, 50]

Ambang atas: [80, 255, 255]

Rentang ini dipilih untuk menangkap warna hijau dengan baik berdasarkan karakteristiknya dalam format HSV.

Nilai-nilai untuk warna "None" diambil dari seluruh rentang warna yang tidak termasuk dalam rentang biru, merah, dan hijau yang telah ditentukan sebelumnya.
Didalam ruang warna HSV, nilai hue (H) dari 0 hingga 180 mencakup seluruh spektrum warna. Maka, nilai-nilai yang tidak termasuk dalam rentang warna biru, merah, dan hijau dapat didefinisikan sebagai nilai yang berada di luar ambang batas yang telah ditentukan untuk warna-warna tersebut.
Rentang nilai saturasi (S) dari 0 hingga 255 dan nilai intensitas (V) dari 0 hingga 255 digunakan untuk mencakup seluruh tingkat kecerahan dan saturasi warna "None" yang mungkin ada dalam gambar.

Nilai-nilai ambang batas yang dihasilkan melalui proses ini kemudian digunakan untuk membuat masker yang memisahkan area-area dengan warna tertentu dari citra. Proses ini penting untuk analisis atau manipulasi lebih lanjut berdasarkan kriteria warna yang telah ditetapkan sebelumnya.

# Jelaskan teori yang mendukung mengenai projek terkait
Projek ini mengimplementasikan beberapa konsep penting dalam pengolahan citra digital dan deteksi warna. Berikut adalah penjelasan mendalam tentang teori yang mendukung projek tersebut:

1. Pengolahan Citra Digital: Menggunakan library OpenCV dan NumPy, yang merupakan alat penting dalam pengolahan citra digital. OpenCV menyediakan berbagai fungsi untuk membaca, memanipulasi, dan menganalisis citra digital, sementara NumPy digunakan untuk manipulasi matriks yang merepresentasikan citra.

2. Representasi Warna: Citra digital direpresentasikan dalam tiga saluran warna: merah (R), hijau (G), dan biru (B) dalam ruang warna RGB. Proyek ini memanfaatkan representasi warna ini untuk memisahkan saluran warna dan menganalisis histogram masing-masing saluran.

3. Histogram Citra: Histogram citra adalah grafik yang menunjukkan distribusi intensitas piksel di dalam citra. Dalam projek ini, histogram digunakan untuk menganalisis distribusi intensitas warna di dalam saluran merah, hijau, dan biru.

4. Konversi Ruang Warna: Konversi citra dari ruang warna RGB ke HSV (Hue, Saturation, Value) dilakukan untuk memfasilitasi deteksi warna yang lebih efektif. Ruang warna HSV memisahkan informasi warna dari kecerahan dan saturasi, memudahkan dalam menentukan ambang batas warna.

5. Masker Warna: Penggunaan masker warna memungkinkan untuk menyoroti piksel dalam citra yang memiliki warna tertentu. Dalam proyek ini, masker warna digunakan untuk menangkap piksel dengan warna biru, merah, hijau, atau kombinasi dari ketiganya.

6. Ambang Batas: Nilai ambang batas ditentukan untuk setiap saluran warna atau kombinasi saluran warna, yang digunakan untuk mengklasifikasikan piksel dalam citra sebagai bagian dari objek yang ingin dideteksi atau tidak.

7. Deteksi Warna: Proses deteksi warna dilakukan dengan membuat masker warna untuk setiap warna yang ingin dideteksi, lalu menggabungkan masker tersebut untuk mendapatkan citra yang menyoroti warna-warna tersebut.

8. Analisis Histogram: Histogram dari saluran warna biru, merah, dan hijau digunakan untuk menganalisis distribusi intensitas warna dalam citra. Informasi dari histogram membantu dalam menentukan ambang batas yang tepat untuk deteksi warna.

9. Pemrosesan Masker: Setelah pembuatan masker warna, operasi bitwise dilakukan untuk menggabungkan masker tersebut dan memperoleh citra yang menyoroti warna yang ingin dideteksi.

10. Penerapan Konsep dalam Deteksi Warna: Melalui penggunaan konsep-konsep tersebut, proyek ini berhasil mengimplementasikan deteksi warna yang efektif dalam citra digital. Dengan menggunakan algoritma dan teknik yang sesuai, deteksi warna dapat digunakan dalam berbagai aplikasi praktis, seperti pemrosesan citra medis, pemantauan lingkungan, dan deteksi objek dalam bidang visi komputer.