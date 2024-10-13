# Linux Unix Tools

## 12 Oktober 2024

---

## Details

#
- ### Command find
    Perintah "find" digunakan untuk mencari daftar berkas dengan berbagai kondisi seperti izin, kepemilikan pengguna, modifikasi, tanggal/waktu, ukuran, dan lain-lain. Perintah ini merupakan utilitas baris perintah yang mampu mencari berkas berdasarkan format yang ditentukan oleh pengguna.


    | Tipe File | Keterangan              |
    | --------- | ----------------------- |
    | `f`         | Berkas biasa            |
    | `d`         | Direktori               |
    | `l`         | Tautan simbolik         |
    | `c`         | Perangkat karakter      |
    | `b`         | Perangkat blok          |


    #
    ### Contoh Penggunaan command find
    |Command                            | Deskripsi                                                                                       |
    |------------------------------------|-------------------------------------------------------------------------------------------------|
    | `find . -name "*.txt"`             | Mencari semua berkas dengan ekstensi '.txt' dari direktori kerja saat ini.                     |
    | `find . -type d -name "*.bak"`     | Menampilkan semua direktori dengan ekstensi '.bak'.                                           |
    | `find . -newer msg.txt`            | Menampilkan semua berkas yang lebih baru dari 'msg.txt' di direktori kerja saat ini.           |
    | `find . -name Demo.txt -delete`    | Menghapus berkas 'Demo.txt' dari direktori kerja saat        |
    | `find . -type d -name Newdirectory`| Mencari lokasi direktori 'Newdirectory'.                                                      |
    | `find ./Newdirectory -mtime -1`    | Menemukan berkas yang dimodifikasi dalam satu hari terakhir di direktori 'Newdirectory'.        |
    | `find ./<nama direktori> -perm 777`| Menampilkan berkas dari direktori yang dapat dibaca, ditulis, dan dieksekusi oleh semua orang.  |
    | `find ./Newdirectory -type f -exec sed -i 's/find/replace/g' {} \;` | Mencari dan mengganti teks 'find' dengan 'replace' dalam berkas-berkas di direktori   'Newdirectory'. |  
    | `find ./Newdirectory -type f -name -exec grep 'demo'  {} \;`  | Mencari baris yang mengandung teks 'demo' dalam berkas-berkas teks di direktori 'Newdirectory'.      |
    | `find / -name file1 -type f -print`| Mencari semua direktori untuk berkas reguler dengan nama 'file1' dan mencetak hasilnya di  layar.      |


#
- ### Command locate
    Perintah "locate" adalah proses latar belakang dan mencari berkas dalam database, sedangkan "find" mencari berkas dalam sistem berkas secara langsung. Perintah "locate" juga lebih cepat daripada "find".

    Jika tidak dapat menemukan berkas dengan perintah "locate", itu berarti database sudah expired, perbarui database tersebut dengan menggunakan perintah "updatedb".

    syntax 
    ```
    locate [OPTION]... PATTERN...  
    ```
    Option yang biasa digunakan
    | Option               | Deskripsi                                                |
    | -------------------- | ------------------------------------------------------- |
    | `-A, --all:`         | Menampilkan entri yang cocok dengan semua PATTERNs.     |
    | `-b, --basename:`    | Membandingkan hanya dengan nama dasar berdasarkan pola. |
    | `-c, --count:`       | Menulis jumlah entri yang cocok daripada nama berkas.    |
    | `-d, --database DBPATH:` | Menggantikan basis data default dengan DBPATH.         |
    | `-e, --existing:`    | Menampilkan hanya entri yang mengacu pada berkas yang ada. |
    | `-L, --follow:`      | Mengikuti tautan simbolik yang ada, menghilangkan yang rusak. |
    | `-h, --help:`        | Menampilkan dokumentasi bantuan.                       |
    | `-i, --ignore-case:` | Mengabaikan sensitivitas huruf.                         |
    | `-p, --ignore-spaces:` | Mengabaikan tanda baca dan spasi.                     |
    | `-t, --transliterate:` | Mengabaikan aksen dengan transliterasi.               |
    | `-l, --limit, -n LIMIT:` | Keluar setelah menemukan jumlah entri sesuai LIMIT. |
    | `-m, --mmap:`        | Mengabaikan kompatibilitas dengan BSD dan GNU locate.   |
    | `-0, --null:`        | Memisahkan entri dengan ASCII NUL daripada baris terpisah. |
    | `-S, --statistics:`  | Menulis statistik tentang basis data.                  |
    | `-r, --regexp REGEXP:` | Mencari pola ekspresi reguler dasar.                 |
    | `--regex:`           | Menggambarkan semua PATTERN sebagai ekspresi reguler lanjutan. |
    | `-V, --version:`     | Menampilkan informasi versi dan lisensi.                |
    | `-w, --wholename:`   | Cocokkan dengan nama jalur lengkap.                     |
    #
    ### Contoh Penggunaan locate
    | Command                          | Deskripsi                                                              |
    | ------------------------------- | ----------------------------------------------------------------------- |
    | `locate <file name>`            | Perintah `locate` digunakan untuk mencari berkas.                       |
    | `locate -n 5 "*.txt"`           | Membatasi hasil pencarian dengan menampilkan lima berkas teks pertama.  |
    | `locate -c Demo*`               | Menampilkan jumlah berkas yang cocok dengan 'Demo' dalam nama berkas.   |
    | `locate -i "demo.txt"`          | Mengabaikan sensitivitas huruf saat mencocokkan nama berkas.            |
    | `sudo updatedb`                 | Memperbarui basis data `mlocate` jika perintah `locate` tidak bekerja. |
    | `locate -i -e *demo.txt*`       | Hanya menampilkan berkas yang fisik tersedia.                          |
    | `locate -S`                     | Melihat statistik basis data `mlocate`.                                |
    | `locate -i -0 "demo.txt"`       | Menggunakan ASCII NUL sebagai pemisah output.                          |


#
- ### Command date
    Perintah "date" digunakan untuk menampilkan tanggal, waktu, zona waktu, dan lainnya. Juga digunakan untuk mengatur tanggal dan waktu sistem Linux. Secara umum, perintah ini digunakan untuk menampilkan tanggal dalam berbagai format dan menghitung tanggal dari waktu ke waktu.

    Syntax
    ```
    date [OPTION]... [+FORMAT]  
    date [-u|--utc|--universal] [MMDDhhmm[[CC]YY][.ss]] 
    ``` 
    Option yang biasa digunakan
    | Option              | Deskripsi                                                                                            |
    | ----------------- | ---------------------------------------------------------------------------------------------------- |
    | `-d, --date=STRING` | Menampilkan waktu yang dijelaskan oleh STRING.                                                      |
    | `--debug`           | Memberikan anotasi pada tanggal yang diparsing dan memberikan peringatan tentang penggunaan yang kontroversial ke stderr. |
    | `-f, --file=DATEFILE` | Mirip dengan opsi '--date'.                                                                          |
    | `-I[FMT], --iso-8601[=FMT]` | Menampilkan tanggal/waktu dalam format ISO 8601.                                                  |
    | `-R, --rfc-email`   | Menampilkan tanggal dan waktu dalam format RFC 5322. Misalnya, Mon, 14 Aug 2006 02:34:56 -0600.        |
    | `--rfc-3339=FMT`    | Menampilkan tanggal/waktu dalam format RFC 3339.                                                   |
    | `-r, --reference=FILE` | Menampilkan waktu modifikasi sebelumnya dari BERKAS.                                              |
    | `-s, --set=STRING`  | Mengatur waktu yang dijelaskan oleh STRING.                                                         |
    | `-u, --utc, --universal` | Menampilkan atau mengatur UTC.                                                                    |
    | `--help`            | Menampilkan panduan bantuan.                                                                        |
    | `--version`         | Menampilkan informasi versi.                                                                         |
    #
    ### Format Option yang dapat digunakan
    | Format | Fungsi |
    | ---- | --------- |
    | `%a` | Menampilkan nama hari singkat (misalnya, Ming) |
    | `%A` | Menampilkan nama hari penuh (misalnya, Minggu) |
    | `%b` | Menampilkan nama bulan singkat (misalnya, Jan) |
    | `%B` | Menampilkan nama bulan penuh (misalnya, Januari) |
    | `%c` | Menampilkan tanggal dan waktu (misalnya, Kam Mar 3 23:05:25 2005) |
    | `%C` | Menampilkan abad; seperti %Y, namun tanpa dua digit terakhir (misalnya, 20) |
    | `%d` | Menampilkan tanggal dalam bentuk angka (misalnya, 01) |
    | `%D` | Menampilkan tanggal; sama dengan %m/%d/%y |
    | `%e` | Menampilkan tanggal dengan jarak spasi, sama dengan %_d |
    | `%F` | Menampilkan tanggal lengkap; sama dengan %Y-%m-%d |
    | `%g` | Menampilkan dua digit terakhir tahun dari nomor minggu ISO (lihat %G) |
    | `%G` | Menampilkan tahun dari nomor minggu ISO (lihat %V); biasanya hanya berguna dengan %V |
    | `%h` | Sama seperti opsi '%b' |
    | `%H` | Menampilkan jam dalam format 24 jam (00..23) |
    | `%I` | Menampilkan jam dalam format 12 jam (01..12) |
    | `%j` | Menampilkan hari dalam tahun (001..366) |
    | `%k` | Menampilkan jam dengan jarak spasi (0..23); sama dengan %_H |
    | `%l` | Menampilkan jam dengan jarak spasi (1..12); sama dengan %_I |
    | `%m` | Menampilkan bulan (01..12) |
    | `%M` | Menampilkan menit (00..59) |
    | `%n` | Menampilkan baris baru |
    | `%N` | Menampilkan nanodetik (000000000..999999999) |
    | `%p` | Menampilkan AM atau PM; kosong jika tidak diketahui |
    | `%P` | Sama seperti opsi '%p', tetapi dalam huruf kecil |
    | `%q` | Menampilkan kuartal tahun (1..4) |
    | `%r` | Menampilkan waktu dalam format jam 12 (misalnya, 11:11:04 PM) |
    | `%R` | Menampilkan waktu dalam format jam 24 dan menit (misalnya, 23:13) |
    | `%s` | Menampilkan detik sejak 1970-01-01 00:00:00 UTC |
    | `%S` | Menampilkan detik (00..60) |
    | `%t` | Menampilkan tab |
    | `%T` | Menampilkan waktu (misalnya, 23:13:48) |
    | `%u` | Menampilkan hari dalam minggu (1..7); 1 adalah Senin |
    | `%U` | Menampilkan nomor minggu tahun, menghitung Minggu sebagai hari pertama minggu (00..53) |
    | `%V` | Menampilkan nomor minggu ISO, menghitung Senin sebagai hari pertama minggu (01..53) |
    | `%w` | Menampilkan hari dalam minggu (0..6); 0 adalah Minggu |
    | `%W` | Menampilkan nomor minggu tahun, menghitung Senin sebagai hari pertama minggu (00..53) |
    | `%x` | Menampilkan representasi tanggal (misalnya, 12/31/99) |
    | `%X` | Menampilkan representasi waktu (misalnya, 23:13:48) |
    | `%y` | Menampilkan dua digit terakhir tahun (00..99) |
    | `%Y` | Menampilkan tahun |
    | `%z` | Menampilkan zona waktu numerik +hh:mm (misalnya, -0400) |
    | `%:z` | Menampilkan zona waktu numerik +hh:mm (misalnya, -04:00) |
    | `%::z` | Menampilkan zona waktu numerik +hh:mm:ss (misalnya, -04:00:00) |
    | `%:::z` | Menampilkan zona waktu numerik dengan ':' sesuai presisi yang diperlukan (misalnya, -04, +05:30) |
    | `%Z` | Menampilkan singkatan zona waktu alfanumerik (misalnya, WIB) |

#
- ### Command cal
    Perintah 'cal' merupakan singkatan dari kalender

    Syntax:
    ```
    cal 
    ```
    Syntax untuk menampilkan bulan dan waktu tertentu
    ```
    cal <month> <year>  
    ```
#
- ### Command sleep
    Perintah sleep memungkinkan terminal untuk menunggu selama jangka waktu yang ditentukan. Secara default, perintah ini menggunakan waktu dalam detik. Namun, kita dapat mengatur waktu jeda dalam menit (m), jam (h), dan hari (d). Perintah ini membantu dalam menghentikan sementara eksekusi suatu perintah untuk jangka waktu tertentu.

    Syntax
    ```
    sleep NUMBER[SUFFIX]...
    ```
    | Sufiks | Deskripsi                           |
    | ------ | ----------------------------------- |
    | `s`    | detik                         |
    | `m`    | menit                         |
    | `h`    | jam                           |
    | `d`    | hari                          |


#
- ### Command time
    Perintah time pada Linux digunakan untuk menampilkan berapa lama waktu yang diperlukan untuk menjalankan suatu perintah. Perintah ini akan menampilkan informasi tentang sumber daya yang digunakan dan waktu yang dibutuhkan oleh perintah yang diberikan.
    Syntax
    ```
    time [option] [perintah]
    ```
    | Option                   | Deskripsi |
    | ----------------------- | ----------------------- |
    | `-o FILE, --output=FILE`| Menentukan sumber daya dan statistik penggunaan ke FILE, bukan aliran kesalahan standar. Secara default, ini akan menghapus konten file sebelumnya dan menimpanya. |
    | `-a, --append`          | Melampirkan sumber daya agar informasi dapat digunakan tanpa menimpanya di file keluaran. Berguna dengan opsi '-o'. |
    | `-f FORMAT, --format FORMAT` | Menggunakan FORMAT sebagai string format yang mengontrol keluaran waktu. |
    | `--help`                | Menampilkan dokumentasi bantuan yang berisi ringkasan opsi yang didukung dan penggunaannya. |
    | `-p, --portability`     | Menggunakan opsi berikut sesuai standar POSIX 1003.2: |
    | `-v, --verbose`         | Menampilkan keluaran secara rinci. |
    | `--quiet`               | Tidak melaporkan status program bahkan jika berbeda dari nol. |
    | `-V, --version`         | Menampilkan informasi versi dari perintah time yang terpasang. |



#
- ### Command zcat/zmore
    Perintah 'zcat' digunakan untuk melihat berkas yang dikompresi atau berkas yang di-zip.

    Syntax
    ```
    zcat <namaBerkas>
    ```
    Perintah ini memungkinkan kita untuk melihat isi berkas yang dikompresi tanpa harus mengeluarkannya dari kompresi. Cukup dengan memberikan nama berkas yang ingin dilihat isinya, perintah 'zcat' akan menampilkan isi berkas tersebut dalam bentuk teks.

    Perintah 'zmore' dan 'zless' memiliki fungsi yang sama untuk berkas yang dikompresi seperti halnya perintah 'more' dan 'less' untuk berkas yang tidak dikompresi.

#
- ### Command bzip/bunzip
    Perintah bzip2 juga digunakan untuk mengompresi berkas seperti perintah gzip, tetapi memerlukan sedikit lebih banyak waktu namun menghasilkan kompresi yang lebih baik. Ekstensinya adalah (.bz2).
    Syntax
    ```
    bzip2 <namaBerkas>
    ```

    Perintah bunzip2 digunakan untuk mendekompresi berkas yang telah dikompresi menggunakan bzip2.
    Syntax
    ```
    bunzip2 <namaBerkas>
    ```
    Perintah ini akan mendekompresi berkas yang telah dikompresi sebelumnya menggunakan metode bzip2, mengembalikannya ke bentuk berkas aslinya.

#
- ### Command bzcat/bzmore
    Perintah bzcat digunakan untuk menampilkan isi berkas yang dikompresi dengan perintah bzip.

    Syntax
    ```
    bzcat <namaBerkas>
    ```
    Perintah ini akan menampilkan isi berkas yang telah dikompresi menggunakan metode kompresi bzip tanpa perlu mendekompresinya secara manual.

#
- ### Command df
    Perintah df menampilkan informasi tentang penggunaan ruang disk dalam sistem file. Singkatan dari df adalah "disk filesystem." Perintah ini menampilkan jumlah blok yang digunakan, jumlah blok yang tersedia, dan direktori tempat sistem file dipasang.
    Syntax
    ```
    df [OPTION]... [BERKAS]...
    ```
    | Option                        | Deskripsi |
    | --------------------------- | ----------------------------------------------------------- |
    | `-a, --all`                 | Termasuk sistem berkas pseudo, duplikat, dan remote.       |
    | `-B, --block-size=UKURAN`   | Skala ukuran dengan UKURAN sebelum mencetaknya, contohnya, opsi '-BM' mencetak ukuran dalam unit 1.048.576 byte. |
    | `-h, --human-readable`      | Menampilkan ukuran dalam pangkat 1024 (misalnya, 1023M).   |
    | `-H, --si`                  | Menampilkan ukuran dalam pangkat 1000 (misalnya, 1.1G).    |
    | `-i, --inodes`              | Menampilkan informasi inode daripada penggunaan blok.      |
    | `-l, --local`               | Membatasi daftar ke sistem berkas lokal.                   |
    | `--no-sync`                 | Tidak menginduksi sinkronisasi sebelum mendapatkan info penggunaan (default). |
    | `--output[=FIELD_LIST]`     | Menggunakan format keluaran yang ditentukan oleh FIELD_LIST atau mencetak semua bidang jika FIELD_LIST diabaikan. |
    | `-P, --portability`         | Menggunakan format keluaran POSIX.                         |
    | `--total`                   | Mengecualikan semua entri yang tidak signifikan terhadap ruang yang tersedia, dan menghasilkan total. |
    | `-t, --type=JENIS`          | Membatasi daftar ke sistem berkas dengan jenis JENIS.     |
    | `-T, --print-type`          | Menampilkan jenis sistem berkas.                           |
    | `-x, --exclude-type=JENIS`  | Membatasi daftar ke sistem berkas yang bukan jenis JENIS. |
    | `--help`                    | Menampilkan panduan bantuan yang berisi informasi ringkas tentang opsi yang didukung. |
    | `--version`                 | Menampilkan informasi versi dari perintah df.              |

