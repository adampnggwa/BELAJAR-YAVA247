# Shell Subtitution
Substitusi dilakukan oleh shell ketika menemukan suatu ekspresi yang mengandung satu atau lebih karakter khusus.

| Escape Sequence | Deskripsi                                   |
| --------------- | ------------------------------------------- |
| `\\`            | Backslash              |
| `\a`           | Sinyal peringatan (BEL)                      |
| `\b`           | Backspace                        |
| `\c`           | Menghilangkan baris baru di akhir teks       |
| `\f`           | Pemindahan halaman dalam teks                |
| `\n`           | Karakter baris baru                         |
| `\r`           | Mengembalikan kursor ke awal baris          |
| `\t`           | Karakter tab horizontal                    |
| `\v`           | Karakter tab vertikal                      |
#
# Command Substitution
Command Substitution adalah mekanisme di mana shell menjalankan serangkaian perintah yang diberikan dan kemudian menggantikan keluaran perintah tersebut di tempat perintah tersebut.

Dalam Command Substitution, tanda backquote (`) atau tanda dolar dan tanda kurung 
digunakan untuk menjalankan perintah dan menggantikan hasil keluarannya.

Contoh : Misalnya, kita ingin mendapatkan tanggal dan waktu saat ini dan menyimpannya dalam variabel current_date.
```sh
current_date=`date`
echo "Tanggal dan waktu saat ini adalah: $current_date"
```
Hasilnya akan seperti ini:
```sh
Tanggal dan waktu saat ini adalah: Wed Aug 25 12:34:56 UTC 2023
```

#
# Variable Substitution
Variable Substitution memungkinkan programmer shell untuk memanipulasi nilai variabel berdasarkan kondisinya.

| Form & Deskripsi                 | Keterangan                          |
| ---------------------- | --------- |
| `${var}`                                    | Menggantikan nilai dari variabel `var`.                                     |
| `${var:-word}`                              | Jika `var` kosong atau tidak diatur, menggantikan dengan nilai `word`. Nilai `var` tidak berubah. |
| `${var:=word}`                              | Jika `var` kosong atau tidak diatur, mengatur `var` dengan nilai `word`.   |
| `${var:?message}`                           | Jika `var` kosong atau tidak diatur, mencetak `message` ke stderr. Ini digunakan untuk memeriksa pengaturan variabel. |
| `${var:+word}`                              | Jika `var` diatur, menggantikan dengan nilai `word`. Nilai `var` tidak berubah. |

#
Contoh

```sh
#!/bin/sh

echo ${var:-"Variable is not set"}
echo "1 - Value of var is ${var}"

echo ${var:="Variable is not set"}
echo "2 - Value of var is ${var}"

unset var
echo ${var:+"This is default value"}
echo "3 - Value of var is $var"

var="Prefix"
echo ${var:+"This is default value"}
echo "4 - Value of var is $var"

echo ${var:?"Print this message"}
echo "5 - Value of var is ${var}"
```
#
Hasil

![test](https://iili.io/HyFfyep.png)

#
Pembahasan per baris syntax :
| Variable Substitution | Keterangan |
| --------------------- | ---------- |
| `${var:-"Variable is not set"}` | Menggantikan nilai `var` dengan teks "Variable is not set" jika `var` kosong atau tidak di set. |
| `${var:="Variable is not set"}` | Meng-set nilai `var` menjadi "Variable is not set" jika `var` kosong atau tidak di set. |
| `${var:+"This is default value"}` | Menggantikan nilai `var` dengan teks "This is default value" jika `var` di set. |
| `${var:+"This is default value"}` | Menggantikan nilai `var` dengan teks "This is default value" jika `var` di set. |
| `${var:?"Print this message"}` | Mencetak pesan "Print this message" ke output error jika `var` kosong atau tidak di set. |
