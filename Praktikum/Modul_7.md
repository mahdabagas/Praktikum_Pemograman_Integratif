Nama : Bagas Mahda Dhani <br>
NIM : 215150700111038 <br>
Matkul : Pemin-A

# 📖 Relasi One-to-Many dan Many-to Many

## 📒 Dasar Teori

### Relasi

<p align="justify">
Hubungan antar tabel yang dilakukan dengan pencocokan primary key dengan foreign key untuk mengombinasikan data dari satu tabel dengan tabel lainnya. 
</p>

### Foreign Key

<p align="justify">
Properti yang digunakan untuk menandai hubungan dua tabel atau lebih. Foreign key pada tabel anak (child) akan menunjuk tabel induk (parent) yang menjadi referensinya (reference). 
</p>

### One-to-Many

<p align="justify">
Relasi yang menunjukkan hubungan antar tabel dimana baris pada tabel induk dapat terhubung dengan satu atau lebih baris di tabel anak. Sementara baris pada tabel anak hanya dapat terhubung dengan satu baris di tabel induk. 
</p>

### Many-to-Many

<p align="justify">
Relasi yang menunjukkan hubungan antar tabel dimana baris pada tabel induk dapat terhubung dengan satu atau lebih baris di tabel anak. Berlaku sebaliknya pada tabel anak yang dapat terhubung dengan satu atau lebih baris di tabel induk. 
</p>

### Junction Table

<p align="justify">
Tabel yang digunakan untuk mengatur kombinasi baris pada relasi many-to-many. Junction table berisi foreign key dari kedua tabel yang memiliki relasi many-to-many. 
</p>

## 📒Langkah Percobaan

### Pembuatan Tabel

Berikut ini tabel yang akan digunakan pada praktikum kali ini
![Tabel User](../Screenshot/Modul_7/1_list_table.png)

1. Memastikan server database aktif dan membuat database dengan nama `lumenapi`<br>
   ![Memastikan server database dan nama database](../Screenshot/Modul_7/2_database_lumenapi.png)
2. Mengubah konfigurasi database pada file `.env` <br>
   ![Mengkonfigurasi env](../Screenshot/Modul_7/3_konfigurasi_env.png)
3. Menghidupkan library bawaan lumen dengan membuka file `app.php` pada folder `boostrapt` <br>
   ![Mengaktifkan library lumen](../Screenshot/Modul_7/4_menghidupkan_library.png)
4. Menjalankan Command untuk membuat file migration
   ![Membuat file migration](../Screenshot/Modul_7/5_creates_migrations.png)
5. Mengubah fungsi `up()` pada file `create_post_table`
   ![Mengubah fungsi up() file create_post_table](<../Screenshot/Modul_7/6_up()_create_post_table.png>)
6. Mengubah fungsi `up()` pada file `create_comment_table`
   ![Mengubah fungsi up() file create_comment_table](<../Screenshot/Modul_7/7_up()_create_comment_table.png>)
7. Mengubah fungsi `up()` pada file `create_tags_table`
   ![Mengubah fungsi up() file create_tags_table](<../Screenshot/Modul_7/8_up()_create_tags_table.png>)
8. Mengubah fungsi `up()` pada file `create_post_tag_table`
   ![Mengubah fungsi up() file create_post_tag_table](<../Screenshot/Modul_7/9_up()_create_post_tag_table.png>)
9. Menjalankan command `php artisan migrate`
   ![Menjalankan command](../Screenshot/Modul_7/10_php_artisan_migrate.png)

### Pembuatan Model

1. Membuat file dengan nama `Post.php` dan mengisi dengan baris kode berikut <br>
   ![Membuat HomeController](../Screenshot/Modul_7/11_model_Post.png)
2. Membuat file dengan nama `Comment.php` dan mengisi dengan baris kode berikut <br>
   ![Mengedit route /](../Screenshot/Modul_7/12_model_comment.png)
3. Membuat file dengan nama `Tag.php` dan mengisi dengan baris kode berikut <br>
   ![Menjalankan aplikasi](../Screenshot/Modul_7/13_model_Tag.png)

### Relasi One-to-Many

1. Tambahkan fungsi `comments()` pada file Post.php<br>
   ![Menambahkan fungsi comment() pada file Post.php](<../Screenshot/Modul_7/14_comment()_post.png>)
2. Tambahkan fungsi `post()` dan atribut postId pada `$fillable` pada file `Comment.php`<br>
   ![Menambahkan fungsi post() pada file Comment.php](<../Screenshot/Modul_7/15_fillable_post()_Comment.png>)
3. Membuat file `PostController.php` dan isilah dengan baris kode berikut <br>
   ![Membuat file PostController.php](../Screenshot/Modul_7/16_create_PostController.png)
4. Membuat file `CommentController.php` dan isilah dengan baris kode berikut <br>
   ![Membuat file CommentController.php](../Screenshot/Modul_7/17_create_CommentController.png)
5. Tambahkan baris berikut pada `routes/web.php` <br>
   ![Menambahkan baris pada routes/web.php](../Screenshot/Modul_7/35_route_web.png)
6. Membuat satu post menggunakan Thunderbolt <br>
   ![Membuat satu post](../Screenshot/Modul_7/18_post_thunderbolt.png)
7. Membuat satu comment menggunakan Thunderbolt <br>
   ![Membuat satu comment](../Screenshot/Modul_7/19_comment_thundebolt.png)
8. Menampilkan post menggunakan Thunderbolt <br>
   ![Menampilkan post](../Screenshot/Modul_7/20_posts_1.png)

### Relasi Many to Many

1. Menambahkan fungsi `tags()` pada file Post.php<br>
   ![Menambahkan fungsi tags() pada file Post.php](../Screenshot/Modul_7/21_tags_Post.png)
2. Menambahkan fungsi `posts()` pada file Tag.php<br>
   ![Menambahkan fungsi posts() pada file Tag.php](<../Screenshot/Modul_7/22_post()_Tag.png>)
3. Membuat file `TagController.php` dan isilah dengan baris kode berikut <br>
   ![Membuat file TagController.php](../Screenshot/Modul_7/23_make_TagController.png)
4. Menambahkan fungsi `addTag` dan response tags pada `PostController.php` <br>
   ![Menambahkan fungsi addTag() pada PostController.php](../Screenshot/Modul_7/24_addTag_PostController.png)
5. Menambahkan baris berikut pada `routes/web.php` <br>
   ![Menambahkan baris pada routes/web.php](../Screenshot/Modul_7/25_add_route_tag.png)
6. Membuat satu tag menggunakan Thunderbolt <br>
   ![Membuat satu tag](../Screenshot/Modul_7/26_tag_post_thunderbolt.png)
7. Menambahkan tag `jadul` pada post `disana engkau berdua` <br>
   ![Menambahkan tag jadul pada post disana engkau berada](../Screenshot/Modul_7/27_put_post_tag.png)
8. Menampilkan post `disana engkau berdua`” menggunakan Thunderbolt <br>
   ![Menampilkan post disana engkau berada](../Screenshot/Modul_7/28_get_post_1.png)
9. Membuat postingan `tanpamu apa artinya` menggunakan Thunderbolt <br>
   ![Membuat post tanpamu apa artinya](../Screenshot/Modul_7/29_post_2.png)
10. Menambahkan tag `jadul` pada postingan `tanpamu apa artinya` <br>
    ![Menambahkan tag jadul pada post tanpamu ada artinya](../Screenshot/Modul_7/30_put_post_2_tag_1.png)
11. Membuat tag `lagu` menggunakan Thunderbolt <br>
    ![Membuat tag lagu](../Screenshot/Modul_7/31_tag_lagu.png)
12. Menambahkan tag `lagu` pada postingan `tanpamu apa artinya` <br>
    ![Menambahkan tag lagu pada post tanpamu aapa artinya](../Screenshot/Modul_7/32_put_post_2_tag_2.png)
13. Menampilkan post pertama <br>
    ![Menampilkan post pertama](../Screenshot/Modul_7/33_get_post_1.png)
14. Menampilkan post kedua <br>
    ![Menampilkan post kedua](../Screenshot/Modul_7/34_get_post_2.png)
