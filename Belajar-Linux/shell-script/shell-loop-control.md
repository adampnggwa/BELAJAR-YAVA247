# The infinite Loop
Suatu loop yang berjalan tanpa berakhir selama kondisi yang ditentukan tetap terpenuhi. Loop ini sering digunakan untuk menjalankan tugas-tugas yang perlu berjalan terus-menerus hingga intervensi eksternal.
```sh
while true
do
    # Blok pernyataan yang akan diulang secara terus-menerus
done
```
Contoh
```sh
#!/bin/bash

while true
do
    echo "Loop ini berjalan tanpa akhir. Tekan Ctrl+C untuk keluar."
    sleep 1
done
```
Pada contoh ini, program akan terus mencetak pesan setiap 1 detik, karena kondisi true selalu terpenuhi. Kita dapat menghentikan loop ini dengan menekan Ctrl+C.

![test1](https://iili.io/HyF3fRI.png)




#
# The break Statement
Pernyataan break digunakan untuk menghentikan pelaksanaan loop secara paksa, bahkan jika kondisi yang diberikan belum terpenuhi. Biasanya, break digunakan ketika suatu kondisi khusus terpenuhi dan tidak perlu melanjutkan iterasi.
```sh
while [ condition ]
do
    if [ some_condition ]
    then
        break
    fi
    # Blok pernyataan lainnya
done
```
Contoh
```sh
#!/bin/bash

count=1

while true
do
    echo "Iterasi Loop: $count"
    
    if [ $count -eq 5 ]
    then
        break
    fi
    
    ((count++))
done
```
Pada contoh ini, program akan melakukan iterasi dalam loop while sampai variabel count mencapai nilai 5. Ketika count mencapai 5, pernyataan break akan dijalankan dan loop akan dihentikan meskipun kondisi true masih terpenuhi.

![test2](https://iili.io/HyF3KHN.png)
#
# The continue statement
Pernyataan continue digunakan untuk menghentikan iterasi saat ini dan melanjutkan ke iterasi berikutnya dalam loop. Hal ini berguna ketika kita ingin melompati beberapa pernyataan dalam satu iterasi tertentu dan langsung melanjutkan ke iterasi berikutnya.
```sh
while [ condition ]
do
    if [ some_condition ]
    then
        continue
    fi
    # Blok pernyataan lainnya
done
```
Contoh
```sh
#!/bin/bash

count=1

while [ $count -le 5 ]
do
    if [ $count -eq 3 ]
    then
        ((count++))
        continue
    fi
    
    echo "Iterasi Loop: $count"
    ((count++))
done
```
Pada contoh ini, program akan melakukan iterasi dalam loop while dari 1 hingga 5. Ketika nilai variabel count sama dengan 3, pernyataan continue akan dijalankan. Akibatnya, pernyataan iterasi saat itu akan diabaikan, dan loop akan langsung melanjutkan ke iterasi berikutnya. Jadi, pesan "Iterasi Loop: 3" akan diabaikan, dan loop akan melanjutkan dengan nilai count berikutnya. Sehingga, output tidak akan menjalankan "Iterasi Loop: 3".

![test3](https://iili.io/HyF33Sp.png)