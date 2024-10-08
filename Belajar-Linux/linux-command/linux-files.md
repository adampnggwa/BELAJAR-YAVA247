# Linux Files

## 3 Oktober 2024

---

## Details

#
- Jenis-jenis berkas di Linux:
    | Jenis Berkas      | Deskripsi    
    |-------------------|----|
    | Berkas Biasa (-)   | Berisi data teks atau program yang dapat dijalankan.        |
    | Berkas Direktori (d) | Mengandung daftar berkas dan direktori.                     |
    | Berkas Blok (b)    | Mewakili perangkat blok (misalnya, hard disk).              |
    | Berkas Perangkat Karakter (c) | Mewakili perangkat karakter (seperti perangkat serial).  |
    | Berkas Named Pipe (p) | Digunakan untuk komunikasi antar proses.                |
    | Berkas Tautan Simbolik (l) | Rujukan ke berkas atau direktori lain.                |
    | Berkas Soket (s)   | Digunakan untuk komunikasi antar proses melalui jaringan.   |

    Berikut ini adalah contoh berkas biasa '-' pada linux (Rocky Linux 8).

    ![berkas](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/berkas1.png)

    Berikut ini adalah contoh berkas direktori 'd' pada linux (Rocky Linux 8).

    ![berkas](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/berkas2.png)

    Berikut ini adalah contoh berkas blok 'b' pada linux (Rocky Linux 8).

    ![berkas](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/berkas3.png)

    Berikut ini adalah contoh berkas perangkat karakter 'c' pada linux (Rocky Linux 8).

    ![berkas](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/berkas4.png)

    Berikut ini adalah contoh berkas named pipe 'p' pada linux (Rocky Linux 8).

    ![berkas](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/berkas4,5.png)

    Berikut ini adalah contoh berkas tautan symbolic 'l' pada linux (Rocky Linux 8).

    ![berkas](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/berkas5.png)

    Berikut ini adalah contoh berkas soket 's' pada linux (Rocky Linux 8).

    ![berkas](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/berkas6.png)

#
- Directory Structure
    | Jenis       | Deskripsi    
    |-------------------|----|
    | /(root) | Direktori tingkat atas. Isi untuk booting sebelum sistem berkas lainnya dipasang. |
    | /boot | Kernel statis, konfigurasi bootloader, dan berkas eksekusi untuk memulai Linux. |
    | /bin | Berkas eksekusi pengguna. |
    | /dev | Berkas perangkat untuk perangkat keras. |
    | /etc | Konfigurasi sistem lokal. |
    | /lib | Pustaka bersama untuk memulai sistem. |
    | /home | Penyimpanan berkas pengguna. |
    | /mnt | Titik pasang sementara. |
    | /media | Tempat perangkat media eksternal. |
    | /opt | Berkas opsional, program aplikasi. |
    | /root | Direktori rumah pengguna root. |
    | /tmp | Direktori sementara untuk berkas sementara. |
    | /sbin | Berkas biner sistem untuk administrasi. |
    | /usr | Berkas baca-saja dan dibagikan, pustaka, berkas biner, dan dokumentasi. |
    | /var | Berkas data variabel seperti log, basis data, dll. |

    Berikut ini adalah contoh direktori /(root) pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file1.png)

    Berikut ini adalah contoh direktori /boot pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file2.png)

    Berikut ini adalah contoh direktori /bin pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file3.png)

    Berikut ini adalah contoh direktori /dev pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file4.png)

    Berikut ini adalah contoh direktori /etc pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file5.png)

    Berikut ini adalah contoh direktori /lib pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file6.png)

    Berikut ini adalah contoh direktori /home pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file7.png)

    Berikut ini adalah contoh direktori /mnt pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file8.png)

    Berikut ini adalah contoh direktori /media pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file9.png)

    Berikut ini adalah contoh direktori /opt pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file10.png)

    Berikut ini adalah contoh direktori /root pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file11.png)

    Berikut ini adalah contoh direktori /tmp pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file12.png)

    Berikut ini adalah contoh direktori /sbin pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file13.png)

    Berikut ini adalah contoh direktori /usr pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file14.png)

    Berikut ini adalah contoh direktori /var pada linux (Rocky Linux 8).

    ![DS](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/file15.png)

#
- Types of Linux File System
    | Jenis       | Deskripsi    
    |-------------------|----|
    | Ext | Extended File System (Ext) adalah sistem berkas lama yang dikembangkan untuk MINIX OS |
    | Ext2 | Sistem berkas pertama yang bisa mengelola dua terabyte data. |
    | Ext3 | Pengembangan dari Ext2 dengan kompatibilitas ke belakang, namun tidak mendukung pemulihan berkas dan snapshot disk. |
    | Ext4 | Sistem berkas paling cepat, cocok untuk SSD, dan default di distribusi Linux. |
    | JFS | Journaled File System dari IBM untuk AIX Unix, alternatif untuk Ext, cocok untuk stabilitas dengan sumber daya terbatas. |
    | ReiserFS | Alternatif untuk Ext3 dengan performa lebih baik dan fitur canggih. |
    | XFS | Sistem berkas berkecepatan tinggi untuk I/O paralel, digunakan oleh NASA untuk penyimpanan besar. |
    | Btrfs | B tree file system dengan toleransi kesalahan dan konfigurasi penyimpanan ekstensif, tidak cocok untuk produksi. |
    | Swap | Digunakan untuk paging memori saat hibernasi, ruang swap setara RAM diperlukan jika tidak dihibernasi. |

    Berikut ini adalah untuk cek file sistem yang terpasang menggunakan command df -T pada linux (Rocky Linux 8).

    ![berkas](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/fs1.png)


#
- Linux File Command
    | Command   | Fungsi |
    |--------|------|
    | file | Menentukan jenis berkas|
    |   touch  |  Untuk membuat berkas |
    | rm|   Untuk menghapus berkas |
    | cp |  Untuk menyalin berkas |
    | mv|   Untuk memindahkan berkas |
    | rename|   Untuk mengubah nama berkas |

    Berikut ini adalah contoh penggunaan command file pada linux (Rocky Linux 8).

    ![cm](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/cm1.png)

    Berikut ini adalah contoh penggunaan command touch pada linux (Rocky Linux 8).

    ![cm](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/cm2.png)

    Berikut ini adalah contoh penggunaan command rm pada linux (Rocky Linux 8).

    ![cm](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/cm3.png)

    Berikut ini adalah contoh penggunaan command cp pada linux (Rocky Linux 8).

    ![cm](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/cm4.png)

    Berikut ini adalah contoh penggunaan command cp -r pada linux (Rocky Linux 8).

    ![cm](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/cm4,5.png)

    Berikut ini adalah contoh penggunaan command mv pada linux (Rocky Linux 8).

    ![cm](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/cm5.png)

    Berikut ini adalah contoh penggunaan command rename pada linux (Rocky Linux 8).

    ![cm](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/command%20linux/cm6.png)