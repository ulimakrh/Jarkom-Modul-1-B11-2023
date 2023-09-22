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
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!

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

## Soal 6
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

## Jawaban Soal 6
Jika dilihat dari huruf kapital yang disediakan di soal, kita mendapatkan sebuah clue "SUBSTITUSI SOURCE ADDRESS 7812". Dari clue tersebut kita dapat melakukan display filter frame.number == 7812 untuk mencari paket nomor 7812 dan mendapatkan source ip address seperti berikut
![image](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/65074635/d894e1ce-b3d6-48de-9195-8d6b6c068728)

Setelah mendapatkan IP , kita mendapatkan sebuah clue cipher dimana apabila a menjadi 1, e menjadi 5, dan u menjadi 21. Dari clue kedua tersebut. Kita dapat memecah IP **104.18.14.101** menjadi 10 4 18 14 10 dan 1 (karena alphabet hanya mencapai bilangan 26 (Z)). Sehingga apabila ditranslate akan menjadi **JDRNJA**.

