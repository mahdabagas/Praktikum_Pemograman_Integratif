Nama : Bagas Mahda Dhani <br>
NIM : 215150700111038 <br>
Matkul : Pemin-A

# 📖 Model, Controller dan Request-Response Handler

## 📒 Dasar Teori

### Model

<p align="justify">
Model merupakan bagian yang bertugas untuk menyiapkan, mengatur, memanipulasi, dan mengorganisasikan data yang ada di database. Model merepresentasikan kolom apa saja yang ada pada databas, termasuk relasi dan primary key dapat didefinisikan di dalam model. Dengan menggunakan perintah Artisan, pembuatan model pada Laravel dapat dilakukan dengan satu perintah menggunakan
</p>

`php artisan make:model nama_model`

### Controller

<p align="justify">
Controller merupakan bagian yang menjadi tempat berkumpulnya logika pemrograman yang digunakan untuk memisahkan organisasi data pada database. Dalam beberapa kasus, controller menjadi penghubung antara model dan view pada arsitektur MVC
</p>

### Request Handler

<p align="justify">
Request handler adalah fungsi yang digunakan untuk berinteraksi dengan request yang datang. Request handler dapat digunakan untuk melihat apa saja yang dikirimkan oleh user seperti parameter, query, dan body.
</p>

### Response Handler

<p align="justify">
Response handler adalah fungsi yang digunakan untuk membentuk output yang diharapkan kepada user dan beberapa properti selain data seperti status code dan header.
</p>

## 📒Langkah Percobaan

### Model

1. Pastikan terdapat tabel users yang dibuat menggunakan migration pada bab sebelumnya<br>
   ![Tabel User](../Screenshot/Modul_6/0_tabel_user.png)
2. Melakukan edit model `User.php` yang ada di dalam path `app/Models/` <br>
   ![Edit Model User](../Screenshot/Modul_6/2_edit_Model_User.png)

### Controller

1. Salin `ExampleController.php` pada folder `app/Http/Controllers`, ganti namanya menjadi `HomeController.php` dan membuat fungsi `index()`. <br>
   ![Membuat HomeController](../Screenshot/Modul_6/3_make_HomeController.png)
2. Mengubah route `/` pada file `routes/web.php` menjadi seperti gambar dibawah <br>
   ![Mengedit route /](../Screenshot/Modul_6/4_edit_route.png)
3. Menjalankan aplikasi untuk melihat hasilnya <br>
   ![Menjalankan aplikasi](../Screenshot/Modul_6/5_run_application.png)

### Request Handler

1. Lakukan import library Request<br>
   ![Mengimpor library Request](../Screenshot/Modul_6/6_import_library_request.png)
2. Ubah fungsi index menjadi gambar di bawah ini<br>
   ![Mengedit fungsi index](../Screenshot/Modul_6/7_edit_fungsi_index.png)
3. Menjalankan aplikasi untuk melihat hasilnya <br>
   ![Menjalankan aplikasi](../Screenshot/Modul_6/8_run_application.png)

### Response Handler

1. Lakukan import library Response  <br>
   ![Mengimpor library Response](../Screenshot/Modul_6/9_import_library_response.png)
2. Membuat fungsi `hello()`<br>
   ![Membuat fungsi hello](../Screenshot/Modul_6/10_create_fungsi_hello.png)
3. Tambahkan route `/hello` pada file `routes/web.php` <br>
   ![Menambahkan route hello](../Screenshot/Modul_6/10b_menambahkan_route_hello.png)
4. Jalankan aplikasi pada route `/hello` untuk melihat hasilnya <br>
   ![Menjalankan aplikasi pada route hello](../Screenshot/Modul_6/11_run_application_route_hello.png)

### Penerapan

1. Lakukan import model User <br>
   ![Mengimport library Model](../Screenshot/Modul_6/12_import_model.png)
2. Menambahkan 3 fungsi di `HomeController.php` <br>
   ![Menambahkan 3 fungsi pada HomeController](../Screenshot/Modul_6/13_membuat_3_fungsi.png)
3. Menambahkan ketiga route pada file `routes/web.php` menggunakan group route <br>
   ![Menghidupkan library bawaan](../Screenshot/Modul_6/14_add_3_route.png)
4. Jalankan aplikasi pada route `/users/default` menggunakan Thunderbolt <br>
   ![Menjalankan aplikasi pada route users/default](../Screenshot/Modul_6/15_run_app_route_users_default.png)
5. Jalankan aplikasi pada route `/users/new` dengan mengisi body  lalu melihat responsenya <br>
   ![Menjalankan aplikasi pada route users/new](../Screenshot/Modul_6/16_run_app_usrs_new.png)
6. Jalankan aplikasi pada route `/users/all` <br>
   ![Menjalankan aplikasi pada route users/all](../Screenshot/Modul_6/17_run_app_users_all.png)
