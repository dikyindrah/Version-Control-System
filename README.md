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
  - [Membuat Dan Menempatkan Project Kedalam Repository](#Membuat-Dan-Menempatkan-Project-Kedalam-Repository)
  - [Memindahkan File Kedalam Staging Area](#Memindahkan-File-Kedalam-Staging-Area)
  - [Ignoring File](#Ignoring-File)
  - [Melakukan Commit](#Melakukan-Commit)
  - [Melihat Status Repository](#Melihat-Status-Repository)
  - [Melihat Riwayat Perubahan](#Melihat-Riwayat-Perubahan)
  - [Membuat Branch](#Membuat-Branch)
  - [Melakukan Checkout](#Melakukan-Checkout)
  - [Melakukan Merge](#Melakukan-Merge)
  - [Menghapus Branch](#Menghapus-Branch)
  - [Melakukan Rebase](#Melakukan-Rebase)
  - [Mempersingkat Perintah Git](#Mempersingkat-Perintah-Git)
  - [Membatalkan Perubahan 🔧](#Membatalkan-Perubahan)
  - [Menambahkan Remote 🔧](#Menambahkan-Remote)
  - [Melakukan Clone 🔧](#Melakukan-Clone)
  - [Melakukan Fetch Dan Pull 🔧](#Melakukan-Fetch-Dan-Pull)
  - [Melakukan Push 🔧](#Melakukan-Push)
  <!-- - [](#) -->
  
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

<!-- | []() | []() | []() | []() | []() |
|---|---|---|---|---|  -->

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

- *modified* : Ketika file sudah disimpan sebagai commit, namun pada file tersebut kembali dilakukan perubahan dan belum di commit.

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

## Membuat Dan Menempatkan Project Kedalam Repository
Agar project dapat dikelola dengan version control system, project harus ditempatkan kedalam repostiory. Lalu bagaimana caranya?...

Cara paling umum digunakan adalah dengan membuat repository terlebih dahulu kemudian membuat project dan menyimpannya kedalam repository yang telah dibuat.

## Memindahkan File Kedalam Staging Area
Seluruh file beserta perubahan yang telah dilakukan pada project di dalam repository perlu di pindahkan ke dalam staging area untuk ditandai agar dapat dipantau oleh git pada setiap perubahanya. perintah `git add` dapat digunakan dalam hal ini, beberapa cara yang dapat dilakukan:

```bash
# Memindahkan satu file yang ada pada working directory
$ git add namaFile

# Memindahkan Seluruh file yang ada pada working directory
$ git add .
```

## Ignoring File
Ignoring adalah sebuah cara yang digunakan untuk menabaikan file yang tidak ingin kita commit. Caranya adalah mendaftarkan nama atau extensi dari file - file tersebut ke sebuah file bernama `.gitignore`.

Nama atau extensi dari file yang sudah di daftarkan akan diabaikan oleh git meski berapapun kita melakukan commit. Dibawah ini adalah contoh ketika saya menggunakan `.gitignore` untuk mengabaikan file yang sebenarnya tidak ingin saya commit:

1. Membuat file bernama .gitignore dan menyimpannya kedalam direktory project.
2. Mendaftarkan nama atau extensi file yang tidak ingin di commit, kedalam file .gitignore.
   ```bash
   # Mengabaikan semua file berekstensi
   *.exe
   *.jar
   *.txt
   
   # Mengabaikan file berdasarkan nama
   project.class
   database.db
   file.*
   
   # Mengabaikan folder
   /folderku
   /folder01/folder02
   
   # Mengabaikan folder berserta file didalamnya
   /folderku/file.txt
   /folderku/*.jar

   # Mengabaikan dengan pengecualian
   ! /folderku
   ! index.html
   ```
3. Lakukan commit seperti biasa.

contoh diatas menggunakan cara manual, sebenarnya ada cara lain yang lebih mudah untuk dilakukan. Kita hanya perlu mengunjungi website yang menyediakan layanan untuk merekomendasikan file apa saja yang sebaiknya kita abaikan untuk project yang sedang kita kembangkan. 

Website penyedian layanan ignoring file:
- [gitignore.io](https://www.toptal.com/developers/gitignore)
- [github.com](https://github.com/github/gitignore)
- [salcode](https://gist.github.com/salcode/10017553)

## Melakukan Commit
Setelah perubahan pada project didalam repository telah di tandai, selanjutnya adalah melakukan commit untuk menyimpan perubahan yang telah dilakukan kedalam git directory. Kita dapat menggunakan perintah `git commit` untuk menyimpan perubahan tersebut. Cara yang dapat dilakukan adalah:

Ketika file atau project didalam repository baru pertama kali dibuat dan dipindahkan ke staging area untuk ditandai, gunakan perintah:
```bash
$ git commit -m "tuslis pesan berupa keterangan commit"

# Contoh ketika saya melakukan perubahan dengan menambahkan file baru bernama index.html pada project didalam repository
$ git commit -m "menambahkan file index.html pada project"
```
perintah tersebut dapat digunakan, tetapi setiap kali perubahan yang ingin kita commit harus kita masukan kedalam staging area terlebih dahulu kemudian commit dapat dilakukan dengan perintah tersebut.

Namun jika sebelumnya file atau project didalam repository sudah pernah dilakukan commit, yang artinya kita kembali melakukan perubahan pada file atau project tersebut. Maka kita dapat memindahkan ke staging area sekaligus melakukan commit menggunakan perintah berikut:
```bash
$ git commit -am "tuslis pesan berupa keterangan commit"

# Contoh ketika saya kembali melakukan perubahan dengan menambahkan struktur html pada file index.html yang sebelumnya sudah pernah saya commit
$ git commit -am "menambahkan struktur html pada file index.html"
```

## Melihat Status Repository
Setiap perubahan yang terjadi pada repository dapat dilihat dan dikontrol oleh pengguna git, ini akan membuat kita lebih mudah dalam mengetahui apa-apa saja yang telah terjadi pada project didalam repository, serta membantu kita dalam menentukan langkah apa yang selanjutnya perlu dilakukan. Perintah `git status` dapat digunakan untuk melihat status perubahan yang terjadi pada project didalam repository, pada git bash ketikan perintah:

```bash
# Melihat Status Repository
$ git status
```

## Melihat Riwayat Perubahan
Tidak hanya melihat status repositoy, tetapi kita juga dapat melihat riwayat perubahan atau history dari sebuah commit yang dilakukan oleh diri kita dan orang lain.

Perintah `git log` dapat kita gunakan untuk melihat seluruh riwayat perubahan project yang yang telah dilakukan, kemudian kita juga dapat menambahkan beberapa argumen untuk menampiilkan sesuatu yang lebih spesifik: 
```bash
# Melihat seluruh riwayat perubahan
$ git log --all

# Melihat 3 riwayat perubahan terakhir
$ git log -3

# Melihat riwayat perubahan berdasarkan nama orang
$ git log --author="nama orang yang melakukan commit"

# Melihat riwayat perubahan berdasarkan nama file
$ git log -- namaFile

# Melihat riwayat perubahan file yang telah dihapus
$ git log --diff-filter=D
```

Hal lain yang dapat kita lakukan adalah melihat seluruh riwayat perubahan yang ada dalam bentuk grafik bercabang, tentunya ini akan membuat kita lebih mudah dalam pemantauan  suadah sampai mana project yang telah dikembangkan.
```bash
# Melihat riwayat perubahan dengan grafik bercabang 
$ git log --all --decorate --oneline --graph
```

## Membuat Branch
Secara umum branch memiliki arti cabang. Pada git pembuatan branch digunakan untuk mengembangkan fitur baru pada project tetapi kita tidak ingin merusak atau menggangu file utama dari project, Kemudian pembuatan branch juga digunakan untuk membagi tugas ke setiap orang yang mengembangkan fitur pada pengembangan project secara kelompok di repository yang sama. 

Gunakan perintah `git branch` untuk membuat branch:
```bash
# Membuat Branch
$ git branch namaBranch
```

## Melakukan Checkout
Checkout memungkinkan kita untuk berpindah branch dan kembali ke keadaan project pada waktu tertentu.

Kita hanya perlu menggunakan perintah `git checkout` untuk memindahkan posisi HEAD -> (ini adalah tanda yang menunjukan posisi saat ini kita berada) ke branch atau keadaan yang kita inginkan:

```bash
# Berpindah branch
$ git checkout namaBranch

# Kembali pada keadaan project pada waktu tertentu
$ git checkout kodeHash
```

Perintah `git checkout` juga dapat digunakan untuk membuat branch sekaligus berpindah pada branch tersebut, tambahkan argumen berikut:

```bash
# Membuat branch sekaligus berpindah pada branch tersebut
$ git checkout -b namaBranch
```

## Melakukan Merge
Ketika telah berhasil menyelesaikan fitur, seseorang harus menyatukan branch dimana dia mengerjakan fitur tersebut ke branch utama (master). 

Hal yang perlu diperhatikan sebelum benar-benar melakukan merge adalah jalur penggabungan branch, pada git terdapat dua jalur penggabungan yaitu:

- *Fast Forward* : branch ini memliki jalur langsung dengan branch utama, jika menggabungakan branch pada jalur ini kedua branch akan tergabung menjadi satu tanpa membuat commit baru.

- *Tree Way Merging* : branch ini tidak memliki jalur langsung dengan branch utama, jika menggabungakan branch pada jalur ini kedua branch akan tergabung menjadi satu dengan membuat commit baru.

Lalu bagaimana cara menggabungkan branch?...

**Menggabungkan branch:**

1. Ketika sedang berada di branch yang gunakan untuk mengerjakan fitur, sebut saja sebagai branch feature, lakukan checkout atau berpindah branch terlebih dahulu ke branch master.
2. Selanjutnya gunakan perintah `git merge` dengan menambahkan nama branch yang ingin kita gabungkan ke branch master, yaitu branch feature:
   ```bash
   # menggabungkan branch
   $ git merge namaBranch
   
   # menggabugnkan branch feature ke branch master
   $ git merge feature
   ```
3. Jika tidak ada masalah maka branch feature secara otomatis akan menjadi satu dengan branch master.

Dalam melakakukan merge di sebuah branch pada project individu sebuah conflict/masalah akan jarang ditemukan. Berbeda jika kita melakukan merge pada project secara kelompok di repository yang sama, setiap orang yang bekerja pada repsoitory tersebut pastinya juga akan melakukan merge. 

Masalahnya adalah ketika perubahan yang kita lakukan bentrok dengan perubahan yang orang lain lakukan, misalnya ketika kita dan orang lain mengubah baris kode yang sama dan kemudian melakukan merge ke branch utama, secara otomatis akan terjadi sebuah confilict dan kita sebagai programmer harus menyelesaikannya. 

Cara menyelesaikan conflict tersebut adalah dengan memilih salah satu dari kedua kode program yang digabungkan, kita cukup menghapus salah satu kode dari kedua branch.

## Menghapus Branch
Selain membuat kita juga dapat menghapus branch yang kita miliki. Penghapusan branch sendiri memiliki dua kriteria yaitu branch yang telah di merge dan baranch yang belum di merge. lalu bagaimana cara kita mengetahi branch mana saja yang sudah di merge dan yang belum di merge jika kita memiliki branyak branch?. Guanakan perintah berikut:
```bash
# Mengetahui branch yang belum di merge
$ git branch --no-merged

# Mengetahui branch yang sudah di merge
$ git branch --merged
```

Setelah kita mengetahui kriteria branch yang akan di hapus, selanjutnya kita dapat menentukan perintah mana yang akan kita gunakan untuk menghapus branch tersebut:
```bash
# Menghapus branch yang telah di merge
$ git branch -d namaBranch

# Menghapus branch yang belum di merge
$ git branch -D namaBranch
```

## Melakukan Rebase
Rebase merupakan cara yang digunakan untuk memindahkan branch yang memiliki titik dimana saat ini bercabang ke titik terbaru dari branch untama.

Rebase digunakan untuk merapikan history commit atau riwayat perubahan pada branch yang ada di repository lokal dan belum di kirim ke remote / git server, rebase juga digunakan untuk mengupdate file project pada branch utama ketika branch yang sedang kita gunakan untuk mengembangkan fitur tertinggal beberapa commit.

Contoh penggunaan rebase:

1. Pastikan kita sedang berada pada branch yang tertingal dari branch utama, branch yang tertinggal sebut saja branch feature.
2. Dari branch feature akukan rebase ke branch utama dengan menggunakan perintah `rebase`
   ```bash
   # Melakukan rebase ke branch utama
   $ git rebase branchUatama
   ```
3. Setelah proses rebase selesai, lakukan checkout ke branch utama.
4. Dari branch utama lakukan merge ke branch feature.

*Note:* Rebase sebaiknya tidak digunakan pada branch yang sudah dipublikasikan ke remote / git server dan dipakai orang lain. 

## Mempersingkat Perintah Git
Mungkin seseorang akan membuat sebuah perintah yang panjang dengan menggabungkan berbagai argumen untuk keperluan yang lebih spesifik, hal ini akan sangat merepotkan jika kita harus mengetik dari awal untuk keperluan yang sama.

Pada kasus ini git telah menyediakan sebuah perintah `alias` untuk mempersingkat perintah yang panjang. Kita cukup memanggil nama singkatan dari perintah yang panjang untuk menggunakannya:
```bash
# Mempersingkat perintah git
$ alias namaSingkatPerintah = "perintah git yang panjang"

# Contoh ketika saya menyingkat perintah untuk menampilkan riwayat perubahan dengan grafik bercabang
$ alias riwayat = "git log --all --decorate --oneline --graph"

# Memanggil perintah riwayat
$ riwayat
```

*Note*: Penggunaan perintah `alias` hanya berlaku pada satu sesi saja dan tidak permanen.

## Membatalkan Perubahan
Perubahan yang telah dilakukana juga dapat dibatalkan, hannya saja kita perlu memperhatikan keadaan atau status perubahan yang terdapat pada project. Beberapa cara yang dapat dilakukan untuk membatalkan perubahan berdasarkan keadaan atau status perubahan pada project:

1. modified

   Keadaan modified pada dasarnya sama dengan `CTRL+S` saat kita menyimpan ketika selesai melakukan perubahan pada project. Jadi ketika kita ingin menembalikan project pada status modified, berarti samahalnya project dikembalikan ke keadaan sebelum disimpan. 

   Cara paling mudah adalah menggunakan kombinasi tombol CTRL+Z untuk melakukan undo atau menggunakan perintah `checkout`:

   ```bash
   # Membatalkan perubahan project pada status modified 
   $ git checkout namaFile
   ```
   Perintah `checkout` tidak hanya dapat digunakan untuk memindahkan HEAD dan membuat branch tetapi juga dapat digunakan untuk hal ini.

2. Staged

   Pembatalan pada keadaan menggunakan perintah `restore`. Ini akan mengembalikan project dari staging area ke git directory, dan akan membuat status perubahannya kembali menjadi modified. 
   ```bash
   # Membatalkan perubahan project pada status staged
   $ git restore --staged
   ```

3. Commited

   Status commited menandakan project sudah di commit dan tersimpan pada database, untuk membatalkan perubahan pada status perubahan ini dapat menggunakan dua cara:

   - Revert

     Revert membatalkan perubahan dengan cara mengambil perubahan pada titik dimana kita ingin kembali dan menggabungkannya dengan perubahan di titik saat ini, atau istilah lain yang lebih mudah adalah mengambil perubahan di masalalu kemudian menggabungkannya dengan perubahan yang ada di masadepan.

     **Contoh penggunaan revert:**
     1. Lihat riwayat perubahan kemudian copy kode hash pada titik perubahan yang ingin di ambil.
     2. Pastikan saat ini posisi HEAD berada di titik yang mengalami kesalahan.
     3. Pada git bash ketikan perintah `revert` untuk membatalkan perubahan:
        ```bash
        # Membatalkan perubahan menggunakan revert
        $ git revert kodeHash
        ```
     4. Perbaiki jika terdapat conflict dan kemudan simpan CTRL+S.
     5. Cek status perubahan kemudian pindahkan kedalam staging area.
     6. Lakukan commit.

   - Reset

     Reset membatalkan perubahan dengan cara kembali pada titik sebelum mengalami kesalahan serta menghapus seluruh riwayat perubahan pada titik yang mengalami kesalahan secara permanen. 

     Pada reset, developer diberikan tiga pilihan argumen, untuk mengembalikan project pada status tertentu:
     - *mixed* : Kembali pada status modified.
     - *soft* : Kembali pada status staged.
     - *hard* : Kembali pada status commited.

     tiga argumen tersebut dapat digunakan sesuai kebutuhan yang kita perlukan.

     **Contoh penggunaan reset:**
     1. Lihat riwayat perubahan kemudian copy kode hash pada titik perubahan yang ingin di ambil.
     2. Pastikan saat ini posisi HEAD berada di titik yang mengalami kesalahan.
     3. Pada git bash ketikan perintah `reset` untuk membatalkan perubahan:
        ```bash
        # Membatalkan perubahan menggunakan reset
        $ git reset --argumen kodeHash
   
        # Kembali pada status modified
        $ git reset --mixed kodeHash

        # Kembali pada status staged
        $ git reset --soft kodeHash

        # Kembali pada status commited
        $ git reset --hard kodeHash
        ```

     4. tandai perubahan lalu lakukan commit jika kembali pada status modified, cukup lakukan commit jika kembali pada status staged, dan tidak perlu melakukan apapun jika kembali pada status commited karena file sudah ditandai dan disimpan kedalam database.

     5. Lakukan push pada remote / git server di branch tertentu:
        ```bash
        # Melakukan push pada remote / git server di branch tertentu
        $ git push -f namaRemote namaBranch
   
        # Melakukan push pada remote (origin) di branch (master)
        $ git push -f origin master
        ```



