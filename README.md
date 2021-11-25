# Jarkom-Modul-4-C08-2021

Berikut adalah laporan resmi Praktikum Jaringan Komputer Modul 4 tahun 2021

Anggota Kelompok C08 :

- 05111940000100 - Muhammad Raihan
- 05111940000208 - Inez Yulia Amanda
- 05111940000209 - Refaldyka Galuh Pratama

![soal](assets/soal.png)

## Carrier Packet Transport (CPT) - CIDR
### Menghitung NID
Hal pertama yang dilakukan untuk menghitung NID adalah menentukan subnet - subnet yang ada pada topologi. Terbentuklah 15 buah subnet seperti gambar berikut :
![1.1](https://i.imgur.com/FEZa6NR.png)

Dalam CIDR tahap selanjutnya adalah menggabungkan tiap - tiap subnet mulai dari yang paling jauh dari router utama (foosha). Lalu hasil penggabungan tersebut dibuat sebuah Pohon. Untuk tampilan pohonnya dapat dilihat [disini](https://miro.com/app/board/o9J_lhIFaO4=/).
Dalam pohon tersebut, dihitunglah pembagian IP dimulai dari root pohon. Tiap node pada pohon pasti memiliki panjang subnet yang berbeda - beda. Pada tiap node bagi 2 jumlah IP yg tersedia. Letakkan NID masing - masing pada child node. hingga didapat NID masing - masing subnet. Pindahkan kedalam tabel agar mudah dilihat.
![1.2](https://i.imgur.com/M5UCTgN.png)

### Memasukkan IP pada masing - masing Node dalam Topologi
Sebagai contoh, berikut cara mengkonfigurasi IP pada node Foosha untuk subnet A6 pada gambar sebelumnya. Gunakan IP yang tersedia pada subnet A6 yaitu mulai dari 10.18.192.0. Jangan lupa masukkan juga netmask-nya.
![1.3](https://i.imgur.com/TJ3tAuk.png)

Lalu konfigurasikan host di subnet A6, yaitu BLUENO. Masukkan gateway sesuai alamat IP Foosha pada subnet A6. Gunakan IP yg tersedia pada subnet A6 yaitu mulai dari 10.18.192.0 selain yang sudah digunakan untuk gateway menuju foosha. Jangan lupa masukkan juga netmask-nya.
![1.4](https://i.imgur.com/glU4EXJ.png)

Lakukan kedua hal tersebut pada seluruh Node dan Subnet dalam topologi yang telah dibuat.

### Routing
Untuk menghubungkan 2 buah node yang tidak berada dalam 1 subnet, diperlukan routing. Routing akan mengarahkan paket yang dikirim dari suatu node menuju ke suatu subnet. Ambil contoh untuk menghubungkan router utama Foosha menuju Subnet A4. Untuk menghubungkan kedua hal tersebut diperlukan routing yang mengarah ke router pada subnet A4. Hal pertama yang dilakukan adalah membuat daftar routing pada konfigurasi node Foosha. Isikan Alamat dan Netmask Cipher serta NextHop (Gateway menuju Subnet A4, alias Water7).
![1.5](https://i.imgur.com/yOpsyNt.png)

Lalu konfigurasikan default routing pada Water7.
![1.6](https://i.imgur.com/gHPugqZ.png)

Lakukan kedua hal tersebut hingga terhubung antara Foosha dengan subnet yang ada pada topologi

### Testing
Untuk mengecek apakah dua buah node sudah dapat saling mengirim paket, gunakan Simple PDU.
![1.7](https://i.imgur.com/cRPxEHD.png)

Lalu, klik saja 2 buah node yang akan dilakukan pengecekan (Source dan Destination).
![1.8](https://i.imgur.com/20lZr7c.png)

Hasilnya akan terlihat pada panel yang terletak di bagian bawah kanan aplikasi CPT.
![1.9](https://i.imgur.com/BYIP0yu.png)

## GNS3 - VLSM
