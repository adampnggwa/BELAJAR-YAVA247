# Defining Array Values
Dengan array, kita dapat menyimpan beberapa nilai dalam satu variabel.

```sh
array_name[index]=value
```
```sh
NAMA[0]="Madara"
NAMA[1]="Sasuke"
NAMA[2]="Uzumaki"
NAMA[3]="Uchiha"
```
#
Syntax Inisialisasii array dalam shell ksh
```sh
set -A array_name value1 value2 ... valuen
```
#
Syntax Inisialisasi array dalam shell bash
```sh
array_name=(value1 ... valuen)
```
#
Misalnya, kita ingin menyimpan daftar nama dalam satu variabel array. 

```sh
AKATSUKI=("Itachi" "Konan" "Pain")
```


#
#
# Accessing Array Values
Setelah kita mendefinisikan nilai dalam array, kita dapat mengaksesnya dengan menggunakan indeks. Indeks dimulai dari 0 untuk elemen pertama, 1 untuk elemen kedua, dan seterusnya.

```sh
#!/bin/bash

AKATSUKI=("Itachi" "Konan" "Pain")

echo "Nama Anggota Pertama: ${AKATSUKI[0]}"
echo "Nama Anggota Kedua: ${AKATSUKI[1]}"
echo "Nama Anggota Ketiga: ${AKATSUKI[2]}"
```
![array1](https://iili.io/Hy2Tj5b.png)

#
Selain itu, kita dapat menggunakan tanda bintang * atau @ untuk mengakses semua nilai dalam array.

```sh
#!/bin/bash

AKATSUKI=("Itachi" "Konan" "Pain")

echo "Semua Nama : ${AKATSUKI[*]}"
echo "Semua Nama : ${AKATSUKI[@]}"
```
![array2](https://iili.io/Hy2Twej.png)