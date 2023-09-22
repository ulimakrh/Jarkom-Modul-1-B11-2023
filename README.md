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
