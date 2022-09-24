# Laporan Praktikum JARKOM Kelompok B07 #

| Nama                      | NRP           |
| ------------------------- | ------------- |
| Danial Farros Maulana     | 5025201004    |
| Rendi Dwi Francisko       | 5025201056    |
| Ahmad Ibnu Malik Rahman   | 5025201232    |

## Nomer 1 ##
Sebutkan web server yang digunakan pada "monta.if.its.ac.id"! 

**Jawab :**

Proses pengenalan web server Menggunakan display filter ``tcp contains monta.if.its.ac.id`` sehingga di didapatkan ``server : nginx/1.10.3\r\n``
![Logo Nomer 1](/src/img/nomer1.png)

## Nomer 2 ##
Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website monta dan menemukan **detail topik** pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq ? 

**Jawab :**

proses pencarian menggunakan ``http contains detailTopik`` sehingga di dapatkan hasil sebagai berikut

![Nomer 2a](/src/img/nomer2.png)
![Nomer 2b](/src/img/nomer2b.png)
![Nomer 2c](/src/img/nomer2c.png)


## Nomer 3 ##

Filter sehingga wireshark hanya menampilkan paket yang menuju port 80! 

**Jawab :**

Proses filtering menggunakan ``tcp.dstport == 80`` sehingga di dapatkan hasil sebagai berikut

![Nomer3](/src/img/nomer3.png)

## Nomer 4 ##

Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21!

**Jawab :**

proses filtering menggunakan ``tcp.srcport == 21`` sehinggga di dapatkan hasil sebagai berikut 
![Nomer 4](/src/img/nomer4.png)

## Nomer 5 ##

Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!

**Jawab :**

proses filtering menggunakna ``tcp.srcport == 443`` sehingga di dapatkan hasil sebagai berikut
![Nomer 5](/src/img/nomer5.png)

## Nomer 6 ##

Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id !

**Jawab :**

1. Dilakukan proses pengecekan alamat lipi, shingga didapatkan 203.160.128.158
    ![Nomer 6a](/src/img/Picture6a.png)
2. alamat IP yang didapat selanjutnya dijadikan filter dengan menggunakan ``http && ip.dst == 203.160.128.158``
   ![Nomer6b](/src/img/Picture6b.png)

## Nomer 7 ##

Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

**Jawab :**

1. Melakukan pengecekan IP terlebih dahulu pada cmd
   ![Nomer7a](/src/img/Picture7a.png)
2. Melakukan pengecekan ip yang menuju ``monta.if.its.ac.id``
   ![Nomer7b](/src/img/Picture7b.png)

## Nomer 8 - 10 ##

Di sebuah planet bernama Viltrumite, terdapat Kementerian Komunikasi dan Informatika yang baru saja menetapkan kebijakan baru. Dalam kebijakan baru tersebut, pemerintah dapat mengakses data pribadi masyarakat secara bebas jika memang dibutuhkan, baik dengan maupun tanpa persetujuan pihak yang bersangkutan. Sebagai mahasiswa yang sedang melaksanakan program magang di kementerian tersebut, kalian mendapat tugas berupa penyadapan percakapan mahasiswa yang diduga melakukan tindak kecurangan dalam kegiatan Praktikum Komunikasi Data dan Jaringan Komputer 2022. Selain itu, terdapat sebuah password rahasia (flag) yang diduga merupakan milik sebuah organisasi bawah tanah yang selama ini tidak sejalan dengan pemerintahan Planet Viltrumite. Tunggu apa lagi, segera kerjakan tugas magang tersebut agar kalian bisa mendapatkan pujian serta kenaikan jabatan di kementerian tersebut!

### Nomer 8 ###
Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum. Percakapan tersebut dilaporkan menggunakan protokol jaringan dengan tingkat keandalan yang tinggi dalam pertukaran datanya sehingga kalian perlu menerapkan filter dengan protokol yang tersebut.
### Nomer 9 ###
Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format [nama_kelompok].des3 dan simpan output file dengan nama “flag.txt”.
### Nomer 10 ###
Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!

**Jawab 8-10:**
1. Data percakapan awal yang di dapat kurang lebih seperti pada gambar, lalu dari data di dapatkan clue untuk mencari lewat port 9002, dan menggunakan decrypt des3 menggunakan open ssl
   ![Picture8-10a](/src/img/Picture8-10a.png)
2. Data di save dengan raw karena jika di format lain tidak bisa nga kwkwk
   ![Picture8-10b](/src/img/Picture8-10b.png)
3. roses decrypt menggunkan ``opensll des3 -d -salt -in encrypted.des3 -out normal.txt`` sesuai dengan petunjuk yang di sarankan
4. berdasar petunjuk password merupakan anime kembar 5 sehingga di dapatkan **nakano**
   ![Picture8-10c](/src/img/Picture8-10c.png)
5. Hasil decrypt di dapatkan hasil sebagai berikut 
   ![Picture8-10c](/src/img/Picture8-10d.png)

 	
