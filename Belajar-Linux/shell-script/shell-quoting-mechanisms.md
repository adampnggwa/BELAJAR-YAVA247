# Quoting Mechanisms
- ### Metacharacters
    Metakarakter adalah karakter-karakter tertentu yang memiliki makna khusus saat digunakan dalam skrip shell. Metakarakter dapat mempengaruhi cara shell menangani teks dan perintah.
    ```sh
    * ? [ ] ' " \ $ ; & ( ) | ^ < > new-line space tab
    ```
    #
    Contoh metakarakter yang umum digunakan dalam shell 
    | Metakarakter | Keterangan |
    | ------------ | ---------- |
    | *            | Cocok dengan nol atau lebih karakter. Misalnya, `*.txt` akan cocok dengan semua berkas yang berakhiran `.txt`. |
    | ?            | Cocok dengan satu karakter tunggal. Misalnya, `?.txt` akan cocok dengan berkas `a.txt` atau `b.txt`. |
    | [ ]          | Dalam rangkaian karakter, cocok dengan salah satu karakter yang ada di dalam tanda kurung. Misalnya, `[aeiou]` akan cocok dengan huruf vokal. |
    | ' dan "      | Digunakan untuk mengapit teks yang akan dianggap secara harfiah. Kutipan tunggal `'` mempertahankan makna khusus metakarakter, sementara kutipan ganda `"` memungkinkan substitusi variabel dan ekspansi. |
    | $            | Digunakan untuk merujuk variabel. Ketika tidak diapit oleh kutipan ganda, shell akan melakukan substitusi variabel. |
    | \            | Digunakan untuk menghindari makna khusus karakter yang mengikuti karakter backslash tersebut. Misalnya, `\$` akan mencetak karakter dolar secara harfiah. |
    | ;            | Digunakan untuk memisahkan perintah shell yang ditempatkan dalam satu baris. |
    | &            | Digunakan untuk menjalankan perintah dalam latar belakang (background). |
    | ( )          | Digunakan untuk mengelompokkan perintah. |
    | <            | Digunakan untuk mengalihkan masukan dari berkas. |
    | >            | Digunakan untuk mengalihkan keluaran ke berkas. |
#

- ### The Single Quotes (' ')
    Single Quotes adalah mekanisme dalam shell yang digunakan untuk mengapit teks agar dianggap secara harfiah. Semua karakter di dalamnya, termasuk karakter khusus dan metakarakter, kehilangan makna khususnya. Hal ini berarti karakter di dalam tanda kutip tunggal dianggap sebagai karakter biasa dan tidak akan diinterpretasikan sebagai bagian dari sintaks shell.

    Contoh
    ```sh
    echo 'Hello, $USER!'
    ```
    ![test1](https://iili.io/Hy3nbWP.png)
    
    Dalam contoh di atas, string $USER! akan dianggap sebagai string biasa, dan akan dicetak Hello, $USER! bukan mengambil nilai dari variabel $USER.
    
#
- ### The Double Quotes (" ")
    Double Quotes memungkinkan beberapa pengecualian di mana karakter khusus tertentu tetap memiliki makna khusus di dalamnya. 
    | Characters    | Keterangan          |
    | ------------------------------------------- | ------------------------------ |
    | $                                          | Substitusi parameter           |
    | Backquotes                                | Substitusi perintah            |
    | \\$                                         | Aktifkan tanda dollar signs   |
    | \\`                                         | Aktifkan literal backquotes |
    | \\"                                         | Aktifkan embedded double quotes|
    | \\\                                         | Aktifkan embedded backslashes |
    | \\ character                  | Karakter bersifat literal      |

    #
    Contoh
    ```sh
    echo "Hello, $USER!"
    ```
    ![test2](https://iili.io/Hy3nms1.png)
    
    Dalam contoh di atas, string $USER! akan bertindak sebagai variabel, program akan mengambil nilai dari variabel $USER.
    
#
- ### The Backquotes ( ` )
    Tanda kutip terbalik (`) digunakan untuk mengapit perintah dalam shell. Saat perintah diapit oleh tanda kutip terbalik, perintah tersebut akan dieksekusi oleh shell.
    ```sh
    DATE=`date`
    echo "Current date is $DATE"
    ```
    Dalam contoh di atas, perintah date dieksekusi, dan hasilnya disimpan dalam variabel DATE. Kemudian, hasilnya digunakan dalam perintah echo untuk mencetak tanggal saat ini. 

    ![test3](https://iili.io/Hy3o8YJ.png)
    
    Backquotes berguna ketika kita ingin menggabungkan hasil eksekusi perintah dengan teks lain dalam shell.