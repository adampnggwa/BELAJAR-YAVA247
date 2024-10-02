# Install paket epel-release dan enable repository powertools

## 2 Oktober 2024

---

## Details

1. **Langkah pertama install dnf-plugins-core**

    Gunakan command dibawah ini

    ``` 
    dnf install dnf-plugins-core -y
    ```

2. **Selanjutnya install epel-release**

    Gunakan command dibawah ini

    ```
    dns install epel-release -y
    ```
    
3. **Kemudian aktifkan repo powertools**

    Gunakan command dibawah ini

    ```
    dnf config-manager --set-enabled powertools
    ```
    
4. **Cek apakah sudah berhasil**

    Gunakan command dibawah ini

    ```
    dnf repolist
    ```

    ![Cek-Epel](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/installepel.png)