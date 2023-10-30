Nama : Bagas Mahda Dhani <br>
NIM : 215150700111038 <br>
Matkul : Pemin-A

# 📖 Register, Authentication dan Authorization

## 📒 Dasar Teori

### Authentication

<p align="justify">
Otentifikasi adalah proses untuk mengenali identitas dengan mekanisme pengasosiasian permintaan yang masuk dengan satu set kredensial pengidentifikasi. Kredensial yang diberikan akan dibandingkan dengan database informasi pengguna yang berwenang di dalam sistem operasi lokal atau server otentifikasi.
</p>

### Token

<p align="justify">
Token merupakan nilai yang digunakan untuk mendapatkan akses ke sumber daya yang dibatasi secara elektronik. Penggunaan token ditujukan pada web service yang tidak menyimpan state yang berkaitan dengan penggunaan aplikasi (stateless) seperti session.
</p>

### Authorization

<p align="justify">
Authorization merupakan proses pemberian hak istimewa yang dilakukan setelah proses authentication. Setelah pengguna diidentifikasi pada proses authentication, authorization akan memberikan hak istimewa dan tindakan yang diizinkan kepada pengguna yang ditentukan.
</p>

## 📒Langkah Percobaan

### Register

1. Memastikan terdapat tabel users yang dibuat menggunakan migration pada Bab 3 Basic Routing dan Migration . Berikut informasi kolom yang harus ada <br>
   ![Struktur Tabel User](../Screenshot/Modul_8/1_struktur_tabel_users.png)
2. Memastikan terdapat model User.php yang digunakan pada Bab 5 Model, Controller dan Request-Response Handler. Berikut baris kode yang harus ada <br>
   ![User.php](../Screenshot/Modul_8/2_User_php.png)
3. Membuat file `AuthController.php` dan isilah dengan baris kode berikut <br>
   ![Membuat AuthController](../Screenshot/Modul_8/3_AuthController_php.png)
4. Menambahkan route `auth/register` pada routes/web.php <br>
   ![Menambahkan route auth/register](../Screenshot/Modul_8/4_add_route_auth_register.png)
5. Menjalankan aplikasi pada endpoint `/auth/register` beserta body data username, email, dan password  
   ![Menjalankan aplikasi /auth/register](../Screenshot/Modul_8/5_menjalankan_register.png)

### Authentication

1. Membuat fungsi `login()` pada file `AuthController.php` <br>
   ![Membuat fungsi login](../Screenshot/Modul_8/6_add_function_login_AuthController.png)
2. Menambahkan route `auth/login` pada routes/web.php <br>
   ![Menambahkan route /auth/login](../Screenshot/Modul_8/7_add_route_login.png)
3. Menjalankan aplikasi pada endpoint `/auth/login` dengan body berikut <br>
   ![Menjalankan aplikasi /auth/login](../Screenshot/Modul_8/8_menjalankan_login.png)

### Token

1. Menjalankan perintah berikut untuk membuat migrasi baru<br>
   ![Membuat migrasi](../Screenshot/Modul_8/9_make_migrations_token.png)
2. Menambahkan baris berikut pada migration yang baru terbuat<br>
   ![Mengedit migration token](../Screenshot/Modul_8/10_edit_migrations_token.png)
3. Menambahkan atribut token di `$fillable` pada `User.php` <br>
   ![Menambahkan token pada $fillable](../Screenshot/Modul_8/11_add_token_in_fillable.png)
4. Menambahkan baris untuk menambahkan token pada file `AuthController.php` <br>
   ![Menambahkan token pada login](../Screenshot/Modul_8/12_add_token_in_login.png)
5. Menjalankan perintah `php artisan migrate` untuk menjalankan migrasi terbaru <br>
   ![Menjalankan migrasi terbaru](../Screenshot/Modul_8/13_php_artisan_migrate.png)
6. Menjalankan aplikasi pada endpoint `/auth/login` dengan body berikut. Salinlah token yang didapat ke notepad <br>
   ![Menjalankan aplikasi endpoint /auth/login](../Screenshot/Modul_8/14_login_response_token.png)

### Authorization

1. Membuat file `Authorization.php` pada folder `App/Http/Middleware` dan isilah dengan baris berikut<br>
   ![Membuat Authorization](../Screenshot/Modul_8/15_create_Authorization_php.png)
2. Menambahkan middleware yang baru dibuat pada `bootstrap/app.php`<br>
   ![Menambahkan middleware pada boostrapt/app](../Screenshot/Modul_8/16_add_middleware_in_boostrapt.png)
3. Membuat fungsi `home()` pada `HomeController.php` <br>
   ![Membuat fungsi home pada HomeController](../Screenshot/Modul_8/17_add_fungsi_home_in_HomeController.png)
4. Menambahkan route `home` pada `route/web.php` <br>
   ![Menambahkan route home](../Screenshot/Modul_8/18_add_home_route.png)
5. Menjalankan aplikasi pada endpoint `/home` dengan melampirkan nilai token yang didapat setelah login pada header <br>
   ![Menjalankan aplikasi endpoint /home](../Screenshot/Modul_8/19_run_home_with_token.png)
