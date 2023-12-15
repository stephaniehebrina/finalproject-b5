# Final Project Teknologi Komputasi Awan Kelas B Kelompok 5

**Anggota :**
| Subkhan Mas Udi | 5027221044 |
| --- | --- |
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

![orders.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/orders.jpeg)

- Get a Specific Orders by ID

![spec.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/spec.jpeg)

- Create a New Order

![new.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/new.jpeg)

- Update an Order by ID

![update.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/update.jpeg)

- Delete an Order by ID

![delete.jpeg](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/delete.jpeg)

## v. Hasil Pengujian dan analisis Loadtesting menggunakan Locust

- **report-1000user-25spawnrate-60second**
<img width="1025" alt="Screenshot 2023-12-15 at 15 59 21" src="https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/fc060a04-7088-4102-8122-e513f6984366">

- **report-1000user-50spawnrate-60second**

![Screenshot 2023-12-15 at 05.13.07.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/Screenshot_2023-12-15_at_05.13.07.png)

- **report-1000user-100spawnrate-60second**

![Screenshot 2023-12-15 at 05.17.48.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/Screenshot_2023-12-15_at_05.17.48.png)

- **report-1000user-25spawnrate-60second**
<img width="519" alt="Screenshot 2023-12-15 at 16 01 31" src="https://github.com/stephaniehebrina/finalproject-b5/assets/143694784/cd3303c8-1cc1-48a8-8ca5-ca1bf400bc52">

- **report-1000user-50spawnrate-60second**

![Screenshot 2023-12-15 at 05.18.56.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/Screenshot_2023-12-15_at_05.18.56.png)

- **report-1000user-100spawnrate-60second**

![Screenshot 2023-12-15 at 05.19.34.png](Final%20Project%20Teknologi%20Komputasi%20Awan%20Kelas%20B%20Kel%2060b232652434444d9c28bbb509c3b1e0/Screenshot_2023-12-15_at_05.19.34.png)

- **report-1000user-25spawnrate-60second**
  
Final ratio
Ratio per User class
100.0% MyUser
50.0% get_orders
50.0% create_order
Total ratio
100.0% MyUser
50.0% get_orders
50.0% create_order
- **report-1000user-50spawnrate-60second**

## Final ratio

### Ratio per User class

- 100.0% MyUser
    - 50.0% get_orders
    - 50.0% create_order

### Total ratio

- 100.0% MyUser
    - 50.0% get_orders
    - 50.0% create_order
    
- **report-1000user-100spawnrate-60second**

## Final ratio

### Ratio per User class

- 100.0% MyUser
    - 50.0% get_orders
    - 50.0% create_order

### Total ratio

- 100.0% MyUser
    - 50.0% get_orders
    - 50.0% create_order
 
Pada 1000user 50spawnrate 60s total request per second dimulai dari 0 hingga 15 terlebih dahulu, dan tidak se stabil pada 100 spawnrate yang langsung dari awal sudah dimulai dengan 13 rps. Untuk response time antara 50 dan 100 spawnrate mirip dan terlihat memiliki response time yang sama.
Selanjutnya pada bagian number of users pada 50 spawnrate terlihat untuk mencapai dari 0 hingga 1000 users membutuhkan waktu yang sedikit lebih lama dibandingkan 100 spawnrate.


## vi. Kesimpulan dan Saran
Kesimpulan rancangan cloud dan aplikasi melibatkan langkah-langkah penting, seperti membuat database dan connection string, menciptakan koneksi baru dengan string database yang sudah ada, serta menciptakan database baru melalui MongoDB Compass dengan data dummy. Proses ini melibatkan instalasi MongoDB, load balancer, dan worker. Selain itu, langkah kedua melibatkan pengunduhan dan eksekusi app.py dari GitHub, dengan penyesuaian API MongoDB. Keseluruhan, rancangan ini fokus pada integrasi efisien antara aplikasi dan layanan cloud untuk memastikan fungsi yang optimal.

