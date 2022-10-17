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
>tesssss

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
```
# **Day 2 Git & Github Lanjutan**


# **Day 3 Responsive Web Design & Bootstrap**
### **Responsive Web Design**
- **Responsive Web Desin** yaitu suatu tampilan website yang dapat menyesuikan dengan perangkat yang digunakan
- Chrome Dev Tools merupakan tools pada google chrome yang digunakan sebagai tools Responsive Web Design
- Untuk mengakses Chrome Dev Tools yaitu 
  > ctrl + shift + j
  > ctrl + shift + m digunakan untuk melihat toggle bar 
- Dalam menggunakan Responsive Web Design pada bagian HTML perlu ditambahkan **viewport** pada bagian head agar tampilan website dapat menyesuaikan dengan berbagai device
- Untuk membuat suatu gambar pada halaman website agar menjadi responsive dapat dilakukan dengan menambahkan atribut Max - width = 100% pada bagian gambar
- **Media Query** salah satu cara untuk mengatur suatu website agar bisa terdiri dari beberapa jenis 
- Penggunaan media query yang umum digunakan adalah min-width dan max-width
- Contoh penerapan media query 
  `` @media screen and (max-width: 500px)``
- Cara mengkondisikan Media Query ada 2 cara yaitu:
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
- Flexbox bertujuan untuk membuat website yang lebih efisien dalam mengatur, menata dan item pada dalam sebuah wadah bahkan ketika ukurannya tidak diketahui dan/atau dinamis (dengan menggunakan kata "flex").
- Flexbox properties :
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
  - Contoh :
  - ![align](https://user-images.githubusercontent.com/64596495/184914490-9233304c-402e-4a70-978d-c34cbd43b44e.JPG)
- Grid merupakan sistem tata letak berbasis dua dimensi.
- Pada Grid ada 2 jenis yaitu grid container dan grid item.


### **Bootstrap**
- Bootstrap adalah salah satu framework opensource yang berfungsi membuat suatu responsive website
- Komponen utama bootstrap :
  - bootstrap.css
  - bootstrap.js
- Cara konfigurasi bootstrap :
  - Membuat tag boostrap di head. Cara memanggil css bootstrap dengan menggunakan href lalu mengganti link href css lokal dengan link boostrap online.
- Contoh penggunaan content bootstrap :
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

- Kapan kita menggunakan bootstrap?
  - Boostrap digunakan ketika membuat website sederhana dan tidak memerlukan load lama
- Layout pada boostrap :
  - Breakpoints merupakan suatu cara yang dilakukan untuk membuat desain responsif dengan mengontrol kapan tata letak yang disesuaikan dengan ukuran perangkat
    tertentu.
    - Breakpoints pada bootstrap ada 5 yaitu sm, md, lg, xl dan xxl.
    - Setiap breakpoint dipilih untuk menampung container yang lebarnya 12 dengan sehingga tersusun rapi. Breakpoint juga mewakili subset ukuran perangkat umum dan
    dimensi area pandang.
 - Container adalah blok dasar atau pembungkus boostrap yang terdiri dari contain, pad dan align  yang menyelaraskan konten website dalam perangkat atau area      
    pandang tertentu.
   - Terdapat 3 container pada boostrap yaitu :
    - .container, yang menerapkan lebar maksimum pada setiap breakpoint responsif
    - .container-{breakpoint}, menerapkan lebar 100% sampai dengan breakpoint yang ditentukan.
    - .container-fluid, menerapkan 100% ukurannya dari breakpoints
 - Grid System pada bootstrap yang terdiri dari 12 kolom default.
 - Grid system pada bootstrap menggunakan container,baris dan kolom untuk menata dan menyelaraskan konten,yang dibangun menggunakan flexbox dan itu sudah responsive.
 
  - contoh penggunaan grid system
   ``` 
     <div class="container text-center">
     <div class="row">
      <div class="col">
        Column
      </div>
      <div class="col">
        Column
      </div>
      <div class="col">
        Column
      </div>
     </div>
     </div>
   ```
- Grid system bootstrap :
  - .col-lg digunakan untuk mengatur grid pada ukuran monitor yang besar
  - .col-md digunakan pada monitor komputer berukuran sedang
  - .col-sm digunakan untuk mengatur monitor pada tablet
  - .col-xs digunakan untuk mengatur monitor pada handphone 