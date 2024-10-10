# Linux File Hierarchy

## 7 Oktober 2024

---

## Details

#
- Linux Directories
    | Jenis Direktori    | Jenis Berkas yang Disimpan  |
    |----------------|-------------------|
    | Direktori biner    | Berisi berkas kode sumber biner atau dikompilasi, misalnya /bin, /sbin, dll.      |
    | Direktori konfigurasi     | Berisi berkas konfigurasi sistem, misalnya /etc, /boot.              |
    | Direktori data       | Menyimpan berkas data, misalnya /home, /root, dll.           |
    | Direktori memori    | Menyimpan berkas perangkat yang tidak memakan ruang hard disk fisik, misalnya /dev, /proc, /sys. |
    | Usr (Sumber Daya Unix)    | Berisi data yang dapat dibagikan dan hanya dapat dibaca, misalnya /usr/bin, /usr/lib, dll.       |
    | var (direktori variabel)  | Berisi data dengan ukuran yang lebih besar, misalnya /var/log, /var/cache, dll.                  |
    | Direktori non-standar     | Direktori yang tidak termasuk dalam standar FHS, misalnya lost+found, /run, dll.     |

#
- Binary Directories

    File binary adalah file yang berisi kode sumber yang telah dikompilasi (atau kode mesin). FIle ini juga disebut file eksekusi karena bisa dijalankan di komputer. 

    | Direktori   | Deskripsi       |
    |---------------|------------------|
    | /bin    | Berisi binary pengguna, file eksekusi, dan perintah umum yang digunakan oleh semua pengguna.     |
    | /sbin      | Berisi binary sistem yang memerlukan hak akses root untuk tugas pemeliharaan, misalnya fsck, init, ifconfig. |
    | /lib      | Berisi pustaka bersama yang sering digunakan oleh /bin dan /sbin, serta modul kernel.                    |
    | /opt    | Digunakan untuk paket perangkat lunak aplikasi opsional, biasanya aplikasi tambahan dari vendor-individual. |

#
- Configuration Directories

    Direktori konfigurasi berisi berkas-berkas yang telah dikonfigurasi untuk mengatur parameter dan pengaturan awal dari beberapa program komputer.- Linux Directories

    | Direktori      | Deskripsi                |
    |----------------|-------------------------|
    | /boot          | Berisi berkas-berkas boot loader yang penting untuk memulai sistem. Hanya berisi berkas yang diperlukan untuk memulai dasar sistem Linux. |
    | /etc           | Semua berkas konfigurasi terkait mesin disimpan di sini. Berisi hampir segala hal yang terkait dengan konfigurasi sistem.                    |
    |                | Juga berisi skrip shell untuk memulai dan menghentikan program. Semua berkas ini berbasis teks dan statis, tanpa berkas biner.              |
    |                | Berkas-berkas konfigurasi memiliki ekstensi .conf.                                                      |
    | /etc/init.d/   | Berisi skrip untuk mengendalikan sistem atau memulai/menghentikan daemon (proses latar belakang).           |
    | /etc/X11/      | Berkas konfigurasi sistem jendela X disimpan di sini. Berkas konfigurasi tampilan grafis (xorg.conf) juga disimpan di sini.                |
    | /etc/skel/     | Berisi berkas-berkas dasar yang digunakan sebagai kerangka dalam pembuatan pengguna baru.                  |


#
- Data Directories
    | Direktori    | Deskripsi       |
    |--------------|-----------------|
    | /home        | Menyimpan berkas pribadi pengguna. Berisi direktori dengan nama pengguna, misalnya /home/sssit.     |
    |              | Di dalam direktori ini terdapat sub-direktori seperti Desktop, Downloads, Documents, Pictures, dll. |
    | /root        | Direktori home untuk pengguna root.                                                                   |
    | /srv         | Berisi data spesifik server untuk layanan yang diberikan oleh sistem, seperti www, cvs, rsync, ftp. |
    | /media       | Titik mount untuk perangkat media yang dapat dilepas, seperti CD-ROM, floppy, perangkat USB, dll.    |
    | /mnt         | Direktori kosong untuk mount sementara filesystem.                                                    |
    | /tmp         | Tempat penyimpanan sementara yang akan dihapus saat sistem direstart. Bukan tempat untuk data penting. |

#
- Memory Directories
    | Direktori  | Deskripsi                       |
    |------------|-----------------------|
    | /dev       | Berisi berkas-berkas yang mewakili dan mengakses perangkat, termasuk perangkat terminal dan virtual.              |
    |            | Misalnya, '/dev/tty' mewakili antarmuka baris perintah, '/dev/null' adalah "lubang hitam" untuk membuang keluaran. |
    | /proc      | Berisi informasi proses dan sumber daya sistem dalam format pseudo filesystem.                                |
    |            | Ini merupakan cara untuk melihat kernel dan berkomunikasi langsung dengan kernel.                             |
    | /sys       | Berisi informasi kernel tentang perangkat keras dan digunakan untuk konfigurasi plug-and-play.                 |

#
- Usr Directory
    | Direktori     | Deskripsi         |
    |---------------|----------------|
    | /usr          | Berisi biner, pustaka, dokumentasi, dan sumber daya aplikasi pengguna, sebagai data baca saja.     |
    | /usr/bin      | Berisi berkas biner non-utama untuk semua pengguna.                                               |
    | /usr/include  | Berisi berkas-berkas inklusi standar untuk C.                                                     |
    | /usr/lib      | Berisi pustaka yang tidak dieksekusi langsung oleh pengguna.                                       |
    | /usr/share    | Berisi data yang tidak bergantung pada arsitektur (bersamaan) dan dapat dibagikan.                 |
    | /usr/local    | Digunakan untuk menginstal perangkat lunak secara lokal. Semua program pengguna akan terinstal di sini. |
    | /usr/src      | Digunakan untuk menyimpan kode sumber, seperti kode sumber kernel dengan file header-nya.       |



#
- Var Directory
    | Direktori     | Deskripsi               |
    |---------------|----------------|
    | /var          | Berisi berkas yang memiliki ukuran yang bervariasi dan kontennya diharapkan berubah terus menerus, seperti berkas log, spool, dan cache. |
    | /var/log      | Berisi semua berkas log.                                                                             |
    | /var/cache    | Menyimpan data cache aplikasi yang dihasilkan secara lokal.                                         |
    | /var/spool    | Digunakan untuk mengantri berkas yang menunggu diproses, seperti antrean cetak dan antrean email. |
    | /var/lib      | Menyimpan berkas yang berisi informasi status seperti basis data. Konten berkas berubah saat program berjalan. |

#
- Non-standard Directories
    | Direktori       | Deskripsi             |
    |-------------|------------|
    | /cdrom          | Direktori '/cdrom' tidak ada dalam standar FHS, namun cdrom dapat dipasang di direktori ini.  Idealnya, sesuai standar FHS, cdrom seharusnya dipasang di bawah '/media'.                            |
    | /run            | Direktori '/run' menyimpan data variabel saat runtime. Data ini mencakup informasi tentang sistem yang sedang berjalan sejak boot terakhir, seperti daemon yang berjalan.                                   |
    | /lost + found   | Selama crash sistem atau situasi lain di mana pemeriksa sistem berkas Linux (fsck) memulihkan data yang hilang, data tersebut disimpan di direktori ini. Data mungkin dalam kondisi baik atau buruk.      |
