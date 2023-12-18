# Final Project Teknologi Komputasi Awan Kelas B Kelompok 5

**Anggota :**
| Nama | NRP |
| --- | --- |
| Subkhan Mas Udi | 5027221044 |
| Ahmad Fauzan Daniswara | Tidak Bekerja |
| Muhammad Ida Bagus Rafi Habibie | Tidak Bekerja |
| Jonathan Adithya Baswara | 5027221062 |
| Stephanie Hebrina Mabunbun Simatupang | 5027221069 |
| Khansa Adia Rahma | 5027221071 |

## i. Permasalahan

Anda adalah seorang lulusan Teknologi Informasi, sebagai ahli IT, salah satu kemampuan yang harus dimiliki adalah **Keampuan merancang, membangun, mengelola aplikasi berbasis komputer menggunakan layanan awan untuk memenuhi kebutuhan organisasi.**(menurut kurikulum IT ITS 2023 😙)

Pada suatu saat teman anda ingin mengajak anda memulai bisnis di bidang digital marketing, anda diberikan sebuah aplikasi berbasis API

Kemudian anda diminta untuk mendesain arsitektur cloud yang sesuai dengan kebutuhan aplikasi tersebut. Apabila dana maksimal yang diberikan adalah **1 juta rupiah per bulan (65 US$)** konfigurasi cloud terbaik seperti apa yang bisa dibuat?

**Maksud soal :** Dalam soal, teman saya ingin memulai bisnis di bidang digital marketing dan memberikan Anda sebuah aplikasi berbasis API. API (Application Programming Interface) adalah antarmuka yang memungkinkan berbagai aplikasi berkomunikasi dan berinteraksi satu sama lain. Aplikasi berbasis API dapat digunakan untuk mengintegrasikan fungsionalitas dari satu aplikasi ke aplikasi lainnya atau untuk mengakses data dan layanan dari aplikasi lain.

## ii. Rancangan Arsitektur **dan Tabel Harga Spesifikasi VM**

Berikut adalah rancangan arsitektur untuk kelompok kami : 

![Your paragraph text.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/Your_paragraph_text.png)

Berikut adalah tabel Harga Spesifikasi VM dari Digital Oceon  : 
<img width="817" alt="table" src="https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/40b690b8-9825-48c4-9db4-96b2f62bf2ce">

## iii. Instalasi / implementasi rancangan cloud dan aplikasi

1. Membuat Database 📊

![fp-2.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/fp-2.jpeg)

2. Create ‘New Connection’ dengan connection string database mongodb yang sudah ada sebelumnya 

![fp-3.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/fp-3.jpeg)

3. Membuat Database yang sudah dibuat orders_db dan collectionnya serta create data dummy ke collection orders_db melalui mongodb compass 

![fp-4.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/fp-4.jpeg)

4. Membuat droplet dan load balancer
![4.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/4.png)

5. Download app.py, ganti mongodb URI nya sesuai dengan connection string mongodb kita, run [app.py](http://app.py) dari github menggunakan gunicorn di setiap **worker** kita dengan port 80 (harus sama dengan load-balancer).
- mengganti MONGO_URI dengan connection string mongodb kita 
![apppymongo.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/apppymongo.png)
- menjalankan [app.py](http://app.py) dengan gunicorn
![fp-5.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/fp-5.jpeg)

menurut dokumentasi Gunicorn, jumlah worker yang optimal adalah (2 * numofcpucore) + 1.

6. kita arahkan alamat health checks load balancer kita ke Endpoint agar load balancer dapat terhubung dengan [app.py](http://app.py) yang ada di worker
- worker masih down
![6.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/6.jpeg)
- ganti alamat health check
![7.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/7.jpeg)
- Load balancer sudah bekerja
![8.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/8.jpeg)



## iv. Hasil Pengujian endpoint setiap API

- Get All Orders

![all-orders](https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/050e33a7-4fba-4047-96e9-525dc987e9cd)

- Get a Specific Orders by ID

![orders-id](https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/37db661e-b4ee-4538-acdc-fa81c5d64bc4)

- Create a New Order

![neworder](https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/24ae7cae-acd7-494e-9134-280d0bc3b217)

- Update an Order by ID

![updatee](https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/d82b17b7-4b3e-4329-a0c4-9d757471e279)

- Delete an Order by ID

![del](https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/a8961dc5-4a4f-4c5c-90b7-9375c3111c88)

## v. Hasil Pengujian dan analisis Loadtesting menggunakan Locust
- **1500 User, 25 Spawn rate, 60s**

  a) Peak RPS

![25_PeakRPS.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/25_PeakRPS.png)

  b) Peak Concurrency

![25_PeakConcurrency.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/25_PeakConcurrency.png)

  c) Hasil
- RPS maksimum yang didapatkan pada tes ini adalah 118.1
- Concurrency max yang didapat adalah 1500 users

##

- **3000 user, 50 Spawn rate, 60s**

  a) Peak RPS

![50_PeakRPS.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/50_PeakRPS.png)

  b) Peak Concurrency

![50_PeakConcurrency.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/50_PeakConcurrency.png)

  c) Hasil
- RPS maksimum yang didapatkan pada tes ini adalah 149
- Concurrency max yang didapat adalah 2923 users

- **6000 user, 100 spawn rate, 60 sec**
  a) Peak RPS

![100_PeakRPS.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/100_PeakRPS.png)

  b) Peak Concurrency

![100_PeakConcurrency.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/100_PeakConcurrency.png)

  c) Hasil
- RPS maksimum yang didapatkan pada tes ini adalah 175
- Concurrency max yang didapat adalah 6000 users

## vi. Kesimpulan dan Saran

Kesimpulan: Merancang cloud melibatkan langkah-langkah penting, seperti menyesuaikan spesifikasi **Droplet**, **Load-balancer**, dan **Database** secara matang. Tujuannya adalah untuk menciptakan arsitektur cloud yang stabil dan memiliki keandalan yang baik sesuai dengan anggaran yang ditentukan **(65$/bulan)**. Hasil yang kami peroleh dari rancangan arsitektur cloud kami menunjukkan **stabilitas** yang tinggi, dengan tingkat kegagalan saat diuji menggunakan **Locust** mencapai 0%, dan **RPS** tertinggi mencapai 175.

