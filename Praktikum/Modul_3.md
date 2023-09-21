Nama : Bagas Mahda Dhani <br>
NIM : 215150700111038 <br>
Matkul : Pemin-A

# 📖 Integrasi MongoDB dan Express

## 📒 Dasar Teori

### Express

<p align="justify">
Express.js adalah framework web app untuk Node.js yang ditulis dengan bahasa pemrograman JavaScript. Framework open source ini dibuat oleh TJ Holowaychuk pada tahun 2010 lalu. Express.js adalah framework back end. Artinya, ia bertanggung jawab untuk mengatur fungsionalitas website, seperti pengelolaan routing dan session, permintaan HTTP, penanganan error, serta pertukaran data di server.
</p>

### Mongoose

<p align="justify">
Mongoose adalah pustaka berbasis Node.js yang digunakan untuk pemodelan data pada MongoDB. Mongoose menyediakan feature diantaranya, model data application berbasis Schema. Dan juga termasuk built-in type casting, validation, query building, business logic hooks dan masih banyak lagi yang menjadi ke andalan mongoose.
</p>

### Async Await

<p align="justify">
Async sendiri merupakan sebuah fungsi yang mengembalikan sebuah Promise. Await sendiri merupakan fungsi yang hanya berjalan di dalam Async. Await bertujuan untuk menunda jalannya Async hingga proses dari Await tersebut berhasil dieksekusi. 
</p>

### Model

<p align="justify">
Model merupakan bagian yang bertugas untuk menyiapkan, mengatur, memanipulasi, dan mengorganisasikan data yang ada di database.
</p>

### Controller

<p align="justify">
Controller merupakan bagian yang menjadi tempat berkumpulnya logika pemrograman yang digunakan untuk memisahkan organisasi data pada database. Dalam beberapa kasus, controller menjadi penghubung antara model dan view pada arsitektur MVC 
</p>

### Route

<p align="justify">
Router mengatur pintu masuk yang berupa request pada aplikasi, mereka memilah dan mengolah request url untuk kemudian diproses sesuai dengan tujuan akhir url tersebut. Bisa jadi url tersebut berfungsi untuk mengambil data kemudian menampilkannya, menghapus data, menampilkan form, sampai mengolah session.
</p>

## 📒Langkah Percobaan

### Melakukan Instalasi Node JS

1. Sudah Melakukan Instalasi NodeJS, untuk memeriksanya dengan menjalankan command `node -v` <br>
   ![Memeriksa Node JS](../Screenshot/Modul_3/1_cek_nodejs_terinstall.png)

### Inisiasi project Express dan pemasangan package

1. Mengenerate file package.json dengan command `npm init -y` <br>
   ![Mengenerate file package.json](../Screenshot/Modul_3/2_mengenerate_package_json.png)
2. Melakukan Instalasi express, mongoose, dan dotenv dengan command `npm i express mongoose dotenv` <br>
   ![install express mongoose dotenv](../Screenshot/Modul_3/3_install_express_mongoose_dotenv.png)

### Koneksi Express ke MongoDB

1. Membuat file Index.js lalu mengkonfigurasi dan menjalankannya dengan command `node index.js` <br>
   ![Membuat mengkonfigurasi index.js dan menjalankannya](../Screenshot/Modul_3/4_membuat_mengkonfigurasi_index_js_dan_menjalankannya.png)
2. Membuat file .env dan mengkonfigurasinya <br>
   ![Membuat file .env](../Screenshot/Modul_3/5_membuat_file_.env.png)
   ![Membuat file .env](../Screenshot/Modul_3/6_melakukan_konfigurasi_index_js.png)
3. Meng-copy connection string pada compass dan mem-paste pada .env <br>
   ![Melakukan konfigurasi index.js](../Screenshot/Modul_3/7_copy_paste_connection_string.png)
4. Menambahkan konfigurasi pada index.js dan menjalankannya kembali <br>
   ![Konfigurasi pada index.js](../Screenshot/Modul_3/8_konfigurasi_pada_index_js.png)
   ![Menjalankan Kembali index.js](../Screenshot/Modul_3/9_menjalankan_kembali_index_js.png)

### Pembuatan Routing

1. Membuat direktori routes <br>
   ![Pembuatan Folder Routes](../Screenshot/Modul_3/10_pembuatan_folder_routes.png)
2. Membuat file book.route,js <br>
   ![Membuat file book.route.js](../Screenshot/Modul_3/11_Pembuatan_file_book.route.js.png)
3. Menambahkan fungsi getAllBooks <br>
   ![fungsi getAllBooks](../Screenshot/Modul_3/12_menambahkan_kode_route.book.js.png)
4. Menambahkan fungsi getOneBooks, createBook, updateBook, dan deleteBook <br>
   ![fungsi getOneBooks, createBook, updateBook, dan deleteBook](../Screenshot/Modul_3/13_getOneBook_createBook_updateBook_deleteBook.png)
5. Melakukan import book.route.js pada file index.js <br>
   ![import bookRoutes](../Screenshot/Modul_3/14_import_bookRoutes.png)
6. Menguji endpoint pada postman <br>
   ![Cek Postman](../Screenshot/Modul_3/15_cek_postman.png)

### Pembuatan Controller

1. Membuat direktori controller <br>
   ![Membuat folder controller](../Screenshot/Modul_3/16_membuat_folder_controllers.png)
2. Membuat file book.controller.js <br>
   ![Membuat file book.controller.js](../Screenshot/Modul_3/17_membuat_file_book.controller.js.png)
3. Membuat fungsi getAllBooks <br>
   ![Funsgi getAllbooks](../Screenshot/Modul_3/18_fungsi_getAllBooks_controller.png)
4. Membuat fungsi getOneBook, createBook, updateBook, dan deleteBook <br>
   ![Funsgi getOneBook, createBook, updateBook, dan deleteBook](../Screenshot/Modul_3/19_getOneBook_updateBook_createBook_deleteBook.png)
5. Melakukan import book.controller.js pada book.route.js dan melakukan perubahan fungsi <br>
   ![Import dan merubah fungsi book.controller.js](../Screenshot/Modul_3/20_import_merubah_code_route.png)
6. Menguji endpoint pada postman <br>
   ![Cek postman](../Screenshot/Modul_3/21_cek_postman.png)

### Pembuatan Model

1. Membuat direktori models <br>
   ![Folder Model](../Screenshot/Modul_3/22_membuat_folder_models.png)
2. Membuat file book.model.js <br>
   ![File book.model.js](../Screenshot/Modul_3/23_file_book.model.js.png)
3. Menambahkan baris kode pada file book.model.js <br>
   ![Menambahkan code file book.model.js](../Screenshot/Modul_3/24_menambahkan_code_book.model.js.png)

### Operasi CRUD

1. Menghapus semua data pada collection books <br>
   ![Mengahpus data collection books](../Screenshot/Modul_3/37_menghapus_collection.png)
2. Melakukan import book.model.js pada file book.controller.js <br>
   ![Import book.model.js](../Screenshot/Modul_3/25_import_book.model.js.png)
3. Melakukan perubahan fungsi createBook <br>
   ![Mengubah createBook](../Screenshot/Modul_3/26_mengubah_createBook.png)
4. Membuat dua buku dengan postman <br>
   ![Membuat buku 1](../Screenshot/Modul_3/27_membuat_buku_1.png)
   ![Membuat buku 2](../Screenshot/Modul_3/28_membuat_buku_2.png)
5. Melakukan perubahan fungsi getAllBooks <br>
   ![Mengubah getAllBooks](../Screenshot/Modul_3/29_mengubah_getAllbooks.png)
6. Melakukan perubahan fungsi getOneBook <br>
   ![Mengubah getOneBook](../Screenshot/Modul_3/30_mengubah_getOneBook.png)
7. Menampilkan semua buku dengan postman <br>
   ![menampilkan semua buku](../Screenshot/Modul_3/31_menampilkan_semua_buku.png)
8. Menampilkan buku dilan 1990 dengan postman <br>
   ![Menampilkan satu buku](../Screenshot/Modul_3/32_menampilkan_satu_buku.png)
9.  Melakukan perubahan fungsi updateBook <br>
    ![Mengubah updateBook](../Screenshot/Modul_3/33_mengubah_updateBook.png)
10. Mengubah judul buku "Dilan 1991" menjadi "Bagas 1991" dengan postman <br>
    ![Mengubah nama judul buku](../Screenshot/Modul_3/34_mengubah_nama_buku.png)
11. melakukan perubahan fungsi deleteBook <br>
    ![Mengubah deleteBook](../Screenshot/Modul_3/35_mengubah_deleteBook.png)
12. Menghapus buku Dilan 1990 dengan postman <br>
    ![Menghapus buku](../Screenshot/Modul_3/36_menghapus_buku.png)
