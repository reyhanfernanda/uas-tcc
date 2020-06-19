# Materi-03 Application Containerization And Microservice Orchestration 



kloning repositori kode demo, mengubah direktori kerja

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-01.png)

# A. Basic Link Extractor Script 

Periksa step0cabang dan daftar file di dalamnya.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-02.png)

kemudiaan cat linkextractor.py jadi mari kita lihat isinya

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-03.png)

Ini adalah skrip Python sederhana yang mengimpor tiga paket: sysdari pustaka standar dan dua paket pihak ketiga populer requestsdan bs4. Argumen baris perintah yang disediakan pengguna (yang diharapkan menjadi URL ke halaman HTML) digunakan untuk mengambil halaman menggunakan requestspaket, kemudian diuraikan menggunakan BeautifulSoup

kemudian jalankan ./linkextractor.py http://example.com/

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-04.png)

Ketika kami mencoba menjalankannya sebagai skrip, kami mendapatkan Permission deniedkesalahan

kita periksa izin saat ini pada file ini

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-05.png)

Izin ini -rw-r--r--menunjukkan bahwa skrip tidak dapat dieksekusi

kemudian jalankan linkextractor.py

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-06.png)

# B. Containerized Link Extractor Script
Periksa step1cabang dan daftar file di dalamnya.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-07.png)

kemudiabn lihat isi file tersebut

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-08.png)

lalu build image tersebut

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-09.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-10.png)

membuat gambar Docker yang diberi nama linkextractor:step1berdasarkan pada Dockerfile

kemudian melihat daftar image 

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-11.png)

selanjutnya jalankan container image dan ekstrak tautan dari beberapa halaman web langsung

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-12.png)

lalu kita coba di halaman web dengan lebih banyak tautan di dalamnya

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-13.png)

# C. Link Extractor Module with Full URI and Anchor Text 
Periksa step2cabang dan daftar file di dalamnya.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-14.png)

kemudian lihat skrip tersebut

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-15.png)

kemudian kita build image 

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-16.png)

menggunakan tag baru linkextractor:step2untuk gambar ini sehingga kami tidak menimpa gambar dari step0untuk mengilustrasikan bahwa mereka dapat berdampingan
 
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-17.png)

lalu jalankan container linkextractor:step2

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-18.png) 

berikutnya jalankan container sebelumnya linkextractor:step1harus tetap menghasilkan keluaran yang lama

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-19.png) 

# D. Link Extractor API Service 
Periksa step3cabang dan daftar file di dalamnya.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-20.png)

lalu lihat file tersebut

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-21.png)

linkextractor.pymodul tetap tidak berubah dalam langkah ini, jadi mari lihat ke dalam baru ditambahkan main.pyberkas

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-22.png)

kemudian build image baru 

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-23.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-24.png)

Kemudian jalankan wadah dalam mode terlepas ( -dbendera) sehingga terminal tersedia untuk perintah lain saat wadah masih berjalan. Perhatikan bahwa kami memetakan port 5000wadah dengan 5000host (menggunakan -p 5000:5000argumen) untuk membuatnya dapat diakses dari host. Kami juga menetapkan nama ( --name=linkextractor) ke wadah untuk membuatnya lebih mudah untuk melihat log dan membunuh atau menghapus

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-25.png)

lalu lihat

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-26.png)

sekarang dapat membuat permintaan HTTP dalam formulir /api/<url>untuk berbicara dengan server ini dan mengambil respons yang berisi tautan yang diekstrak

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-27.png)

Karena wadah berjalan dalam mode terpisah, jadi kami tidak dapat melihat apa yang terjadi di dalamnya, tetapi kami dapat melihat log menggunakan nama yang linkextractorkami tetapkan untuk wadah

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-28.png)

kemudian dapat melihat pesan yang dicatat ketika server muncul, dan entri dari log permintaan ketika kita menjalankan curl perintah.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-29.png)

# E. Link Extractor API and Web Front End Services 
Periksa step4cabang dan daftar file di dalamnya.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-30.png)

lihat docker-compose.yml

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-31.png)

lihat www/index.php

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-32.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-33.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-34.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-35.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-36.png)

Ini adalah file panjang yang sebagian besar berisi semua markup dan gaya halaman. Namun, blok kode yang penting adalah di awal file

Mari kita bawa layanan ini dalam mode terpisah menggunakan docker-compose

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-37.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-38.png)

Memeriksa daftar kontainer yang berjalan mengonfirmasi bahwa kedua layanan tersebut memang berjalan

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-39.png)

Kita sekarang dapat berbicara dengan layanan API seperti sebelumnya

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-40.png)

Sekarang, mari kita modifikasi www/index.phpfile untuk mengganti semua kemunculan Link Extractordengan Super Link Extractor

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-41.png)

kembalikan perubahan ini sekarang untuk membersihkan pelacakan Git

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-42.png)

Sebelum kita melanjutkan ke langkah selanjutnya kita harus mematikan layanan ini, tetapi Docker Compose dapat membantu kita mengurusnya dengan sangat mudah

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-43.png)


# F. Redis Service for Caching 
Periksa step5cabang dan daftar file di dalamnya.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-44.png)

Pertama-tama mari kita periksa yang baru ditambahkan di Dockerfilebawah ./wwwfolder

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-45.png)

Selanjutnya, kita akan melihat api/main.pyfile server API tempat kita menggunakan cache Redis

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-46.png)

Sekarang, mari kita lihat docker-compose.ymlfile yang diperbarui

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-47.png)

kemudian kita compose build

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-48.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-49.png)

kita dapat menggunakan docker-compose execdiikuti oleh redisnama layanan dan perintah monitor Redis CLI

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-50.png)

Sekarang kita tidak menginstal /www folder di dalam wadah, perubahan lokal seharusnya tidak tercermin dalam layanan yang berjalan

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-51.png)

Sekarang, matikan layanan ini dan bersiap-siap untuk langkah selanjutnya

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-52.png)

# G. Swap Python API Service with Ruby 
Periksa step6cabang dan daftar file di dalamnya.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-53.png)

Mari kita berjalan cepat melalui file yang diubah

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-54.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-55.png)

File Ruby ini hampir sama dengan yang kami miliki di Python sebelumnya, kecuali, selain itu ia juga mencatat permintaan ekstraksi tautan dan kejadian cache yang sesuai. Dalam aplikasi arsitektur microservice, menukar komponen dengan komponen yang setara itu mudah asalkan harapan konsumen terhadap komponen tersebut tetap terjaga.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-56.png)

Di atas Dockerfileditulis untuk skrip Ruby dan cukup jelas.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-57.png)

docker-compose.ymlberkas memiliki beberapa perubahan kecil di dalamnya. Gambar apilayanan sekarang dinamai linkextractor-api:step6-ruby, pemetaan port diubah dari 5000menjadi 4567(yang merupakan port default untuk server Sinatra), dan API_ENDPOINTvariabel lingkungan diweb layanan diperbarui sesuai sehingga kode PHP dapat berbicara dengannya.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-58.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-59.png)

Kita sekarang harus dapat mengakses API (menggunakan nomor port yang diperbarui)

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-60.png)

kemudian kita matikan docker-compose down

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-61.png)

Karena kami memiliki log yang bertahan, mereka harus tetap tersedia setelah layanan hilang

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-03/gambar-62.png)

Ini menggambarkan bahwa caching berfungsi sebagai upaya kedua untuk http://example.com/menghasilkan cache HIT