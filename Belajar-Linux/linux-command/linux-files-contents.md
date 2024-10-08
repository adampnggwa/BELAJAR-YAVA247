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

#
- Command Tac
    | Command            | Fungsi      |
    |--------------|---------------|
    |tac [nama berkas]	|Menampilkan isi berkas dalam urutan terbalik (dari baris terakhir ke baris pertama).|
    |tac [nama berkas] --separator "string"	|Memisahkan isi berkas dari string yang ditentukan.|

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

#
- Command Less
    | Command            | Fungsi      |
    |--------------|---------------|
    |less [nama berkas]	|Menampilkan isi berkas satu layar penuh, menyesuaikan lebar dan tinggi jendela terminal.|
    |less [berkas1] [berkas2]	|Menampilkan isi beberapa berkas secara berurutan. Dapat berpindah antar berkas saat tampilan "less" terbuka.|