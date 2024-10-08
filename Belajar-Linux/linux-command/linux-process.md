# Linux Process

## 6 Oktober 2024

---

## Details

#
Perintah umum untuk menghentikan proses adalah kill dan diikuti dengan PID proses yang akan dihentikan. Perintah ini mengirimkan sinyal ke proses yang ditentukan dengan format:
```
kill -SIGNAL PID
```
- ### Nomor Signal yang sering digunakan
    |Nama Sinyal	|Nomor Sinyal	|Penggunaan Sinyal|
    |-------------|------------|----|
    |SIGNULL	|0	|NULL, periksa akses ke PID|
    |SIGHUP|	1	|Hangup|
    |SIGINT|	2	|Interupsi|
    |SIGQUIT	|3	|Berhenti (Quit)|
    |SIGKILL	|9	|Menghentikan (Kill)|
    |SIGTERM	|15	|Mengakhiri (Terminate)|
    |SIGSTOP	|24	|Berhenti (Stop)|
    |SIGTSTP	|25|	Berhenti/Pause proses|
    |SIGCONT	|26	|Melanjutkan proses yang berhenti|

#
- ### Command killall
    Perintah killall membutuhkan nama proses daripada PID. Perintah ini digunakan untuk menghentikan semua proses dengan nama yang ditentukan di dalam sistem.
    ```
    killall -<nama sinyal atau opsi> <nama proses>
    ```
    Perintah killall bersifat case sensitive, jika ingin membuatnya menjadi non case sensitive, gunakan perintah berikut:
    ```
    killall -I
    ```

#
- ### Command pkill
    Perintah pkill menggunakan nama proses bukan nomor PID. pkill mengirim sinyal ke proses berdasarkan nama, baik nama lengkap maupun sebagian.

    Nama yang ditentukan dalam sebagian nama harus dalam 15 karakter pertama.

    Contoh:

    ```
    pkill -2 sample
    ```

    Sinyal akan dikirim ke semua proses yang memiliki nama "sample".


#
- ### Command xkill
    Perintah xkill digunakan untuk menghentikan proses di server X tanpa perlu tahu nama proses atau PID. Ini akan memaksa server X untuk menghentikan klien-kliennya dengan menggunakan sumber daya X. 

    Gunakan command berikut untuk mendapatkan daftar klien-klien X :
    ```
    xlsclients
    ```

    Selanjutnya jalankan 
    ```
    xkill
    ```
    Lalu klik jendela yang ingin dihentikan dengan kursor berbentuk "x".

#
- ### Command Nohup
    Nohup adalah utilitas Linux yang merupakan singkatan dari "no hang-up." Utilitas ini memungkinkan proses tetap berjalan bahkan setelah keluar dari terminal atau shell. Fungsi utamanya adalah mencegah proses menerima sinyal SIGHUP (Signal hang up) yang biasanya digunakan untuk mengakhiri proses saat keluar dari terminal.

    Perintah nohup dapat digunakan dalam dua cara:
    ```
    nohup <command> <arguments>
    ```
    ```
    nohup <options>
    ```
#
- ### Command at
    Perintah at digunakan untuk menjadwalkan tugas agar dieksekusi satu kali pada waktu tertentu, tanpa perlu mengedit berkas konfigurasi. Ini adalah alternatif untuk penjadwal tugas cron. Berguna jika kita ingin menjalankan proses setelah beberapa waktu, seperti mematikan sistem, membuat cadangan data, mengirim email sebagai pengingat, dan lainnya.

    Perintah at dapat menjalankan perintah atau skrip pada waktu dan tanggal tertentu, atau pada interval waktu yang ditentukan. Waktu dapat ditentukan dalam menit, jam, hari, atau minggu.
    
    **Option tambahan command at**
    |Opsi|	Deskripsi|
    |----|---|
    |-V	|Menampilkan nomor ke kesalahan standar dan keluar dengan sukses.|
    |-q	|Menentukan antrian tugas.|
    |-m	|Mengirim surel ke pengguna saat pekerjaan berhasil dieksekusi.|
    |-M	|Tidak pernah mengirim surel ke pengguna.|
    |-f	|Membaca pekerjaan dari berkas daripada keluaran standar.|
    |-t	|Menentukan waktu menjalankan tugas.|
    |-l	|Alias untuk perintah atq.|
    |-r	|Alias untuk perintah atrm.|
    |-d	|Alias untuk perintah atrm.|
    |-b	|Alias untuk perintah batch.|
    |-v	|Menampilkan waktu tugas sebelum dieksekusi.|
    
    #
    **Cara penggunaan at**

    Install at
    ```
    sudo apt-get install at
    ```
    Memulai dan mengaktifkan layanan
    ```
    systemctl start atd
    systemctl enable atd
    ```
    Menjadwalkan tugas dengan at
    ```
    at 10.20 pm
    sh backup.sh
    ^d
    ```
    Melihat daftar tugas terjadwal
    ```
    atq
    ```
    Menghapus tugas terjadwal
    ```
    atrm 2
    ```
    Melihat konten tugas terjadwal
    ```
    at -c 2
    ```

#
- ### Command Exit
    Perintah exit pada Linux digunakan untuk keluar dari shell saat ini. Perintah ini digunakan untuk mengakhiri skrip shell atau menutup shell itu sendiri.
    - Perintah ini menghentikan skrip shell dengan status keluar N.
    - Status keluar digunakan oleh perintah lain untuk menentukan tindakan mereka.
    - Jika N tidak ditentukan, status keluar adalah status dari perintah terakhir.
    - Nilai N diatur menjadi 0 untuk keluar shell normal.