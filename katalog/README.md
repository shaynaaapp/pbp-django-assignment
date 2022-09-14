Nama    : Shayna Putri Fitria
NPM     : 2106703084
Kelas   : PBP - F

Heroku app --> https://shaynaskatalog.herokuapp.com/katalog/ 

**1. Buatlah bagan yang berisi request client ke web aplikasi berbasis Django beserta responnya dan jelaskan pada bagan tersebut kaitan antara urls.py, views.py, models.py, dan berkas html;**

![Bagan Request Client] (katalog\Bagan.png)!

**2. Jelaskan kenapa menggunakan virtual environment? Apakah kita tetap dapat membuat aplikasi web berbasis Django tanpa menggunakan virtual environment?**

*Jelaskan kenapa menggunakan virtual environment?*
Virtual environment adalah environment yang terisolasi dari environment-environment lainnya. Istilahnya adalah ketika sebuah user membuat website A dan B, maka paket atau variabel yang di dalam website A berada diluar jangkauan website lain yang dibuat oleh user, contohnya website B.

Dalam kata-kata lain, tentunya setiap website membutuhkan dependencies nya sendiri yang berbeda-beda untuk setiap projectnya yang mungkin berada pada suatu sistem operasi yang sama. Alasan penggunaan virtual environment sangat disarankan adalah untuk menghindari perubahan-perubahan sistem atau library suatu program karena sedang mengubah program-program lainnya.

*Apakah kita tetap dapat membuat aplikasi web berbasis Django tanpa menggunakan virtual environment?*
Jika seorang user hanya ingin membuat 1 program dalam 1 sistem operasi, maka kemungkinan pembuatan aplikasi berbasis Django tanpa menggunakan virtual environment dapat dilakukan. Namun, hal tersebut juga berpotensi dapat menimbulkan sebuah error. Tidak semua program yang akan dibuat dapat dijalankan oleh semua library. Sehingga, menurut saya jawabannya adalah bisa (dalam kemungkinan yang kecil) namun sangat riskan, sehingga sangat disarankan untuk menggunakan virtual environment.

*Ilustrasi*
Ilustrasinya adalah jika Andi membuat suatu program A menggunakan library X karena memang library itulah yang sesuai dengan ketentuan program A, sehingga sistem operasi yang digunakan oleh Andi adalah menggunakan library X. Namun, Andi ingin membuat program kedua, yaitu B yang tidak dapat menggunakan library X, tetapi program B perlu menggunakan library Y untuk bisa dijalankan. Sehingga, Andi perlu mengubah library nya menjadi library Y pada sistem operasinya. Hal tersebut dapat menimbulkan error pada program A karena sistem operasi Andi tidak lagi menjalankan library X yang dibutuhkan oleh program A.

**3. Jelaskan bagaimana cara kamu mengimplementasikan poin 1 sampai dengan 4 di atas.**

*Membuat sebuah fungsi pada views.py yang dapat melakukan pengambilan data dari model dan dikembalikan ke dalam sebuah HTML.*
a. Membuat fungsi pada views.py di folder katalog bernama show_katalog. Fungsi tersebut menerima sebuah database dari Model yang kemudian di render ke template html dan kemudian ditampilkan sesuai dengan template tersebut.
*Membuat sebuah routing untuk memetakan fungsi yang telah kamu buat pada views.py.*
b. Membuat file pada aplikasi katalog bernama urls.py untuk melakukan routing terhadap fungsi views dengan menjalankan fungsi show_katalog pada URL patterns aplikasi katalog
*Memetakan data yang didapatkan ke dalam HTML dengan sintaks dari Django untuk pemetaan data template.*
c. Pada step sebelumnya, sebuah fungsi pada views.py akan digunakan untuk mengambil fungsi query ke database dari Model CatalogItem yang kemudian disimpan pada variabel context. Django akan memunculkan data tersebut pada halaman HTML.
*Melakukan deployment ke Heroku terhadap aplikasi yang sudah kamu buat sehingga nantinya dapat diakses oleh teman-temanmu melalui Internet.*
d. Membuat sebuah aplikasi baru pada Heroku yang kemudian API KEY dan APP NAME nya disimpan dalam secrets pada repository yang digunakan. Menghubungkan Heroku dengan Github dan melakukan deploy aplikasi katalog
    

