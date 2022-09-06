# Barcode

![gambar barcode]()
## Pendahuluan
**Barcode adalah** salah satu cara yang digunakan manusia dalam menjadikan sejumlah data secara khas meliputi nama barang, jenis barang, jumlah, harga, periode suatu barang, dan lain sebagainya. Semua informasi yang dibutuhkan untuk keperluan tertentu mengenai suatu barang akan dijadikan suatu kode yang mempunyai bentuk batang dengan warna hitam/gelap.Barcode juga bisa disebut dengan sederetan garis hitam putih yang disusun secara vertikal dengan tingkat ketebalan yang berbeda. Tingkat ketebalan dan jumlah garis dari barcode memberikan arti pada masing- masing komponen barcode dan membedakan antara jenis barcode yang satu dengan yang lain. Garis putih pada barcode adalah sebagai spasi sedangkan garis hitam menunjukkan pengkodean suatu barcode. Barcode menyediakan suatu metode pengkodean informasi teks yang sederhana dan murah. Barcode juga sebagai media penangkapan informasi data yang cepat dan akurat. Tujuan pokok barcode adalah untuk mengidentifikasi sesuatu dengan memberi label yang berisi barcode.

## Tujuan Pokok
Tujuan pokok barcode adalah untuk mengidentifikasi sesuatu dengan memberi label yang berisi barcode, selain untuk penyandian suatu barang juga dapat digunakan untuk penyandian sistem keamanan, seperti doorlock system. Aplikasi yang biasa dijumpai yaitu pada supermarket, dimana kode barcode yang tertera pada barang mengandung kode jenis barang, dan kode produsen

## Tahapan
Bentuk citra yang digunakan berupa citra biner sehingga pada data input harus dilakukan proses edge detection, grayscalling dan thresholding. Untuk mendapatkan input yang cocok untuk jaringan syaraf tiruan.

Sistem pembaca barcode berbasis pengolahan citra digital dengan menggunakan metode morfologi. 
- Barcode yang digunakan akan diambil fotonya dengan menggunakan kamera digital. Untuk mendapatkan citra yang diinginkan 
- dilakukan proses cropping sehinnga hanya citra barcode yang dihasilkan. 
Namun sebelumnya dilakukan pre-processing antara lain: 
- mengubah citra RGB ke citra gray, 
- mereduksi noise dengan median filter, 
- perbaikan kekontrasan dengan histogram ekualisasi, 
- mengubah citra gray ke citra biner (monocrhome). 

Preprecessing selanjutnya dengan menggunakan metode morfologi, antara lain: labeling, filling, dilatasi dan erosi.

Sistem diujikan dengan kondisi pencahayaan normal, -60, -40, -20, +20, +40 dan +60. Hasil implementasi diuji tingkat keakurasiannya. Akurasi dibedakan menjadi 3 macam, yaitu akurasi kiri, kanan dan akurasi total. Melalui implementasi dan pengujian, sistem mampu memberikan tingkat keakurasian lebih dari 70 % untuk akurasi kiri dan lebih dari 75% untuk akurasi kanan dan akurasi total.
