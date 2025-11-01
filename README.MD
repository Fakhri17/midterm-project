# 🧰 PySpark Environment Setup (Midterm Project)

Panduan ini membantu menyiapkan lingkungan untuk menjalankan proyek **PySpark (Midterm Project)** di Windows menggunakan **JDK 21** dan **Python virtual environment** tanpa WSL.

---

## Install Java Development Kit (JDK)

1. Unduh **JDK 21** dari salah satu situs berikut:
   - [Oracle JDK 21](https://www.oracle.com/asean/java/technologies/downloads/#java21)

2. Setelah instalasi selesai, pastikan JDK terpasang di:
`C:\Program Files\Java\jdk-21`

3. Verifikasi instalasi lewat **Command Prompt**:
```bash
java -version
java version "21.x.x" ...
```

## Setup Environment Variables
1. Buka menu Edit the system environment variables
→ klik Environment Variables…
2. Tambahkan variabel baru di System Variables:
```bash
Variable name: JAVA_HOME
Variable value: C:\Program Files\Java\jdk-21
```
lakukan verifikasi dengan command
```bash
echo %JAVA_HOME%
output yang diharapkan:
C:\Program Files\Java\jdk-21
```

## Setup Project
1. python -m venv venv
2. venv\Scripts\activate
3. pip install -r requirements.txt
4. run file  `check.ipynb` untuk mengecek apakah sudah terinstall dengan benar