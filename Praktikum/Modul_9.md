Nama : Bagas Mahda Dhani <br>
NIM : 215150700111038 <br>
Matkul : Pemin-A

# 📖 JSON Web Token (JWT)

## 📒 Dasar Teori

### JSON Web Token

<p align="justify">
JSON Web Token (JWT) adalah standar terbuka yang mendefinisikan cara ringkas dan mandiri untuk transmisi informasi antar pihak secara aman dalam bentuk objek JSON. Informasi ini dapat diverifikasi karena ditandatangani secara digital menggunakan secret key (dengan algoritma HMAC) atau pasangan kunci publik/pribadi menggunakan RSA atau ECSDA
</p>

### Penggunaan

<div align="justify">
    <ul> 
        <li>
            <p>Authorization</p>
            <p>Setelah user masuk, setiap request perlu menyertakan. Hal ini mengizinkan user untuk mengakses route, service, dan resource yang diizinkan menggunakan token.</p>
        </li>
        <li>
            <p>Information Exchange</p>
            <p>JWT dapat digunakan untuk mengamankan transmisi data antar pihak. Hal ini dimungkinkan karena JWT dapat ditandatangani untuk memastikan data dikirimkan oleh pengirim yang benar. Penggunaan signature yang dihitung dengan header dan payload dapat memverifikasi data yang dikirimkan tidak diubah di tengah jalan.</p>
        </li>
    </ul>
</div>

### Struktur

<p align="justify">JSON Web Token menggunakan pola berikut. Header, payload, signature dipisahkan dengan titik.</p>
<p style="background-color:grey; color: black; padding: 5px">xxxxx.yyyyy.zzzzz</p>
<div align="justify">
    <ul> 
        <li>
            <p>Header</p>
            <p>Berisi algoritma yang digunakan serta jenis token.</p>
            <p style="background-color:grey; color: white; padding: 8px">
                { <br>
                    "alg": "HS256", <br>
                    "typ": "JWT" <br>
                }
            </p>
            <p>Data di atas akan di-encode menjadi Base64</p>
            <p style="background-color:grey; color: white; padding: 8px">
                eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9
            </p>
        </li>
        <li>
            <p>Payload</p>
            <p>Berisi data yang ditransmisikan. Walaupun JWT memastikan dapat yang dikirim tidak diubah, Base64 yang digunakan dapat di-decode. Hal ini membuat JWT tidak dapat digunakan untuk transmisi data rahasia seperti plain text password.</p>
            <p style="background-color:grey; color: white; padding: 8px">
                { <br>
                    "sub": "1234567890", <br>
                    "name": "Nilou", <br>
                    "iat": 1516239022 <br>
                }
            </p>
            <p>Data di atas akan di-encode menjadi Base64</p>
            <p style="background-color:grey; color: white; padding: 8px">
                eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6Ik5pbG91IiwiaWF0IjoxNTE2MjM5MDIyfQ
            </p>
        </li>
        <li>
            <p>Signature</p>
            <p>Hasil penandatanganan yang dilakukan dengan header dan payload yang sudah di-encode diikuti dengan secret key menggunakan algoritma yang didefinisikan di header. Proses penandatanganan menggunakan rumus sebagai berikut</p>
            <p style="background-color:grey; color: white; padding: 8px">
                HMACSHA256( <br>
                    base64UrlEncode(header) + "." + <br>
                    base64UrlEncode(payload), <br>
                secret)
            </p>
            <p>Yang menghasilkan signature sebagai berikut</p>
            <p style="background-color:grey; color: white; padding: 8px">
                58_9vUl1BQN7Fpqs7u7r4tyJC_wvFJ5n4GibGTVnGpU
            </p>
        </li>
    </ul>
</div>

## 📒Langkah Percobaan

### Penyesuaian database

1. Melakukan perubahan pada length kolom token dengan menghapus parameter 72 di belakangnya<br>
   ![Edit Migrations add_column_token_to_user](../Screenshot/Modul_9/1_edit_migrations_add_column_token_to_users.png)
2. Menjalankan perintah `php artisan migrate:fresh` untuk memperbaharui migrasi dan menghapus data yang lama <br>
   ![php artisan migrate refresh](../Screenshot/Modul_9/2_php_artisan_migrate_fresh.png)
3. Menjalankan aplikasi pada endpoint `/auth/register` dengan body berikut. <br>
   ![Menjalankan pada route /auth/register](../Screenshot/Modul_9/3_run_route_auth_register.png)

### JWT Manual

1. Menambahkan ketiga fungsi berikut pada `AuthController.php` <br>
   ![Menambahkan 3 fungsi](../Screenshot/Modul_9/4_add_3_function_add_base64_sign_jwat.png)
2. Melakukan perubahan pada fungsi `login` <br>
   ![Mengedit fungsi login](../Screenshot/Modul_9/5_edit_login_AuthController.png)
3. Menambahkan keempat fungsi berikut pada `Middleware/Authorization.php` <br>
   ![Menambahkan 4 fungsi](../Screenshot/Modul_9/6_add_4_function_Auhtorization.png)
4. Melakukan perubahan pada fungsi `handle` <br>
   ![Mengedit fungsi handle](../Screenshot/Modul_9/7_edit_handle_Authorization.png)
5. Menjalankan aplikasi pada endpoint `/auth/login` dengan body berikut. Salinlah token yang didapat ke notepad <br>
   ![Menjalankan pada route /aut/login](../Screenshot/Modul_9/8_run_auth_login.png)
6. Menjalankan aplikasi pada endpoint `/home` dengan melampirkan nilai token yang didapat setelah login pada header <br>
   ![Menjalankan route /home](../Screenshot/Modul_9/9_run_home.png)

### JWT Library

1. Melakukan generate jwt key secara online menggunakan website Djecrety dan menambahkan pada .env <br>
   ![generate jwt key](../Screenshot/Modul_9/10_Djecrety.png)
   ![Instalasi package jwt firebase](../Screenshot/Modul_9/11_JWT_SECRET_ENV.png)
2. Melakukan instalasi package jwt firebase dengan menggunakan command `composer require firebase/php-jwt`<br>
   ![Instalasi package jwt firebase](../Screenshot/Modul_9/12_install_jwt_php.png)
3. Menambahkan fungsi berikut pada file `AuthController`<br>
   ![Menambahkan fungsi jwt](../Screenshot/Modul_9/13_add_function_jwt_AuthController.png)
4. Lakukan perubahan pada fungsi `login` menjadi seperti berikut <br>
   ![Mengedit fungsi login](../Screenshot/Modul_9/14_edit_login_jwt.png)
5. Membuat file `JwtMiddleware.php` dan isikan baris code berikut <br>
   ![Membuat file JWT Middleware](../Screenshot/Modul_9/15_add_JwtMiddleware.png)
6. Daftarkan middleware yang telah dibuat pada `bootstrap/app.php` <br>
   ![Mendaftarkan middleware pada bootstrap/app.php](../Screenshot/Modul_9/16_add_middleware_jwt_in_bootsrapt.auth.png)
7. Menambahkan baris berikut pada file `web.php` <br>
   ![Mengedit route](../Screenshot/Modul_9/17_edit_route_home.png)
8. Menjalankan aplikasi pada endpoint `/auth/login` dengan body berikut. Salinlah token yang didapat ke notepad yang nanti akan digunakan ketika mengakses .home <br>
   ![Menjalankan route /auth/login](../Screenshot/Modul_9/18_run_auth_login.png)
9. Menjalankan aplikasi pada endpoint `/home` dengan melampirkan nilai token yang didapat setelah login pada header <br>
   ![Menjalankan route /home](../Screenshot/Modul_9/19_run_home.png)
