Nama    : Shayna Putri Fitria

NPM     : 2106703084

Link Aplikasi: https://shaynaskatalog.herokuapp.com/todolist/ 

# Tugas 4: Pengimplementasian Form dan Autentikasi Menggunakan Django
## **Apa kegunaan {% csrf_token %} pada elemen <form>? Apa yang terjadi apabila tidak ada potongan kode tersebut pada elemen <form>?**

CSRF adalah kependekan dari Cross-Site Request Forgery adalah sebuah serangan yang membuat user mengirimkan request ke website lain melalui website yang sedang di akses. Kode ini digunakan untuk melindungi serangan-serangan dalam pengisian Form, seperti pengambil alihan akun. CSRF token digunakan untuk membandingkan token yang dimiliki oleh user dan request. Jike kedua token tidak sesuai, maka permintaan akan ditolak. Dan jika sesuai, maka pengeksekusian program akan terus berjalan.

Jika tidak ada potongan kode tersebut, maka bisa saja website yang sedang kita akses, dapat diakses oleh orang lain tanpa kita sadari. Sehingga, bisa saja ada perubahan-perubahan yang terjadi pada akun tersebut, misalnya perubahan pada data, foto, atau adanya transaksi.

## **Apakah kita dapat membuat elemen <form> secara manual (tanpa menggunakan generator seperti {{ form.as_table }})? Jelaskan secara gambaran besar bagaimana cara membuat <form> secara manual.**

Bisa. Form bisa dibuat secara manual, seperti pada file HTML taskform. Pengimplementasian untuk mendapatkan datanya adalah dengan method POST dan penggunaan CSRD token. Secara gambaran besar, kita perlu membuat tag table untuk penginisiasian tabel, lalu membuat objek/ elemen pada tag < tr > untuk row dan < td > untuk data cell row tersebut. Untuk input, perlu dibuat tag input dengan parameter tipe input yang akan diminta. Terdapat method request.POST.get() yang dapat digunakan untuk mengakses/ mengambil data input yang diberikan oleh user pada tag tersebut.

## **Jelaskan proses alur data dari submisi yang dilakukan oleh pengguna melalui HTML form, penyimpanan data pada database, hingga munculnya data yang telah disimpan pada template HTML.**

Dengan adanya tag input, kita dapat mengambil data yang diinput dengan method request.POST.get() dengan parameter data yang mau diambil. Kita perlu membuat sebuah object dengan potongan kode Task.objects.create() dengan parameter data-data yang perlu diinput ke model tersebut. Dengan begitu, data akan tersimpan pada Django Model Database. Pada fungsi show_todolist pada views, kita perlu mengakses data-data model tersebut dengan potongan kode Task.objects.filter() dengan parameter user yang sesuai dengan login. Data diinput dalam context pada function dan ditampilkan pada file HTML.

## **Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas.**

- ### **Membuat suatu aplikasi baru bernama todolist di proyek tugas Django yang sudah digunakan sebelumnya.**

    Membuat aplikasi baru dengan potongan kode (python manage.py startapp todolist) dan memasukan variabel 'todolist' ke INSTALLED_APP pada folder Django Project.

- ### **Menambahkan path todolist sehingga pengguna dapat mengakses http://localhost:8000/todolist.**

    Membuat fungsi pada views.py bernama show_todolist untuk menampilkan data pada HTML. Membuat file urls.py pada folder todolist dan menambahkan '' sebagai pathlist tautan tersebut dengan fungsi show_todolist yang sudah dibuat sebelumnya. Menambahkan juga path todolist/ pada urls di folder project_django.

- ### **Membuat sebuah model Task yang memiliki atribut sebagai berikut: user, date, title, description**

    Membuat class Model pada file models.py yang berisi field-field data yang ingin disimpan. Dalam program ini, field yang disimpan adalah user, data, title, description, dan apakah todolist sudah diselesaikan.

- ### **Mengimplementasikan form registrasi, login, dan logout agar pengguna dapat menggunakan todolist**

    Membuat 3 fungsi pada views.py untuk mengeksekusi fungsi Registrasi, Login, dan Logout. Dan untuk memastikan, setiap user yang ingin membuka todolist harus melakukan login, ditambahkan kode @login_required(login_url='/todolist/login/').

- ### **Membuat halaman utama todolist yang memuat username pengguna, tombol Tambah Task Baru, tombol logout, serta tabel berisi tanggal pembuatan task, judul task, dan deskripsi task.**

    Membuat folder templates dengan isinya file HTML. Pengimplementasian pembuatan elemen-elemennya diisi pada file HTML tersebut. Pemuatan username pengguna adalah dengan menggunakan variabel nama yang sebelumnya sudah didefinisikan pada context fungsi show_todolist dengan kode request.user.username. Pembuatan tombol tambah task baru dan logout adalah dengan menggunakan tag button yang mengarahkan pada href yang sesuai. Pembuatan tabel menggunakan tag table.

- ### **Membuat halaman form untuk pembuatan task. Data yang perlu dimasukkan pengguna hanyalah judul task dan deskripsi task**

    Membuat fungsi pada views.py untuk menambahkan task. Kita juga perlu membuat template baru, yaitu file HTML untuk taskform dengan tag form dan method POST yang meminta data title dan deskripsi todo list.

- ### **Membuat routing sehingga beberapa fungsi dapat diakses melalui URL**

    Agar bisa diakses, kita perlu memasukan path dari file HTML dan fungsi pada views.py dalam urls.py di folder todolist. 

- ### **Melakukan deployment ke Heroku**

    Melakukan push kode-kode yang sudah diperbarui ke GitHub, dan karena saya sudah menghubungkan github dengan heroku tujuan saya, maka aplikasi akan di deploy secara langsung.

- ### **Membuat dua akun pengguna dan tiga dummy data**

    Setelah aplikasi berhasil di deploy, kita dapat langsung mengisinya dengan data-data dan akun yang kita inginkan