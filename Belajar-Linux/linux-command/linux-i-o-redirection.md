# Linux I/O Redirection

## 11 Oktober 2024

---

## Details

#

Redirection adalah cara mengubah arah masukan (input) dan keluaran (output) perintah. Hal ini dapat dilakukan dengan menggunakan karakter-karakter meta. Misalnya, '>' atau '>>' untuk mengalihkan ke berkas, dan '|' untuk mengalihkan ke program lain.

Aliran Standar dalam Pengalihan I/O

- **standard input  (stdin):** Dinomori sebagai stdin (0). Shell bash mengambil masukan dari papan ketik secara default.
- **standard output (stdout):** Dinomori sebagai stdout (1). Shell bash mengirim keluaran ke layar.
- **standard error (stderr):** Dinomori sebagai stderr (2). Shell bash mengirim pesan kesalahan ke layar.
#

- Penggantian (Overwrite)

    |Perintah|	Deskripsi|
    |--|--|
    |`command > <berkas>`	|Menggantikan isi berkas dengan keluaran perintah.|
    |`command < <berkas>`	|Menggunakan berkas sebagai masukan.|
    |`command 2> <berkas>`	|Mengalihkan pesan kesalahan ke berkas.|
#
- Penambahan (Append)
    |Perintah|	Deskripsi|
    |--|--|
    |`command >> <berkas>`	|Menambahkan keluaran perintah ke berkas tanpa menggantikan isi|
    |`command << <berkas>` |	Menggunakan berkas sebagai masukan.|
    |`command 2>> <berkas>`|	Menambahkan pesan kesalahan ke berkas tanpa menggantikan isi|

#
### Pengalihan ke Program

Symbol | digunakan untuk mengalihkan keluaran dari satu program ke program lain. Perintah pertama tidak ditampilkan di layar.

Contoh: 
```
ls *.txt | cat > berkasTxt
```
Pada contoh di atas, berkas 'berkasTxt' akan berisi daftar berkas '.txt'.

#
### Linux Input Redirection
```
command < <namaBerkas>
```

Input redirection adalah teknik yang memungkinkan  mengarahkan aliran masukan (stdin) dari suatu perintah ke dalam berkas atau perangkat tertentu. Dalam sintaks di atas, 'command' adalah perintah yang ingin jalankan, dan '< namaBerkas' menunjukkan bahwa user ingin mengambil masukan dari berkas tersebut.

Contoh:
```
cat < file.txt
```
Dalam contoh ini, isi 'file.txt' akan dijadikan masukan untuk perintah 'cat', dan hasil keluaran dari perintah 'cat' akan ditampilkan di layar.
#
### Linux Output Redirection

```
command > <namaBerkas>
```
Output redirection adalah teknik yang memungkinkan mengarahkan aliran keluaran (stdout) dari suatu perintah ke dalam berkas atau perangkat tertentu. Dalam sintaks di atas, 'command' adalah perintah yang ingin jalankan, dan '> namaBerkas' menunjukkan bahwa user ingin mengarahkan keluaran dari perintah ke berkas tersebut.

Contoh :
```
echo Hello everyone. > afile.txt
```
Setelah perintah dijalankan, berkas 'afile.txt' akan berisi teks 'Hello everyone.'.

#
### Error Redirection
Error redirection digunakan untuk mengalihkan keluaran kesalahan (error output) dari suatu perintah. Ini membantu menjaga tampilan agar tidak berantakan dengan mengalihkan pesan kesalahan.

```
command 2> <namaBerkas>
```
Error Redirection digunakan untuk mengalihkan keluaran kesalahan (stderr) dari suatu perintah ke dalam berkas atau perangkat lain. Dalam sintaks di atas, 'command' adalah perintah yang di jalankan, dan '2>' menunjukkan bahwa user ingin mengalihkan keluaran kesalahan.

Contoh, perintah berikut akan menjalankan perintah 'zcho hyii', tetapi mengalihkan pesan kesalahannya ke '/dev/null', yang berarti pesan-pesan kesalahan akan diabaikan:
```
zcho hyii 2> /dev/null
```
Jika perintah 'zcho hyii' menghasilkan kesalahan, pesan error tersebut tidak akan ditampilkan di layar namun output nya kosong.