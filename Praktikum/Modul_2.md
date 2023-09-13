Nama    : Bagas Mahda Dhani <br>
NIM     : 215150700111038 <br>
Matkul  : Pemin-A

# CRUD MONGODB

## Dasar Teori
### MongoDB Compass
MongoDB Compass adalah tool berbasis Graphical User Interface (GUI) yang digunakan untuk berinteraksi dengan MongoDB yang terpasang secara on-premise dan MongoDB Atlas yang berbasis cloud. Tool ini dapat melakukan aktivitas dasar seperti CREATE, READ, UPDATE, dan DELETE (CRUD) tanpa berhadapan dengan baris perintah (command line).

### MongoDB Shell
Walaupun dapat melakukan operasi seperti MongoDB Compass, interaksi yang dilakukan MongoDB Shell berbasis Command Line Interface (CLI) sehingga diperlukan baris perintah untuk melakukan aktivitas dasar. MongoDB Shell dapat diakses langsung dari MongoDB Compass atau menggunakan mongosh pada Command Prompt

## Langkah Percobaan
### MongoDB Compass
1. Melakukan koneksi ke MongoDB menggunakan connection String Secara local <br>
![Membuat Koneksi pada MongoDB](../Screenshot/Modul_2/1_Membuat_Connection.png)
2. Membuat Database bookstore <br>
![Membuat Database](../Screenshot/Modul_2/2_Membuat_Database.png)
3. Melakukan Insert buku pertama <br>
![Melakukan Insert buku 1](../Screenshot/Modul_2/3_Insert_Book_1.png)
4. Melakukan Insert buku kedua <br>
![Melakukan insert buku 2](/Screenshot/Modul_2/4_Insert_Book_2.png)
5. Melakukan Pencarian menggunakan filter <br>
![Melakukan filter](/Screenshot/Modul_2/5_Filter_Author.png)
6. Melakukan Update summary pada buku "No Longer Human" <br>
![Melakukan Update](/Screenshot/Modul_2/6_Update_Summary.png)
7. Melakukan Delete pada buku "I Am a Cat" <br>
![Melakukan Delete](/Screenshot//Modul_2/7_Delete_Data.png)
<br>

### MonogDB Shell
1. Melakukan koneksi ke mongoDB dengan perintah `mongosh`
![Koneks pada Shell](/Screenshot/Modul_2/8_Koneksi_Shell.png)
2. Melihat list database, berpindah database, dan melihat collections
    - Melihat list database dengan perintah `show dbs` <br>
    ![List database](/Screenshot/Modul_2/8_List_Database.png)
    - Berpindah ke database bookstore dengan perintah `use bookstore` <br>
    ![Berpindah Database](/Screenshot/Modul_2/9_berpindah_database_bookstore.png)
    - Melihat collections dengan perintah `show collections` <br>
    ![Melihat Collections](/Screenshot/Modul_2/10_melihat_collections.png)
3. Melakukan Insert satu buku dengan perintah `db.books.insertOne(data_buku)` <br>
![Insert One book](/Screenshot/Modul_2/11_Insert_One_shell.png)
4. Melakukan Insert banyak buku dengan perintah `db.books.insertMany([data_buku, data_buku, ....])` <br>
![Insert Many book](/Screenshot/Modul_2/12_Inser_Many_shell.png)
5. Melakukan pencarian buku dengan perintah `db.books.find()` <br>
![find book](/Screenshot/Modul_2/13_find_book_shell.png) <br>
6. Melakukan pencarian buku berdasarkan parameter author dengan perintah `db.books.find({author: "Osamu Dazai"})` <br>
![find author](/Screenshot/Modul_2/14_find_author_shell.png)
7. melakukan update pada satu buku dengan perintah `db.books.updateOne({filter}, {$set: {data_yang_diubah}})` <br>
![update one book](/Screenshot/Modul_2/15_update_summary_shell.png)
8. Melakukan update pada banyak buku dengan perintah `db.books.updateMany({filter}, {$set: {data_yang_diubah}})` <br>
![update many book](/Screenshot/Modul_2/16_update_many_shell.png)
9. Melakukan delete pada satu buku dengan perintah `db.books.deleteOne({_id: ObjectId(....)})` <br>
![delete one book](/Screenshot/Modul_2/17_delete_one_shell.png)
10. Melakukan delete pada banyak buku dengan perintah `db.books.deleteMany({author: "Osamu Dazai"})` <br>
![delete many book](/Screenshot/Modul_2/18_delete_many_shell.png)