# Linux directory

## 3 Oktober 2024

---

## Details

#
- Print Working Directory (pwd)
    | Command   | Fungsi |
    |--------|------|
    | pwd | Menampilkan direktori kerja saat ini. |
    | pwd -L  | Menampilkan jalur logis direktori kerja saat ini.|
    | pwd -P | Menampilkan jalur fisik direktori kerja saat ini. |

    Berikut ini adalah contoh penggunaan command pwd pada linux (Rocky Linux 8).

    ![PWD](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/pwd.png)

#
- Change Directory (cd)
    | Command   | Fungsi |
    |--------|------|
    | cd         | Berpindah antara direktori.                             |
    | cd ~ or cd | Selalu membawa pengguna ke direktori utama.            |
    | cd .       | Memungkinkan pengguna tetap berada di direktori saat ini.|
    | cd ~username | Memungkinkan pengguna tetap berada di direktori utama dari username. |
    | cd dir     | (tanpa menggunakan /) Memungkinkan pengguna tetap berada di subdirektori. |
    | cd ..      | Mengarahkan pengguna satu tingkat di atas direktori.  |
    | cd -       | Mengubah pengguna ke direktori sebelumnya.             |

    Berikut ini adalah contoh penggunaan command cd pada linux (Rocky Linux 8).

    ![CD](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/cd.png)

#
- List (ls)
    | Command   | Fungsi      |
    |------------------------|-----------------|
    | ls         | Menampilkan daftar file dan direktori. 
    | ls -a                  | Menampilkan seluruh daftar direktori saat ini termasuk berkas tersembunyi.          |
    | ls -l                  | Menampilkan daftar dalam format daftar panjang.                                           |
    | ls -lh                 | Menampilkan ukuran berkas dalam format yang mudah dibaca manusia.                         |
    | ls -lhS                | Menampilkan daftar dalam urutan menurun (terbesar di atas) berdasarkan ukuran berkas.     |
    | ls -l --block-size=[SIZE] | Menampilkan berkas dalam format ukuran tertentu.                                         |
    | ls -d */               | Menampilkan hanya subdirektori.                                                          |
    | ls -g atau ls -lG      | Mengecualikan kolom informasi grup dan pemilik.                                          |
    | ls -n                  | Menampilkan ID grup dan pemilik sebagai angka, bukan nama.                               |
    | ls --color=[VALUE]     | Menampilkan daftar dalam warna atau tanpa warna.                                          |
    | ls -li                 | Menampilkan nomor indeks berkas jika berada di kolom pertama.                             |
    | ls -p                  | Mengidentifikasi direktori dengan menandai menggunakan garis miring (/) di belakang.       |
    | ls -r                  | Menampilkan daftar dalam urutan terbalik.                                                |
    | ls -R                  | Akan menampilkan isi subdirektori juga.                                                  |
    | ls -lX                 | Mengelompokkan berkas dengan ekstensi yang sama dalam daftar.                             |
    | ls -lt                 | Mengurutkan daftar dengan menampilkan berkas yang baru diubah di bagian atas.             |
    | ls ~                   | Menampilkan isi direktori beranda.                                                       |
    | ls ../                 | Menampilkan isi direktori induk.                                                          |
    | ls --version           | Memeriksa versi dari perintah ls.                                                          |

    Berikut ini adalah contoh penggunaan command 'ls sampai ls -lh' pada linux (Rocky Linux 8).

    ![LS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/ls-lh.png)

    Berikut ini adalah contoh penggunaan command 'ls -lhs sampai ls -g' pada linux (Rocky Linux 8).

    ![LS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/ls-g.png)

    Berikut ini adalah contoh penggunaan command 'ls -n sampai ls -p' pada linux (Rocky Linux 8).

    ![LS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/ls-p.png)

    Berikut ini adalah contoh penggunaan command 'ls -r sampai ls -lt' pada linux (Rocky Linux 8).

    ![LS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/ls-lt.png)

    Berikut ini adalah contoh penggunaan command 'ls ~ sampai ls --version' pada linux (Rocky Linux 8).

    ![LS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/ls-last.png)

#
- Make Directory (mkdir)
    | Command             | Fungsi       |
    |----------|-----------------|
    | mkdir      | Membuat direktori baru.  
    | mkdir -p, -parents      | Membuat direktori beserta subdirektorinya.             |
    | mkdir -v, -verbose      | Menampilkan pesan untuk setiap direktori yang dibuat.   |
    | mkdir -m -mode=MODE     | Mengatur hak akses (privilege) untuk direktori.         |

    Berikut ini adalah contoh penggunaan command mkdir pada linux (Rocky Linux 8).

    ![PWD](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/mkdir.png)


#
- Remove Directory (rmdir)
    | Command   | Fungsi |
    |--------|------|
    | rmdir | Menghapus direktori |
    |rmdir -p, -parents | Menghapus direktori beserta subdirektorinya jika ada |

    Berikut ini adalah contoh penggunaan command rmdir pada linux (Rocky Linux 8).

    ![RMDIR](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/rmdir.png)