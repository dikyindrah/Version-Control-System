<h1 align='center'>
    Version Control System
</h1>

- ## List
  - [Tentang Version Control System](#Tentang-Version-Control-System)
  - [Jenis Version Control System](#Jenis-Version-Control-System)
  - [Apa Itu Git?](#Apa-itu-Git)
  - [Apa Itu Github?](#Apa-itu-Github)
  - [Area dan Keadaan File Pada Git](#Area-dan-Keadaan-File-Pada-Git)
  - [Instalasi Git](#Instalasi-Git)
  - [Konfigurasi Akun](#Konfigurasi-Akun)
  - [Konfigurasi Kode Editor](#Konfigurasi-Kode-Editor)
  - [Melihat Seluruh Konfigurasi](#Melihat-Seluruh-Konfigurasi)
  - [Membuat Repository](#Membuat-Repository)

## Tentang Version Control System
Version Control System (VCS) merupakan sebuah sistem yang digunakan untuk mengelola perubahan project pada sebuah repository (sebuah tempat dimana project itu disimpan). Sistem ini secara otomatis mencatat dan menyimpan setiap informasi perubahan yang terjadi pada project di titik waktu tertentu (Snapshot). 

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
   
Tidak hanya melakukan perubahan project pada repository di sebuah server. Seluruh orang yang berkontribusi pada project di sistem ini memiliki salinan penuh repository, artinya project tidak hanya disimpan pada repository server saja melainkan juga di distribusikan dan di simpan pada repository lokal yaitu di komputer collaborator (orang yang memiliki akses pada repository untuk berkolaborasi). Jadi jika server rusak sekalipun, seluruh orang masih masih dapat melakukan pekerjaanya, karena mereka masih memiliki backup project yang ada di repository lokal (jika dibutuhkan project tersebut hanya perlu dikirim kemabali ke server).

[<img width='500' src='https://miro.medium.com/max/1050/1*CEyiDu_mQ5u9NI0Fr2pSdA.png'>](https://medium.com/faun/centralized-vs-distributed-version-control-systems-a135091299f0)

## Apa Itu Git?
Git adalah software version control yang diciptakan oleh Linus Torvalds, yang pada awalnya ditujukan untuk pengembangan kernel Linux (Wikipedia). Git dapat digunakan untuk mengelola perubahan project secara offline maupun online pada sebuah repository. Kemudian salah satu kelebihan dari Git adalah menggunakan sistem terdistribusi yang artinya project tidak hanya disimpan pada satu tempat saja melainkan juga tersebar dan tersimpan di seluruh komputer orang yang berkerja pada repository yang sama, hal ini membuat seluruh data dari project akan lebih terjamin keamanannya.

**Software version control lain:**

| [<img width='190' src='https://git-scm.com/images/logos/logomark-orange@2x.png'>](https://git-scm.com/) | [<img width='190' src='https://azuharu.net/wp-content/uploads/2014/01/subversion-logo.png'>](https://subversion.apache.org/) | [<img width='190' src='https://upload.wikimedia.org/wikipedia/commons/thumb/0/0e/Mercurial_no_border_logo.svg/1200px-Mercurial_no_border_logo.svg.png'>](https://www.mercurial-scm.org/) | [<img width='190' src='https://img2.pngio.com/what-are-the-top-version-control-systems-the-linux-juggernaut-concurrent-versions-system-png-193_261.png'>](https://www.nongnu.org/cvs/) | [<img width='190' src='https://upload.wikimedia.org/wikipedia/en/thumb/c/c1/Bazaar_logo_%28software_product%29.svg/1200px-Bazaar_logo_%28software_product%29.svg.png'>](https://bazaar.canonical.com/en/) |
|---|---|---|---|---|

| []() | []() | []() | []() | []() |
|---|---|---|---|---| 

## Apa Itu Github?
Github adalah version control system berbasis web yang dapat digunakan untuk menyimpan project, mengelola project didalam repository, dan sebagai remote atau git server pada pengembangan project secara kelompok, ini digunakan untuk menyimpan repository secara online melalui layanan cloud di internet agar setiap orang dapat mengakses dan bekeja pada repository yang sama.

**Version control system berbasis web lain:**

| [<img width='190' src='https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png'>](https://github.com/) | [<img width='190' src='https://cdn.iconscout.com/icon/free/png-256/bitbucket-8-1175256.png'>](https://bitbucket.org/) | [<img width='190' src='https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/GitLab_Logo.svg/1108px-GitLab_Logo.svg.png'>](https://gitlab.com/explore) | [<img width='190' src='https://cdn.worldvectorlogo.com/logos/sourcetree-1.svg'>](https://www.sourcetreeapp.com/) |
|---|---|---|---|

## Area dan Keadaan File Pada Git
Git memiliki area dan beberapa keadaan file yang perlu diketahui. Hal ini akan memberikan gambaran tentang alur kerja penggunaan git.

**Area :**

- *Working Directory* : Ini adalah area diamana kita bekerja untuk mengembangkan project. pada area ini kita dapat menambah, mengubah isi, dan menghapus file pada project didalam repository.

- *Staging Area* : Area ini untuk menampung file - file beserta perubahan yang ingin kita commit (Rekaman perubahan (Snapshot) yang disimpan). File yang sudah masukan ke area ini akan dilacak atau ditandai untuk dipantau pada setiap perubahan yang terjadi. 

- *Git Directory* : Seluruh file beserta perubahannya disimpan pada area ini (database lokal git) sebagai commit.

**Keadaan File :**

- *Untracked* : File belum dimasukan ke staging area yang artinya file tersebut belum terlacak atau ditandai oleh git, dalam keadaan ini apapun yang terjadi pada file tersebut akan diabaikan oleh git.

- *Modifed* : Ketika file sudah disimpan sebagai commit, namun pada file tersebut kembali dilakukan perubahan dan belum di commit.

- *Staged* : File beserta perubah yang telah dilakukan sudah dimasukan ke staging area dan file tersebut sudah ditandai oleh git untuk dipantau setiap perubahannya.

- *Commited* : Keadaan ini menunjukan bahwa file beserta perubahannya sudah di commit dan sudah dismpan pada database git.

## Instalasi Git
- Linux
  - Instalasi git dengan linux selengkapnya dapat mengunjungi website resmi git [klik disini.](https://git-scm.com/download/linux)

- Windows
  - Kunjungi website resmi git [klik disini.](https://git-scm.com/download/win)
  - Kemudian pilih dan download sesuai tipe sistem yang digunakan oleh windows (32 bit atau 64 bit).
  - Lakukan prosedur instalasi software hingga selesai.

## Konfigurasi Akun
Akun perlu ditambahkan sebagai pengenal ketika kita melakukan commit. Untuk konfigurasi akun sendiri terdiri dari lokal dan global.

konfigurasi lokal digunakan untuk mengatur pengenal pada penggunaan git secara lokal, ketika kita mengelola project secara mandiri/offline di komputer pribadi:
```bash
# Konfigurasi akun secara lokal
$ git config --lokal user.name "nama"
$ git config --lokal user.email "email"
```

konfigurasi global digunakan untuk mengatur pengenal pada penggunaan git secara global yang artinya pada konfigurasi global digunakan ketika kita mengembangkan project secara kelompok di repository yang terdapat pada remote / git server:
```bash
# Konfigurasi akun secara global
$ git config --global user.name "nama"
$ git config --global user.email "email"
```
*Note:* Perintah `git config` secara umum digunakan untuk mengatur seluruh kofigurasi pada git.

## Konfigurasi Kode Editor
Git telah menyediakan kode editor bawaan bernama VIM untuk membantu kita menulis kode pada project. Namun akan lebih mudah jika kita dapat menggunakan kode editor lain sebagai kode editor utama, mungkin kode editor yang sering kita pakai seperti Visual Studio Code, Sublime Text, Atom, Notepad++, dll. Konfigurasinya dapat dilakukan dengan cara:

```bash
# Konfigurasi kode editor
$ git config --global core.editor "'paste direktori kode editor disini' -n -w "

# Contoh ketika saya menggunakan visual studio code
$ git config --global core.editor "'C:\Program Files (x86)\VSCode-win32-x64-1.40.2\Code.exe' -n -w "
```

Setelah mengatur kode editor yang kita inginkan sebagai kode editor utama, selanjutnya kita dapat memanggilnya dengan cara:

```bash
# Memanggil kode editor
$ git config --global -e
```

## Melihat Seluruh Konfigurasi
Untuk melihat seluruh konfigurasi yang telah di lakukan dapat menggunakan perintah berikut:

```bash
#Melihat seluruh konfigurasi
$ git config --list
```

## Membuat Repository
Pada dasarnya kita membutuhkan sebuah tempat untuk menyimpan seluruh data dan informasi mengenai project yang kita miliki. Git telah menyediakan tempat penyimpanan yang disebut sebagai Repository, ini adalah sebuah folder dimana seluruh data berupa file dan informasi penting mengenai project disimpan. untuk membuat repository kita perlu membuat sebuah folder yang di inisialisasi sebagai repository, lalu bagaimana caranya?.. 

Kita dapa menggunakan perintah `git init`, ini adalah perintah yang digunakan untuk menginisialisasi folder menjadi sebuah repository. Beberapa cara yang dapat dilakukan dengan perintah ini:

Membuat folder terlebih dahulu pada komputer kemudian masuk pada folder tersebut dan ketikan perintah git bash:
```bash
# Menginisialiasi folder yang sudah ada menjadi sebuah repository
$ git init .
```

Tentukan lokasi penyimpanan repository kemudian berikan perintah berikut pada git bash:
```bash
# Membuat folder sekaligus menginisialisasi menjadi sebuah repository
$ git init namaRepository

# Membuat folder untuk meletakan folder yang di inisialisasi sebagai repository  
$ git init namaFolder/namaRepository
```