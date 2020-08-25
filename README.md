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

## Apa itu Git?
Git adalah software version control yang diciptakan oleh Linus Torvalds, yang pada awalnya ditujukan untuk pengembangan kernel Linux (Wikipedia). Git dapat digunakan untuk mengelola perubahan project secara offline maupun online pada sebuah repository. Kemudian salah satu kelebihan dari Git adalah menggunakan sistem terdistribusi yang artinya project tidak hanya disimpan pada satu tempat saja melainkan juga tersebar dan tersimpan pada seluruh orang yang berkerja pada repository yang sama, hal ini membuat seluruh data dari project akan lebih terjamin keamanannya.

**Software version control lain:**

| [<img width='190' src='https://git-scm.com/images/logos/logomark-orange@2x.png'>](https://git-scm.com/) | [<img width='190' src='https://azuharu.net/wp-content/uploads/2014/01/subversion-logo.png'>](https://subversion.apache.org/) | [<img width='190' src='https://upload.wikimedia.org/wikipedia/commons/thumb/0/0e/Mercurial_no_border_logo.svg/1200px-Mercurial_no_border_logo.svg.png'>](https://www.mercurial-scm.org/) | [<img width='190' src='https://img2.pngio.com/what-are-the-top-version-control-systems-the-linux-juggernaut-concurrent-versions-system-png-193_261.png'>](https://www.nongnu.org/cvs/) | [<img width='190' src='https://upload.wikimedia.org/wikipedia/en/thumb/c/c1/Bazaar_logo_%28software_product%29.svg/1200px-Bazaar_logo_%28software_product%29.svg.png'>](https://bazaar.canonical.com/en/) |
|---|---|---|---|---|



