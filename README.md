<h1 align='center'>
    Version Control System
</h1>

- ## Daftar Isi
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
  - [Melihat Perbandingan Pada Riwayat Perubahan](#Melihat-Perbandingan-Pada-Riwayat-Perubahan)
  - [Membuat Branch](#Membuat-Branch)
  - [Mengubah Nama Branch](#Mengubah-Nama-Branch)
  - [Melakukan Checkout](#Melakukan-Checkout)
  - [Melakukan Merge](#Melakukan-Merge)
  - [Menghapus Branch](#Menghapus-Branch)
  - [Melakukan Rebase](#Melakukan-Rebase)
  - [Mempersingkat Perintah Git](#Mempersingkat-Perintah-Git)
  - [Membatalkan Perubahan](#Membatalkan-Perubahan)
  - [Bekerja Dengan Remote Repsoitory](#Bekerja-Dengan-Remote-Repsoitory)
  - [Membuat Remote Repsoitory](#Membuat-Remote-Repsoitory)
  - [Melakukan Clone](#Melakukan-Clone)
  - [Melakukan Fetch Dan Pull](#Melakukan-Fetch-Dan-Pull)
  - [Melakukan Push](#Melakukan-Push)
  - [Berkontribusi Pada Sebuah Project Di Github](#Berkontribusi-Pada-Sebuah-Project-Di-Github)
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
Github adalah version control system berbasis web yang dapat digunakan untuk menyimpan project, mengelola project didalam repository, dan sebagai remote atau git server pada pengembangan project yang melibatkan orang banyak, ini digunakan untuk menyimpan repository secara online melalui layanan hos web di internet agar setiap orang dapat mengakses dan bekeja pada repository yang sama.

**Version control system berbasis web lain:**

| [<img width='190' src='https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png'>](https://github.com/) | [<img width='190' src='https://cdn.iconscout.com/icon/free/png-256/bitbucket-8-1175256.png'>](https://bitbucket.org/) | [<img width='190' src='https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/GitLab_Logo.svg/1108px-GitLab_Logo.svg.png'>](https://gitlab.com/explore) | [<img width='190' src='https://cdn.worldvectorlogo.com/logos/sourcetree-1.svg'>](https://www.sourcetreeapp.com/) |
|---|---|---|---|

## Area dan Keadaan File Pada Git
Git memiliki area dan beberapa keadaan file yang perlu diketahui. Hal ini akan memberikan gambaran tentang alur kerja penggunaan git.

**Area :**

- **Working Directory.** Ini adalah area diamana kita bekerja untuk mengembangkan project. pada area ini kita dapat menambah, mengubah isi, dan menghapus file pada project didalam repository.

- **Staging Area.** Area ini untuk menampung file - file beserta perubahan yang ingin kita commit (Rekaman perubahan (Snapshot) yang disimpan). File yang sudah masukan ke area ini akan dilacak atau ditandai untuk dipantau pada setiap perubahan yang terjadi. 

- **Git Directory.** Seluruh file beserta perubahannya disimpan pada area ini (database lokal git) sebagai commit.

**Keadaan File :**

- **Untracked.** File belum dimasukan ke staging area yang artinya file tersebut belum terlacak atau ditandai oleh git, dalam keadaan ini apapun yang terjadi pada file tersebut akan diabaikan oleh git.

- **modified.** Ketika file sudah disimpan sebagai commit, namun pada file tersebut kembali dilakukan perubahan dan belum di commit.

- **Staged.** File beserta perubah yang telah dilakukan sudah dimasukan ke staging area dan file tersebut sudah ditandai oleh git untuk dipantau setiap perubahannya.

- **Commited.** Keadaan ini menunjukan bahwa file beserta perubahannya sudah di commit dan sudah dismpan pada database git.

## Instalasi Git
- Linux
  - Instalasi git dengan linux selengkapnya dapat mengunjungi halaman resmi git **[https://git-scm.com/download/linux.](https://git-scm.com/download/linux)**

- Windows
  - Kunjungi halaman resmi git **[https://git-scm.com/download/win.](https://git-scm.com/download/win)**
  - Kemudian pilih dan download sesuai tipe sistem yang digunakan oleh windows (32 bit atau 64 bit).
  - Lakukan prosedur instalasi software hingga selesai.

## Konfigurasi Akun
Akun perlu ditambahkan sebagai pengenal ketika kita melakukan commit. Untuk konfigurasi akun sendiri terdiri dari lokal dan global.

Konfigurasi lokal digunakan untuk mengatur pengenal pada penggunaan git secara lokal, ketika kita mengelola project secara individu atau offline di komputer pribadi. Pada git bash berikan perintah:
```bash
# Konfigurasi akun secara lokal
$ git config --lokal user.name "nama"
$ git config --lokal user.email "email"
```

Konfigurasi global digunakan untuk mengatur pengenal pada penggunaan git secara global yang artinya pada konfigurasi ini digunakan ketika kita mengembangkan project di repository yang terdapat pada remote / git server bersama oran lain. Pada git bash berikan perintah:
```bash
# Konfigurasi akun secara global
$ git config --global user.name "nama"
$ git config --global user.email "email"
```
**Note:** Perintah `git config` secara umum digunakan untuk mengatur seluruh kofigurasi pada git.

## Konfigurasi Kode Editor
Git telah menyediakan kode editor bawaan bernama VIM untuk membantu kita menulis kode pada project. Namun akan lebih mudah jika kita dapat menggunakan kode editor lain sebagai kode editor utama, mungkin kode editor yang sering kita pakai seperti Visual Studio Code, Sublime Text, Atom, Notepad++, dll. Konfigurasi kode editor dapat dilakukan dengan cara:
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

Membuat folder terlebih dahulu pada komputer kemudian masuk pada folder tersebut dan berikan perintah berikut pada git bash:
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
# Memindahkan satu file yang ada pada working direktori
$ git add namaFile

# Memindahkan Seluruh file yang ada pada working direktori
$ git add .
```

## Ignoring File
Ignoring adalah sebuah cara yang digunakan untuk menabaikan file yang tidak ingin kita commit. Caranya adalah dengan menuliskan nama atau extensi dari file - file tersebut ke sebuah file bernama `.gitignore`.

Nama atau extensi dari file yang sudah di daftarkan akan diabaikan oleh git meski berapapun kita melakukan commit. Dibawah ini adalah contoh ketika saya menggunakan `.gitignore` untuk mengabaikan file yang sebenarnya tidak ingin saya commit:

1. Membuat file bernama .gitignore dan menyimpannya kedalam direktori project.
2. Menuliskan nama atau extensi file yang tidak ingin di commit, kedalam file .gitignore.
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
- **[https://www.toptal.com/developers/gitignore](https://www.toptal.com/developers/gitignore)**
- **[https://github.com/github/gitignore](https://github.com/github/gitignore)**
- **[https://gist.github.com/salcode/10017553](https://gist.github.com/salcode/10017553)**

## Melakukan Commit
Setelah perubahan pada project didalam repository telah di tandai, selanjutnya adalah melakukan commit untuk menyimpan perubahan yang telah dilakukan kedalam git direktori. Kita dapat menggunakan perintah `git commit` untuk menyimpan perubahan tersebut. Cara yang dapat dilakukan adalah:

Ketika file atau project didalam repository baru pertama kali dibuat dan dipindahkan ke staging area untuk ditandai, gunakan perintah:
```bash
$ git commit -m "tuslis pesan berupa keterangan commit"

# Contoh ketika saya melakukan perubahan dengan menambahkan file baru bernama index.html pada project didalam repository
$ git commit -m "menambahkan file index.html pada project"
```
perintah tersebut dapat digunakan, tetapi setiap kali perubahan yang ingin kita commit harus kita masukan kedalam staging area terlebih dahulu kemudian commit dapat dilakukan dengan perintah tersebut.

Jika sebelumnya file atau project didalam repository sudah pernah dilakukan commit, yang artinya kita kembali melakukan perubahan pada file atau project tersebut. Maka kita dapat memindahkan ke staging area sekaligus melakukan commit menggunakan perintah berikut:
```bash
$ git commit -am "tuslis pesan berupa keterangan commit"

# Contoh ketika saya kembali melakukan perubahan dengan menambahkan struktur html pada file index.html yang sebelumnya sudah pernah saya commit
$ git commit -am "menambahkan struktur html pada file index.html"
```

## Melihat Status Repository
Setiap perubahan yang terjadi pada repository dapat dilihat dan dikontrol oleh pengguna git, ini akan membuat kita lebih mudah dalam mengetahui apa-apa saja yang telah terjadi pada project yang ada didalam repository, serta membantu kita dalam menentukan langkah apa yang selanjutnya perlu dilakukan. Perintah `git status` dapat digunakan untuk melihat status perubahan yang terjadi pada project didalam repository, pada git bash ketikan perintah:
```bash
# Melihat Status Repository
$ git status
```

## Melihat Riwayat Perubahan
Tidak hanya melihat status repositoy, tetapi kita juga dapat melihat riwayat perubahan atau history dari sebuah commit yang kita lakukan dan orang lain.

Perintah `git log` dapat kita gunakan untuk melihat seluruh riwayat perubahan project yang yang telah dilakukan, kemudian kita juga dapat menambahkan beberapa argumen untuk menampiilkan sesuatu yang lebih spesifik. Beberapa cara yang dapat dilakukan: 
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

Hal lain yang dapat kita lakukan adalah melihat seluruh riwayat perubahan yang ada dalam bentuk grafik bercabang, tentunya ini akan membuat kita lebih mudah dalam memantau perkembangan project yang telah dilakukan.
```bash
# Melihat riwayat perubahan dengan grafik bercabang 
$ git log --all --decorate --oneline --graph
```
## Melihat Perbandingan Pada Riwayat Perubahan
Selain melihat riwayat perubahan, kita juga bisa melihat perbandingan pada setiap perubahan yang kita lakukan. Kita dapat menggunakan perintah `git diff` untuk memperlihatkan perbandingan file pada keadaan sebelum diuabah dan pada keadaan setelah diubah.

**Melihat riwayat perbandingan:**
1. Lihat riwayat perubahan menggunakan perintah `git log`, kemudian tentukan dua riwayat perubahan yang ingin dibangingkan.
2. Copy kode hash dari dua riwayat perubahan tersebut.
3. Pada git bash berikan perintah:
   ```bash
   # Melihat perbandingan pada riwayat perubahan
   $ git diff kodeHashA kodeHashB
   ```
4. Akan terlihat perbandingan file pada keadaan sebelum diuabah (-) dan pada keadaan setelah diubah (+).

## Membuat Branch
Secara umum branch memiliki arti cabang. Pada git pembuatan branch digunakan untuk mengembangkan fitur baru pada project tetapi kita tidak ingin merusak atau menggangu file utama dari project, Kemudian pembuatan branch juga digunakan untuk membagi tugas ke setiap orang yang bekerja pada pengembangan project skala besar di repository yang sama. 

Gunakan perintah `git branch` untuk membuat branch:
```bash
# Membuat Branch
$ git branch namaBranch
```

## Mengubah Nama Branch
Jika nama branch yang kita buat dirasa kurang pas atau ada penulisan nama branch yang salah, kita dapat mengubahnya dengan cara:
```bash
# Jika posisi HEAD berada pada branch lain
$ git branch -m namaBranchLama namaBranchBaru

# Jika posisi HEAD berada pada branch yang kita ingin ubah namanya
$ git branch -m namaBranchBaru
```

Untuk mengubah nama branch yang ada pada remote repository atau git server:
```bash
$ git push origin :namaBranchLama namaBranchBaru
```
atau
```bash
$ git push origin :namaBranchBaru
```

## Melakukan Checkout
Checkout memungkinkan kita untuk berpindah branch dan kembali ke keadaan project pada waktu tertentu.

Kita hanya perlu menggunakan perintah `git checkout` untuk memindahkan posisi HEAD -> (ini adalah tanda yang menunjukan posisi saat ini kita berada) ke branch atau keadaan yang kita inginkan. Pada git bash berikan perintah:
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

- **Fast Forward.** Branch ini memliki jalur langsung dengan branch utama, jika menggabungakan branch pada jalur ini kedua branch akan tergabung menjadi satu tanpa membuat commit baru.

- **Tree Way Merging.** Branch ini tidak memliki jalur langsung dengan branch utama, jika menggabungakan branch pada jalur ini kedua branch akan tergabung menjadi satu dengan membuat commit baru.

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

Dalam melakakukan merge di sebuah branch pada project individu sebuah conflict atau masalah akan jarang ditemukan. Berbeda jika kita melakukan merge pada project yang dikembangkan bersama orang lain dalam team di repository yang sama, setiap orang yang bekerja pada repsoitory tersebut pastinya juga akan melakukan merge. 

Masalahnya adalah ketika perubahan yang kita lakukan bentrok dengan perubahan yang orang lain lakukan, misalnya ketika kita dan orang lain mengubah baris kode yang sama dan kemudian melakukan merge ke branch utama, secara otomatis akan terjadi sebuah confilict dan kita sebagai programmer harus menyelesaikannya. 

Cara menyelesaikan conflict tersebut adalah dengan memilih salah satu dari kedua kode program yang digabungkan, kita cukup menghapus salah satu kode dari kedua branch.

## Menghapus Branch
Selain membuat kita juga dapat menghapus branch yang kita miliki. Penghapusan branch sendiri memiliki dua kriteria yaitu branch yang telah di merge dan baranch yang belum di merge. lalu bagaimana cara kita mengetahui branch mana saja yang sudah di merge dan yang belum di merge jika kita memiliki branyak branch?. Guanakan perintah berikut pada git bash:
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

Kemudian jika memiliki branch yang sudah di push ke remote / git server, dapat menghapusnya dengan cara:
```bash
# Menghapus branch yang ada pada remote
$ git push namaRemote --delete namaBranch
   
# # Menghapus branch (feature) yang ada pada remote (origin)
$ git push origin --delete feature
```

## Melakukan Rebase
Rebase merupakan cara yang digunakan untuk memindahkan branch yang memiliki titik dimana saat ini bercabang ke titik terbaru dari branch untama.

Rebase digunakan untuk merapikan history commit atau riwayat perubahan pada branch yang ada di repository lokal dan belum di kirim ke remote repositoy atau git server, rebase juga digunakan untuk memperbarui file project pada branch utama ketika branch yang sedang kita gunakan untuk mengembangkan fitur tertinggal beberapa commit.

**Contoh penggunaan rebase:**
1. Pastikan kita sedang berada pada branch yang tertingal dari branch utama, branch yang tertinggal sebut saja branch feature.
2. Dari branch feature akukan rebase ke branch utama dengan menggunakan perintah `git rebase`
   ```bash
   # Melakukan rebase ke branch utama
   $ git rebase branchUatama
   ```
3. Setelah proses rebase selesai, lakukan checkout ke branch utama.
4. Dari branch utama lakukan merge ke branch feature.
5. Lakukan push pada remote / git server di branch tertentu:
   ```bash
   # Melakukan push pada remote / git server di branch tertentu
   $ git push namaRemote namaBranch
   
   # Melakukan push pada remote (origin) di branch (master)
   $ git push origin master
   ```

**Note:** Rebase sebaiknya tidak digunakan pada branch yang sudah dipublikasikan ke remote / git server dan dipakai orang lain. 

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

**Note:** Penggunaan perintah `alias` hanya berlaku pada satu sesi saja dan tidak permanen.

## Membatalkan Perubahan
Perubahan yang telah dilakukan juga dapat dibatalkan, hannya saja kita perlu memperhatikan keadaan atau status perubahan yang terdapat pada project. Beberapa cara yang dapat dilakukan untuk membatalkan perubahan berdasarkan keadaan atau status perubahan pada project:

- Modified

Keadaan modified pada dasarnya sama dengan `CTRL+S` saat kita menyimpan ketika selesai melakukan perubahan pada project. Jadi ketika kita ingin menembalikan project pada status modified, berarti samahalnya project dikembalikan ke keadaan sebelum disimpan. 

Cara paling mudah adalah menggunakan kombinasi tombol CTRL+Z untuk melakukan undo atau menggunakan perintah `git checkout`:
```bash
# Membatalkan perubahan project pada status modified 
$ git checkout namaFile
```
Perintah `git checkout` tidak hanya dapat digunakan untuk memindahkan HEAD dan membuat branch tetapi juga dapat digunakan untuk hal ini.

- Staged

Pembatalan pada keadaan menggunakan perintah `git restore`. Ini akan mengembalikan project dari staging area ke git direktori, dan akan membuat status perubahannya kembali menjadi modified. 
```bash
# Membatalkan perubahan project pada status staged
$ git restore --staged
```

- Commited

Status commited menandakan project sudah di commit dan tersimpan pada database, untuk membatalkan perubahan pada status perubahan ini dapat menggunakan dua cara:

- Revert

Revert membatalkan perubahan dengan cara mengambil perubahan pada titik dimana kita ingin kembali dan menggabungkannya dengan perubahan di titik saat ini, atau istilah lain yang lebih mudah adalah mengambil perubahan di masalalu kemudian menggabungkannya dengan perubahan yang ada di masadepan.

**Contoh penggunaan revert:**
1. Lihat riwayat perubahan kemudian copy kode hash pada titik perubahan yang ingin di ambil.
2. Pastikan saat ini posisi HEAD berada di titik yang mengalami kesalahan.
3. Pada git bash ketikan perintah `git revert` untuk membatalkan perubahan:
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
3. Pada git bash ketikan perintah `git reset` untuk membatalkan perubahan:
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
   
## Bekerja Dengan Remote Repsoitory
Remote Repository adalah ketika kita bekerja pada repository yang disimpan dan dikelola secara online melalui layanan git server seperti github, gitlab, bitbucket, dll. Repository yang dikelola secara remote, biasanya ditujukan untuk pengembangan project yang melibatkan banyak orang. Tujuannya agar semua orang dapat mengakses dan bekerja untuk mengembangkan project yang sama.

Untuk dapat bekerja dengan remote reposoitory kita perlu melakukan kloning repository dari git server ke komputer pribadi. Repository yang sudah dikloning akan terisimpan pada komputer pribadi dan akan terhubung pada remote saat kita bekeraja dengan repository tersebut.

Karena orang lain juga bekerja pada repostory yang sama, maka seluruh informasi mengenai riwayat perubahan orang lain dapat kita lihat dan orang lain juga dapat melihat informasi mengenai riwayat perubahan yang kita lakukan.

## Membuat Remote Repsoitory
Kita dapat membuat remote repository pada layanan git server seperti github, gitlab, bitbucket, dll. Namun sebelum itu kita harus terlebih dahulu membuat akun pada salah satu layanan git server tersebut, baru kemudian kita dapat membuat repository.

- Ada dua cara yang dapat dilakukan untuk membuat remote rempositoy: 
  - Membuat langsung repository di git server kemudian melakukan kloning repository yang telah dibuat tadi ke komputer pribadi.
  - Membuat repositoy pada komputer pribadi terlebih dahulu kemudian mengirimnya ke git server.

**Github**
- Cara pertama:
1. Kunjungi halaman **[https://github.com/](https://github.com/).**
2. Klik tanda `+` di bagian kanan atas navbar, lalu pilih *New repository*.
3. Pada menu *Create a new repository* pilih dan isi nama repository, deskripsi, privasi,initialize this repository with (**Pilih "Add a file README.md"**).
4. Jika sudah klik tombol `Create repository`
5. Buka git bash, kemudian kofigurasi akun secara global (gunakan username dan email yang sama dengan akun git server)
6. Tentukan direktori penyimpanan dan lakukan kloning dari git server ke komputer pribadi.

- Cara kedua:
1. Kunjungi halaman **[https://github.com/](https://github.com/).**
2. Klik tanda `+` di bagian kanan atas navbar, lalu pilih *New repository*.
3. Pada menu *Create a new repository* pilih dan isi nama repository, deskripsi, privasi,initialize this repository with (**Jangan pilih apapun!**).
4. Jika sudah klik tombol `Create repository`.
5. Tentukan direktori penyimpanan, kemudian buat folder dengan nama sama persis seperti nama repository yang telah dibuat di git server.
6. Buka git bash, kemudian kofigurasi akun secara global (gunakan username dan email yang sama dengan akun git server)
6. Pada git bash dan masuk ke folder tersebut, kemudian berikan perintah:
   ```bash
   $ echo "# namaFolder" >> README.md
   $ git init
   $ git add README.md
   $ git commit -m "pesan commit"
   $ git remote add origin https://github.com/dikyindrah/namaRepository.git
   $ git push -u origin master
   ``` 
7. Repository di komputer pribadi berhasil dikirim ke git server dan terhubung secara remote.
 
**Gitlab** 🔧

**Bitbucket** 🔧

## Melakukan Clone
Clone adalah ketika kita menduplikat remote repository yang ada pada git server ke komputer pribadi. Tujuanya agar kita memiliiki salinan repository sehingga kita dapat mengerjakan project di komputer pribadi, agar dapat terhubung dengan remote repository untuk mengirim perubahan yang kita dilakukan (push), dan mengambil serta memperbarui setiap perubahan project yang terjadi pada remote repository ke lokal repository (pull).

Kita dapat memilih salah satu dari dua cara yang dapat digunakan untuk melakukan clone. Kedua cara ini terkait dengan protokol yang akan digunakan yaitu HTTPS (Hypertext Transfer Protocol Secure) dan SSH (Secure Shell). Pertanyaannya adalah kapan kita harus menggunakan HTTPS dan SSH untuk melakukan clone?

- **HTTPS**. Beberapa layanan git server merekomendasikan clone menggunakan HTTPS untuk penggunaan umum karena lebih mudah untuk digunakan. Namun dari segi keamanan HTTPS masih banyak kekurangan, tapi bukan berati tidak aman sama sekali hanya saja tidak disarankan pada pengemabangan project skala besar di perusahaan.

- **SSH**. Clone menggunakan SSH banyak digunakan programmer yang bekerja di perusahaan besar, karena penggunaan algoritma kriptografi pada setiap pertukaran data yang dilakukan sehingga memiliki tingkat keamanan yang lebih tinggi.

**Kesimpulan:** Jika kita hanya mengembangkan project pribadi lebih baik clone menggunakan HTTPS, namun jika kita bekerja pada sebuah perusahaan dan mengembangkan project skala besar bersama orang - orang yang terlibat didalamnya lebih baik clone menggunakan SSH.

**Melakukan clone:**

**GitHub**
- **HTTPS**

1. Kunjungi halaman **[https://github.com/](https://github.com/)**, kemudian buat repository.
2. Pada repository klik menu `Code` kemudian pilih *Use HTTPS*.
3. Copy url yang ada pada menu *Clone with HTTPS*.
4. Di komputer pribadi, tentukan direktori penyimpanan kemudian buka git bash dan berikan perintah:
   ```bash
   # Melakukan clone dengan protokol https
   $ git clone urlRemote

   $ git clone https://github.com/dikyindrah/namaRepository.git
   ```
5. Tunggu hingga seluruh file project beserta repsotory selesai di unduh.

- **SSH**

**STEP 1: Membuat SSH Key**
1. Buka git bash, kemudian masuk ke direktori konfigurasi ssh bernama `.ssh` dengan mengetikan perintah berikut:
   ```bash
   # Masuk ke direktory konfigurasi ssh
   $ cd ~/.ssh

   # Atau
   $ cd C:/Users/namaUsers/.ssh
   ```
2. Buat SSH Key pada direktori tersebut dengan perintah:
   ```bash
   # Membuat SSH Key
   $ ssh-keygen -o

   # Atau
   $ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```
3. Cek apakah file SSH Key yang dibuat tadi sudah tersimpan di dalam direktori `.ssh` menggunakan perintah `$ ls`.
4. Tampilkan dan kemudian copy public key *.pub yang telah dibuat menggunakan perintah `cat`:
   ```bash
   # Menampilkan public key yang telah dibuat
   $ cat fileKamu.pub

   # Atau jika diluar direktori .ssh
   $ cat ~/.ssh/fileKamu.pub
   ```  

**STEP 2: Menambahkan Public Key kedalam Pengaturan Github**
1. Buka pengaturan SSH Keys pada akun github **[https://github.com/settings/ssh/new](https://github.com/settings/ssh/new).**
2. Beri tittle sesuai nama file public key dan paste public key yang telah di copy tadi.
3. Klik tombol *Add SSH Key*.

**STEP 3: Menambahkan key kedalam ssh-agen**
1. Masih pada direktori `.ssh`, jalankan ssh-agen menggunakan perintah berikut:
   ```bash
   # Menjalankan ssh-agen
   $ eval `ssh-agent -s`
   ```
   **Note:** Ssh-agen hanya berlaku satu sesi, artinya ssh-agen perlu dijalankan setiap kali membuka git saat bekerja pada project yang di clone melalui SSH.
2. Cek apakah ssh-agen sudah berjalan:
   ```bash
   # Mengecek apakah ssh-agen sudah berjalan
   $ ps -e | grep [s]sh-agent
   ```
3. Menambahkan private key kedalam ssh-agen:
   ```bash
   # Menambahkan private key kedalam ssh-agen
   $ ssh-add ~/.ssh/fileKamu
   ```
   **Note:** Private key tidak memiliki ekstensi file seperti public key *.pub.
4. Periksa apakan private key berhasil di tambahkan ke ssh-agen:
   ```bash
   # Memeriksa apakah private key berhasil di tambahkan ke ssh-agen
   $ ssh-add -l
   ```

**STEP 4: Melakukan Clone**
1. Kunjungi halaman **[https://github.com/](https://github.com/)**, kemudian buat repository.
2. Pada repository klik menu `Code` kemudian pilih *Use SSH*.
3. Copy url yang ada pada menu *Clone with SSH*.
4. Jika masih di direktori `.ssh`, pindah dan tentukan direktori lain untuk menyimpan repository yang akan di kloning.
5. Lakukan clone:
   ```bash
   # Melakukan clone menggunakan ssh
   $ git clone git@github.com:dikyindrah/namaRepository.git
   ```
6. Tunggu hingga proses selesai.
7. Masuk kedalam repostory untuk mengelola project.

## Melakukan Fetch Dan Pull
Fetch dan pull adalah dua cara yang digunakan untuk mengambil perubahan yang terjadi pada remote repository, kedua cara ini sebenarnya memiliki kegunaan yang sama tetapi memiliki prilaku yang berbeda, fetch mengambil informasi perubahan sedangkan pull mengambil perubahan.

- **Fetch** 

  Mengambil seluruh informasi mengenai perubahan yang terjadi pada remote repository. fetch dapat dilakukan di branch manapun, karena pada dasarnya fetch hanya mengambil informasi saja. Pada git bash berikan perintah:
  ```bash
  # Melakukan fetch
  $ git fetch namaRemote

  $ git fetch origin
  ```

- **Pull** 

  Mengambil seluruh perubahan pada remote repository untuk memperbarui repository yang ada di lokal. Kita perlu pindah ke branch master terlebih dahulu untuk melakukan pull, karena jika tidak maka baranch master akan merge ke branch dimana saat ini kita berada. Pada git bash berikan perintah:
  ```bash
  # Melakukan pull
  $ git pull namaRemote namaBranch

  $ git pull origin master
  ```

## Melakukan Push
Push adalah cara yang digunakan untuk mengirim perubahan project yang telah di commit pada repostory lokal ke remote repository. Untuk melakukan push pada git bash berikan perintah:
```bash
# Mengirim perubahan yang ada di lokal ke remote
$ git push namaRemote namaBranch

# Mengirim perubahan pada remote origin di branch master
$ git push origin master

# Mengirim perubahan pada remote origin di branch feature
$ git push origin feature
```
## Berkontribusi Pada Sebuah Project Di Github
Github sudah seperti rumah bagi programmer di seluruh dunia, mereka menyimpan dan mengelola project mereka disini secara pribadi maupun saling berkontribusi satu sama lain.

Untuk dapat berkontribusi pada sebuah project di github, hal pertama yang perlu diperhatikan adalah peraturan untuk melakukan kontribusi pada project tersebut. Biasanya seluruh peraturan disimpan pada sebuah file markdown bernama CONTRIBUTING.md atau README.md .

Kita perlu memahami serta mematuhi peraturan tersebut agar kontribusi yang kita berikan diterima oleh pemilik project.

**Melakukan Kontribusi:**

**STEP 1: Persiapan**

Beberapa hal yang perlu dipersiapkan:
1. Git
2. Akun github
3. Kode Editor

**STEP 2: Mengirim Kontribusi**

1. Kunjungi halaman github **[https://github.com/](https://github.com/)**, kemudian login dengan akun pribadi.
2. Masuk ke alamat github repostory yang ingin kita kontribusi.
3. Lakukan fork pada repository tersebut ke akun github pribadi.
4. Buka repository yang telah di fork.
5. Tentukan direktori penyimpanan kemudian lakukan clone repository ke komputer lokal.
6. Lakukan perubahan dengan membuat branch baru, kemudain commit dan push perubahan pada branch tersebut ke repository yang ada di akun github pribadi.
7. Masuk ke repository akun github pribadi dan lakukan "Pull request" ke repository yang kita kontribusi untuk mengajukan perubahan yang telah kita lakukan.
8. Tunggu hingga perubahan yang kita ajukan di rivew dan di setujui oleh pemilik repository yang kita kontribusi.
9. Jika disetujui maka akan ada pemberitahuan pesan bahwa perubahan yang telah kita lakukan diterima dan telah di merge ke repository yang kita kontribusi, jika tidak disetujui kemungkinan terdapat beberapa kekurangan dari perubahan yang kita lakukan dan biasanya kita diminta untuk memperbaiki kekurangan tersebut kemudian mengirimkannya kembali.

**STEP 3: Mengupdate Repostiory**

1. Tambahkan remote satu lagi dari repository yang kita kontribusi dengan cara masuk kembali ke alamat github repostory tersebut, kemudian copy url clone repository tersebut.
2. Pada git bash berikan perintah `git remote add` untuk menambahkan remote baru:
   ```bash
   # Menambahkan remote baru
   $ git remote add namaRemote urlRemote

   # Contoh
   $ git remote add github https://github.com/namaAkun/namaRepository.git
   ```
3. Periksa remote menggunakan perintah `git remote`, ini untuk memastikan apakah remote sudah berhasil terhubung:
   ```bash
   # Menampilkan daftar nama remote yang terhubung
   $ git remote

   # Menampilkan daftar nama remote yang terhubung beserta url remote
   $ git remote -v
4. Lakukan fetch ke repository yang kita kontribusi untuk mengambil informasi perubahan terbaru.
   ```bash
   # Melakukan fetch ke repository yang kita kontribusi
   $ git fetch namaRemote

   # Contoh 
   $ git fetch github
   ```
5. Cek menggunakan perintah `git log` untuk melihat informasi perubahan terbaru.
6. Lakukan push informasi yang telah kita fetch dari repostiory yang kita kontribusi ke repository yang ada di akun github pribadi.
7. Hapus branch yang sudah tidak terpakai baik yang ada di repository lokal maupun repostory di github pribadi.

Referensi: **[https://www.petanikode.com/github-workflow/](https://www.petanikode.com/github-workflow/)**