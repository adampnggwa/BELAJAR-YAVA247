# Linux Files Contents

## 4 Oktober 2024

---

## Details

#
- Command Head
    | Command            | Fungsi      |
    |--------------|---------------|
    | head [file name]       | Menampilkan konten awal dari sebuah berkas. Secara default, menampilkan 10 baris awal dari berkas.            |
    | head [file name] [file name]    | Menampilkan 10 baris awal dari setiap berkas dengan judul terpisah.  |
    | head -n [file name]             | Menampilkan jumlah baris yang ditentukan dari sebuah berkas.     |
    | head -n [jumlah_baris] [file]   | Menampilkan jumlah baris yang ditentukan dari sebuah berkas.     |
    | head -c [number] [file]         | Menghitung jumlah byte dari sebuah berkas                        |
    | head -c [jumlah_byte]k [file]   | Menghitung jumlah byte dengan pengali dan satuan. Pengali dapat berupa "b" (bytes=512), "k" (kilobytes=1024), atau "m" (megabytes=1048576).    |

    Berikut ini adalah contoh penggunaan command head pada linux (Rocky Linux 8).

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc1.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc2.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc3.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc4.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc5.png)

#
- Command Tail
    | Command            | Fungsi      |
    |--------------|---------------|
    |tail [nama berkas]	|Menampilkan sepuluh baris terakhir dari satu berkas.|
    |tail -n [jumlah] [nama berkas]	| Menampilkan jumlah baris yang ditentukan dari berkas terakhir.|
    |tail -c [jumlah] [nama berkas]	| Menampilkan jumlah byte yang ditentukan dari berkas terakhir.|
    | tail -f [nama berkas]	| Memantau perubahan pada berkas dan menampilkan baris baru saat ditambahkan (gunakan Ctrl+C untuk keluar).|
    | tail -n 6 [perintah] tail	| Menampilkan enam baris terakhir dari keluaran suatu perintah.|
    | tail [berkas1] [berkas2]	| Menampilkan sepuluh baris terakhir dari beberapa berkas sekaligus.|

    Berikut ini adalah contoh penggunaan command tail pada linux (Rocky Linux 8).

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc6.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc7.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc8.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc9.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc10.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc11.png)

#
- Command Cat
    | Command            | Fungsi      |
    |--------------|---------------|
    |cat [nama berkas]	|Menampilkan isi dari sebuah berkas.|
    |cat > [nama berkas]	|Membuat berkas baru atau mengganti isi berkas yang ada.|
    |cat >> [nama berkas]	|Menambahkan isi berkas yang ada ke berkas yang lain.|
    |cat [berkas1] [berkas2] > [berkas_baru]	|Menggabungkan isi dari beberapa berkas ke dalam satu berkas baru.|
    |cat -n [nama berkas]	|Menampilkan isi berkas dengan nomor baris.|
    |cat -b [nama berkas]	|Menampilkan isi berkas dengan nomor baris, mengabaikan baris kosong.|
    |cat -e [nama berkas]	|Menampilkan isi berkas dengan simbol '$' di akhir setiap baris.|
    |cat << EOF	|Membuat dan mengisi berkas dengan menghentikan pada tanda "EOF".|

    Berikut ini adalah contoh penggunaan command cat pada linux (Rocky Linux 8).

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc12.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc13.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc14.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc15.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc16.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc17.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc18.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc19.png)
#
- Command Tac
    | Command            | Fungsi      |
    |--------------|---------------|
    |tac [nama berkas]	|Menampilkan isi berkas dalam urutan terbalik (dari baris terakhir ke baris pertama).|
    |tac [nama berkas] --separator "string"	|Memisahkan isi berkas dari string yang ditentukan.|

    Berikut ini adalah contoh penggunaan command tac pada linux (Rocky Linux 8).

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/tac.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc20.png)

#
- Command More
    | Command            | Fungsi      |
    |--------------|---------------|
    |more [nama berkas]	|Menampilkan isi berkas satu layar penuh pada satu waktu. Dapat digulir ke bawah atau ke atas.  |
    |more -num [nama berkas]	|Batasi jumlah baris yang ditampilkan per halaman.  |
    |more -d [nama berkas]	|Menampilkan pesan pengguna di sudut kanan bawah.  |
    |more -s [nama berkas]	|Memampatkan baris kosong.  |
    |more +/string [nama berkas]	|Mencari string dalam berkas dan mulai menampilkan dari baris pertama yang cocok.  |
    |more +num [nama berkas]|Memulai menampilkan isi dari berkas dari baris tertentu.  |

    Berikut ini adalah contoh penggunaan command more pada linux (Rocky Linux 8).

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc21.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc22.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc23.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc24.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc25.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc26.png)

#
- Command Less
    | Command            | Fungsi      |
    |--------------|---------------|
    |less [nama berkas]	|Menampilkan isi berkas satu layar penuh, menyesuaikan lebar dan tinggi jendela terminal.|
    |less [berkas1] [berkas2]	|Menampilkan isi beberapa berkas secara berurutan. Dapat berpindah antar berkas saat tampilan "less" terbuka.|

    Berikut ini adalah hasil penggunaan command less pada linux (Rocky Linux 8).

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc27.png)

    ![LC](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/lc28.png)