- ### Creating Functions
    Fungsi dalam shell adalah cara untuk memecah skrip menjadi bagian-bagian yang lebih kecil dan terorganisir, yang dapat dipanggil saat diperlukan. Fungsi membantu dalam menciptakan penggunaan kembali kode dan mengelompokkan tugas-tugas terkait.
    ```sh
    nama_fungsi () {
    daftar_perintah
    }
    ```

#
- ### Pass Parameters to a Function
    Kita dapat memberikan parameter kepada fungsi saat memanggilnya. Parameter ini direpresentasikan oleh $1, $2, dan seterusnya.
    ```sh
    #!/bin/sh

    # Mendefinisikan fungsi dengan parameter
    Sapa () {
    echo "Halo $1 $2"
    }

    # Memanggil fungsi dengan parameter
    Sapa Uchiha Jebi
    ```
    ![test1](https://iili.io/Hy35HRn.png)

    Script ini mendefinisikan sebuah fungsi bernama ***Sapa*** yang mengambil dua parameter. Fungsi ini bertugas menampilkan pesan "Halo" diikuti oleh nilai dari parameter pertama dan kedua.

    Setelah mendefinisikan fungsi Sapa, script ini memanggil fungsi tersebut dengan parameter "Uchiha" dan "Jebi". Hasilnya, di layar akan ditampilkan pesan "Halo Uchiha Jebi".
#
- ### Returning Values from Functions
    Kita dapat mengembalikan nilai dari fungsi menggunakan perintah return. Jika ingin menghentikan eksekusi fungsi tanpa menghentikan seluruh skrip, gunakan perintah return dengan nilai yang diinginkan.
    ```sh
    #!/bin/sh

    # Mendefinisikan fungsi yang mengembalikan nilai
    TampilkanPesan () {
    echo "Halo $1 $2"
    return 10
    }

    # Memanggil fungsi dan menangkap nilai yang dikembalikan
    TampilkanPesan Uchiha Jebi
    ret=$?

    echo "Nilai return adalah $ret"
    ```
    ![test2](https://iili.io/Hy359HX.png)

    Langkah-langkah yang dijalankan oleh program :
    1. Mendefinisikan sebuah fungsi bernama TampilkanPesan yang mengambil dua parameter. Fungsi ini bertugas menampilkan pesan "Halo" diikuti oleh nilai dari parameter pertama dan kedua, kemudian mengembalikan nilai 10 menggunakan pernyataan return 10.

    2. Setelah mendefinisikan fungsi TampilkanPesan, script ini memanggil fungsi tersebut dengan parameter "Uchiha" dan "Jebi". Selanjutnya, script menangkap nilai kembalian dari fungsi yang disimpan dalam variabel ret.

    3. Kemudian menampilkan pesan "Nilai return adalah" diikuti oleh nilai yang disimpan dalam variabel ret.
#
- ### Nested Functions
    Fungsi dapat memanggil fungsi lain, termasuk dirinya sendiri. Ini dikenal sebagai fungsi bertingkat atau rekursif.
    Contoh :
    ```sh
    #!/bin/sh

    # Memanggil fungsi lain dari dalam fungsi
    FungsiSatu () {
    echo "Ini adalah fungsi pertama..."
    FungsiDua
    }

    FungsiDua () {
    echo "Ini sekarang adalah fungsi kedua..."
    }

    # Memanggil fungsi pertama
    FungsiSatu
    ```
    ![test3](https://iili.io/Hy3RpSt.png)
    
    Script ini memanggil fungsi FungsiSatu, yang kemudian mencetak pesan pertama dan memanggil FungsiDua. FungsiSatu memanggil FungsiDua dari dalam tubuh fungsinya sendiri, inilah mengapa output nya adalah menampilkan pesan dari kedua fungsi.
#
- ### Function Call from Prompt
    Kita dapat menempatkan definisi-definisi fungsi yang sering digunakan di dalam file .profile. Definisi-definisi ini akan tersedia setiap kali user login dan user dapat menggunakannya pada command prompt.

    Atau sebagai alternatif, kita dapat mengelompokkan definisi-definisi tersebut dalam sebuah file dan kemudian menjalankan file tersebut di shell saat ini dengan mengetikkan :

    ```sh
    $. nama_berkas.sh
    ```
    Hal ini akan membuat fungsi-fungsi yang didefinisikan di dalam test.sh dibaca dan didefinisikan di shell saat ini seperti berikut "
    ```sh
    $ number_one
    This is the first function speaking...
    This is now the second function speaking...
    $
    ```

    Untuk menghapus definisi fungsi dari shell, kita dapat menggunakan perintah unset dengan opsi -f. Perintah ini juga digunakan untuk menghapus definisi variabel dari shell.
    ```sh
    $ unset -f nama_fungsi
    ```
    Misalnya, unset -f number_one akan menghapus definisi fungsi number_one dari shell.
    