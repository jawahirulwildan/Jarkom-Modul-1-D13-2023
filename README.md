# Jarkom-Modul-1-D13-2023

Anggota Kelompok:
- Thalent Athalla Razzaq (5025211101)
- Jawahirul Wildan (5025211150)

## Soal 1
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.<br />
a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? <br />
b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? <br />
c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?<br />
d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?<br />

### Penyelesaian
![No Image](https://github.com/jawahirulwildan/Jarkom-Modul-1-D13-2023/blob/main/img/1a.png)
<p align="center">
Soal a dan b
</p>

- Filter menggunakan
  ```
  ftp
  ```
- Lalu cari packet yang berisi **Request : STOR (namafile)** (karena aktivitasnya berupa mengunggah suatu file)
- Sehingga, sequence number (raw) dan acknowledge number (raw) dapat diketahui<br />
a. sequence number (raw) : 258040667<br />
b. acknowledge number (raw) : 104486103925<br />

![No Image](https://github.com/jawahirulwildan/Jarkom-Modul-1-D13-2023/blob/main/img/1cd.png)
<p align="center">
Soal c dan d
</p>

- Filter menggunakan
  ```
  ftp
  ```
- Lalu cari packet yang berisi **Response : 150 ... (namafile)**
- Sehingga, sequence number (raw) dan acknowledge number (raw) dapat diketahui<br />
a. sequence number (raw) : 1044861039<br />
b. acknowledge number (raw) : 258040696<br />

## Soal 2
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
### Penyelesaian
![No Image](https://github.com/jawahirulwildan/Jarkom-Modul-1-D13-2023/blob/main/img/2.png)

- Filter menggunakan
  ```
  http contains "10.21.78.111"
  ```
- Pilih salah satu paket
- Klik kanan pada paket tersebut
- Pilih follow -> TCP STREAM
- Sehingga, web server yang digunakan dapat terlihat yaitu **gunicorn**

## Soal 3
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:<br />
a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?<br />
b. Protokol layer transport apa yang digunakan?<br />
### Penyelesaian
Diketahui bahwa IP 239.255.255.250 dengan Port 3702
![No Image](https://github.com/jawahirulwildan/Jarkom-Modul-1-D13-2023/blob/main/img/3.png)
a. 
- Filter menggunakan
  ```
  ip.src == 239.255.255.250 || ip.addr == 239.255.255.250 && udp.port == 3702
  ```
- Lalu, dapat kita hitung paket yang tercapture yaitu sebanyak **21 paket**<br />

![No Image](https://github.com/jawahirulwildan/Jarkom-Modul-1-D13-2023/blob/main/img/3.png)
b.  
- Filter menggunakan
  ```
  ip.src == 239.255.255.250 || ip.addr == 239.255.255.250 && udp.port == 3702
  ```
- Lalu, dapat kita lihat protokol layer transport yang digunakan adalah **UDP**


## Soal 4
Berapa nilai checksum yang didapat dari header pada paket nomor 130?
### Penyelesaian
![No Image](https://github.com/jawahirulwildan/Jarkom-Modul-1-D13-2023/blob/main/img/4.png)

- Filter menggunakan
  ```
  frame.number==130
  ```
- Lalu, dapat kita lihat bahwa nilai cheksum nya adalah **0x18e5**

## Soal 5
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.<br />
a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?<br />
b. Port berapakah pada server yang digunakan untuk service SMTP?<br />
c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?<br />
### Penyelesaian

a. ![No Image](URL_gambar)

<br />
![No Image](URL_gambar)
b.
- Filter menggunakan
  ```
  smtp
  ```
- Lalu pilih salah satu paket
- Sehingga dapat terlihat nilai port nya yaitu **25**

c. ![No Image](URL_gambar)


## Soal 6
Soal 6-7 menggunakan file pcap yang sama.
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
### Penyelesaian

## Soal 7
Berapa jumlah packet yang menuju IP 184.87.193.88?
### Penyelesaian
- Filter menggunakan
  ```
  ip.dst == 184.87.193.88
  ```
184.87.193.88

## Soal 8
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
### Penyelesaian
- Filter menggunakan
  ```
  tcp.dstport == 80 || udp.dstport == 80
  ```

## Soal 9
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
### Penyelesaian
- Filter menggunakan
  ```
  ip.src == 10.51.40.1 && ip.dst != 10.39.55.34
  ```
## Soal 10
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
### Penyelesaian
- Filter menggunakan
  ```
  telnet
  ```
