Shayna Putri Fitria - 2106703084


# **Tugas 6 - Javascript dan AJAX**

## **Jelaskan perbedaan antara asynchronous programming dengan synchronous programming!**

- **Asynchronous Programming**

    Sebuah program yang dijalankan tanpa adanya urutan atau antrian, dilakukan secara bersamaan. Contohnya adalah AJAX

    - Disebut juga dengan multi-thread, yaitu menjalankan program secara paralel
    - Asynchronous adalah sebuah non-blocking yang akan mengirimkan beberapa file sekaligus ke server

- **Synchronous Programming**
    
    Sebuah program yang dijalankan secara sequential atau sesuai dengan urutan kode yang ditulis. 

    - Merupakan single-thread, yang membuat program hanya bisa menjalankan 1 proker di waktu yang sama
    - Synchronos adalah sebuah blocking parameter dan hanya bisa mengirimkan 1 file ke setiap server pada waktu tertentu
 
## **Dalam penerapan JavaScript dan AJAX, terdapat penerapan paradigma Event-Driven Programming.**
 
- Event Driven Programming merupakan salah satu paradigma programming yang alur pengeksekusiannya disesuaikan dengan event yang berjalan dan merupakan flow untuk pengeksekusian kode

## **Jelaskan maksud dari paradigma tersebut dan sebutkan salah satu contoh penerapannya pada tugas ini.**

Contohnya adalah dengan saat kita melakukan submit atau menekan suatu button. Pada penjelasan ini, khususnya akan ditekankan pada button yang akan menambahkan task dan deskripsi baru, penggunaan Modal dari AJAX. Penambahan task dan deskripsi akan dikelola atau digabungkan ketika suatu event terjadi, diantaranya adalah penekanan button.
 
## **Jelaskan penerapan asynchronous programming pada AJAX.**

Program secara automatis akan melakukan penambahan task, tanpa harus dilakukan refresh halaman terkait dan memunculkannya pada halaman depan. Setelah mendapatkan task baru, secara automatis, halaman akan diperbarui.

## **Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas.**

- Membuat views `show_json`  dan path baru untuk mengakses `todolist/json/` 
- Membuat views baru `tambah_task_ajax` baru untuk menambahkan task ke JSON
- Membuat modal untuk menambahkan task dan menambahkan tag form di dalam modal tersebut
- Membuat path di `urls.py`, sehingga `todolist/add/` mengarahkan pada fungsi tambah_task_ajax yang sudah dibuat di views
- Menghubungkan input di form dengan fungsi AJAX dengan menambahkan id pada tag input dan menghubungkannya dengan pengolahan data AJAX
- Menggunakan AJAX untuk melakukan get dan mengambil data dari JSON
- Menggunakan AJAX untuk melakukan post ketika button save_button diklik, dengan demikian, asynchronous programming akan terjadi
- Membuat button untuk menghapus task
- Membuat views baru untuk menghapus task, yaitu `delete_task_ajax`
- Membuat path `todolist/delete/{id}` dan menghubungkan views pada path
