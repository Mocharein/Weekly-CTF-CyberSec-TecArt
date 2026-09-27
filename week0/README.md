NIM: 260530911014

Nama: Ni Kadek Dwi Indira

Divisi: Cyber Security

Kategori: Forensics


##1. Dokumentasi Instalasi dan Pengujian
---
![Kode Uji WSL](images/kode_uji_wsl.png)
![Hasil Uji WSL](images/hasil_uji_wsl.png)

![Kode Uji Python](images/kode_uji_python.png)
![Hasil Run Python](images/hasil_run_python.png)

![Instalasi Exiftool](images/instal_exiftool.png)
![Hasil Uji Exiftool](images/uji_exiftool.png)


##2. Challenge Undo
---
Challenge undo dimulai dengan menghubungkan terminal ke alamat server foggy-cliff.picoctf.net melalui port 52581 menggunakan perintah nc (netcat).

Diberikan teks yang dienkode menggunakan format base64.

Teks didekode menggunakan perintah: 

base64 -d

Selanjutnya, teks yang diberikan berada dalam posisi terbalik.

Teks tersebut dibalikkan dengan menggunakan perintah: 

rev

Karakter underscores (_) telah diubah menjadi tanda hubung/dash (-).

Ubah kembali dengan menggunakan perintah:

tr '-' '_'

Tanda kurung kurawal {} telah diubah menjadi tanda kurung biasa ().

Karakter diubah kembali menggunakan perintah:

tr '()' '{}'

Teks dienkripsi menggunakan substitusi ROT13.

Teks kemudian diubah menggunakan perintah:

tr 'A-Za-z' 'N-ZA-Mn-za-m'

Dengan A-Za-z merepresentasikan urutan abjad; dan 

N-ZA-Mn-za-m merepresentasikan abjad yang berubah 13 posisi.

Hasil Flag:

picoCTF{Revers1ng_t3xt_Tr4nsf0rm@t10ns_72088a35}

##Dokumentasi

![Challenge Undo](images/undo.png)

##Referensi

[PicoCTF: Undo Writeup - Rodrigo Quispe](https://share.google/ELDO8sHug98BMn7TT)


##3. Challenge Information
---
Mengunduh file cat.jpg via URL menggunakan perintah wget.

Memeriksa metadata file dengan menggunakan exiftool:

exiftool cat.jpg

Pada hasil metadata, terdapat teks acak pada bagian license.

Teks acak tersebut merupakan teks yang dienkode dengan format base64.

Teks harus didekode menggunakan perintah:

'echo' dan 'base64 -d'

contoh: echo "cGljb0NURntheV9tM3RhZGF0YTFzX21vZGlmaWVkfQ==" | base64 -d

Proses dekode akan menghasilkan flag:

picoCTF{the_m3tadata_1s_modified}

##Dokumentasi

![Challenge Information](images/information.png)
