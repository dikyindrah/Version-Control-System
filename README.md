<h1 align='center'>
    Version Control System
</h1>

- ## List
  - [Tentang Version Control System](#Tentang-Version-Control-System)
  - [Jenis Version Control System](#Jenis-Version-Control-System)
  - [Apa itu Git?](#Apa-itu-Git?)
  - [Apa itu Github?](#Apa-itu-Github?)
  - [Instalasi Git](#Instalasi-Git)
  - [Konfigurasi Akun](#Konfigurasi-Akun)
  - [Konfigurasi Kode Editor](#Konfigurasi-Kode-Editor)
  - [Membuat Repository](#Membuat-Repository)

## Tentang Version Control System
Version control system (VCS) merupakan sebuah sistem yang digunakan untuk mengelola perubahan project pada sebuah repository (sebuah tempat dimana project itu disimpan). Sistem ini secara otomatis mencatat dan menyimpan setiap informasi perubahan yang terjadi pada project di titik waktu tertentu (Snapshot). 

**Beberapa informasi perubahan yang disimpan:**
- Kode hash
- Orang yang telah melakukan perubahan. 
- Waktu ketika perubahan tersebut dilakukan. 
- Bagian yang telah diubah, dihapus, dan ditambahkan.
- Keterangan perubahan.

## Jenis Version Control System
**1. Local Version Control System**

Pada local VCS, project di kelola secara manual dengan cara membuat salinan pada setiap versinya dan disimpan pada direktori penyimpanan yang ada di komputer pribadi. Karena project masih dikelola manual, maka kemungkinan besar akan terjadi beberapa masalah yang akan ditemukan seperti lupa diamana project disimpan, tidak sengaja terhapus, lupa tidak membuat salinan versi, dll.

**2. Centralized Version Control System**

Sistem ini dikembangkan untuk memenuhi kebutuhan programmer yang ingin bekerja secara berkolaborasi. Project disimpan pada repository di sebuah server terpusat sehingga memungkinkan orang lain yang memiliki akses pada repository tersebut dapat melakukan perubahan pada project yang sama. Meskipun pengelolaan project sudah sepenuhnya oleh sistem,namum masih terdapat kelemahan pada centralized VCS ini yaitu jika suatu saat server mengalami masalah maka seluruh anggota team yang berkolaborasi tidak dapat mengakses project yang di simpan pada server, kemudian masalah terburuknya adalah ketika server benar - benar rusak dan jika project tidak memiliki backup maka kemungkinan project akan hilang secara permanen.

[<img width='500' src='https://miro.medium.com/max/1050/1*GgaGcwh5L246YcU5NVDA5A.png'>](https://medium.com/faun/centralized-vs-distributed-version-control-systems-a135091299f0)

**3. Distributed Version Control System**
   
Tidak hanya melakukan perubahan project pada repository di sebuah server. Seluruh orang yang berkontribusi pada project di sistem ini memiliki salinan penuh repository, artinya project tidak hanya disimpan pada repository server saja melainkan juga di distribusikan dan di simpan pada repository lokal yaitu di komputer colaborator (orang yang memiliki akses pada repository untuk berkolaborasi). Jadi jika server rusak sekalipun, seluruh orang masih masih dapat melakukan pekerjaanya, karena mereka masih memiliki backup project yang ada di repository lokal (jika dibutuhkan project tersebut hanya perlu dikirim kemabali ke server).

[<img width='500' src='https://miro.medium.com/max/1050/1*CEyiDu_mQ5u9NI0Fr2pSdA.png'>](https://medium.com/faun/centralized-vs-distributed-version-control-systems-a135091299f0)


