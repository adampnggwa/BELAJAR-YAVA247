### Operator Perbandingan Numerik dalam Shell Scripting
#
| Operator  | Keterangan                     |
| --------- | ----------------------------- |
| `-eq`     | Sama dengan                    |
| `-ne`     | Tidak sama dengan              |
| `-lt`     | Kurang dari                    |
| `-le`     | Kurang dari atau sama dengan   |
| `-gt`     | Lebih besar dari               |
| `-ge`     | Lebih besar dari atau sama dengan |

#
- ## If then else
    Pernyataan if-then-else mengatur eksekusi skrip berdasarkan kondisi. Jika kondisi benar, blok then dieksekusi, jika tidak, blok else dieksekusi

    Kata "fi" digunakan untuk menutup blok perulangan if.

    ```sh
    if [ kondisi 1 ]; then
     echo "pernyataan 1"
    elif [ kondisi 2 ]; then
     echo "pernyataan 2"
    else
     echo "pernyataan lainnya"
    fi
    ```
#
- ## If then elif
    Pernyataan if-then-elif menguji beberapa kondisi berurutan menggunakan elif. Ketika kondisi terpenuhi, blok then sesuai dieksekusi.
    ```sh
    if [ kondisi_1 ]; then
     echo "pernyataan"
    elif [ kondisi_2 ]; then
     echo "pernyataan"
    else
     echo "pernyataan"
    fi
    ```

#
- ## For loop
    Perulangan for digunakan untuk mengulangi serangkaian perintah dengan mengulanginya berdasarkan rentang nilai tertentu atau daftar elemen.
    ```sh
    for varname in list
    do
     echo "pernyataan"
    done
    ```
    ***list*** adalah kumpulan variabel yang dipisahkan oleh spasi.

    contoh :
    
    ```sh
    for angka in 1 2 3 4 5
    do
     echo "Angka: $angka"
    done
    ```
#
- ## While loop
    Perulangan while digunakan untuk mengulang serangkaian perintah selama kondisi tertentu terpenuhi. Selama kondisi tersebut benar (true), pernyataan dalam blok while akan terus dieksekusi. 
    ```sh
    while [ kondisi ]
    do
     command
    done
    ```
    Contoh
    ```sh
    counter=1
    while [ $counter -le 10 ]
    do
     echo "Iterasi ke-$counter"
     ((counter++))
    done
    ```
    Dalam contoh ini, perulangan while akan berjalan selama nilai $counter kurang dari atau sama dengan 10
#
- ## Until loop
    Perulangan until mirip dengan while, tetapi pernyataan dalam blok until akan terus dieksekusi selama kondisi yang diberikan tidak terpenuhi (false). Ini berarti pernyataan dalam blok until akan berjalan hingga kondisi menjadi benar (true)

    ```sh
    until [ kondisi ]
    do
     command
    done
    ```
    Contoh :
    ```sh
    counter=1
    until [ $counter -gt 5 ]
    do
     echo "Iterasi ke-$counter"
     ((counter++))
    done
    ```
    Dalam contoh ini, perulangan until akan berjalan selama nilai $counter tidak lebih dari 5. Dalam setiap perulangan nilai $counter akan ditingkatkan. Saat $counter lebih dari 5 maka perulangan akan berhenti.

    ### Nesting Loops
Nesting loops adalah jenis pengulangan di dalam pengulangan lainnya. Hal ini memungkinkan kita untuk melakukan nesting pada berbagai jenis pengulangan seperti while, for, dan until.
#
### Nesting While Loops
Nesting while loops melibatkan menempatkan satu pengulangan while di dalam pengulangan while lainnya.


```sh
while [condition1]
do
   # Perintah-perintah dalam blok pertama
   while [condition2]
   do
      # Perintah-perintah dalam blok kedua
   done
done
```
Contoh
```sh
#!/bin/bash

outer=1

while [ $outer -le 3 ]
do
    inner=1
    while [ $inner -le 3 ]
    do
        echo "Iterasi loop luar: $outer, Iterasi loop dalam: $inner"
        ((inner++))
    done
    ((outer++))
done
```
Pada contoh ini, terdapat dua pengulangan while yang bersarang. Loop luar akan beriterasi dari 1 hingga 3. Di dalam setiap iterasi loop luar, loop dalam juga akan beriterasi dari 1 hingga 3. Outputnya akan menampilkan kombinasi iterasi dari kedua loop.
![test1](https://iili.io/HyFf9Ve.png)


#
### Nesting For Loops
```sh
for (( initialization; condition; iteration ))
do
   # Blok pernyataan dalam loop for pertama
   for (( initialization; condition; iteration ))
   do
      # Blok pernyataan dalam loop for kedua
   done
done
```
Contoh
```sh
#!/bin/bash

for (( i = 1; i <= 3; i++ ))
do
    for (( j = 1; j <= 3; j++ ))
    do
        echo "Iterasi loop luar: $i, Iterasi loop dalam: $j"
    done
done
```
Pada contoh ini, dua loop for bersarang. Loop luar akan beriterasi dari 1 hingga 3. Di dalam setiap iterasi loop luar, loop dalam juga akan beriterasi dari 1 hingga 3. Outputnya akan menampilkan kombinasi iterasi dari kedua loop.


![test2](https://iili.io/HyFfHiu.png)
#
### Nesting until Loops
```sh
until [ condition ]
do
   # Blok pernyataan dalam loop until pertama
   until [ condition ]
   do
      # Blok pernyataan dalam loop until kedua
   done
done
```


Contoh
```sh
#!/bin/bash

outer=1

until [ $outer -gt 3 ]
do
    inner=1
    until [ $inner -gt 3 ]
    do
        echo "Iterasi loop luar: $outer, Iterasi loop dalam: $inner"
        ((inner++))
    done
    ((outer++))
done
```
Pada contoh ini, terdapat dua pengulangan until yang bersarang. Loop luar akan beriterasi selama nilai variabel outer kurang dari atau sama dengan 3. Di dalam setiap iterasi loop luar, loop dalam juga akan beriterasi selama nilai variabel inner kurang dari atau sama dengan 3. Outputnya akan menampilkan kombinasi iterasi dari kedua loop.

![test3](https://iili.io/HyFKyx9.png)