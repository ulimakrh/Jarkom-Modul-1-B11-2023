# Jarkom-Modul-1-B11-2023

| No | Nama | NRP |
| -------- | -------- | -------- |
| 1 | Muhammad Rafif Tri Risqullah | 5025211009 |
| 2 | Ulima Kaltsum Rizky Hibatullah | 5025211232 |

## Soal 1
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? `258040667`

b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? `1044861039`

c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut? `1044861039`

d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut? `258040696`

## Jawaban Soal 1
Pertama, pada poin a dan b diminta menunjukkan raw number pada packet "mengunggah file" sehingga dilakukan filter `tcp contains “STOR”` karena STOR adalah command untuk mengunggah file. 
![Screenshot 2023-09-18 191938](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/a3137b20-466d-41eb-970d-6861a98f6c34)

Dari situ, kita mendapatkan nama file .zip dari packet response yaitu `c75-GrabThePhisher.zip` yang bisa kita gunakan untuk filtering soal c dan d.
![WhatsApp Image 2023-09-22 at 18 09 58](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/2746a512-4751-4d62-abd2-0909c1f217b3)

Di bagian bawah akan muncul sequence dan acknowledge raw number dari soal a-d seperti berikut.
![WhatsApp Image 2023-09-22 at 18 13 50](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/9ea95dce-23e2-4c35-aa0e-1ac5fd3dc08c)

## Soal 2
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer! `gunicorn`

## Jawaban Soal 2
Pertama, dilakukan filter menggunakan `http contains “10.21.78.111:8000”` yang merupakan alamat dari platform praktikum Jarkom.
Lalu dilakukan TCP Stream sehingga didapatkan nama web server yang digunakan yaitu Gunicorn.
![WhatsApp Image 2023-09-22 at 18 10 00](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/5ada35c2-192b-4c6e-b533-10f80ae1e330)

## Soal 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702? `21`

b. Protokol layer transport apa yang digunakan? `UDP`

## Jawaban Soal 3
Dilakukan filter menggunakan `ip.addr == 239.255.255.250 && udp.port == 3702` untuk mendapatkan jumlah packet tercapture yang berjumlah 21.
Dari situ juga dapat dilihat bahwa protocol yang digunakan adalah UDP.
![WhatsApp Image 2023-09-22 at 18 09 59](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/e5705783-af2d-49bc-8483-be4d25cc9c96)

## Soal 4
Berapa nilai checksum yang didapat dari header pada paket nomor 130? `0x18e5`

##Jawaban Soal 4
Dicari paket dengan nomor 130 dan dapat terlihat nilai checksumnya adalah 0x18e5.
![WhatsApp Image 2023-09-22 at 18 09 59](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/c4099048-21c7-473d-b777-ec8e6cfc48dc)

## Soal 5
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?

b. Port berapakah pada server yang digunakan untuk service SMTP?

c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?

## Jawaban Soal 5
Open TCP stream dari pcap soal 5.
Lalu, scroll ke bawah dan ditemukan sebuah password untuk membuka zip folder.
![WhatsApp Image 2023-09-18 at 21 10 26](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/49fe6c56-b473-4a6c-a967-4d470f9a1275)

Decode password tersebut menggunakan base64 menjadi 5implePas5word. Setelah itu buka folder connection.txt dan lakukan nc pada nc 10.21.78.111 11111.
![image](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/2b5eae31-d957-416b-9c8f-8c9c4481415a)

Lalu untuk menjawab poin A lakukan filter tcp || udp untuk mendapatkan total paket yang diterima.
![image](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/d046b576-a24c-43a1-9873-cad0844b094e)

Untuk menjawab poin B lakukan filter smtp dan kemudian cek di salah satu packet pada src port (didapatkan port 25).
![image](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/8c334935-4eae-495c-8d6c-990e07cc1a44)

Lalu untuk poin C gunakan statistics, pilih Endpoints dan pilih IPv4. Maka ditemukan 
![image](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/1d413227-15d4-47a9-8f2a-ff2ad0b808ce)

Karena baris pertama (10) merupakan private ip, dan 192 adalah private ip (untuk kebanyakan). Maka jawabannya adalah 74.
![image](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/957c5193-8fc7-4969-940e-e40178d38ff6)

## Soal 6
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

## Jawaban Soal 6
Jika dilihat dari huruf kapital yang disediakan di soal, kita mendapatkan sebuah clue "SUBSTITUSI SOURCE ADDRESS 7812". Dari clue tersebut kita dapat melakukan display filter frame.number == 7812 untuk mencari paket nomor 7812 dan mendapatkan source ip address seperti berikut
![image](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/65074635/d894e1ce-b3d6-48de-9195-8d6b6c068728)

Setelah mendapatkan IP , kita mendapatkan sebuah clue cipher dimana apabila a menjadi 1, e menjadi 5, dan u menjadi 21. Dari clue kedua tersebut. Kita dapat memecah IP **104.18.14.101** menjadi 10 4 18 14 10 dan 1 (karena alphabet hanya mencapai bilangan 26 (Z)). Sehingga apabila ditranslate akan menjadi **JDRNJA**.

## Soal 7
Berapa jumlah packet yang menuju IP 184.87.193.88?

## Jawaban Soal 7
Dilakukan filter dengan `ip.dst == 184.87.193.88` dan didapatkan packet sejumlah 6.
![WhatsApp Image 2023-09-18 at 20 31 42](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/b7f6a081-9797-4a08-80c8-73c2c13bf096)

## Soal 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)

## Jawaban Soal 8
Query filter yang digunakan adalah `tcp.dstport == 80 || udp.dstport == 80` 
![WhatsApp Image 2023-09-18 at 20 32 10](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/881ea37f-b6e2-4e7f-bb28-9958c376b490)

## Soal 9
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!

## Jawaban Soal 9
Query filter yang digunakan adalah ip.src == 10.51.40.1 && ip.dst != 10.39.55.34 

## Soal 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet

## Jawaban Soal 10
Dilakukan filter menggunakan `telnet contains "Login"`
![WhatsApp Image 2023-09-18 at 21 03 38](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/c9bf3382-6406-40a8-909c-00491287a1b9)

Lalu follow TCP Stream dan didapatkan password = kesayangannyak0k0, dan username = dhafin (ambil character yang merah).
![WhatsApp Image 2023-09-18 at 21 04 20](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/7e9dd6ae-3758-487b-b020-e9dcf5301b2d)
