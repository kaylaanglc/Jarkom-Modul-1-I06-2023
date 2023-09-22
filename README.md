# Praktikum Jarkom Modul 1 (I06)
Group Members:
| NRP | Name |
| ------ | ------ |
|5025211259|Ahmad Danindra Nugroho|
|5025211262|Raden Roro Kayla Angelica Priambudi|

## Question #1
```
User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.
- a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut? 
- b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut? 
- c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
- d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
```

### Solution:
- Filter the packet capture file with `ftp`.
- Look for information with requests to upload a file in the `Info` column in the format `Request: STOR..`. With this search, we found that the packet in question is packet number 147.
- Double-click on that packet and click on the `Transmission Control Protocol` dropdown.
- - For question A, the answer is found in the `Sequence Number (raw)`, which is 258040667.
  - For question B, the answer is found in the `Acknowledgment Number (raw)`, which is 1044861039.
- Then, to find the packet that shows the response to this activity, we open the packet after 147, which is packet 148, and perform the same steps as for questions A and B for questions C and D.
- - For question C, the answer is found in the `Sequence Number (raw)`, which is 1044861039.
  - For question D, the answer is found in the `Acknowledgment Number (raw)`, which is 258040696.

### Screenshot:

### Answer:

### Obstacle(s) encountered:


## Question #2
```
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
```

### Solution:
- Apply the filter `frame contains "Jarkom"`
- Right-click and click on `Follow` then `TCP Stream`
- The answer will be the name of `Server:` which is `gunicorn`

### Screenshot:

### Answer:

### Obstacle(s) encountered:


## Question #3

### Solution:

### Screenshot:

### Answer:

### Obstacle(s) encountered:


## Question #4
```
Berapa nilai checksum yang didapat dari header pada paket nomor 130?
```

### Solution:
- In the `No.` column, find packet no. 130.
- Click on the `User Datagram Protocol` dropdown, located on the bottom left of the Wireshark application.
- The answer will be the `Checksum:` value, which is `0x18e5`
  
### Screenshot:

### Answer:

### Obstacle(s) encountered:


## Question #5
```
Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.
- a. Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
- b. Port berapakah pada server yang digunakan untuk service SMTP?
- c. Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?
```

### Solution:
For this question, the Netcat command is not given. The following are the steps on how to get the Netcat command:
- Apply the filter `smtp`.
- `Follow TCP Stream` on one of the packets.
- An encoded password for a zip file is given, which should be decoded in Base64.
- The decoded password for the zip file containing the Netcat command is `5implePas5word`
- - For question A, the answer is displayed on the right bottom part of the screen where it is written that there are `60` packets
  - For question B, with the help of Google, we found that the port for SMTP is `port 25`.
  - For question C, public IPs are the one other than 10.0.0.0 — 10.255.255.255, 172.16.0.0 — 172.31.255.255, 192.168.0.0 — 192.168.255.255, which means that the answer will be `74.53.140.153`.
  
### Screenshot:

### Answer:

### Obstacle(s) encountered:
Finding the values for the password

## Question #6
```
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
```

### Solution:
- From the "server SOURCE ADDRESS is invalid", find packet no. 7812.
- Take note of the IP Source and decrypt that using substitution cipher. We used the website `https://www.dcode.fr/letter-number-cipher` to decrypt and the answer will be the result of the decryption which only consists of A-R, 1-18 and a total of 6 letters: `JDRNJA`
  
### Screenshot:

### Answer:

### Obstacle(s) encountered:
Finding which values to decrypt





