Nama : Bagas Mahda Dhani <br>
NIM : 215150700111038 <br>
Matkul : Pemin-A

# 📖 Basic Routing dan Migration

## 📒Langkah Percobaan

### GET

1. Menambahkan endpoint dengan method GET pada file web.php folder routes <br>
   ![Menambahkan endpoint GET](../Screenshot/Modul_4/1_menambahkan_endpoint_get.png)
2. Menjalankan aplikasi dengan command `php -S localhost:8080 -t public` <br>
   ![Menjalankan Aplikasi](../Screenshot/Modul_4/2_menjalankan_server.png)
3. Membuka browser dengan url `http://localhost:8080` <br>
   ![Membuka Web](../Screenshot/Modul_4/3_membuka_web_url.png)

### POST, PUT, PATCH, DELETE, dan OPTIONS

1. Menambahkan methode POST, PUT, PATCH, DELETE, dan OPTIONS pada file web.php folder routes <br>
   ![Menambahkan endpoint POST, PUT, PATCH, DELETE, OPTIONS](../Screenshot/Modul_4/4_post_put_patch_delete_options.png)
2. Menginstall extension Thunder client untuk melakukan request ke server <br>
   ![Menginstall extension thunder client](../Screenshot/Modul_4/5_install_thunder_client.png)
3. Membuat request dengan menekan "New Request" lalu memasukan method dan url yang dituju <br>
   ![Membuat request](../Screenshot/Modul_4/6_membuat_request.png)

### Migrasi Database

1. Membuat database dengan nama 'lumenapi' <br>
   ![Membuat database lumenapi](../Screenshot/Modul_4/7_membuat_database_lumenapi.png)
2. Mengubah konfigurasi database pada file .env <br>
   ![Konfigurasi file .env](../Screenshot/Modul_4/8_konfigurasi_.env.png)
3. Menghidupkan beberapa library bawaan dari lumen dengan membuka file app.php pada folder boostrapt <br>
   ![Menghidupkan library bawaan](../Screenshot/Modul_4/9_menghidupkan_library.png)
4. Membuat file migration untuk tabel user dan tabel product <br>
   ![Membuat file migration tabel user dan product](../Screenshot/Modul_4/10_migration_table_user_product.png)
5. Mengubah fungsi up pada file migration create_user_table <br>
   ![Mengubah fungsi up pada file create_user_table](../Screenshot/Modul_4/11_ubah_fungsiUp_user_table.png)
6. Mengubah fungsi up pada file migration <br>
   ![Mengubah fungsi up pada file create_product_table](../Screenshot/Modul_4/12_ubah_fungsiUp_product_table.png)
7. Kemudian menjalankan command `php artisan migrate` <br>
   ![menjalankan php artisan migrate](../Screenshot/Modul_4/13_jalankan_cmd.png)
