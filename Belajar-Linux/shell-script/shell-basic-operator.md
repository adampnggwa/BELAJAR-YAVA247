- ### Arithmetic Operators
    Operator aritmatika digunakan untuk melakukan operasi matematika pada bilangan

    | Operasi Aritmatika  | Keterangan |
    | ------------------- | --------------------------- |
    | `+`                 | Penjumlahan                  |
    | `-`                 | Pengurangan                  |
    | `*`                 | Perkalian                    |
    | `/`                 | Pembagian                    |
    | `%`                 | Modulus                      |
    | `=`                 | Penugasan                    |
    | `==`                | Persamaan                    |
    | `!=`                | Ketidaksamaan                |
#
- ### Relational Operators
    Operator relasional digunakan untuk membandingkan nilai antara dua ekspresi atau variabel

    | Operasi Relasional  | Keterangan |
    | ------------------- | -------------------------- |
    | `-eq`               | Sama dengan                |
    | `-ne`               | Tidak sama dengan          |
    | `-gt`               | Lebih besar dari           |
    | `-lt`               | Lebih kecil dari           |
    | `-ge`               | Lebih besar atau sama dengan |
    | `-le`               | Lebih kecil atau sama dengan |
#
- ### Boolean Operators
    Operator boolean digunakan untuk melakukan operasi logika antara dua nilai boolean (true atau false).

    | Operator Logika     | Keterangan |
    | ------------------- | -------------------------- |
    | `!`                 | Negasi logika              |
    | `-o`                | OR logika                  |
    | `-a`                | AND logika                 |
#
- ### String Operators
    Operator string digunakan untuk memanipulasi tipe data string.

    | Operator | Deskripsi |
    | -------- | ----------------------------------------- |
    | `=` | Memeriksa apakah nilai dua operand sama atau tidak; jika ya, maka kondisinya menjadi true. |
    | `!=` | Memeriksa apakah nilai dua operand sama atau tidak; jika nilai tidak sama, maka kondisinya menjadi true. | 
    | `-z` | Memeriksa apakah ukuran operand string yang diberikan adalah nol; jika panjangnya nol, maka mengembalikan kondisi true. |
    | `-n` | Memeriksa apakah ukuran operand string yang diberikan tidak nol; jika panjangnya tidak nol, maka mengembalikan kondisi true. |
    | `str` | Memeriksa apakah str bukan string kosong; jika kosong, maka mengembalikan kondisi false. |

#
- ### File Test Operators
    Operator uji berkas (file test operators) digunakan untuk memeriksa status berkas dalam shell scripting. 
    
    | Operator   | Keterangan                                                  |
    | ---------- | ------------------------------------------------------------ |
    | `-b file`  | Memeriksa apakah file merupakan jenis berkas blok; jika ya, maka kondisinya dianggap true. |
    | `-c file`  | Memeriksa apakah file merupakan jenis berkas karakter; jika ya, maka kondisinya dianggap true. |
    | `-d file`  | Memeriksa apakah file adalah sebuah direktori; jika ya, maka kondisinya dianggap true. |
    | `-f file`  | Memeriksa apakah file adalah berkas biasa, bukan direktori atau jenis berkas khusus; jika ya, maka kondisinya dianggap true. |
    | `-g file`  | Memeriksa apakah file memiliki bit Set Group ID (SGID) terpasang; jika ya, maka kondisinya dianggap true. |
    | `-k file`  | Memeriksa apakah file memiliki bit sticky terpasang; jika ya, maka kondisinya dianggap true. |
    | `-p file`  | Memeriksa apakah file adalah pipa bernama; jika ya, maka kondisinya dianggap true. |
    | `-t file`  | Memeriksa apakah deskriptor file terbuka dan terhubung dengan terminal; jika ya, maka kondisinya dianggap true. |
    | `-u file`  | Memeriksa apakah file memiliki bit Set User ID (SUID) terpasang; jika ya, maka kondisinya dianggap true. |
    | `-r file`  | Memeriksa apakah file dapat dibaca; jika ya, maka kondisinya dianggap true. |
    | `-w file`  | Memeriksa apakah file dapat ditulis; jika ya, maka kondisinya dianggap true. |
    | `-x file`  | Memeriksa apakah file dapat dieksekusi; jika ya, maka kondisinya dianggap true. |
    | `-s file`  | Memeriksa apakah file memiliki ukuran lebih dari 0; jika ya, maka kondisinya dianggap true. |
    | `-e file`  | Memeriksa apakah file ada; dianggap true meskipun file adalah direktori. |

