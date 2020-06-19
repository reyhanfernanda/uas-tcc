# Docker for Beginners - Linux


bahan yang dibutuhkan untuk melakukan praktik ini
1. Klon dari repo GitHub
2. DockerID

Melakukan Clone tweet app dari repo di Github.
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-02.png)

# A. Run a single task in an Alpine Linux container 
1. Melakukan run container linux alpine secara single task

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-03.png)

2. Melakukan cek terhadap container yang dijalankan sebelumnya dengan nama "hostname"

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-04.png)

# B. Run an interactive Ubuntu container
1. Menjalankan container interaktif ubuntu dan menggunakan perintah dasar linux didalamnya. 

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-05.png)

2. ls /akan mencantumkan isi direktur root , ps auxakan menunjukkan proses yang berjalan  , cat /etc/issueakan menunjukkan Linux mana yang berjalan, dalam hal ini Ubuntu 18.04.3 LTS
3. Ketik exit untuk meninggalkan sesi shell. Ini akan menghentikan bash proses.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-06.png)

4. periksa versi host VM

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-07.png)

# C. Run a background MySQL container
1. perintah untuk menjalankan container Mysql di background.
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-08.png)

2. Melakukan pengecekan terhadap container yang berjalan di background menggunakan perintah docker untuk melihat list container.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-09.png)

3. Menggunakan perintah docker untuk melihat proses yang berjalan di container.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-10.png)

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-11.png)

4. Daftar versi MySQL menggunakan docker container exec. serta menambahkan shell interaktif ( sh) lalu Ketik exituntuk meninggalkan sesi shell interaktif.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-12.png)



# D. Package and run a custom app using Docker
1. Masuk ke direktori linux tweet-app yang sebelumnya di clone, dan membuat DockerFile yang menggunakan image nginx.
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-13.png)

2. Melakukan export environment variabel yang isinya id dockerhub kita.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-14.png)

3. Melakukan build image yang sebelumnya sudah disiapkan.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-15.png)

4. Melakukan run terhadap image, dan melihat hasilnya dibrowser.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-16.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-17.png)

5. Memberhentikan container-nya menggunakan perintah force, dan melakukan cek apakah berhasil.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-18.png)

# E. Modify a running website
1. Pertama kita menjalankan container pada task sebelumnya (tweet app), akan tetapi kali ini container di mount untuk proses terhadap task ini.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-19.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-20.png)

2. Lalu kita menambahlan file html didalam direktori tweet-app, dan melakukan cek terhadap perubahan di website tweet-app yang berjalan.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-21.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-22.png)

3. setelah telah memodifikasi index.html sistem file lokal dan melihatnya berubah didalam container yang sedang berjalan, kita belum benar-benar mengubah image Docker dicontainer tersebut (karena menggunakan mount), maka kita melakukan pemberhentian container, dan melakukan start ulang, dan hasilnya image tidak berubah sama sekali.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-23.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-24.png)

4. melakukan modifikasi(update) terhadap image tweet-app dan menggunakan tag 2.0 didalam proses build ulangnya. Dan melihat hasilnya di list container.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-25.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-26.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-27.png)

5. Lalu  melakukan run (yang didalam direktorinya kita sudah menggunakan file html yang di update sebelumnya), dan melihat hasilnya.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-28.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-29.png)

6. Lalu untuk perbandingan terhadap image baru, dan lama kita akan menjalankan container lain dengan port berbeda, yaitu 80-8080 (karena yang baru sudah berjalan di port 80-80), dan nama containernya adalah old linux tweet app. Lalu melihat image yang lama di port tersebut.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-30.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-31.png)

7. Lalu kita akan melakukan push terhadap 2 image yang sudah kita buat didalam proses tutorial ini, yaitu tweet app 1.0, dan tweet app 2.0 .

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-32.png)

8. Sebelum push kita harus melakukan login.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-33.png)

9. Lalu melakukan push ke repo dockerhub

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-34.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-35.png)

10. Dan berikut adalah hasil dari push ke repo dockerhub

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-01/gambar-36.png)