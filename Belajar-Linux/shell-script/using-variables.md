# Using Shell Variables
### Variable Names
Nama variabel di shell Unix hanya dapat mengandung huruf (a hingga z atau A hingga Z), angka (0 hingga 9), atau karakter garis bawah (_).

#
### Defining Variables
Variabel didefinisikan dengan format: nama_variabel=nilai_variabel
```sh
NAMA="Jebi Hendardi"
```
Variabel jenis ini disebut variabel skalar, yang hanya bisa menyimpan satu nilai pada satu waktu.

#
### Accessing Values
Nilai dalam variabel diakses dengan menambahkan tanda dolar ($) di depan nama variabel.
```sh
echo $NAMA
```
Perintah di atas akan mencetak nilai yang tersimpan dalam variabel NAMA.


#
### Read-only Variables
Variabel dapat ditandai sebagai read-only dengan perintah ***read-only***. Setelah ditandai, nilai variabel tidak dapat diubah

```sh
NAMA="Jebi Hendardi"
read-only NAMA
NAMA="Uchiha Itachi" #akan terjadi error
```
Script tersebut akan mengalami kesalahan
```sh
/bin/sh: NAMA: This variable is read only.
```


#
### Unsetting Variables
Variabel dapat dihapus dari daftar variabel yang dilacak oleh shell menggunakan perintah unset. Setelah dihapus, nilai dalam variabel tidak lagi dapat diakses. 

Perintah unset tidak dapat digunakan untuk menghapus variabel yang ditandai sebagai read-only.
```sh
NAMA="Jebi Hendardi"
unset NAMA
echo $NAMA #tidak mencetak apa pun
```

#
### Variable Types
- ### Local Variables
    Hanya berlaku dalam sesi shell saat ini dan tidak bisa diakses di luar sesi tersebut. Umumnya digunakan untuk menyimpan sementara dalam skrip atau interaksi baris perintah.
    ```sh
    NAMA="Jebi"
    ```

- ### Environment Variables
    Tersedia untuk semua proses yang dimulai dari sesi shell saat ini. Digunakan untuk membagikan informasi antar proses dan seringkali mengonfigurasi perilaku sistem atau memberikan data penting ke program.
    ```sh
    export PATH="/usr/local/bin:$PATH"
    ```

- ### Shell Variables:
    Variabel khusus yang diatur oleh shell sendiri dan digunakan untuk mengontrol perilaku dan fitur-fiturnya. Beberapa variabel ini digunakan untuk konfigurasi, sedangkan yang lain memengaruhi cara kerja shell. Variabel ini bisa bersifat lokal atau environment.
    ```sh
    SHELL="/bin/bash"
    ```