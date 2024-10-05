# Konfigurasi Static IP Address

## 1 Oktober 2024

---

## Details

1. **Langkah pertama tambahkan jaringan pada VM**

    ![Jaringan](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/jaringan.png)

2. **Cek apakah anda sudah mendapatkan IP Bridgenya**

    Untuk cek IP gunakan command dibawah ini

    ``` 
    ip addr show
    ```

3. **Buka file ifcfg-enp0s3 untuk konfigurasi ip menjadi static**

    Gunakan command dibawah ini

    ```
    nano /etc/sysconfig/network-scripts/ifcfg-enp0s8
    ```
    Sesuaikan bagian dibawah ini
    
    ```sh
    BOOTPROTO=none
    IPADDR=192.168.1.100
    NETMASK=255.255.255.0
    ONBOOT=yes
    ```
    Save dan Exit

4. **Restart NetworkManager**
    ```
    systemctl restart NetworkManager
    ```
5. **Cek apakah IP Static telah berhasil dibuat**
    ```
    ip addr show
    ```
    ![IP static](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/ipstatic.png)