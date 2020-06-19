# Materi-06 Kubernetes for Beginners

Getting Started

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-01.png)

Start the cluster

Langkah pertama adalah menginisialisasi gugus di terminal pertama

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-02.png)

menginisialisasi jaringan cluster di terminal pertama

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-05.png)

kemudian mengkloning repositori GitHub, dimana Repositori juga berisi skrip dan alat yang akan kami gunakan melalui workshop

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-06.png)

Aplikasi terus menerus menghasilkan log

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-07.png)

Dengan browser web, sambungkan ke node1 sini di port 8000 (dibuat saat Anda menjalankan aplikasi)

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-08.png)

Sebelum melanjutkan, mari matikan semuanya dengan mengetik Ctrl-C

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-09.png)

kubectl get Mari kita lihat sumber Node kami dengan get kubectl

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-10.png)

Memperoleh hasil yang bisa dibaca mesin kubectl get dapat menampilkan JSON, YAML, atau langsung diformat

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-11.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-12.png)

menggunakan kubectl dan jq. Tampilkan kapasitas semua node kami sebagai aliran objek JSON

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-13.png)

Suatu layanan adalah titik akhir yang stabil untuk terhubung ke "sesuatu" (Dalam proposal awal, mereka disebut "portal")

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-14.png)

Daftarkan pod di kluster kami

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-15.png)

Ruang nama memungkinkan kami untuk memisahkan sumber daya. Daftar ruang nama pada kluster kami dengan salah satu dari perintah ini

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-16.png)

Mengakses ruang nama. Secara default, kubectlgunakan defaultnamespace. Kita dapat beralih ke namespace yang berbeda dengan -nopsi

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-17.png)

Mulai pod sederhana dengan kubectl run. Kita harus menentukan setidaknya nama dan gambar yang ingin kita gunakan. Mari kita ping 8.8.8.8, DNS publik Google

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-18.png)

Di belakang layar kubectl run. Mari kita lihat sumber daya yang diciptakan oleh kubectl run

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-19.png)

Mari kita gunakan kubectl logs. Kami akan melewati salah satu nama pod , atau tipe / nama (Misalnya jika kami menentukan set penyebaran atau replika, itu akan mendapatkan pod pertama di dalamnya). Kecuali ditentukan lain, itu hanya akan menampilkan log dari wadah pertama di pod (Untung hanya ada satu di kita!). Sama seperti docker logs, kubectl logsmendukung opsi yang mudah. Kami dapat membuat salinan tambahan dari wadah kami (atau lebih tepatnya pod kami) dengan kubectl scale

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-20.png)

Set replika memastikan jumlah pod yang tepat berjalan. Ctrl-C untuk mengakhiri

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-21.png)

Melihat log beberapa pod. Saat kami menentukan nama penggunaan, hanya satu log pod tunggal yang ditampilkan. log terakhir dari semua pod dengan run=pingpong

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-22.png)

Menjalankan kontainer dengan port terbuka. Karena ping tidak memiliki apa pun untuk dihubungkan, kita harus menjalankan sesuatu yang lain

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-23.png)

-wopsi “jam tangan” peristiwa yang terjadi pada sumber daya yang ditentukan.

Kami akan membuat ClusterIPlayanan default. Cari alamat IP yang dialokasikan

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-24.png)

Menguji layanan. Kami sekarang akan mengirim beberapa permintaan HTTP ke pod ElasticSearch kami

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-25.png)

Membersihkan. Kami sudah selesai dengan elasticpenyebaran, jadi mari kita bersihkan

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-26.png)

Aplikasi kami di Kube. Di terminal pertama, setel variabel lingkungan untuk nama pengguna Docker Hub Anda . Ini bisa menjadi nama pengguna Docker Hub yang sama dengan yang Anda gunakan untuk masuk ke terminal di situs ini

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-27.png)

Kami akan menggunakan fitur Docker Compose 

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-28.png)

Kami sekarang dapat menggunakan kode kami (serta instance redis)

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-29.png)

Setelah menunggu penyebaran selesai, mari kita lihat log!. (Petunjuk: gunakan kubectl get deploy -wuntuk menonton acara penempatan)

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-30.png)

Mengekspos layanan secara internal. Tiga penyebaran harus dicapai oleh orang lain: hasher, redis,rng

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-31.png)

workermemiliki loop tak terbatas, yang retries 10 detik setelah kesalahan

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-32.png)

Menskalakan penyebaran. Kami akan mulai dengan yang mudah: workerpenyebaran

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-33.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-34.png)

Sekarang, buat lebih banyak workerreplika

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-35.png)

Setelah beberapa detik, grafik di UI web akan muncul. (Dan puncaknya pada 10 hash / detik, sama seperti ketika kita menjalankan satu hash.)

Membuat set daemon. Sayangnya, pada Kubernetes 1.9, CLI tidak dapat membuat set daemon.Lebih tepatnya: tidak memiliki sub perintah untuk membuat set daemon.Tetapi segala jenis sumber daya selalu dapat dibuat dengan memberikan deskripsi YAML

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-36.png)

Kami juga bisa memberi tahu Kubernetes untuk mengabaikan kesalahan ini dan tetap mencoba.--forcebendera Nama sebenarnya adalah--validate=false

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-37.png)

Memeriksa apa yang telah kami lakukan. Lihatlah sumber yang kita miliki sekarang

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-38.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-39.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-40.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-41.png)

Apa yang dilakukan semua pod. Mari kita periksa log dari semua rngpod ini. Semua pod ini memiliki run=rng

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-06/gambar-42.png)







