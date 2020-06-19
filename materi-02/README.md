# Materi-02 Docker Networking 

Docker Networking Hands-on Lab 

# A. Run a single task in an Alpine Linux container 
1. Menggunakan perintah "docker network" untuk melihat command yang dapat digunakan untuk mengelola networking di container

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-01.png)

2. Menggunakan perintah "docker network -ls" untuk melihat list network docker yang ada di docker host

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-02.png)

3. Menggunakan perintah inspect yang ada di docker network untuk melihat detail konfigurasi dari network yang memiliki nama bridge.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-03.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-04.png)

4. Menggunakan perintah "docker info" untuk melihat informasi mengenai docker yang ter-install di vm yang gunakan.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-05.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-06.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-07.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-08.png)

# B. Bridge Networking 
1. Melakukan cek terhadap network container bridge di list menggunakan "docker networking -ls"

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-09.png)

2. Lalu melakukan update, dan menambahkan command bridge control ke linux vm yang gunakan.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-10.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-11.png)

3. Selanjutnya adalah menghubungkan container, pertama kita melakukan run terhadapa container yang berjalan di background.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-13.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-14.png)

Lalu menggunakan perintah bridge control untuk melihat bahwa container yang baru di run sudah otomatis menjadi interface dari bridge docker0.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-15.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-16.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-17.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-18.png)

kemudian kita lihat kembali

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-19.png)

Selanjutnya melakukan tes konektivitas terhadap container baru yang aktif di background melalui ping ke ip yang sebelumnya sudah diketahui menggunkan perintah inspect.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-20.png)

Lalu untuk memastikan bahwa container dapat terhubung ke jaringan luar kita menjalankan shell linux di container yang berjalan dibackground, dan menginstall program untuk melakukan ping ke github.com.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-21.png)

kemudian exit untuk keluar

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-22.png)

4. Selanjutnya melakukan konfigurasi NAT untuk koneksi external, pertama melakukan run terhadap container yang menggunakan image nginx.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-23.png)

kemudian lihat pada docker ps

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-24.png)

dan dilakukan curl 

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-25.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-26.png)


# C. Overlay Networking 
1. Melakukan inisiasi docker swarm.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-27.png)

Dan melakukan cek.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-28.png)

2. Lalu melakukan pembuatan overlay network dengan nama overnet.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-29.png)

menjalankan perintah untuk melihat list network pada node2/terminal2 dan hasilnya overnet tidak kelihatan karena Docker hanya memperluas network overlay ke host ketika diperlukan.

node1/terminal1 dan node 2/terminal2

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-30.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-31.png)

lalu jalankan docker network inspect overnet

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-32.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-33.png)

3. Selanjutnya membuat service dengan nama myservice, dan memastikannya sudah menjalankan task untuk mereplika berjalan dikedua node.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-34.png)

Karena sudah berjalan didua node maka overnet akan ditampilkan ketika melihat list network pada node2/terminal2.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-35.png)

lalu jalankan service ps myservice

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-36.png)

kemudian buka kembali docker network ls

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-37.png)

5. selanjutnya jalankan network inspect , tetapi terjadi error disini

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-38.png)

lalu jalankan network inspect overnet

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-39.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-40.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-41.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-42.png)

kemudian lihat di docker ps

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-43.png)

dan untuk menutup dapat dilakukan dengan docker swarm leave --force

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-02/gambar-47.png)





