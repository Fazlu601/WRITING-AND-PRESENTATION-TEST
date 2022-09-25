# **Writing and Presentation Test Week 1**
# **Day 1 : Unix Comand Line Interface & Git - GitHub**
## **Unix Comand Line**
**Pengertian Shell :** Shell adalah program yang dapat menerima perintah dari kita, lalu diteruskan ke system sehingga dapat menjadi suatu instruksi yang dapat menghasilkan suatu output.

### **Shell terbagi menjadi 2 tipe yaitu :** 

- Shell Berbasis Text : sh, bash, zsh, cmd.exe, windows powershell.
- Shell Berbasis Grapich / GUI : windows 10, ubuntu, macOs.

### **File System & Root Directory** :
<figure>
<img src="img/guiRoot.jpg" width="300" />
<figcaption>Tampilan File System dan Root Directory di GUI</figcaptiom>
</figure>
<figure>
<img src="img/cliRoot.jpg" width="300" />
<figcaption>Tampilan File System dan Root Directory di CLI</figcaptiom>
</figure>


### **Berikut Contoh Perintah yang sering dipakai pada Comand Line Interface :**
#### Navigasi
- `pwd`  : melihat directory saat ini yang sedang aktif berdasarkan root directory
- `cd <directory location>`  : berpindah directory berdasarkan current directory
- `ls`  : melihat isi directory
- `clear` : membersihkan terminal

#### File Manipulation
- `touch <name file.ekstention>`   : membuat file baru dengan ekstensi yang sudah ditentukan
- `cp <name file.ekstention> <location>`      : menduplikat file
- `mv <name file.ekstention> <location>`      : memindahkan file, selain itu bisa digunakan untuk rename
- `rm <name file.ekstention>`      : menghapus file secara permanen

#### Directory Manipulation
- `mkdir <name directory>`   : membuat directory baru
- `cp <name directory> <location>`      : menduplikat file atau directory
- `mv <name directory> <location>`      : memindahkan directory, selain itu bisa digunakan
- `rm <-d> <name directory>`      : menghapus directory secara permanen

#### Text
- `cat <name file.ekstention>` : melihat isi text dari keseluruhan file
- `nano <name file.ekstention>` : mengedit file

## **Git & GitHub**
### **Pengertian apa itu Git**
Git adalah Tools wajib bagi programmer yaitu sebagai Version Control System atau bisa disingkat dengan VCS yang berfungsi sebagai tools yang dapat merekam aktifitas source code kita ataupun 
melacak setiap perubahan 
yang terjadi pada folder ataupun file yang ada didalam projek yang biasa disebut dengan repositori.

### **Bedanya dengan GitHub?**
GitHub adalah merupakan manajemen project, sistem versioning code, sekaligus platform jaringan sosial bagi para developer seluruh dunia. Banyak sekali fungsi yang bisa digunakan oleh para developer, sehingga melalui platform ini memudahkan developer dalam mengembangkan sebuah karya.

GitHub juga memberikan layanan cloud untuk menyimpan dan mengelola project/repository git. Karena bersifat online, kita meng-edit sebuah repository/project secara bersamaan dengan orang lain di tempat yang berbeda. Oleh karena itu, platform ini sangat membantu tim project dalam menyusun suatu folder yang berisikan files terkait pemrograman.

### **Alur Kerja dari Git**
- Konfigurasi git
- Masukan perintah `git config global user.name <username>` untuk konfigurasi username
- Masukan perintah `git config global user.email <email>` untuk konfigurasi email
- Melihat hasil konfigurasi dengan `git config --list Config list`
- Tentukan directory yang ingin kita jadikan sebagai repositori dengan memberikan command `git init`
- Jika sudah kita jadikan sebagai repositori maka git dapat melacak setiap perubahan yang ada dalam repo directory
- Kita dapat mengecek tiap perubahan tersebut dengan memberi perintah `git status`  !["Working Area Git"!](/img/git-1.png)

- Jika setelah kita cek terdapat perubahan, kita dapat menyimpan perubahan tersebut ke dalam staging area sehingga perubahan tersebut siap kita commit
- Kita dapat menyimpan perubahan dengan melakukan commit dengan memberi command `git commit -m <pesan>` !["Working Area Git"!](/img/git-2.png)
 - Setelah kita berhasil melakukan commit, kita dapat mengupload perubahan yang terjadi di lokal repositori ke public atau cloud repositori yang ada di github, untuk dapat melakukan itu kita harus mempunyai akun github terlebih dahulu dan membuat repositori baru
 - Setelah berhasil membuat repositori, kita harus menambahkan remote terlebih dahulu agar repositori lokal kita dapat terhubung ke github, kita dapat menggunakan perintah `git remote add origin <link repo>`
 - Setelah berhasil menambahkan remote, kita dapat melakukan push ke repositori github dengan menggunakan perintah `git push -u origin <nama branch>`
 - Jika kita liat di repositori github maka akan terlihat kalau perubahan-perubahan yang kita lakukan sebelumnya di lokal berhasil berpindah!["Working Area Git"!](/img/git-push.png)

 Yang tadi itu adalah alur jika kita ingin membuat projek dari lokal dan ingin mengupload perubahan dari lokal ke public repositori, tapi bagaimana jika kita ingin mengambil projek dari github sehingga bisa kita jadikan sebagai lokal projek kita? 
 - Kita bisa mengkloning projek atau repositori dari github, caranya cukup dengan menyalin link dari repo yang kita inginkan lalu gunakan perintah `git clone <link repo>` pada terminal bash
 - Selain menggunakan perintah `git clone` kita juga bisa mengambil projek dengan melakukan perintah `git pull` untuk menarik tiap perubahan yang ada di repo !["Working Area Git"!](/img/git-pull.png)
# **Day 2 : HTML - Hypertext Markup Languange**
## **Pengertian HTML**
Hypertext Markup Languange atau singkatnya disebut HTMl adalah bahasa markup yang biasa digunakan untuk membuat struktur konten pada suatu website, HTML merupakan pondasi utama dalam membangun visual yang kita tampilkan pada antarmuka web browser.
## **Tools yang dapat digunakan untuk membuat HTML**
- Visual Studio Code
- Sublime Text
- Atom
- Notepad++
## **Anatomi pada HTML**
!["Anatomi HTML"!](img/anatomiHtml.jpg)

`<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Blog</title>
    <link href="coba.css" type="text/css" rel="stylesheet"/>
</head>
    <body>
        <div>
            <h1 class="header">Hi! This is my Blog</h1>
            <p>I love learning and sharing</p>
        </div>
    </body>
</html>`













