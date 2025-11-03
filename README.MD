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

## (Tambahan) Setup Binaries Hadoop

Ini diperlukan, karena beberapa library PySpark bekerja dengan binaries hadoop (contohnya untuk write file).

1. Unduh semua file bin **Hadoop 3.3.6** di [github.com/cdarlint/winutils](https://github.com/cdarlint/winutils/tree/master/hadoop-3.3.6/bin)

2. Siapkan direktori `C:\hadoop\bin` untuk menampung semua file bin tersebut

3. Kemudian masukkan semua file bin Hadoop tersebut ke direktori

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
> Tambahan: *Setup binary Hadoop tanpa instalasi Hadoop 👇*

1. Masih di menu Edit the system environment variables
→ klik Environment Variables…
2. Tambahkan variabel baru di System Variables:
```bash
Variable name: HADOOP_HOME
Variable value: C:\hadoop
```
Kemudian, klik dua kali pada variabel bernama `Path`, klik tombol `New` dan tambahkan path baru berikut:
```bash
C:\hadoop\bin
```
lakukan verifikasi dengan command
```bash
echo %HADOOP_HOME%
output yang diharapkan:
   C:\hadoop
```
lakukan juga verifikasi winutils.exe (binary hadoop) dengan command
```bash
winutils.exe
output yang diharapkan:
   Usage: winutils.exe [command] ...
   Provide basic command line utilities for Hadoop on Windows.
```

## Setup Project
1. python -m venv venv
2. venv\Scripts\activate
3. pip install -r requirements.txt
4. run file  `check.ipynb` untuk mengecek apakah sudah terinstall dengan benar


### Struktur Folder
```bash
C:\python-project\midterm-project\
│
├── data\                    
│   ├── raw\                 
│   └── processed\         
│
├── notebooks\  
│   ├── 01_setup_environment.ipynb
│   ├── 02_data_preprocessing.ipynb
│   ├── 03_model_training.ipynb
│   └── 04_evaluation.ipynb
│
├── src\                     # Script Python modular
│   ├── preprocessing.py
│   ├── training.py
│   └── evaluation.py
│
│
├── venv\                   
│
├── README.md                
├── requirements.txt 
└── .gitignore               

```