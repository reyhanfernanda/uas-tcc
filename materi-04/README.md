# Materi-04 Docker Orchestration Hands-on Lab

1. Membuat container baru yang dijalankan pada node 1, perintah berikut berguna untuk membuat container baru yang akan tetap berjalan pada background image docker saat sleep. 

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-01.png)

2. Melakukan cek apakah container tersebut sudah berjalan. 

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-02.png)

3. Membuat Swarm baru, dan join dengan single node lalu melakukan verifikasi jika operasi berhasil.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-03.png)

4. Melakukan join swarm untuk node 2 dan node 3 dengan menggunakan token yang didapat dari pembuaatan swarm sebelumnya. 

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-04.png)

5. Mari kita sebarkan sleepsebagai Layanan di Docker Swarm kami

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-05.png)

6. Verifikasi bahwa service createtelah diterima oleh manajer Swarm

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-06.png)

7. Skala jumlah kontainer dalam layanan aplikasi-tidur ke 7 dengan docker service update --replicas 7 sleep-appperintah. replicasadalah istilah yang kami gunakan untuk menggambarkan wadah identik yang menyediakan layanan yang sama.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-07.png)

8. ami akan menggunakan docker service ps sleep-appperintah. Jika Anda melakukan ini cukup cepat setelah menggunakan --replicasopsi, Anda dapat melihat wadah muncul secara real time

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-08.png)

9. Skala layanan kembali menjadi hanya empat kontainer dengan docker service update --replicas 4 sleep-appperintah.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-09.png)

10. Verifikasi bahwa jumlah kontainer telah dikurangi menjadi 4 menggunakan docker service ps sleep-appperintah.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-10.png)

11. Lihatlah status node lagi dengan menjalankan docker node ls pada node1

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-11.png)

12. lihat di node2

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-12.png)

13. Sekarang mari kita kembali ke node1 (manajer Swarm) dan mengambil node2 dari layanan. Untuk melakukannya, mari kita jalankan docker node ls lagi

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-13.png)

14. Periksa status node

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-15.png)

15. Beralih kembali ke node2 dan lihat apa yang sedang berjalan di sana dengan menjalankan docker ps.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-16.png)

16. Terakhir, periksa lagi layanan pada node1 untuk memastikan bahwa kontainer dijadwal ulang. Anda harus melihat keempat kontainer berjalan di dua node yang tersisa.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-17.png)

17. Jalankan docker service rm sleep-appperintah pada node1 untuk menghapus layanan yang disebut myservice .

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-18.png)

18. Jalankan docker psperintah pada node1 untuk mendapatkan daftar kontainer yang berjalan.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-19.png)

19. Anda dapat menggunakan docker kill <CONTAINER ID>perintah pada node1 untuk membunuh wadah tidur yang kita mulai di awal.

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-20.png)

20. Mari kita jalankan docker swarm leave --forcedi node1 , node2 dan node3

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-04/gambar-21.png)
