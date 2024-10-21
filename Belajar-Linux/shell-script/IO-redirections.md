- ## Output Redirection
    Output redirection adalah teknik di lingkungan shell di mana Anda mengarahkan keluaran dari suatu program. Dalam Unix-like shell, keluaran dari program biasanya ditampilkan di layar atau terminal. Namun, dengan menggunakan output redirection, kita dapat mengalihkan keluaran ini ke dalam berkas atau perintah lain.
    
    Contoh :
    ```sh
    command > output.txt
    ```
    Perintah ini akan mengalihkan keluaran dari command ke berkas output.txt.
    #
    ```sh
    ls -l > directory_contents.txt
    ```
    Perintah ini akan mengalihkan daftar isi direktori ke berkas directory_contents.txt
#
- ## Input Redirection
    Input redirection adalah teknik di lingkungan shell di mana Anda mengarahkan masukan ke suatu program. Biasanya, masukan program atau perintah berasal dari keyboard atau terminal. Namun, dengan menggunakan input redirection, Anda dapat mengalihkan masukan dari berkas atau perintah lain.

    Contoh :
    ```sh
    command < input.txt
    ``` 
    Perintah ini akan mengalihkan masukan dari berkas input.txt ke command.
    #
    ```sh
    sort < unsorted.txt
    ```
    Perintah ini akan mengalihkan isi berkas unsorted.txt sebagai masukan ke perintah sort.
#
- ## Here Document
    Here document adalah cara untuk memberikan masukan teks panjang ke suatu perintah di dalam skrip shell. Biasanya, perintah diikuti oleh tanda << dan suatu "delimiter" yang Anda tentukan sendiri. Setelah delimiter, Anda dapat memasukkan teks sebanyak yang Anda inginkan hingga delimiter tersebut muncul kembali pada baris terpisah. Teks ini akan dianggap sebagai masukan oleh perintah tersebut.
    ```sh
    command << delimiter
        text
    delimiter
    ```

    Misalnya, perintah cat biasanya digunakan untuk menampilkan isi berkas. Namun, dengan here document, Anda dapat memberikan teks langsung ke perintah cat sebagai masukan.
    ```sh
    cat << END
    This is a multiline
    text input for the cat command.
    END
    ```
    Pada contoh di atas, cat adalah perintah yang akan menerima masukan dari here document. Delimiter yang digunakan adalah END. Setelah delimiter END, kita memberikan teks yang ingin dimasukkan sebagai masukan. Teks ini bisa terdiri dari beberapa baris. Here document akan berakhir ketika delimiter END muncul pada baris terpisah setelah teks yang dimasukkan.

    Hasil :
    ```sh
    This is a multiline
    text input for the cat command.
    ```
    Here document sangat berguna ketika Anda ingin memberikan masukan panjang atau kompleks ke dalam perintah tanpa harus membuat berkas terpisah.

#
- ## Discard the output
    Dalam lingkungan shell, ada situasi di mana kita mungkin tidak ingin melihat atau menyimpan keluaran dari suatu perintah. Kita dapat membuang keluaran ini dengan menggunakan operator dev/null.

    Contoh
    ```sh
    command > /dev/null
    ```
    Perintah ini akan mengalihkan keluaran dari command ke "tempat sampah" (/dev/null), sehingga tidak ditampilkan atau disimpan.
#
- ## Redirection Commands
    | Perintah                 | Deskripsi                                                 |
    | ------------------------ | --------------------------------------------------------- |
    | `pgm > file`              | Keluaran dari `pgm` diarahkan ke dalam berkas             |
    | `pgm < file`              | Program `pgm` membaca masukan dari berkas                 |
    | `pgm >> file`             | Keluaran dari `pgm` ditambahkan ke dalam berkas           |
    | `n > file`                | Keluaran dari aliran dengan deskriptor `n` diarahkan ke berkas |
    | `n >> file`               | Keluaran dari aliran dengan deskriptor `n` ditambahkan ke dalam berkas |
    | `n >& m`                  | Menggabungkan keluaran dari aliran `n` dengan aliran `m` |
    | `n <& m`                  | Menggabungkan masukan dari aliran `n` dengan aliran `m`  |
    | `<< tag`                  | Masukan standar berasal dari sini melalui tag berikutnya di awal baris |
    | `\|`                      | Mengambil keluaran dari satu program atau proses, dan mengirimkannya ke program atau proses lain |

