# Install and enable paket ntp

## 2 Oktober 2024

---

## Details

1. **Langkah pertama install Chrony**

    Gunakan command dibawah ini

    ``` 
    dnf install chrony -y
    ```

2. **Masuk ke file chrony untuk melakukan konfigurasi**

    Gunakan command dibawah ini

    ```
    vi /etc/chrony.conf
    ```
    
3. **Kemudian lakukan konfigurasi dengan mengganti bagian pool dengan ntp server yang diinginkan**

    Contoh

    ```
    pool time.google.com iburst
    ```
    
4. **Restart Chrony untuk menyimpan perubahan**

    Gunakan command dibawah ini

    ```
    systemctl restart chronyd
    ```

5. **Setelah itu lakuakan perizinan**

    Gunakan command dibawah ini

    ```
    systemctl enable chronyd
    ```

6. **Jalankan Chrony**

    Gunakan command dibawah ini

    ``` 
    systemctl start chronyd
    ```

7. **Cek apakah sudah berjalan dengan benar**

    Gunakan command dibawah ini

    ```
    systemctl status chronyd
    ```
             
    ![Status-Chrony](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/ntpstatus.png)

8. **Terakhir, cek apakah sudah berhasil**

    Gunakan command dibawah ini

    ```
    chronyc tracking
    ```
             
    ![Cek-Chrony](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/installntp.png)