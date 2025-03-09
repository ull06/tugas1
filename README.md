# TUGAS LAB SDA
o Anggota Kelompo : 1. Rahmatul Uliya (2408107010012)
                    2. Nayla Nabila Syahel
                    3. Hazairin
                    4. Raisa Saalsa Nabila
                    5. Dara Ramadhani
                    6. Habib Nuran Mulkan

o Deskripsi Singkat Program: 
  Program ini adalah sitem manajemen antrean nasabah di bank yang menggunakan queue berbasis linked list untuk mengelola antrean
  layanan, serta stack berbasis linked list untuk menyimpan riwayat transaksi nasabah yang telah di proses.

o Instruksi compilasi dan cara menjalankan program:
     Program ini menggunakan Makefile untuk mempermudah proses kompilasi dan eksekusi.
    - Jalankan perintah berikut di terminal: Make
      📌 Perintah ini akan mengompilasi semua file sumber dan menghasilkan file eksekusi mainSda.
    - Setelah berhasil dikompilasi, jalankan program dengan: ./mainSda
       📌 Pastikan file mainSda telah dibuat sebelum menjalankan perintah ini.
    - Jika ingin menghapus file eksekusi dan file .o untuk kompilasi ulang, gunakan perintah: Make clean
      📌 Perintah ini akan menghapus file yang dihasilkan dari kompilasi sebelumnya.
      
o Struktur data yang digunakan untuk membangun program antrean bank:
  1. Queueu bebasis linked list
     Program ini menggunakan queue berbasis linked list untuk menyimpan data antrean nasabah yang sedang menunggu untuk diproses.
     Queue mengikuti prinsip FIFO (First In, First Out), sehingga nasabah yang pertama masuk akan diproses lebih dahulu.

  2. Stack berbasis linked list
     Selain antrean, program ini juga menggunakan stack berbasis linked list untuk menyimpan transaksi nasabah yang telah diproses.
     Stack mengikuti prinsip LIFO (Last In, First Out), sehingga transaksi terakhir yang diproses akan berada di bagian atas dan bisa 
     dibatalkan jika diperlukan.


o Alasan Pemilihan Struktur Data:
  "Queue dan Stack diimplementasikan menggunakan Linked List karena:
  ✅ Fleksibel – Tidak memiliki batasan ukuran seperti array, cocok untuk antrean yang jumlahnya tidak dapat diprediksi.
  ✅ Efisien dalam penambahan & penghapusan – Operasi enqueue, dequeue, push, dan pop dapat dilakukan dalam O(1) waktu tanpa perlu geser       elemen seperti pada array.
  ✅ Cocok untuk sistem antrean bank – Karena jumlah nasabah yang antre bisa terus bertambah atau berkurang, sehingga penggunaan memori        lebih efisien."

   
Struktur data stack dan qeueu dipilih diimplementasikan menggunakan linked list, sebab ukuran linked list tidak terbatas 
selama memori masih tersedia, hal ini sesuai sesuai dengan konsep antrean bank, karena banyaknya antrean dalam bank tidak dapat di tentukan sehingga akan sangat tidak efisien jiga diimplementasikan menggunakan array. Sehingga linked list menjadi solusi
yang sangat cocok dalam program ini.

o Implementasi Struktur data
 1. queueu berbasis linked list
    Dalam program antrean nasabah queue diimplementasikan untuk melakukan beberapa proses berikut:
    a. enqueu(); Menambahkan nasabah ke daftar antrean. Nasabah ditambahkan dari belakang sesuai dengan konsep antrian pada kehiudpan nyata
       sehingga proses pelayanan dilakukan teratur sesuai dengan urutan antrean nasabah.
    b. dequeu(); Menghapus nasabah dari antrean setelah selesai di proses. Penghapusan nasabah dilakukan dari depan sesuai dengan konsep          inqueu, setelah dilakukan penghapusan nasabah, maka nasabah yang berada di urutan sebelumnya akan di set untuk menajadi nasabah
       yang harus di proses berikutnya.
    c. tampilkanAntrian (); Menampilkan daftar antrian yang menunggu untuk dilayani.
       - Data antrian yang menunggu dilayani ditampilkan sesuai dengan daftar antrean nasabah,
         nasabah yang pertama masuk akan berada diurutan pertama antrean.
       - Antrean selalu diperbaharui, sehingga setelah satu nasabah selesai dilayani, nasabah berikutnya akan maju ke posisi paling depan.
       - Jika tidak ada nasabah dalam antrean, sistem akan menampilkan pesan "A ntrean kosong" dalam tabel. 

3. Stac berbasis linked list
   Dalam program antrean nasabah stack diimplementasikan untuk melakukan beberapa proses berikut:
   a. pop(); Menambahkan nasabah ke daftar riwayat layanan
      - ketika seorang nasabah telah selesai dilayani (dikeluarkan dari antrean queue), data nasabah tersebut akan dimasukkan
        ke dalam stack.
      - Penambahan dilakukan dari arah depan (top), sehinngga data nasabah terakhir yang siap dilayani akan selalu berada di posisi
        paling atas.
      - posisi top akan selalu di update ketika  proses penambahkan nasabah dilakukan.5r
   b. push() atau di program dinamakan undoTransaksi; Menghapus data nasabah dari riwayat layanan
      - Data nasabah yang terakhir masuk ke daftar riwayat layanan akan di hapus (dikemablikan lagi ke datar antrean).
      - Penghapusan dilakukan dari posisi top sehingga nasabah yang terakhir masuk akan di hapus  lebih dulu.
      - Nasabah yang dihapus dikembalikan lagi ke daftar antrean seperti sebelumnya, kembali menjadi top dalam daftar antrean.
   c. tampilkanRiwayat(); Menampilkan riwayat nasabah yang telah selesai di proses
      - setiap nasabah yang telah selesai diproses akan dipindahkan ke dalam riwayat layanan yang ditampilkan dalam urutan
        yang sesuai dengan wkatu pelayanan.
      - Nasabah yang pertama diproses akan ditampilkan lebih dahulu, karena riwayat layanan ini disusun agar mudah dibaca dalam urutan     
        yang benar.
      - Data riwayat tetap disimpan meskipun antrean utama terus berjalan, sehingga dapat digunakan untuk melihat daftra layanan yang
        sudah dilakukan.
      - Jika tidak ada nasabah yang telah dilayani sistem akan menampilkan pesan " Riwayat kosong" dalam tabel.
  


🔍 Kendala dan Solusi dalam Program Antrean Bank:
1. Kendala dalam Pengelolaan Antrean (Queue)
💡 Masalah:
Nasabah yang telah selesai diproses dihapus dari antrean, tetapi data nasabah yang telah diproses tidak tersimpan.
Tidak ada mekanisme untuk membatalkan proses nasabah yang sudah dikeluarkan dari antrean.
✅ Solusi:
Implementasi Stack (Riwayat Layanan) untuk menyimpan nasabah yang telah diproses.
Menambahkan fitur Undo Transaksi menggunakan pop() untuk memungkinkan pembatalan transaksi dan mengembalikan nasabah ke antrean utama.

2.  Kendala dalam Alokasi Memori
💡 Masalah:
Karena menggunakan linked list, jika tidak dikelola dengan baik, memori bisa bocor (memory leak) akibat node yang tidak dibebaskan setelah digunakan.
✅ Solusi:
Menggunakan free() untuk menghapus node setelah nasabah dikeluarkan dari antrean atau stack.
Menambahkan fungsi clearQueue() dan clearStack() untuk membersihkan semua node sebelum program berakhir.

3.  Menampilkan Riwayat dalam Urutan Kronologis
💡 Masalah:
Riwayat transaksi disimpan dalam stack yang bersifat LIFO (Last-In-First-Out), sehingga urutan tampil terbalik (terbaru ke terlama).
✅ Solusi:
Gunakan stack sementara untuk membalikkan urutan:
1️⃣ Pindahkan semua data dari stack utama ke stack sementara.
2️⃣ Tampilkan data dari stack sementara, yang kini dalam urutan kronologis.
3️⃣ Kembalikan data ke stack utama agar tidak mengubah struktur aslinya.

4.  Sinkronisasi Antrean dan Riwayat
💡 Masalah:
Setelah undo, nomor antrean bisa menjadi tidak berurutan.
Data harus tetap sinkron antara antrean (nasabah aktif) dan stack (riwayat layanan).
✅ Solusi:
Gunakan renumberQueue untuk memastikan nomor antrean tetap berurutan setelah perubahan.
Saat nasabah diproses (deQueue), datanya dipindahkan ke stack. Jika undo dilakukan, data diambil dari stack dan dikembalikan ke antrean.

5. Penanganan Kesalahan dan Stabilitas Program
💡 Masalah:
Program bisa mengalami gagal alokasi memori saat malloc tidak berhasil.
Operasi yang tidak valid, seperti menghapus antrean kosong, bisa menyebabkan error.
✅ Solusi:
Cek hasil alokasi memori (malloc/strdup). Jika gagal, tampilkan pesan error agar pengguna tahu ada masalah.
Cegah error kritis dengan:
🔹 Menampilkan peringatan "Antrean kosong!" saat pengguna mencoba menghapus antrean yang sudah habis.
🔹 Memeriksa kondisi isEmpty() sebelum melakukan operasi yang membutuhkan data, seperti menghapus antrean atau mengambil data dari stack.

6. Validasi Input
🔴 Kendala:
Input nama nasabah harus hanya berisi huruf dan spasi.
Kesalahan input pada pilihan menu, seperti memasukkan huruf atau simbol yang tidak valid.
✅ Solusi:
Untuk mengatasi masalah ini, program menerapkan fungsi validasi khusus:
 o isValidName: Memeriksa nama hanya berisi huruf dan spasi menggunakan isalpha.
 o isValidNumber: Memastikan input angka menggunakan isdigit.
 o Membersihkan buffer input setelah memasukkan data agar tidak terjadi kesalahan saat membaca input berikutnya.

7. Format Antarmuka Pengguna
Kendala
Menampilkan data antrean dan riwayat dalam format tabel yang rapi.
Solusi
Gunakan format printf dengan spesifikasi seperti %-4d (untuk nomor) dan %-50s (untuk nama) untuk merapikan kolom.
Tambahkan garis pemisah (contoh: ===================) untuk kejelasan visual.
 
8. Kendala dalam Efisiensi Kompilasi dan Eksekusi
💡 Masalah:
Setiap kali ingin menjalankan program, pengguna harus mengetik perintah kompilasi yang panjang secara manual.
✅ Solusi:
Menggunakan Makefile untuk mempermudah kompilasi hanya dengan menjalankan perintah make, lalu menjalankan program dengan ./mainSda.

