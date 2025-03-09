# TUGAS LAB SDA
o Anggota Kelompo : 1. Rahmatul Uliya (2408107010012)
                    2. Nayla Nabila Syahel
                    3. Hazairin
                    4. Raisa Saalsa Nabila
                    5. Dara Ramadhani
                    6. Muhammad Habib Nuran Mulkan

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
  
  

  
