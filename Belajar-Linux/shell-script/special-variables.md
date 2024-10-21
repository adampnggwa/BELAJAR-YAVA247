# Special Variables
| Variabel | Keterangan                              |
| -------- | ----------------------------- |
| `$0`     | Mewakili nama berkas dari skrip yang sedang berjalan.                                                            |
| `$n`     | Menunjukkan argumen sesuai dengan posisi (n) di mana n adalah angka posisi argumen (dimulai dari $1, $2, dst).  |
| `$#`     | Menampilkan jumlah total argumen yang diberikan saat memanggil skrip.                                          |
| `$*`     | Merepresentasikan semua argumen sebagai satu string yang diapit oleh tanda kutip ganda.                        |
| `$@`     | Menggambarkan semua argumen sebagai daftar terpisah yang diapit oleh tanda kutip ganda untuk masing-masing.  |
| `$?`     | Menunjukkan status keluaran dari perintah yang terakhir kali dieksekusi.                                        |
| `$$`     | Menampilkan nomor proses (PID) dari shell saat ini.                                                            |
| `$!`     | Mengindikasikan nomor proses dari perintah latar belakang terakhir yang dieksekusi.                            |
#
### Command-Line Arguments
Argumen baris perintah $1, $2, $3, ..., $9 merupakan parameter-posisi, di mana $0 mengarahkan kepada perintah, program, skrip shell, atau fungsi sebenarnya, dan $1, $2, $3, ..., $9 adalah argumen-argumen bagi perintah tersebut.
```sh
#!/bin/sh

echo "Nama Berkas: $0"
echo "Parameter Pertama: $1"
echo "Parameter Kedua: $2"
echo "Quoted Values: $@"
echo "Quoted Values: $*"
echo "Total Jumlah Parameter : $#"
```
![cli_arg](https://iili.io/Hy2BdaR.png)
#
### Special Parameters
Parameter khusus dalam shell script digunakan untuk mengakses semua argumen baris perintah secara bersamaan. 

- ***$****: Parameter ini menggabungkan semua argumen menjadi satu string tunggal dengan spasi sebagai pemisah di antara mereka. Dalam hal ini, seluruh daftar argumen dianggap sebagai satu entitas tunggal. Jika dilakukan iterasi, akan diperlakukan seolah-olah hanya ada satu argumen.
    ```sh
    #!/bin/sh

    for arg in $*
    do
        echo $arg
    done
    ```

- ***$@***: Parameter ini memperlakukan semua argumen sebagai argumen terpisah. Setiap argumen dianggap sebagai entitas terpisah dan tidak digabungkan dengan argumen lain. Jika dilakukan iterasi, setiap argumen akan diperlakukan secara terpisah.

    ```sh
    #!/bin/sh

    for arg in $@
    do
        echo $arg
    done
    ```
#
### Exit Status
Variabel $? dalam shell script mewakili exit status dari perintah yang paling baru dieksekusi. Exit status ini memberikan informasi tentang hasil dari eksekusi perintah tersebut, apakah berhasil atau tidak.

Secara umum, exit status memiliki makna sebagai berikut:

- 0 : Menunjukkan bahwa perintah berhasil dieksekusi tanpa masalah.
    
    Contoh Jika perintah berhasil (exit status 0)
    ```sh
    $ ls
    file1.txt  
    file2.txt
    $ echo $?
    0
    ```
    #
- Non-zero: Menunjukkan bahwa perintah gagal atau mengalami masalah selama eksekusi. Nilai non-zero ini bisa berbeda-beda tergantung jenis masalah yang dialami.
    
    Contoh jika perintah gagal (exit status 1)
    ```sh
    $ cat non_existent_file.txt
    cat: non_existent_file.txt: No such file or directory
    $ echo $?
    1
    ```
#
Contoh penggunaan dalam script
```sh
#!/bin/bash
ls non_existent_file.txt
if [ $? -ne 0 ]; then
    echo "Berkas tidak ditemukan"
else
    echo "Berkas ditemukan"
fi
```
Script ini menjalankan perintah ls pada sebuah berkas yang tidak ada. Jika perintah gagal (exit status akan bernilai non-zero), pesan "Berkas tidak ditemukan" akan ditampilkan.

![testmain](https://iili.io/HyFqsyl.png)