# **Writting & Presentation Week 4**
# **Day 1 Async Await**
## **Apa itu Async await ?**
Async await merupakan fitur baru JavaScript yang hadir sejak ES2017, async await merupakan suatu handler atau function khusus yang dapat menangani proses asyncronus yang bekerja dengan cara menunda eksekusi hingga proses asynchronous selesai.

## **Fetch**
merupakan cara baru dalam melakukan network request yang memanfaatkan sebuah Promise dalam penggunaanya. Karen Fetch mengembalikan sebuah Promise maka respon handling yang digunakan adalah then jika promise mengembalikan resolve dan catch jika promise mengembalikan nilai reject.

### **Contoh Penggunaan Async Await :**
```
//Async await dengan declaration function
async function getData() {
    let url = 'https://digimon-api.vercel.app/api/digimon';
    let response = await fetch(url);
    let data = await response.json();
    console.log(data);
}

getData();

//Async await dengan arrow function
const getData = async () => {
     let url = 'https://digimon-api.vercel.app/api/digimon';
    let response = await fetch(url);
    let data = await response.json();
    console.log(data);
}

getData();
```
>Pertama dari contoh yang ada diatas, kita membuat function seperti biasa, yang membedakan disini adalah kita menambahkan keyword async didepannya yang berarti itu membuat function tersebut dianggap sebagai asyncronus function, dan dengan begitu kita bisa memanggil keyword await di dalamnya sebagai pengganti .then().

### **Contoh implementasi dari async await :**
```
const getData = async () => {
     let url = 'https://digimon-api.vercel.app/api/digimon';
    let response = await fetch(url);
    let data = await response.json();
    return data;
}

getData().then( data => {
    renderData(data);
} )

const renderData = (data) => {
    data.forEach( item => {
        let card = `<p>${item.name}</p>
                    <p>${item.level}</p>
                    <hr>`;
        document.body.insertAdjacentHTML("afterbegin", card);
    } );
}

//Output : Menampilkan data digimon dari hasil looping array of object yang didapat dari API.
```
<br>

# **Day 2 Git & Github Lanjutan**
Perlu diingat kalau programmer yang ada di seluruh penjuru dunia memanfaatkan git & github bukan hanya sebagai alat bantu penyimpanan source code, melainkan juga sebagai alat bantu yang memungkinkan kita untuk berkolaborasi dengan tim.
### **Bagaimana cara kita berkolaborasi ?**
- **Branch :** Dengan memanfaatkan fitur git yaitu branch, kita dapat membagi pekerjaan berdasarkan fitur yang kita ingin buat dengan anggota-anggota lainnya.

- **Pull Request :** Setelah kita berhasil membuat branch dan merasa yakin jika hasil yang kita buat sudah sesuai, pasti biasanya kita akan melakukan git push untuk mengirimkan perubahan terhadap branch kita ke remote repository, lalu saat perubahan sudah sampai ke github kita bisa memanfaatkan pull request untuk dapat mengirimkan request agar code yang kita buat dapat di review lebih lanjut oleh team leader.
- **Merge :**
Jika tidak terjadi conflict dan pull request kita sudah diterima oleh team leader, kita bisa melakukan merge untuk menggabungkan perubahan yang ada pada branch yang kita buat sebelumnya ke dalam branch dev sebagai branch utama yang biasa digunakan oleh grup project dalam tahap development.

### **Contoh command :**
- `git branch <nama branch>` : Membuat branch baru.
- `git branch switch <nama branch>` : Berganti branch.
- `git branch -D <nama branch>` : menghapus branch.
- `git merge <nama branch>` : menggabungkan antar branch.

### **Kapan Conflict bisa terjadi ?**
<img src="https://user-images.githubusercontent.com/3016805/42661300-6855faac-85f3-11e8-948c-249ac49c45c8.png" width="500" />

>Conflict biasa terjadi jika ada 2 branch yang ingin melakukan merge dan memiliki code yang berbeda di baris yang sama, sehingga jika hal tersebut terjadi kita tidak dapat melakukan merge dan harus memperbaikinya terlebih dahulu dengan cara memilih baris code mana yang ingin digunakan.

<br>

# **Day 3 Responsive Web Design & Bootstrap**
## **Responsive Web Design**
### **Apa itu Responsive Web Design ?**
Yaitu adalah tampilan antarmuka web yang dapat menyesuaikan viewport dari masing-masing ukuran device yang berbeda, dan tentunya dengan tampilan yang tetap bagus dan menarik.

### **Bagaimana cara kita melihat website yang kita buat sudah responsive atau belum ?**
Kita bisa menggunakan Chrome Dev Tools pada google chrome yang digunakan sebagai tools Responsive Web Design.

### **Cara mengakses Chrome Dev Tools :**

  > ctrl + shift + j
  > ctrl + shift + m digunakan untuk melihat toggle bar 

- Dalam menggunakan Responsive Web Design pada bagian HTML perlu ditambahkan **viewport** pada bagian head agar tampilan website dapat menyesuaikan dengan berbagai device
- Untuk membuat suatu gambar pada halaman website agar menjadi responsive dapat dilakukan dengan menambahkan atribut Max - width = 100% pada bagian gambar
- **Media Query** salah satu cara untuk mengatur suatu website agar bisa terdiri dari beberapa jenis 
- Penggunaan media query yang umum digunakan adalah min-width dan max-width
### **Contoh penerapan media query :**
```
 @media screen and (max-width: 500px)
 ```
### **Cara mengkondisikan Media Query ada 2 cara yaitu:**
  - Memisahkan beberapa file css sesuai dengan tampilan device yang ingin dibuat 
  - Menggabungkan semua styling css device menjadi 1 
- Breakpoint yaitu istilah saat terjadi perubahan ukuran pada suatu website ketika berganti device
- Terdapat 3 jenis breakpoint yaitu desktop, tablet, dan mobile phone
- Penggunaan breakpoint pada media query dapat dilakukan dengan membuat range ukuran sesuai dengan tampilan device yang ingin dibuat
- Contoh breakpoint dapat ditulis seperti ini
  ```
  @media screen and (min-width: 500px) and (max-width: 700px) {
  body {
    background-color: grey 
    }
   }
  ```

### **Flexbox**
Flexbox bertujuan untuk membuat website yang lebih efisien dalam mengatur, menata dan item pada dalam sebuah wadah bahkan ketika ukurannya tidak diketahui dan/atau dinamis (dengan menggunakan kata "flex").
### **Flexbox properties :**
  - Flex direction : menetapkan sumbu utama item, sehingga menentukan arah item fleksibel ditempatkan di wadah fleksibel. 
    - Row : Kiri ke kanan
    - Row-Reverse : Kanan ke kiri
    - Column : Atas ke bawah
    - Column-Reverse : Bawah ke atas
  - Flex Wrap : Secara default, semua item pada flexbox akan mencoba berada dalam satu baris. Maka dengan flex wrap kita dapat mengubah hal tersebut.
    - nowrap : semua item flex akan berada dalam satu baris
    - wrap : item fkex akan membungkus ke beberapa baris, dari atas ke bawah.
    - wrap-reverse :item flex akan membungkus beberapa baris dari bawah ke atas.
  - Flex flow : cara singkat untuk properti flex-direction dan flex-wrap, yang bersama-sama menentukan sumbu utama dan sumbu silang container flex. Nilai default adalah baris nowrap.
  - Align items

 ### **Grid System** 
- Grid merupakan sistem tata letak berbasis dua dimensi.
- Pada Grid ada 2 jenis yaitu grid container dan grid item.


## **Bootstrap**
Bootstrap adalah salah satu framework css open source yang dapat membantu kita dalam membangun web responsif dengan cepat.
### **Komponen utama bootstrap** :
  - bootstrap.css
  - bootstrap.js
### **Cara konfigurasi bootstrap :**
  - Membuat tag boostrap di head. Cara memanggil css bootstrap dengan menggunakan href lalu mengganti link href css lokal dengan link boostrap online.
### ***Contoh penggunaan content bootstrap :***
  - CSS : bootstrap.min.css, bootstrap-grid.css, dll
  - JS : bootstrap.bundle.js, bootstrap.min.js, dll
- Komponen Bootstrap sebagian besar dibangun dengan base-modifier nomenclature.Contohnya mengelompokkan beberapa properti kedalam kelas dasar seperti .btn, seperti .btn-primary or .btn-success.
- Penggunaan theme color pada boostrap dapat menggunakan keyword berikut :
  ```
  $theme-colors: (
  "primary":    $primary,
  "secondary":  $secondary,
  "success":    $success,
  "info":       $info,
  "warning":    $warning,
  "danger":     $danger,
  "light":      $light,
  "dark":       $dark
  );
  ```

### **Kapan kita menggunakan bootstrap?**
Boostrap digunakan ketika membuat website sederhana dan tidak memerlukan load lama
### **Layout pada boostrap :**
Breakpoints merupakan suatu cara yang dilakukan untuk membuat desain responsif dengan mengontrol kapan tata letak yang disesuaikan dengan ukuran perangkat tertentu. Breakpoints pada bootstrap ada 5 yaitu sm, md, lg, xl dan xxl. Setiap breakpoint dipilih untuk menampung container yang lebarnya 12 dengan sehingga tersusun rapi. 
Breakpoint juga mewakili subset ukuran perangkat umum dan dimensi area pandang.

### **Container**
Container adalah blok dasar atau pembungkus boostrap yang terdiri dari contain yang berguna untuk menyelaraskan konten website dalam perangkat atau area pandang tertentu.

### **Terdapat 3 container pada boostrap yaitu :**
    - .container, yang menerapkan lebar maksimum pada setiap breakpoint responsif
    - .container-{breakpoint}, menerapkan lebar 100% sampai dengan breakpoint yang ditentukan.
    - .container-fluid, menerapkan 100% ukurannya dari breakpoints

 - Grid System pada bootstrap terdiri dari 12 kolom default.
 - Grid system pada bootstrap menggunakan container, row dan column.
 
  - contoh penggunaan grid system
   ``` 
     <div class="container text-center">
     <div class="row">
      <div class="col col-md col-xl">
        Column
      </div>
      <div class="col col-md col-xl">
        Column
      </div>
      <div class="col  col-md col-xl">
        Column
      </div>
     </div>
     </div>
   ```
### **Breakpoint Grid pada bootstrap :**
  - `.col-lg` : digunakan untuk mengatur grid layout pada monitor ukuran besar.
  - `.col-md` : digunakan pada layout komputer berukuran sedang.
  - `.col-sm` : digunakan untuk mengatur layout tablet.
  - `.col` : digunakan untuk mengatur layout handphone. 