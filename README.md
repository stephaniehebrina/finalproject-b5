# Final Project Teknologi Komputasi Awan Kelas B Kelompok 5

**Anggota :**
| Nama | NRP |
| --- | --- |
| Subkhan Mas Udi | 5027221044 |
| Ahmad Fauzan Daniswara | 5027221057 |
| Muhammad Ida Bagus Rafi Habibie | 502722159 |
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

1. Membuat Database dan connection string 📊

![fp-2.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/fp-2.jpeg)

2. Create ‘New Connection’ dengan string database yang sudah ada sebelumnya 

![fp-3.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/fp-3.jpeg)

3. Membuat Database yang sudah dibuat di app.py

![fp-4.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/fp-4.jpeg)

4. Create database baru dengan cara copy data dummy ke mongodb compass 

5. Download app.py, Run [app.py](http://app.py) dari github, serta mengganti mongodb API-nya

![fp-5.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/fp-5.jpeg)

6. Check kalau sudah berhasil install mongodb, load balancer dan worker

![fp-1.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/fp-1.jpeg)

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
  <br />
  a) Request Statistics & Response Time Statistics
  <br />
     <img width="1024" alt="Screenshot 2023-12-18 at 08 36 10" src="https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/3129db9d-89c0-42b2-a5a4-a5525b0805e0">

  <br />
  Request Statics : hasil dari pengujian kinerja menggunakan Locust, sebuah alat uji beban dan kinerja open-source yang umumnya digunakan untuk mengukur sejauh mana sistem dapat menangani beban tertentu, Response Time Statistics : memberikan gambaran tentang berbagai persentil (percentiles) waktu yang diperlukan untuk menanggapi permintaan pada suatu endpoint atau sumber daya tertentu
  <br />

  b) Charts
  <br />
  <img width="538" alt="Screenshot 2023-12-18 at 08 53 12" src="https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/c904af77-c74f-4a5f-921c-5bb7ec75f66e">
  <br /> 
  c) Ratio per User class (Rasio per Kelas Pengguna):

- 100.0% MyUser: Semua beban kerja atau permintaan berasal dari kelas pengguna "MyUser."
- 50.0% get_orders: Separuh dari beban kerja berasal dari metode atau permintaan "get_orders."
- 50.0% create_order: Separuh sisanya berasal dari metode atau permintaan "create_order."
<br />
 Total ratio (Total Rasio):

- 100.0% MyUser: Keseluruhan beban kerja atau permintaan sepenuhnya berasal dari kelas pengguna "MyUser."
- 50.0% get_orders: Separuh dari seluruh beban kerja terdiri dari metode atau permintaan "get_orders."
- 50.0% create_order: Separuh sisanya berasal dari metode atau permintaan "create_order."

- **3000 user, 50 Spawn rate, 60s**
 <br />
  a) Request Statistics & Response Time Statistics
  <br />
<img width="1024" alt="Screenshot 2023-12-18 at 08 49 32" src="https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/49907113-bb2e-424f-89d9-2b839cf29905">

  <br />
  Request Statics : hasil dari pengujian kinerja menggunakan Locust, sebuah alat uji beban dan kinerja open-source yang umumnya digunakan untuk mengukur sejauh mana sistem dapat menangani beban tertentu, Response Time Statistics : memberikan gambaran tentang berbagai persentil (percentiles) waktu yang diperlukan untuk menanggapi permintaan pada suatu endpoint atau sumber daya tertentu
  <br />
  b) Charts
  <br />
  <img width="538" alt="Screenshot 2023-12-18 at 08 52 23" src="https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/57ee485f-63d6-4528-b4ec-883f20c31736">

  <br /> 
  c) Ratio per User class (Rasio per Kelas Pengguna):

- 100.0% MyUser: Semua beban kerja atau permintaan berasal dari kelas pengguna "MyUser."
- 50.0% get_orders: Separuh dari beban kerja berasal dari metode atau permintaan "get_orders."
- 50.0% create_order: Separuh sisanya berasal dari metode atau permintaan "create_order."
<br />
 Total ratio (Total Rasio):

- 100.0% MyUser: Keseluruhan beban kerja atau permintaan sepenuhnya berasal dari kelas pengguna "MyUser."
- 50.0% get_orders: Separuh dari seluruh beban kerja terdiri dari metode atau permintaan "get_orders."
- 50.0% create_order: Separuh sisanya berasal dari metode atau permintaan "create_order."
  
- **6000 user, 100 spawn rate, 60 sec**
- a) Request Statistics & Response Time Statistics
  <br />
<img width="1024" alt="Screenshot 2023-12-18 at 08 50 24" src="https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/d6f7558a-45d1-4626-921a-a70c633202b0">
  <br />
  Request Statics : hasil dari pengujian kinerja menggunakan Locust, sebuah alat uji beban dan kinerja open-source yang umumnya digunakan untuk mengukur sejauh mana sistem dapat menangani beban tertentu, Response Time Statistics : memberikan gambaran tentang berbagai persentil (percentiles) waktu yang diperlukan untuk menanggapi permintaan pada suatu endpoint atau sumber daya tertentu
  <br />
  b) Charts
  <br />
  <img width="538" alt="Screenshot 2023-12-18 at 08 51 28" src="https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/27081a06-698f-4aac-937e-e7557c11b2e7">

  <br /> 
  c) Ratio per User class (Rasio per Kelas Pengguna):

- 100.0% MyUser: Semua beban kerja atau permintaan berasal dari kelas pengguna "MyUser."
- 50.0% get_orders: Separuh dari beban kerja berasal dari metode atau permintaan "get_orders."
- 50.0% create_order: Separuh sisanya berasal dari metode atau permintaan "create_order."
<br />
 Total ratio (Total Rasio):

- 100.0% MyUser: Keseluruhan beban kerja atau permintaan sepenuhnya berasal dari kelas pengguna "MyUser."
- 50.0% get_orders: Separuh dari seluruh beban kerja terdiri dari metode atau permintaan "get_orders."
- 50.0% create_order: Separuh sisanya berasal dari metode atau permintaan "create_order."

## vi. Kesimpulan dan Saran
Kesimpulan rancangan cloud dan aplikasi melibatkan langkah-langkah penting, seperti membuat database dan connection string, menciptakan koneksi baru dengan string database yang sudah ada, serta menciptakan database baru melalui MongoDB Compass dengan data dummy. Proses ini melibatkan instalasi MongoDB, load balancer, dan worker. Selain itu, langkah kedua melibatkan pengunduhan dan eksekusi app.py dari GitHub, dengan penyesuaian API MongoDB. Keseluruhan, rancangan ini fokus pada integrasi efisien antara aplikasi dan layanan cloud untuk memastikan fungsi yang optimal.

