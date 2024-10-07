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

