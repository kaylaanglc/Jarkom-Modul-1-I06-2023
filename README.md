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
![ss1_1](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/f8605c63-22a6-4ee9-85a0-7eebed59c8a8)
![ss1_2](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/8aa6de3d-f840-4e15-9cd6-f75ddbca3204)


### Answer:
![jwbn1](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/881eae10-409e-43ef-ba26-4d01ea5860c3)

### Obstacle(s) encountered:
None

## Question #2
```
Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
```

### Solution:
- Apply the filter `frame contains "Jarkom"`
- Right-click and click on `Follow` then `TCP Stream`
- The answer will be the name of `Server:` which is `gunicorn`

### Screenshot:
![ss2](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/c0bb0d01-82cd-4ca3-954b-efe52980aa57)

### Answer:
![jwbn2](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/3f3289fc-bbb2-4de9-a89e-6ba1e9e5b7ad)

### Obstacle(s) encountered:
None

## Question #3
```
Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:
- a. Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
- b. Protokol layer transport apa yang digunakan?
```

### Solution:
- Apply the filter `ip.addr == 239.255.255.250 and udp.port == 3702.`
- You can see how many packets and see what protocol were captured with the source and destination IP addresses being 239.255.255.250 with port 3702.
- The answer for a. and b. will be on the list.

### Screenshot:
<img width="452" alt="ss3" src="https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/27dd96c6-ddf6-46dc-8ad7-e0029f6a2583">

### Answer: 
![jwbn3](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/0befdbee-6f3f-4a0d-9889-0b4b8677bf30)

### Obstacle(s) encountered:
None

## Question #4
```
Berapa nilai checksum yang didapat dari header pada paket nomor 130?
```

### Solution:
- In the `No.` column, find packet no. 130.
- Click on the `User Datagram Protocol` dropdown, located on the bottom left of the Wireshark application.
- The answer will be the `Checksum:` value, which is `0x18e5`
  
### Screenshot:
![ss4](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/6bb7417c-ffd7-4e88-bc99-9c76abbaa393)

### Answer:
![jwbn4](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/ea2f6a6e-2af2-427d-ba24-d36b2830c54c)

### Obstacle(s) encountered:
None

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
![ss5](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/baf552e9-9ecc-4bbb-832b-907fcd502cb5)

### Answer:
![jwbn5](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/46e873d8-cb4a-40dd-8bf3-425a8d8e244f)

### Obstacle(s) encountered:
Finding the values for the password

## Question #6 (REVISI)
```
Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. jiwa detektif slamet pun bergejolak. bantulah udin dan slamet untuk menemukan solusi kode error tersebut.
```

### Solution:
- From the "server SOURCE ADDRESS is invalid", find packet no. 7812.
- Take note of the IP Source and decrypt that using substitution cipher. We used the website `https://www.dcode.fr/letter-number-cipher` to decrypt and the answer will be the result of the decryption which only consists of A-R, 1-18 and a total of 6 letters: `JDRNJA`
  
### Screenshot:
![ss6](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/41430be0-23d8-4c7b-babf-f0b995b7d5a7)

### Answer:
![jwbn6](https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/6aec5135-d791-4197-8dfe-49900f58fb01)

### Obstacle(s) encountered:
Finding which values to decrypt

## Question #7
```
Berapa jumlah packet yang menuju IP 184.87.193.88?
```

### Solution:
- To search for packets going to the IP address `184.87.193.88`, use the filter expression `ip.dst == 184.87.193.88` which limits the display to only show packets going to the IP address `184.87.193.88`.
- Then, count the number of packets displayed.
  
### Screenshot:
<img width="452" alt="ss7" src="https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/ef2dbee4-a903-41c8-a577-dfaef5e3da9b">

### Answer:
`6`

### Obstacle(s) encountered:
None

## Question #8
```
Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
```

### Solution:
- The filter used to retrieve all protocol packets going to port 80 is `tcp.dstport == 80 || udp.dstport == 80`.
- This filter will capture all packets going to port 80, with TCP and UDP protocols. If there is more than one port 80, the packets will be sorted in alphabetical order.
  
### Screenshot:
<img width="452" alt="ss8" src="https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/a26ecb18-672d-4659-9231-45bf9bb5a1b7">

### Answer:
`tcp.dstport == 80 || udp.dstport == 80`

### Obstacle(s) encountered:
None

## Question #9
```
Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
```

### Solution:
- The filter that will be used to take packets originating from address 10.51.40.1 but not going to address `10.39.55.34 ` is `ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`.
- This filter filters packets that meet the conditions must come from IP address `10.51.40.1 (ip.src == 10.51.40.1)` and must not go to IP address `10.39.55.34` (`ip.dst != 10.39.55.34`).
  
### Screenshot:
<img width="452" alt="ss9" src="https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/c8f701fa-0ca1-4a8a-8148-e5dbb2689cf3">

### Answer:
`ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`

### Obstacle(s) encountered:
None

## Question #10
```
Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet.
```

### Solution:
- The initial step that needs to be taken is to apply a filter or query to filter packets related to the Telnet protocol. The filter used is `tcp.stream eq 15`.
- After that, slide the display down until you reach the very end, assuming the user is connected in the bottom frame.
- Once you get to the end, continue by selecting the option that allows you to follow the data flow in the TCP protocol used in this Telnet connection.
- As a result, you will be able to find the correct login information.

### Screenshot:
<img width="452" alt="ss10" src="https://github.com/kaylaanglc/Jarkom-Modul-1-I06-2023/assets/116704203/9e4a131d-da35-435a-a631-2c7d469249b9">

### Answer:
`dhafin:kesayangannyak0k0`

### Obstacle(s) encountered:
None




