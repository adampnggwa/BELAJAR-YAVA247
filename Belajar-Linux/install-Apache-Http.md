# Install and enable paket apache httpd

## 2 Oktober 2024

---

## Details

1. **Langkah pertama install paket**

    Gunakan command dibawah ini

    ``` 
    dnf install httpd -y
    ```

2. **Setelah selesai terinstall, jalankan paket**

    Gunakan command dibawah ini

    ```
    systemctl start httpd
    ```
    
3. **Kemudian izinkan paket**

    Gunakan command dibawah ini

    ```
    systemctl enable httpd
    ```
    
4. **Cek apakah sudah berjalan dengan benar**

    Gunakan command dibawah ini

    ```
    systemctl status httpd
    ```

5. **Langkah terakhir setting Firewall untuk http dan https**

    Gunakan command dibawah ini

    ```
    sudo firewall-cmd --permanent --add-service=http
    ```

    ```
    sudo firewall-cmd --permanent --add-service=https
    ```

    ```
    sudo firewall-cmd --reload
    ```
            
    ![Apache-Http](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/installapache.png)