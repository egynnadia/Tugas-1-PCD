
# TUGAS KELOMPOK 5

- Egyn Terescova Nadia
- Nurhaliza
- Risma Wulandari

## FILTER




## Low Pass Filtering

<p align = "justify">Low-pass filtering adalah proses filter yang melewatkan komponen citra dengan nilai intensitas yang rendah dan meredam komponen citra dengan nilai intensitas yang tinggi.<br>
LPF (Low Pass Filter) atau disebut juga smoothing filter merupakan salah satu metode untuk menghilangkan noise acak, noise berkala, dan menampilkan pola latar belakang. <br>
Fungsi dasar dari low-pass filter yang ideal adalah untuk memperkirakan rata-rata sebuah piksel dan semua piksel tetangga dan akhirnya mengganti nilai asli dari piksel tersebut. <br>
Low pass filter diterapkan untuk menghasilkan citra yang lebih halus dan lebih blur. </p>

<p align = "justify">Aturan kernel untuk low-pass filter adalah:<br>
1. Semua koefisien kernel harus positif.<br>
2. Jumlah semua koefisien kernel harus sama dengan 1.<br>

Contoh kernel yang dapat digunakan pada <b>low-pass filtering</b> adalah</p>

![low-pass](gambar/low-pass.png)



## High Pass Filtering

<p align = "justify">High Pass Filter (HPF) adalah proses filter yang mengambil citra dengan gradiasi intensitas yang tinggi dan perbedaan intensitas yang rendah akan dikurangi atau dibuang. High Pass Filtering adalah salah satu dari metode penajaman (sharpening).<br>
Tujuan utama dari proses penajaman ini adalah untuk menyoroti detail-detail halus dalam gambar atau untuk meningkatkan detail yang telah dikaburkan baik dalam kesalahan atau efek alami dari proses akuisisi citra tertentu.</p>

<p align = "justify">Aturan kernel untuk high-pass filter adalah:<br>
1. Koefisien penapis boleh negatif, nol, ataupun bernillai positif.<br>
2. Total keseluruhan koefisiennya ialah bernilai 0 ataupun 1.<br>
3. Apabila jumlah koefisiennya berjumlah = 0, maka setiap elemen yang rendah frekuensinya nilainya akan menurun. <br>
4. Namun, apabila total dari koefisien adalah = 1, maka elemen yang memiliki frekuensi rendah nilainya tetap sama dengan nilai semula.</p>

![high-pass](gambar/high-pass.png)

### Implementasi High Pass Filtering menggunakan Octave
<p align = "justify">

   1. Kode Program Manual <br>
       ![hpf](gambar/hpf.png)<br>
       ![hpf](gambar/hpf2.png)<br>
       ![hpf](gambar/hpf3.png)<br>

       <h3>Output Kode Program</h3>
       
       ![manual1](gambar/manual1.png)<br>
       ![manual2](gambar/manual2.png)<br>
       ![manual3](gambar/manual3.png)

<br>

   2. Kode Program yang Tersedia di Octave<br>
       ![hpf_kode](gambar/hpf_kode.png)<br>

       <h3>Output Kode Program</h3>

      - Kernel 1<br>
       ![kernel1](gambar/kernel1.png)<br>

      - Kernel 2<br>
       ![kernel2](gambar/kernel2.png)<br>

      - Kernel 3<br>
       ![kernel3](gambar/kernel3.png)<br>

      - Kernel 4<br>
       ![kernel4](gambar/kernel4.png)<br>

      - Kernel 5<br>
       ![kernel5](gambar/kernel5.png)<br>

      - Kernel 6<br>
       ![kernel1](gambar/kernel6.png)


## High Boost Filtering

<p align = "justify">High-Boost Filtering merupakan salah satu bagian dari operasi yang dapat dilakukan untuk melakukan perbaikan citra.<br>
High-Boost Filtering bertujuan untuk menekankan komponen frekuensi tinggi yang mewakili detail gambar tanpa menghilangkan komponen frekuensi rendah (seperti sharpening). Filter high boost dapat digunakan untuk mengubah komponen frekuensi tinggi.<br>
High boost filter disusun oleh semua pass filter dan edge detection filter (Laplacian filter). Dengan demikian,  High boost filtering menekankan  edge dan menghasilkan image sharpener.</p>

<p align = "justify">cara menghitung:<br>
Highboost = a Original – Lowpass

       = (a – 1) Original + Original – Lowpass

       = (a – 1) Original + Highpass

Jika a = 1, kita mendapatkan unsharp masking.<br>
Jika a >1, bagian citra original ditambahkan kembali ke citra hasil high pass filter. Highboost = (a – 1) Original + Highpass<br>

ilustrasi dari High Boost Filtering<br>

![high-boost](gambar/high-boost.png)

</p>


## Median Filtering

<p align = "justify">Median Filtering adalah salah satu teknik filter yang mengurutkan nilai intensitas sekelompok pixel, kemudian mengganti nilai pixel yang diproses dengan nilai mediannya (nilai tengahnya).<br>
Metode ini digunakan dalam penghalusan citra (image smoothing) atau menghilangkan derau noise. Filter ini merupakan suatu filter non linear yang dikembangkan oleh Tukey.
</p>

<p align = "justify">Algoritma dari Median Filtering<br>

- Memasukkan dan membaca image / gambar untuk dapat diproses
- Penentuan mask filter tersebut. Bisa 3x3 atau 5x5
- Mengurutkan nilai pixel dari nilai pixel terkecil ke terbesar
- Tentukan mediannya
- Mengubah nilai tengah pixel dengan nilai median yang telah ditemukan
- Proses diatas berulang hingga ke piksel terakhir citra
- Menampilkan gambar berupa perbandingan sebelum dan sesudah di filter</p>

## Edge Detection

1. Edge Detection Sobel

<p align = "justify"> Metode atau operator Sobel merupakan operator yang menghindari adanya perhitungan gradient di titik interpolasi. Operator Sobel menggunakan kernel ukuran 3x3 piksel untuk perhitungan gradientnya, dengan pembobotan yang lebih besar pada piksel-piksel yang dekat dengan titik pusat. Kelebihan dari metode sobel ini adalah kemampuan untuk mengurangi noise sebelum melakukan perhitungan deteksi tepi.<br>

Kernel filter yang digunakan dalam metode Sobel ini adalah:<br>

![kernel sobel](gambar/kernelSobel.PNG)<br>
</p>

<p align = "justify">Algoritma Edge Detection Sobel<br>

- Memasukkan dan membaca image / gambar untuk dapat diproses
- Mengkonversikan image RGB warna asli ke citra skala kelabu
- Mengubah citra menjadi dua kali lipat
- Pra-alokasikan matriks baru seukuran citra asli dengan nol
- Masukkan matriks kernel sobel
- Proses Deteksi Tepi dengan memperkirakan gradien komputasi dan besarnya vektor
- Mendefinisikan treshold gambar yang di filter
- Menampilkan citra hasil deteksi tepi

</p>

#### Implementasi Edge Detection Sobel menggunakan Octave
<p align = "justify">

   1. Kode Program Manual <br>
       ![Sobel](gambar/sobelManual1.PNG)<br>
       ![Sobel](gambar/sobelManual2.PNG)<br>

       <h3>Output Kode Program</h3>
       
       ![Output](gambar/sobelManual3.PNG)<br>
       ![Output](gambar/sobelManual4.PNG)<br>
       ![Output](gambar/sobelManual5.PNG)<br>

<br>

   2. Kode Program yang Tersedia di Octave<br>
       ![Sobel](gambar/sobelFungsi1.PNG)<br>

       <h3>Output Kode Program</h3>

       ![Sobel](gambar/sobelFungsi2.PNG)<br>

</p>

2. Edge Detection Prewitt

<p align = "justify"> Metode Prewitt merupakan pengembangan metode robert dengan menggunakan filter HPF yang diberi satu angka nol penyangga. Metode ini mengambil prinsip dari fungsi laplacian yang dikenal sebagai fungsi untuk membangkitkan HPF. Persamaan gradien pada operator prewitt sama dengan gradien pada operator sobel perbedaannya adalah pada prewitt menggunakan konstanta c = 1.<br>

Kernel filter yang digunakan dalam metode Prewitt ini adalah:<br>

![kernel Prewitt](gambar/kernelPrewitt.PNG)<br>
</p>

<p align = "justify">Algoritma Edge Detection Prewitt<br>

- Memasukkan dan membaca image / gambar untuk dapat diproses
- Mengkonversikan image RGB warna asli ke citra skala kelabu
- Mengubah citra menjadi dua kali lipat
- Pra-alokasikan matriks baru seukuran citra asli dengan nol
- Masukkan matriks kernel Prewitt
- Proses Deteksi Tepi dengan memperkirakan gradien komputasi dan besarnya vektor
- Mendefinisikan treshold gambar yang di filter
- Menampilkan citra hasil deteksi tepi

</p>

#### Implementasi Edge Detection Prewitt menggunakan Octave
<p align = "justify">

   1. Kode Program Manual <br>
       ![Prewitt](gambar/prewittManual1.PNG)<br>
       ![Prewitt](gambar/prewittManual2.PNG)<br>

       <h3>Output Kode Program</h3>
       
       ![Output](gambar/prewittManual3.PNG)<br>
       ![Output](gambar/prewittManual4.PNG)<br>
       ![Output](gambar/prewittManual5.PNG)<br>

<br>

   2. Kode Program yang Tersedia di Octave<br>
       ![Prewitt](gambar/prewittFungsi1.PNG)<br>

       <h3>Output Kode Program</h3>

       ![Prewitt](gambar/prewittFungsi2.PNG)<br>

</p>

