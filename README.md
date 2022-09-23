
<table>
<tr>
<th>Nama</th>
<th>NRP </th>
</tr>
<tr>
<td>Surya Abdillah</td>
<td>5025201229 </td>
</tr>
<tr>
<td>Muhammad Afdal Abdallah</td>
<td>5025201163 </td>
</tr>
<tr>
<td>Kadek Ari Dharmika</td>
<td>5025201239 </td>
</tr>
</table>

# Modul 1

## 1
Sebutkan web server yang digunakan pada "monta.if.its.ac.id"!
```http.host==monta.if.its.ac.id```
> Dengan menggunakan ekspresi tersebut, maka didapatkan hasil:

![image](https://user-images.githubusercontent.com/103357229/192022850-3a94c6ee-7129-4733-9918-1867588207c1.png)

> Dari hasil tersebut, kita mengklik kanan pada salah satu data -> follow -> TCP stream

![image](https://user-images.githubusercontent.com/103357229/192023446-08f99e24-67de-43df-9f13-a8536dc1b834.png)

> Dari proses di atas, maka akan muncul tampilan sebagai berikut:

![image](https://user-images.githubusercontent.com/103357229/192023800-627a76a6-58c5-421a-a768-e9c49b5141b2.png)

Dari data di atas, kita bisa mengetahui bahwa server yang digunakan adalah "nginx/1.10.3"

## 2
Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq ?
> Pertama kita melalukan display filter dengan ekspresi berikut <br>
```http.host==monta.if.its.ac.id```
> Didapatkan hasil sebagai berikut:

![image](https://user-images.githubusercontent.com/103357229/192024891-eaaba41b-379d-4ece-ab7f-ea1805ddc7ac.png)

> Pada data no 576, bisa kita lihat bahwa Ishaq mengakses detailTopik, yakni pada link berikut http://monta.if.its.ac.id/index.php/topik/detailTopik/194 . Berikut judul topik TA yang telah dibuka Ishaq

![image](https://user-images.githubusercontent.com/103357229/192025346-e8600944-ae20-49c0-9889-d96007bc218a.png)

## 3
Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!
> Berdasar soal, maka kita diminta untuk membuat ekspresi display filter dengan destination port 80. Adapun, ekspresi yang digunakan adalah 
```tcp.dstport==80 || udp.dstport==80```

> Dari ekspresi didapati hasil:

![image](https://user-images.githubusercontent.com/103357229/192025676-c8a5e724-ee3e-495c-84a2-6c64f330fa91.png)


## 7 
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian! <br>
``` src host <ip address>```<br>
![img7](https://drive.google.com/uc?export=view&id=1AgOwdPaj0WR_iGVZ3NPSfr-KsvJH1M8W)

## 9
Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud! Untuk memudahkan laporan kepada atasan, beri nama file yang ditemukan dengan format [nama_kelompok].des3 dan simpan output file dengan nama “flag.txt”. <br>

Bedasarkan nomor 8, pertukaran file terjadi di port 9002, maka kita lakukan <br>
```tcp.srcport == 9002```<br>
Setelah itu kita cek satu per satu paket yang mengandung Salted
![salted](https://drive.google.com/uc?export=view&id=1btaiWnhaDOrd66_2M0fmQpYZ_i5wuNS5)
<br>
Kemudian kita export data paket tersebut menjadi E11.des3 <br>
![e11](https://drive.google.com/uc?export=view&id=1Eu0pTQpJet1tdYjiuMmajnmFPYjNdImf)<br>
Selanjutnya kita jalankan powershell untuk mendecrypt file e11.des3 . Berdasarkan informasi, kita perlu mendecrypt menggunakan openssl dan des3, maka commandnya yaitu <br>
```openssl des3 -d -salt -in e11.des3 -out flag.txt```
<br>
Namun ternyata diperlukan password untuk mendecrypt file tersebut, maka password didapatkan dari penjelasan nomor 10.
Setelah di decrypt, didapatkan bahwa isi filenya yaitu:<br>
![flag](https://drive.google.com/uc?export=view&id=1gNzNWfliqVtWXs7j4A2QjpWEgHVsmdBV)


## 10 
Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!
Berdasarkan stream pada nomor 8, didapatkan clue untuk password yaitu "Nama karakter anime yang kembar 5", maka dapat disimpulkan anime tersebut yaitu 5-Toubun no Hanayome, karena mereka kembar, mereka memiliki satu nama yang sama, yaitu "nakano". Oleh karena itu, "nakano" merupakan password untuk mendecrypt soal nomor 9.

 
