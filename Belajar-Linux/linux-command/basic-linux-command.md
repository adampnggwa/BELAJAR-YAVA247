# Basic Linux Command

## 3 Oktober 2024

---

## Details

1. **Konsep dasar file Linux**

    - Strucktur directory

        ‘/' root directory
        ‘/home’ directory home untuk user
        ‘/etc’ directory configurasi system
        ‘/var’ directory untuk file yang sering berubah
        ‘/user’ direktory untuk file aplikasi yang di bagikan
        '/bin’ direktory untuk biner

2. **Konsep dasar Navigasi**

    - ‘pwd’ (print working directory) untuk mengecheck directory saat ini
    - 'ls' (list) untuk menampilkan isi 
    - 'ls -l' menampilkan dalam format panjang
    - 'ls -a' menampilkan semua file termasuk yang ter hidden
    - 'ls -la' gabungan dari 2 di atas
    - 'cd' Change Directory
    - ‘lsblk’ list block device

3. **Perintah manipulasi file dan directory**

    - 'touch' Create empty file
    - 'mkdir' create new directory
    - ‘rm’ remove
    - ‘cp’ copy
    - ‘mv’ move

4. **Command lain lain**

    - ‘cat’ menampilkan isi file
    - ‘less’ Menampilkan isi file satu halaman pada satu waktu.
    - ‘head’ menampilkan baris pertama dari file
    - ‘tail’ Menampilkan baris terakhir dari file
    - ‘nano’ teks editor sederhana dan gampang di pake
    - ‘vim’ teks editor yang lebih komplit

        1. mencoba menulis
        2. mengcopy baris
        3. menghapus baris
        4. menyimpan file

5.  **Hak akses RWX**

    - r (read)
    - w (write)
    - x (execute)

6. **Kategori Hak akses**

    - Owener pemilik
    - Group Grup yang file-nya dimiliki
    - Others Pengguna lain yang tidak termasuk dalam grup

7. **Cara Melihat hak akses**

    - ‘ls -l nama_file.txt’
    - contoh output
    
        ‘-rw-r--r-- 1 user group 4096 Jun  6 10:00 nama_file.txt’

    - penjelasan

        1. -rw-r--r-- menunjukkan hak akses
        2. rw- menunjukan hak owner ‘read dan write’
        3. r-- menunjukan hak grup ‘read’
        4. r-- menunjukan hak other ‘read’

8. **Cara mengubah hak akses**

    - menambah hak akses (+)

        1. chmod u+x nama_file.txt  # Menambahkan hak eksekusi untuk pemilik.
        2. chmod g+w nama_file.txt  # Menambahkan hak tulis untuk grup.
        3. chmod o+r nama_file.txt  # Menambahkan hak baca untuk pengguna lain.

    - menghapus hak akses (-)

        1. chmod u-x nama_file.txt  # Menghapus hak eksekusi untuk pemilik.
        2. chmod g-w nama_file.txt  # Menghapus hak tulis untuk grup.
        3. chmod o-r nama_file.txt  # Menghapus hak baca untuk pengguna lain.

    - Format oktal (gantinya RWX tapi pake angka)

        - 4 = read (r)
        - 2 = write (w)
        - 1 = execute (x)

            - contoh menggunakannya untuk membuat format (-rw-r--r--)

                1. chmod 644 nama_file.txt

            - atau mau membuat format (-rwx-xr-x)

                1. chmod 755 nama_file.txt

9. **Mengubah pemilik dan grup (chown)**

    - Mengubah Pemilik

        1. chown user nama_file.txt

    - mengubah grup

        1. chown :group nama_file.txt

    - mengubah pemilik dan grup

        1. chown user:group nama_file.txt

10. **Management Sistem dan Penggunaan packet**

    - Managemen pengguna dan grup

       - managemen pengguna (useradd)

            'sudo useradd nama_user' (membuat user)
            ‘sudo passwd nama_user’ (set password)
            ‘sudo userdel nama_user’ (menghapus user)
            ‘sudo userdel -r nama_user’ (menghapus beserta direktori user)
            ‘sudo passwd nama_user’ (menganti password)

        - Managemen Group (groupadd)

            ‘sudo groupadd nama-grup’ (membuat grup)
            ‘sudo groupdel nama_grup’ (menghapus grup)
            ‘sudo usermod -aG nama_grup nama_user’ (memasukan user ke grup)

        - Management Packet dengan dnf untuk (fedora, CentOS,Rocky)

            ‘sudo dnf install nama_packet’ (untuk install packet)
            ‘sudo dnf remove nama_packet’ (untuk menghapus packet)
            ‘sudo dnf update’ (untuk update packet yang sudah terinstall)
            ‘sudo dnf search nama_packet’ (mencari packet yang sudah terinstall)

    - Layanan system dan Log (systemctl dan journalctl)

        - Layanan system (systemctl)

            ‘sudo systemctl start nama_layanan’ (memulai layanan)
            ‘sudo systemctl stop nama_layanan’ (menghentikan layanan)
            ‘sudo systemctl restart nama_layanan’ (merestart layanan)
            ‘sudo systemctl enable nama_layanan’ (untuk membuat layanan berjalan otomatis seteleh boot)
            ‘sudo systemctl disable nama_layanan’ (untuk menonaktifkan)

        - Log System

            'journalctl' (untuk melihat log system)
            ‘journalctl -b’ (untuk melihat log boot terakhir)

                - bisanya log di simpan di /var/log
                - untuk melihat isi log bisa menggunakan perintak(cat,less,tail) - - - contoh

                    1. cat /var/log/syslog
                    2. less /var/log/syslog
                    3. tail /var/log/syslog