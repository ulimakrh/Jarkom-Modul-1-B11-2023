# Jarkom-Modul-1-B11-2023

| No | Nama | NRP |
| -------- | -------- | -------- |
| 1 | Muhammad Rafif Tri Risqullah | 5025211009 |
| 2 | Ulima Kaltsum Rizky Hibatullah | 5025211232 |

## Soal 1
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 258040667

b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 1044861039

c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut? 1044861039

d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut? 258040696

## Jawaban Soal 1
Pertama, dilakukan filter `tcp contains “STOR”` karena STOR adalah command untuk mengunggah file. Hal itu kita lakukan untuk mendapatkan nama file .zip yaitu `c75-GrabThePhisher.zip`.
![Screenshot 2023-09-18 191938](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/114993076/a3137b20-466d-41eb-970d-6861a98f6c34)

## Soal 6
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

## Jawaban Soal 6
Jika dilihat dari huruf kapital yang disediakan di soal, kita mendapatkan sebuah clue "SUBSTITUSI SOURCE ADDRESS 7812". Dari clue tersebut kita dapat melakukan display filter frame.number == 7812 untuk mencari paket nomor 7812 dan mendapatkan source ip address seperti berikut
![image](https://github.com/ulimakrh/Jarkom-Modul-1-B11-2023/assets/65074635/d894e1ce-b3d6-48de-9195-8d6b6c068728)

Setelah mendapatkan IP , kita mendapatkan sebuah clue cipher dimana apabila a menjadi 1, e menjadi 5, dan u menjadi 21. Dari clue kedua tersebut. Kita dapat memecah IP **104.18.14.101** menjadi 10 4 18 14 10 dan 1 (karena alphabet hanya mencapai bilangan 26 (Z)). Sehingga apabila ditranslate akan menjadi **JDRNJA**.

