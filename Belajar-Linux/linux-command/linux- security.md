# File Security

## 12 Oktober 2024

---

## Details

#
- ### File Ownership
    | Jenis Ownership  | Deskripsi               |
    | ---------------- | ---------------- |
    | `User`                  | User adalah orang yang membuat berkas. Secara default, siapa pun yang membuat berkas menjadi user     | pemilik berkas tersebut. Seorang pengguna dapat membuat, menghapus, atau mengubah berkas.           |
    | `Group`                  | Sebuah grup dapat berisi beberapa pengguna. Semua pengguna yang termasuk dalam suatu grup memiliki izin akses yang sama untuk berkas.    |
    | `Other`                  | Siapa pun yang memiliki akses ke berkas selain pengguna dan grup masuk dalam kategori lainnya. Other tidak membuat berkas dan bukan anggota grup.     |

    #
    User dan grup dapat dikelola secara lokal di /etc/passwd atau /etc/group. Contoh penggunaan command dalam file ownership
    | Command                                          | Deskripsi                                                           |
    | ------------------------------------------------ | ------------------------------------------------------------------- |
    | `ls -lh`                                         | Menampilkan informasi kepemilikan file.                             |
    | `chgrp <grupBaru> <namaFile>`                   | Mengganti grup pemilik berkas.                                     |
    | `chown <pemilikBaru> <namaFile>`                 | Mengganti pemilik berkas.                                          |
    | `chown <pemilikBaru:grupBaru> <namaFile>`       | Mengganti pemilik pengguna dan grup berkas.                        |

#
- ### Linux chgrp Command | Linux Change Group
    Command chgrp digunakan untuk mengubah kepemilikan grup dari suatu berkas atau direktori. 

    Syntax
    ```
    chgrp [OPTION]... GROUP FILE...
    chgrp [OPTION]... --reference=RFILE FILE...
    ```

    | Option                  | Deskripsi                      |
    | ----------------------- | --------------- |
    | `-c, --changes`         | Melaporkan perubahan hanya ketika perubahan dilakukan.          |
    | `-f, --silent, --quiet` | Menekan sebagian besar pesan kesalahan.                          |
    | `-v, --verbose`         | Menampilkan informasi diagnostik untuk setiap berkas yang diproses. |
    | `--dereference`         | Mempengaruhi signifikansi setiap tautan simbolik, bukan tautan itu sendiri. |
    | `-h, --no-dereference`  | Mengubah tautan simbolik daripada berkas yang dirujuk.          |
    | `--no-preserve-root`    | Tidak memperlakukan '/' secara khusus.                           |
    | `--preserve-root`       | Mengoperasikan secara rekursif pada '/.' setelah perintah default gagal. |
    | `--reference=RFILE`     | Menggunakan grup dari RFILE sebagai referensi.                   |
    | `-R, --recursive`       | Beroperasi secara rekursif pada berkas dan direktori.            |
    | `-H`                    | Menelusuri tautan simbolik ke direktori.                         |
    | `-L`                    | Menelusuri setiap tautan simbolik ke direktori yang ditemui.     |
    | `-P`                    | Tidak menelusuri tautan simbolik.                                |
    | `--help`                | Menampilkan panduan bantuan tentang opsi yang didukung.           |
    | `--version`             | Menampilkan informasi versi.                                      |

#
- ### File Permission
    | Permission | Pada Berkas               | Pada Direktori               |
    |------------|---------------------------|-----------------------------|
    | `r (read)` | Membaca isi berkas (`cat`) | Membaca isi direktori (`ls`) |
    | `w (write)`| Mengubah isi berkas (`vi`) | Membuat berkas dalam direktori (`touch`) |
    | `x (execute)`| Menjalankan berkas       | Masuk ke direktori (`cd`)   |
    #
    ### Permission Set dengan chmod
    | Command                    | Deskripsi                           |
    | -------------------- | -------------------------------- |
    | `chmod <groupName>+<permissionName> <fileName>` | Menambahkan izin kepada grup pada berkas.                                                               |
    | `chmod <groupName>-<permissionName> <fileName>` | Menghapus izin dari grup pada berkas.                                                                 |
    | `chmod a+<permissionName> <fileName>`          | Menambahkan izin kepada semua grup pada berkas.                                                          |
    | `chmod +<permissionName> <fileName>`            | Menambahkan izin kepada semua grup tanpa mengetik nama grup.                                               |
    | `chmod <groupName>=<permissions> <fileName>`    | Mengatur izin eksplisit pada grup pada berkas.                                                           |
    | `chmod <groupName>=<permissions> <fileName>`    | Mengatur izin eksplisit pada grup pada berkas.                                                           |
    | `chmod u=rwx,g=rw,o=r file`                    | Mengatur izin eksplisit pada berbagai grup pada berkas.                                                   |
    | `mkdir -m <mode> <fileName>`                    | Membuat direktori dengan mode izin yang ditentukan.                                                      |
    | `cp -p <sourceFile> <destinationFile>`          | Menyalin berkas sumber ke berkas tujuan dengan mempertahankan izin dan stempel waktu dari berkas sumber. |

#
- ### Command chmod
    Perintah chmod digunakan untuk mengubah izin (permissions) dari berkas atau direktori. Izin ini mengontrol akses pengguna terhadap berkas atau direktori, termasuk hak membaca, menulis, dan mengeksekusi.
    
    Syntax
    ```
    chmod [OPTION]... MODE FILE
    ```
    | Option                       | Deskripsi   |
    | -------------------- | ----- |
    | `-c, --changes`           | Menampilkan perubahan izin yang terjadi.                                 |
    | `-f, --silent, --quiet`   | Mengabaikan pesan kesalahan kecuali pesan yang kritis.                   |
    | `-v, --verbose`           | Menampilkan pesan detail tentang setiap berkas yang diubah.              |
    | `--reference=RFILE`       | Menggunakan izin dari berkas referensi RFILE untuk diterapkan pada berkas lainnya. |
    | `-R, --recursive`         | Mengubah izin secara rekursif pada seluruh berkas dan direktori di bawahnya. |
    #
    | Contoh Penggunaan             | Deskripsi    |
    | --------------------------- | --------------------------- |
    | `chmod u+x file.txt`                              | Menambah izin eksekusi untuk pengguna pada berkas 'file.txt'.              |
    | `chmod g-w file.txt`                              | Menghapus izin tulis untuk grup pada berkas 'file.txt'.                    |
    | `chmod u=rwx,g=rx,o=r file.txt`                   | Memberikan izin baca, tulis, dan eksekusi kepada pengguna, izin baca dan eksekusi kepada grup, serta izin baca kepada lainnya pada berkas 'file.txt'. |
    | `chmod 755 file.txt`                              | Menggunakan notasi oktal untuk mengubah izin menjadi 755 (rwxr-xr-x) untuk pengguna, grup, dan lainnya pada berkas 'file.txt'. |
    | `chmod -R 644 directory/`                         | Mengubah izin rekursif pada direktori 'directory' dan seluruh berkas di dalamnya menjadi 644. |

#
- ### Command chown
    Perintah chown di Linux digunakan untuk mengubah kepemilikan file, direktori, atau tautan simbolik untuk pengguna atau grup.

    Syntax 
    ```
    chown [OPTION]... [PEMILIK][:[GRUP]] BERKAS...
    ```
    | Option              | Deskripsi                                                        |
    | ----------------- | ---------------------------------------------------------------- |
    | `-c`              | Menampilkan keluaran terperinci saat terjadi perubahan.         |
    | `-f`              | Menekan pesan kesalahan.                                       |
    | `-v`              | Menampilkan informasi diagnostik untuk setiap file yang diproses. |
    | `--dereference`   | Memengaruhi referensi dari setiap tautan simbolik.             |
    | `-h`              | Memengaruhi tautan simbolik daripada file yang dirujuk.        |
    | `--from=PEMILIK_SEKARANG:GRUP_SEKARANG` | Mengubah pemilik dan grup tertentu. |
    | `--no-preserve-root` | Tidak memperlakukan karakter backslash ('/') secara khusus. |
    | `--preserve-root` | Menggunakan karakter backslash ('/') saat gagal beroperasi secara rekursif. |
    | `-R`              | Melakukan operasi secara rekursif pada berkas dan direktori.    |
    | `--help`          | Menampilkan panduan bantuan mengenai penggunaan dan opsi.      |
    | `--version`       | Menampilkan informasi versi.                                  |

    # 
    ### Contoh penggunaan
    | Command                               | Deskripsi                                                      |
    | ------------------------------------- | -------------------------------------------------------------- |
    | `sudo chown <nama_pengguna> <nama_berkas>` | Mengganti pemilik berkas dengan nama pengguna.            |
    | `sudo chown <UID> <nama_berkas>`       | Mengganti pemilik berkas berdasarkan UID.                 |
    | `sudo chown :<nama_grup> <nama_berkas>` | Mengganti grup dari sebuah berkas.                       |
    | `sudo chown <Nama_pengguna/UID>:<Nama_grup/GID> <Nama_berkas>` | Mengganti nama pengguna dan grup bersamaan. |
#
- ### Advanced File Permission
    Advanced File Permission memungkinkan pengguna untuk mengontrol lebih banyak aspek dari kepemilikan dan akses berkas dan direktori.
    #
    ### Sticky Bit on Directory
    Sticky bit digunakan pada direktori untuk melindungi berkas dari penghapusan oleh pengguna lain yang bukan pemiliknya. Ini diindikasikan di lokasi yang sama dengan izin x untuk pengguna lain.
    
    Contoh 
    ```
    chmod +t new1
    ```
    Dalam contoh di atas, izin untuk berkas "new1" diubah menjadi t di tempat izin x untuk pengguna lain.

    #
    ### Setgid Bit on Directory
    Setgid digunakan untuk memastikan bahwa semua berkas dalam direktori dimiliki oleh pemilik grup dari direktori tersebut. Ini ditampilkan di lokasi yang sama dengan izin x untuk grup.
    Contoh
    ```
    chmod g+s new1
    ```
    Dalam contoh di atas, pemilik grup diubah menjadi "neww" untuk direktori "new1". Izin grup diubah menjadi s di tempat izin x untuk grup. Anda dapat melihat bahwa berkas "file1" yang berada di dalam direktori "new1" memiliki nama grup "neww".
    #
    ### Setgid dan Setuid pada Berkas Biasa
    Dengan bantuan izin ini, berkas yang dapat dijalankan diakses dengan izin pemilik berkas daripada pemilik yang menjalankan. Ini berarti jika suatu program dimiliki oleh pengguna root dan izin setuid diaktifkan, maka pengguna akan menjalankan program tersebut sebagai root. 

    Contoh
    ```
    chmod +s example_program
    ```
    Dalam contoh di atas, izin setuid diaktifkan pada berkas "example_program". Jika berkas ini dimiliki oleh root dan dijalankan oleh pengguna lain, program tersebut akan dijalankan dengan hak akses root.
#
- ### Linux File Links
    Terdapat dua jenis tautan yang digunakan untuk menghubungkan antara nama file dan data aktual di ruang disk. Tautan memungkinkan beberapa nama file merujuk pada data yang sama.

    ### Hard Links:
    - Hard link adalah tautan tingkat rendah yang menghubungkan lebih dari satu nama file dengan Inode yang sama.
    - Hard link menghubungkan langsung ke Inode file asli di ruang disk, tanpa menciptakan Inode baru.
    - Direktori tidak dapat dibuat dengan hard link, dan hard link tidak dapat melintasi batas sistem file.
    - Ketika file sumber dihapus atau dipindahkan, hard link tidak terpengaruh.
    - Inode adalah struktur data yang menyimpan informasi dasar tentang file, seperti permission, owner, dan timestamp.
    #
    ### Soft Links (Symbolic Links):
    - Soft link adalah tautan yang mewakili lokasi virtual atau abstrak dari file. Mirip dengan pintasan yang dibuat di Windows.
    - Soft link tidak berisi informasi atau konten dari file yang dihubungkan, melainkan memiliki pointer ke lokasi file yang dihubungkan.
    - Soft link menciptakan Inode baru dengan pointer ke lokasi Inode file asli.
    - Soft link digunakan untuk membuat tautan antara direktori dan dapat melintasi batas sistem file.
    - Ketika file sumber dihapus atau dipindahkan, soft link tidak diperbarui.
    #
    ### Linux Inode
    Inode adalah struktur data yang berisi metadata tentang file. Setiap Inode memiliki nomor unik, dan nomor Inode dapat dilihat dengan bantuan perintah :
    ```
    ls -li
    ```
    Berikut adalah konten yang disimpan dalam Inode untuk sebuah file:

    - User ID file
    - Group ID file
    - Device ID
    - Ukuran file
    - Tanggal pembuatan
    - Izin (permissions)
    - Pemilik file
    - Flag perlindungan file
    - Penghitung tautan untuk menentukan jumlah hard link
    #
    Membuat Hard link
    ```
    ln source_file hard_link_name
    ```

    Membuat Soft Link
    ```
    ln -s source_file soft_link_name
    ```
    Menghapus tautan
    ```
    rm link_name
    ```
