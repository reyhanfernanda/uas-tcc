# Materi-05 Learn Kubernetes Basics

1. Membuat sebuah cluster Kubernetes Disini kita melakukan pengecekan versi minikube, menjalankan minikube dan juga versi cluster serta informasi detailnya.

a. Cluster up and running

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-01.png)

b. Cluster version

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-02.png)

c. Cluster details

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-03.png)

2. Mendeploy aplikasi Disini kita melakukan deploy pada aplikasi dan mengeceknya. 

a. kubectl basics

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-05.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-04.png)

b. Deploy our app

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-06.png)

c. View our app

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-07.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-08.png)

3. Mengexplore aplikasi Disini kita melakukan pengecekan konfigurasi aplikasi, menampilkan app pada terminal. Melihat catatan containers dan mengeksekusi perintah pada container. 

a. Step 1 Check application configuration

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-09.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-10.png)

b. Step 2 Show the app in the terminal

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-11.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-12.png)

c. Step 3 View the container logs

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-13.png)

d. Step 4 Executing command on the container

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-14.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-15.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-16.png)


4. Mengekpos aplikasi ke public Disini kita membuat sebuah servicel/layanan baru, menggunakan label dan menghapus service/layanan.

a. Step 1 Create a new service

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-17.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-18.png)

b. Step 2: Using labels

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-19.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-20.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-21.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-22.png)

c. Step 3 Deleting a service

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-23.png)

5. Penskalaan aplikasi Disini kita mengecek skala aplikasi yang telah di deploy, memuat keseimbangan dan melakukan scaling down.

a. Step 1: Scaling a deployment

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-24.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-25.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-27.png)

b. Step 2: Load Balancing

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-28.png)

c. Step 3: Scale Down

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-29.png)

6. Memperbarui aplikasi Disini kita melakukan pembaruan versi dari aplikasi, memastikan pembaruannya dan melakukakan rollback pada aplikasi yang telah di perbarui. 

a. Step 1: Update the version of the app

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-30.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-31.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-32.png)

b. Step 2: Verify an update

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-33.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-34.png)

c. Step 3: Rollback an update

![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-35.png)
![image](https://github.com/reyhanfernanda/uas-tcc/blob/master/materi-05/gambar-36.png)

