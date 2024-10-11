# Linux Filters

## 10 Oktober 2024

---

## Details

#

- ### Command cat
    Ketika perintah "cat" digunakan dalam pipa (pipes), ia tidak melakukan apa pun kecuali memindahkan stdin ke stdout.
    ```
    cat weeks.txt | tac | cat | cat | tac
    ```
    Dalam contoh ini, Hasil dari satu perintah 'cat' atau 'tac' diteruskan sebagai masukan ke perintah berikutnya.
#
- ### Command cut
    Perintah cut digunakan untuk memotong dan menampilkan bagian tertentu dari baris berkas. 
    | Perintah | Deskripsi |
    |----------|-----------|
    | cut -b, --bytes=LIST | Memotong berdasarkan posisi byte. |
    | cut -c, --characters=LIST | Memotong berdasarkan karakter atau posisi karakter. |
    | cut -d, --delimiter=DELIM | Memotong berdasarkan delimiter yang ditentukan. |
    | cut -f, --fields=LIST | Memotong berdasarkan field yang ditentukan. |
    | cut -n | Mengabaikan opsi lain. |
    | cut --complement | Memotong dengan pola komplement. |
    | cut -s, --only-delimited | Hanya menampilkan baris dengan delimiter. |
    | cut --output-delimiter=STRING | Menggunakan STRING sebagai delimiter output. |
    | cut -z, --zero-terminated | Menggunakan NUL sebagai delimiter baris. |
    | cut --help | Menampilkan bantuan manual. |
    | cut --version | Menampilkan informasi versi. |


#
- ### Command grep
    Perintah grep digunakan untuk mencari baris dalam berkas yang cocok dengan pola atau kata kunci yang diberikan.
    | Perintah          | Fungsi                  |
    |-----------------------|--------------------|
    | grep [searchWord] [fileName]              | Mencari baris dalam berkas yang mengandung [searchWord].                                        |
    | grep -v [searchWord] [fileName]           | Menampilkan baris-baris yang tidak mengandung [searchWord].                                      |
    | grep -i [searchWord] [fileName]           | Mencari baris-baris yang mengandung [searchWord] tanpa memperdulikan besar kecilnya huruf.       |
    | grep -A[lineNumber] [searchWord] [fileName] | Menampilkan baris sesudah hasil pencarian dalam jumlah yang ditentukan.                         |
    | grep -B[lineNumber] [searchWord] [fileName] | Menampilkan baris sebelum hasil pencarian dalam jumlah yang ditentukan.                         |
    | grep -C[lineNumber] [searchWord] [fileName] | Menampilkan baris sebelum dan sesudah hasil pencarian dalam jumlah yang ditentukan.              |
    | grep -E [regexPattern] [fileName]         | Mencari baris-baris yang cocok dengan pola ekspresi reguler.                                     |
    | grep -n [searchWord] [fileName]           | Menampilkan nomor baris untuk setiap hasil pencarian.                                            |
    | grep -r [searchWord] [folderPath]         | Mencari pola dalam semua berkas di dalam folder dan subfolder.                                   |
    | grep -l [searchWord] *                    | Mencari berkas yang mengandung [searchWord] dalam direktori saat ini.                            |
    | grep -c [searchWord] [fileName]           | Menampilkan jumlah baris yang mengandung [searchWord].                                            |
    | grep [searchWord] -e [startLine] -e [endLine] [fileName] | Mencari [searchWord] dalam rentang baris yang ditentukan.                              |
    | grep -f [patternFile] [fileName]          | Mencari baris-baris yang cocok dengan pola dalam berkas eksternal [patternFile].                 |


#
- ### Command comm:
    Perintah comm digunakan untuk membandingkan dua berkas yang telah diurutkan. Ini menunjukkan baris yang ada di kedua berkas, baris yang hanya ada di berkas pertama, dan baris yang hanya ada di berkas kedua. Contoh :
    ```
    comm berkas1.txt berkas2.txt
    ``` 
#
- ### Command sed
    Perintah sed digunakan sebagai editor aliran teks untuk melakukan manipulasi teks dalam berkas.
    ```
    sed 's/kata-lama/kata-baru/g' berkas.txt
    ```
    Dalam contoh ini, perintah akan mengganti semua "kata-lama" dengan "kata-baru" dalam berkas "berkas.txt".

#
- ### Command tee
    Perintah tee membaca input dari pipa dan menyalurkannya ke output serta berkas
    ```
    cat berkas.txt | tee berkas_baru.txt
    ```
    Dalam contoh ini, isi berkas "berkas.txt" akan ditampilkan di layar dan juga disimpan dalam "berkas_baru.txt".
#
- ### Command tr
    Perintah tr digunakan untuk mengganti karakter dalam berkas
    ```
    tr 'a-z' 'A-Z' < berkas.txt
    ```
    Dalam contoh ini, perintah akan mengubah huruf kecil menjadi huruf besar dalam berkas "berkas.txt".

#
- ### Command uniq
    Perintah uniq digunakan untuk menghapus baris berulang berdekatan dalam berkas dan menampilkan baris unik.
    | Perintah                | Fungsi              |
    |------------|---------------|
    | sort dupli.txt \| uniq                        | Menghapus baris yang berulang dari 'dupli.txt' dan menuliskannya ke stdout.                |
    | sort dupli.txt \| uniq -c                     | Menghitung berapa kali kata muncul dalam 'dupli.txt' dan menuliskannya ke stdout.            |
    | sort dupli.txt \| uniq -d                     | Menampilkan baris yang berulang dari 'dupli.txt' dan menuliskannya ke stdout.               |
    | sort dupli.txt \| uniq -u                     | Menampilkan baris unik (tidak berulang) dari 'dupli.txt' dan menuliskannya ke stdout.        |
    | sort dupli.txt \| uniq -s 2                   | Mengabaikan 2 karakter pertama dalam perbandingan dan menuliskannya ke stdout.                |
    | uniq -f 2 dupli2.txt                          | Mengabaikan 2 kolom pertama dalam perbandingan dan menuliskannya ke stdout.                   |


#
- ### Command wc
    Perintah wc digunakan untuk menghitung jumlah baris, kata, dan karakter dalam berkas.
    | Perintah                            | Fungsi   |
    |------------|----|
    | wc exm.txt                          | Menampilkan jumlah baris, kata, karakter, dan bytes dari file 'exm.txt'.  |
    | wc exm.txt marks.txt                | Menampilkan informasi jumlah kata, karakter, dan bytes dari kedua file.   |
    | wc -l exm.txt                       | Menampilkan jumlah baris dari file 'exm.txt'.                            |
    | wc -m exm.txt                       | Menampilkan jumlah karakter dari file 'exm.txt'.                         |
    | wc -c exm.txt                       | Menampilkan jumlah bytes dari file 'exm.txt'.                            |
    | wc -w exm.txt                       | Menampilkan jumlah kata dari file 'exm.txt'.                             |
    | wc -L exm.txt                       | Menampilkan panjang baris terpanjang dari file 'exm.txt'.                |

#
- ### Command od
    Perintah od digunakan untuk mengonversi berkas biner ke bentuk oktal atau heksadesimal, memberikan tampilan dalam kode karakter
    | Perintah              | Fungsi        |
    |-------------|----|
    | od -b format.txt                  | Menampilkan isi file dalam format oktal.                                |
    | od -t x1 format.txt               | Menampilkan isi file dalam format heksadesimal untuk setiap byte.       |
    | od -c format.txt                  | Menampilkan isi file dalam format karakter ASCII dengan \n untuk baris baru. |

#
- ### Command sort
    Perintah sort digunakan untuk mengurutkan baris dalam berkas secara alfanumerik atau berdasarkan kriteria tertentu
    | Perintah                           | Fungsi                                                          |
    |------------------|-----------------|
    | sort [namaFile]                    | Mengurutkan konten file secara alfabetis.                       |
    | sort -k[nomorKolom] [namaFile]     | Mengurutkan kolom tertentu menggunakan nomor kolom yang ditentukan. |
    | sort -n -k[nomorKolom] [namaFile]  | Mengurutkan kolom tertentu secara numerik dengan nomor kolom yang ditentukan. |

#
- ### Command gzip
    Perintah gzip digunakan untuk mengompresi berkas menggunakan algoritma kompresi gzip, menghasilkan berkas dengan ekstensi ".gz"
    ```
    gzip berkas.txt
    ```
    Dalam contoh ini, berkas "berkas.txt" akan dikompresi menjadi "berkas.txt.gz".