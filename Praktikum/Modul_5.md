Nama : Bagas Mahda Dhani <br>
NIM : 215150700111038 <br>
Matkul : Pemin-A

# 📖 Dynamic Routing dan Middleware

## 📒Langkah Percobaan

### Dynamic Route

Dynamic route adalah route yang dapat berubah-ubah, seperti ketika kita membuka halaman web, kita melihat `/user/1` atau `/user/2`, hal ini dinamakan dynamic route. kita dapat menggunkaan syntax berikut ini untuk mengatur dynamic route lalu melakukan request

![Dynamic Route user/id](../Screenshot/Modul_5/1_user_id.png)

Kita juga dapat membuat dynamic route yang tidak hanya terbatas satu variabel saja. Kita dapat menambahkan sebanyak yang diperlukan seperti pada syntax berikut lalu melakukan request

![Dynamic Route post/id/comments/id](../Screenshot/Modul_5/2_post_id_comments_id.png)

Kita juga dapat membuat optional route pada dynamic route. Optional route tidak mengharuskan kita untuk memberi variabel ketika memanggil endpoint. Contoh optional route seperti syntax berikut lalu melakukan request

![Dynamic Route Optional Route](../Screenshot/Modul_5/3_users_null.png)

### Aliases Route

Aliases route digunakan untuk memberi nama route yang telah kita buat, hal ini memudahkan ketika memanggil route pada sebuah aplikasi. Kita dapat menggunakan syntax berikut ini untuk membuat aliases route

![Aliases Route](../Screenshot/Modul_5/4_aliases.png)

### Group Route

Group route memudahkan kita saat penulisan kode route pada file web.php. Kita dapat menggunkaan syntax berikut ini unuk membuat group route lalu melakukan request

![Group Route](../Screenshot/Modul_5/5_group_route.png)

### Middleware

Middleware digunakan untuk memfilter permintaan HTTP yang masuk pada aplikasi kita. Middleware adalah penengah antara komunikasi aplikasi dan client. Untuk membuat middleware, kita menambahkan file pada folder `app/http/Middleware`. Kita menambahakn file AgeMiddleware seperti dibawah ini 

![Membuat AgeMiddleware](../Screenshot/Modul_5/6_AgeMiddleware.png)

Kemudian, kita mendaftarkan AgeMidleware pada file `bootstrap/app.php` seperti dibawah ini
![Register Middleware](../Screenshot/Modul_5/7_register_middleware.png)

Terakhir, kita menambahkan middleware pada routes menambahkan opsi
middleware pada salah satu route seperti dibawah ini lalu melakukan request
![Membuat AgeMiddleware](../Screenshot/Modul_5/8_route_middleware.png)