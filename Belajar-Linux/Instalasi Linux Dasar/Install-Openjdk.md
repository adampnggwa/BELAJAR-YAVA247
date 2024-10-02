# Install openjdk 1.8 and set as default jdk version

## 2 Oktober 2024

---

## Details

1. **Langkah pertama install Openjdk**

    Gunakan command dibawah ini

    ``` 
    dnf install java-devel -y
    ```

2. **Cek apakah instalasi sudah berhasil**

    Gunakan command dibawah ini

    ```
    java -version
    ```
    
3. **Masuk ke file Java untuk melakukan konfigurasi**

    Gunakan command dibawah ini

    ```
    vi /etc/profile.d/java.sh 
    ```
    
4. **Lakukan konfigurasi**

    Tambahkan command seperti dibawah ini

    ```
    export JAVA_HOME=/usr/lib/jvm/java-11-openjdk
    ```

    ```
    export PATH=$JAVA_HOME/bin:$PATH
    ```

5. **Jika sudah, aktifkan perubahan tadi**

    Gunakan command dibawah ini

    ```
    source /etc/profile.d/java.sh
    ```

6. **Cek apakah sudah berhasil**

    Gunakan command dibawah ini

    ```
    echo $JAVA_HOME
    ```

    ```
    java -version
    ```

    ![Cek-Openjdk](https://github.com/adampnggwa/BELAJAR-YAVA247/blob/main/Image/installjava.png)