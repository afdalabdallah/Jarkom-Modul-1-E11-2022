
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

 
