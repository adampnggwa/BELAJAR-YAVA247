# Decision Making
### The if...else statements
- if...fi statement
    
    Bentuk dasar pernyataan if. Blok kode dijalankan jika kondisi benar.
    ```sh
    if [ kondisi ]; 
    then
     # Blok kode yang dijalankan jika kondisi benar
    fi
    ```
    Contoh :
    ```sh
    #!/bin/bash

    nilai=75

    if [ $nilai -ge 60 ];
    then
        echo "Selamat, Anda lulus!"
    fi
    ```
    Program memeriksa apakah nilai variabel $nilai (dalam contoh ini = 75) lebih besar atau sama dengan 60. Karena kondisi benar (75 >= 60), blok kode di dalam pernyataan if dijalankan, sehingga program mencetak "Selamat, Anda lulus!"
    
    ![test1](https://iili.io/HyF9omu.png)

    
#
- if...else...fi statement
    
    Memungkinkan program menjalankan blok kode jika kondisi benar dan blok lain jika kondisi salah.
    ```sh
    if [ kondisi ]; 
    then
     # Blok kode yang dijalankan jika kondisi benar
    else
     # Blok kode yang dijalankan jika kondisi salah
    fi
    ```
    Contoh
    ```sh
    #!/bin/bash

    umur=17

    if [ $umur -ge 18 ];
    then
        echo "Anda boleh memilih."
    else
        echo "Anda belum cukup umur untuk memilih."
    fi
    ```
    Program mengevaluasi apakah nilai variabel $umur (17 dalam contoh ini) lebih besar atau sama dengan 18. Karena kondisi false (17 < 18), blok kode di dalam pernyataan else dijalankan, sehingga program mencetak "Anda belum cukup umur untuk memilih."

    ![test2](https://iili.io/HyF9nee.png)

#
- if...elif...else...fi statement
    ```sh
    if [ kondisi1 ]; then
        # Blok kode dijalankan jika kondisi1 benar
    elif [ kondisi2 ]; then
        # Blok kode dijalankan jika kondisi2 benar
    else
        # Blok kode dijalankan jika semua kondisi salah
    fi
    ```

    Contoh
    ```sh
    #!/bin/bash

    nilai=85

    if [ $nilai -ge 90 ]; then
        echo "Anda mendapatkan nilai A."
    elif [ $nilai -ge 80 ]; then
        echo "Anda mendapatkan nilai B."
    elif [ $nilai -ge 70 ]; then
        echo "Anda mendapatkan nilai C."
    else
        echo "Anda mendapatkan nilai D."
    fi
    ```
    Program mengevaluasi nilai variabel $nilai (85 dalam contoh ini). Karena kondisi pertama salah (85 < 90), dan kondisi kedua benar (85 >= 80), blok kode di dalam pernyataan elif kedua dijalankan, sehingga program mencetak "Anda mendapatkan nilai B."

    ![test3](https://iili.io/HyF9Bd7.png)
#
### The case...esac Statement
Pernyataan case...esac digunakan ketika kita ingin melakukan pengambilan keputusan berdasarkan nilai dari satu variabel. 
```sh
case $variable in
    nilai1)
        # Blok kode jika variable == nilai1
        ;;
    nilai2)
        # Blok kode jika variable == nilai2
        ;;
    *)
        # Blok kode jika tidak ada nilai yang cocok
        ;;
esac
```
Contoh
```sh
#!/bin/bash

buah="apel"

case $buah in
    "apel")
        echo "Ini adalah buah apel."
        ;;
    "pisang")
        echo "Ini adalah buah pisang."
        ;;
    "jeruk")
        echo "Ini adalah buah jeruk."
        ;;
    *)
        echo " Input salah"
        ;;
esac
```

Dalam contoh ini, pernyataan case...esac digunakan untuk memilih tindakan berdasarkan nilai variabel $buah ("apel" dalam contoh ini). Program membandingkan nilai buah dengan beberapa kemungkinan. Karena $buah cocok dengan "apel", blok kode yang sesuai dijalankan, dan program mencetak "Ini adalah buah apel."

![test4](https://iili.io/HyF9C79.png)