# Konfigurasi Static Hostname FQDN (Full Qualified Domain Name)

## 1 Oktober 2024

---

## Details

1. **Gunakan Perintah Berikut untuk Membuka file Hostname**

   ``` 
   nano /etc/hostname
   ```
2. **Ganti Hostname sesuai apa yang di inginkan**

    ```
    adam-server.com
    ```
    Kemudian Save perubahan tadi dengan Ctrl+O dan Ctrl+X
3. **Ganti Hostnamectl dengan hostname yang baru**
    ```
    hostnamectl set-hostname adam-server.com
    ```
4. **Cek apakah hostname sudah terganti**
    ```
    hostname -f
    ```
    jika sudah berhasil maka akan muncul hostname yang diinginkan
    ![Hostname Configuration](https://github.com/adampnggwa/BELAJAR-YAVA247/raw/main/image/hostname.png)