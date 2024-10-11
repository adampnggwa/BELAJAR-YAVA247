# Linux Awk Command

## 11 Oktober 2024

---

## Details

#
Awk adalah sebuah bahasa pemrograman seperti pada shell atau C yang memiliki karakteristik yaitu sebagai tool yang cocok untuk filter dan manipulasi file teks. 

Fungsi dasar awk adalah untuk mencari pola pada file per baris (atau unit teks lain) yang berisi pola tertentu. Ketika suatu baris sesuai dengan pola, awk melakukan aksi yang khusus pada baris tersebut. Awk tetap memproses baris input sedemikian hingga mencapai akhir baris input. 

Sebuah instruksi memuat pola yang diikuti oleh aksi. Aksi
tersebut diapit oleh kurung kurawal untuk memisahkannya dari pola. Akhir baris biasanya memisah instruksi. Untuk itu, program awk terlihat seperti ini:
```
condition {action}
condition {action}
```

Berikut adalah Contoh Awk Command pada file **student.txt** yang mengandung isi sebagai berikut
``````
Sam CS  
Daniel IT  
John IT  
Arya IT  
Mike ECE  
Helena ECE  
``````
- ### Contoh 1 : Menampilkan baris yang sesuai dengan pola tertentu.

    Dalam contoh ini, kita memiliki sebuah file teks yang berisi daftar mahasiswa beserta jurusan mereka. Kita ingin menampilkan baris-baris yang mengandung pola " CS" (Computer Science).
    ```
    awk '/CS/ {print}' student.txt
    ```
    **awk** adalah Command Awk.
    **'/ CS/ {print}'** adalah pola dan tindakan. / CS/ adalah pola yang digunakan untuk mencari baris yang mengandung " CS". Setelah itu, {print} adalah tindakan yang akan diambil pada baris yang cocok dengan pola.

    Hasil dari perintah diatas adalah 
    ```
    Sam CS
    Daniel CS
    ```
#
- ### Contoh 2: Perilaku default perintah awk.
    Jika kita tidak menentukan pola, perintah AWK akan menampilkan seluruh konten dari file.
    ```
    awk '{print}' student.txt
    ```
    Hasilnya adalah seluruh baris dari file "student.txt".

#
- ### Contoh 3: Menampilkan Kolom Tertentu
    Dalam contoh ini, kita ingin mencetak kolom pertama dan kelima dari setiap baris dalam file.
    ```
    awk '{print $1,$5}' student.txt
    ```
    '{print $1,$5}' adalah tindakan yang mencetak kolom pertama dan kelima. $1 dan $5 adalah variabel yang mewakili kolom pertama dan kelima. Jika kolom kelima tidak ada, hanya kolom pertama yang akan dicetak.
    ```
    Sam 
    Daniel
    John
    Arya
    Mike
    Helena
    ```
    
- ### Contoh 4: Menampilkan Output dengan Nomor Baris
    Dalam contoh ini, kita ingin menampilkan nomor baris di depan setiap baris dalam output.
    ```
    awk '{print NR,$0}' student.txt
    ```
    NR adalah Variabel bawaan yang mewakili nomor baris dan '$0' adalah Variabel yang mewakili seluruh baris. Hasil nya akan seperti berikut 
    ```
    1 Sam CS
    2 Daniel IT
    3 John IT
    4 Arya IT
    5 Mike ECE
    6 Helena ECE
    ```
- ### Contoh 5: Menampilkan Kolom Terakhir dari File
    Dalam contoh ini, kita ingin mencetak kolom terakhir dari setiap baris dalam file.
    ```
    awk '{print $NF}' student.txt
    ```
    '$NF' adalah Variabel yang mewakili kolom terakhir. Hasil nya akan seperti berikut 
    ```
    CS
    IT
    IT
    IT
    ECE
    ECE
    ```

- ### Contoh 6: Memisahkan Output dalam Format Tertentu
    Dalam contoh ini, kita ingin memisahkan setiap baris dalam output dengan tanda hubung (-).
    ```
    awk 'BEGIN {ORS ="-"} {print $0}' student.txt
    ```
    'BEGIN {ORS ="-"}' adalah bagian yang dieksekusi sebelum memproses file. Kita mengatur ORS (Output Record Separator) menjadi tanda hubung (-) dan '{print $0}'adalah tindakan yang mencetak seluruh baris.

    Hasil :
    ```
    Sam CS-Daniel IT-John IT-Arya IT-Mike ECE-Helena ECE-
    ```
#
- ### Contoh 7: Mencetak Kuadrat dari Angka 1 hingga 8
    Dalam contoh ini, kita ingin mencetak kuadrat dari angka 1 hingga 8.
    ```
    awk 'BEGIN { for(i=1;i<=8;i++) print "square of", i, "is",i*i; }'
    ```
    Hasil :
    ```
    square of 1 is 1
    square of 2 is 4
    square of 3 is 9
    square of 4 is 16
    square of 5 is 25
    square of 6 is 36
    square of 7 is 49
    square of 8 is 64
    ```
#
- ### Contoh 8: Menghitung Jumlah dari Kolom Tertentu
    Dalam contoh ini, kita ingin menghitung jumlah dari kolom ketiga (skor maksimal) dalam data skor mahasiswa.

    Pertama, buat data skor mahasiswa dengan menggunakan perintah cat seperti berikut:
    ```
    cat >  StudentMarks  
    Name, Marks, Max marks              
    Sam,75,100  
    Daniel,80,100  
    John,74,100  
    Arya,85,100  
    Mike,70,100   
    Helena,74,100  
    ```

    Dalam contoh ini, kita ingin menghitung jumlah dari kolom ketiga (nilai maksimal) dalam data skor mahasiswa.
    ```
    awk -F"," '{x+=$3}END{print x}' StudentMarks
    ```
    - '-F","': Opsi -F digunakan untuk mengatur pemisah kolom sebagai koma (,).
    - 'x+=$3': Setiap kali baris diproses, nilai kolom ketiga ditambahkan ke variabel x.
    - 'END{print x}': Setelah semua baris diproses, kita mencetak nilai akhir dari variabel x.

    Hasil :
    ```
    600
    ```
#
- ### Contoh 9: Menemukan Total Skor Individu
    ```
    awk -F, '{a[$1]+=$2;}END{for(i in a)print i", "a[i];}' StudentMarks
    ```
    - '-F,': Opsi -F digunakan untuk mengatur pemisah kolom sebagai koma (,).
    - '{a[$1]+=$2;}': Setiap kali baris diproses, nilai kolom kedua (skor) ditambahkan ke array asosiatif a dengan indeks berdasarkan nama mahasiswa.
    - 'END{for(i in a)print i", "a[i];}': Setelah semua baris diproses, kita mencetak total skor untuk setiap mahasiswa.

    Hasil :
    ```
    Sam, 75
    Daniel, 80
    John, 74
    Arya, 85
    Mike, 70
    Helena, 74
    ```
#
- ### Contoh 10: Menghitung Nilai e^8
    ```
    awk 'BEGIN{x=exp(8); print x}'
    ```
    Bagian 'BEGIN{x=exp(8); print x}' dieksekusi sebelum memproses file. Kita menghitung nilai e^8 menggunakan fungsi exp() dan mencetak hasilnya.
    Hasil :
    ```
    2980.95798704
    ```