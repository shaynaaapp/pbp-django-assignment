Nama    : Shayna Putri Fitria
NPM     : 2106703084

# Tugas 3 - PBP
## Jelaskan perbedaan antara JSON, XML, dan HTML!

JSON adalah JavaScript Object Notation, XML adalah Extensible Markup Language, dan HTML adalah Hyperlink Markup Language. Perbedaan yang paling terlihat adalah bagaimana ketiga data tersebut ditampilkan, disimpan, dan diolah. 

**HTML**

- HTML adalah sebuah markup language yang digunakan untuk membuat sebuah web site yang nantinya ditampilkan pada WWW
- Markup language digunakan untuk mendeskripsikan struktur/ layout dari suatu website, bukan bahasa pemrograman karena tidak memiliki logika didalamnya
- Disusun dari baris-baris kode yang kemudian dikompilasi dalam sebuah file dan dieksekusi ke dalam tampilan layar laptop
- Ekstensi file HTML adalah .html

**JSON**

- JSON adalah sebuah format data
- Menyimpan data dalam format map yang terdiri dari key dan value
- Data JSON dapat dibaca oleh manusia yang dapat 
- Ekstensi JSON adalah .json

**XML**

- XML merupakan sebuah markup language
- Digunakan untuk menyimpan dan mentransfer, simpan dan kirim, data antar aplikasi dengan bantuan internet
- Ekstensi file XML adalah .xml

## Jelaskan mengapa kita memerlukan data delivery dalam pengimplementasian sebuah platform?

Dalam pembangunan suatu platform, akan ada banyak jenis data yang digunakan di dalamnya. Apalagi dengan perkembangan teknologi, sehingga data stream akan semakin besar dan kompleksitas pemrosesan data akan semakin berat. Konsep data delivery ini memudahkan pengimplementasian suatu platform dengan membantu mengolah, mengirimkan, atau men-transfer data sesuai dengan tipe data yang diminta. Permisalan jika website membutuhkan suatu file HTML, maka server akan mengembalikan file dengan ekstensi html. Atau jika suatu website membutuhkan suatu data untuk platformnya, maka server akan mengembalikan data dengan ekstensi xml atau json.

## Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas.

**a. Membuat suatu aplikasi baru bernama mywatchlist di proyek Django Tugas 2 pekan lalu -->** Menjalankan perintah "python manage.py startapp mywatchlist" di command prompt untuk membuat aplikasi baru. Dengan demikian, sebuah folder mywatchlist beserta default isinya akan dibuat pada direktori yang sesuai. Kemudian, kita perlu melakukan beberapa penyesuaian di settings dengan menambahkan 'mywatchlist' ke dalam array INSTALLED_APPS.

**b. Menambahkan path mywatchlist sehingga pengguna dapat mengakses http://localhost:8000/mywatchlist -->** Menambahkan fungsi show_mywatchlist ke dalam views.py yang mengembalikan rendering ke file html, membuat template dari file html yang diinginkan, serta membuat file urls.py untuk melakukan routing views.py terhadap file html dengan menambahkan url patterns mywatchlist.

**c. Membuat sebuah model MyWatchList dengan atribut -->** Membuat file models.py dan menyesuaikannya dengan data-data yang ingin dimasukan ke model dan mendefinisikan jenis data tersebut. Lalu, perlu melakukan migrasi skema model ke database Django lokal, serta menginisialisasikan data yang ingin ditampilkan dengan membuatnya dalam file ekstensi JSON dan me-load data tersebut. 

**d. Menambahkan minimal 10 data untuk objek MyWatchList yang sudah dibuat di atas -->** Memasukan data yang diinginkan ke dalam initial data pada file ekstensi JSON yang sudah dibuat sebelumnya.

**e. Mengimplementasikan sebuah fitur untuk menyajikan data yang telah dibuat sebelumnya dalam tiga format (HTML, JSON, XML) -->** Membuat fungsi baru pada views.py yang melakukan return sebuah HTTPResponse dengan content_type XML atau JSON untuk format XML atau JSON, serta return render untuk format HTML. 

**f. Membuat routing sehingga data di atas dapat diakses melalui URL -->** Memperbarui urls.py dengan menambahkan path url yang sesuai ke dalam urlpatterns, seperti contoh; path('[url path]', [fungsi yang sudah dibuat pada step sebelumnya], name=’[nama fungsi]’)

**g. Melakukan deployment ke Heroku terhadap aplikasi yang sudah kamu buat sehingga nantinya dapat diakses oleh teman-temanmu melalui Internet. -->** Karena saya melanjutkan repositori tugas 2 yang sudah pernah di deploy sebelumnya, maka yang saya lakukan adalah melakukan push perubahan repositori ke dalam github dan men-deploy ulang heroku.

## Mengakses tiga URL di poin 6 menggunakan Postman, menangkap screenshot, dan menambahkannya ke dalam README.md

**HTML**
![Screenshot Postman HTML](https://github.com/shaynaputri/tugas2-pbp/blob/main/mywatchlist/postman-html.jpg)

**JSON**
![Screenshot Postman JSON](https://github.com/shaynaputri/tugas2-pbp/blob/main/mywatchlist/postman-json.jpg)

**XML**
![Screenshot Postman XML](https://github.com/shaynaputri/tugas2-pbp/blob/main/mywatchlist/postman-xml.jpg)