# **Writting & Presentation Test Week 3**
# **Day 1 Array & Multidimensional Array**
## **Pengertian Array**
Array adalah tipe data list order yang dapat menyimpan banyak data sekaligus didalamnya, array di dalam JavaScript dapat menyimpan berbagai macam tipe data yang berbeda, baik tipe data primitive seperti string, number, boolean, ataupun tipe data non primitive seperti object.
### **Contoh :**
```
let hewan = ["Kucing", "Anjing", "Kelinci"];

console.log(hewan); // Output ["Kucing", "Anjing", "Kelinci"]
```
>Biasanya array di deklarasikan didalam sebuah variabel dengan menggunakan simbol square bracket "[]", untuk memisahkan antara index 1 dan index lainnya kita dapat memberikan "," di penghujung value.

### **Contoh jika array diisi dengan berbagai macam tipe data :**
```
let mahasiswa = ["Fazlu", 20, true];

console.log(mahasiswa); // Output ["Fazlu", 20, true];
```

## **Cara mengakses array**
Array pada JavaScript dihitung dari index ke-0 yang merupakan representasi dari data pertama yang ada di dalam array.

<img src="img/accessIndexArray.png" />

### **Contoh cara mengakses index array :**
```
let productTeam = ["Product Manager", "UI & UX Designer", "Front-End Developer", "Back-End Developer"];

console.log(productTeam[0],  productTeam[2], productTeam[3]); // Output "Product Manager", "Front-End Developer", "Back-End Developer"
```
>Pada contoh diatas kita coba mengakses array yang ada dengan memberikan nomor index didalam square bracket, sesuai dengan urutan yang kita inginkan dan sudah pasti index dimulai dari 0.
## **Update Array**
Berikutnya disini kita juga bisa melakukan update terhadap value dari array.
### **Contoh :**
```
let productTeam = ["Product Manager", "UI & UX Designer", "Front-End Developer", "Back-End Developer"];

productTeam[1] = "UI Designer";
console.log(productTeam[1]) // Output UI Designer
```
>Pertama kita akses terlebih dahulu index dari array yang ingin kita tuju, setelah itu baru kita melakukan assignment dan memasukan value baru yang sudah kita tetapkan kedalam index array yang sudah kita seleksi.

## **Const In Array**
Perbedaan jika kita menggunakan `const` kita tidak dapat melakukan update atau merubah array menjadi array yang baru, tetapi kita tetap bisa melakukan perubahan pada value dari masing-masing index.
### **Contoh penggunaan const**
```
const mahasiswa = ["Fazlu"];
mahasiswa.push(20);

console.log(mahasiswa[1]) // Output TypeError: assignment to constant variabel.
```
>Kita tidak bisa melakukan perubahan dengan menambahkan index baru jika menggunakan const

## **Array Properties**
### **Apa itu properties ?**
Properties adalah merupakan fitur yang sudah disediakan oleh JavaScript untuk memudahkan developer, salah satu contoh dari properties array yang sering digunakan adalah properties `.length`.
### **Contoh penggunaan length :**
```
const productTeam = ["Product Manager", "UI & UX Designer", "Front-End Developer", "Back-End Developer"];

console.log(productTeam.length); // Output 4;
```
>Dengan menggunakan properties length kita dapat melihat jumlah atau panjang index pada array productTeam.

## **Array Method**
Array memiliki method bawaan atau built-in method, yang artinya JavaScript sudah memudahkan kita dengan menyediakan function / method umum yang biasa kita gunakan. Jadi kita tidak perlu membuat function secara manual untuk memproses sesuatu, contohnya jika kita ingin melooping array.

### **Contoh beberapa array built-in method :**
- `.push()` : adalah method untuk menambahkan item array pada urutan paling akhir.
- `.pop()` : adalah method yang menghapus item array dari index terakhir.
- `.shift()` : adalah method untuk menghapus item array pada index pertama.
- `unshift()` : adalah method untuk menambahkan item array pada index pertama.
- `sort()` : adalah method untuk mengurutkan array secara ascending atau descending alphanumerik.
### **Looping menggunakan built-in method pada array**
- `forEach()` : adalah method untuk melakukan looping pada setiap elemen array.
**Contoh :**
```

```
- `map()` : adalah method perulangan yang dapat mengembalikan array baru.
**Contoh :**
```

```

### **Kapan harus menggunakan forEach dan kapan harus menggunakan map ?**

## **Array Multidimensional**

<br/>

# **Day 2 Object**
## **Pengertian Object**
Object pada programming artinya adalah representasi dari suatu tipe data yang memiliki properties dan method di dalamnya yang dapat diakses dari luar maupun dari dalam.
- Properties : adalah kumpulan data dari sebuah object
- Method : adalah action atau process yang bisa dijalankan dari object tersebut.
### **Contoh properties dan method pada object mobil :**
<img src="img/objectCar.png" />

>Pada contoh gambar berikut dapat terlihat bahwa sebuah mobil mempunyai properties dan method, properties disini terdiri dari kumpulan data pada mobil tersebut, sedangkan method disini terdiri dari fungsi-fungsi atau proses yang bisa dilakukan oleh mobil.

## **Cara membuat object**
```
let mahasiswa {
    nama : "Fazlu Rachman",
    umur : 20,
    jurusan : "Sistem Informasi",
    lulus : false
}

console.log(mahasiswa) // Output show object mahasiswa
```
>Sama seperti membuat array, sebuah object dapat kita assign ke dalam variabel, bisa disebut dengan object literal. Kita juga bisa menyimpan berbagai tipe data di dalam object, sama seperti array sebelumnya.

## **Cara Mengakses object dan propertinya**
```
let mahasiswa {
    nama : "Fazlu Rachman",
    umur : 20,
    jurusan : "Sistem Informasi",
    lulus : function cekKelulusan(){
        //aksi
    }
}

console.log(mahasiswa.nama); // Output Fazlu Rachman
console.log(mahasiswa.umur); // Output 20
```
>Untuk dapat mengakses baik properties ataupun method pada object, kita dapat memanggil nama object lalu dilanjutkan dengan menambahkan operator "." lalu nama key yang ingin kita akses valuenya.

```
let mahasiswa {
    nama : "Fazlu Rachman",
    umur : 20,
    jurusan : "Sistem Informasi",
    lulus : function cekKelulusan(){
        //aksi
    },
    'current address' : 'jambi, indonesia'
}

console.log(mahasiswa['current address']); // Output jambi, indonesia
```
>Jika kita ingin menggunakan spasi pada key kita dapat menggunakan single quote, tapi jika kita ingin mengaksesnya kita harus menggunakan square bracket sama seperti array, bedanya kita tidak menggunakan nomor index melainkan nama key=.

## **Update Data pada Object**
Object dapat menambahkan key dan value baru jika kita mendeklarasikannya dengan menggunakan let, tapi jika kita menggunakan const maka akan menyebabkan error seperti sebelumnya, sama seperti jika kita ingin merubah array yang kita deklarasikan dengan const. Jadi jika membutuhkan 
fitur update pada seluruh data object, gunakan ‘let’ pada saat deklarasi variabel.

### **Contoh :**
```
let mahasiswa {
    nama : "Fazlu Rachman",
    umur : 20,
    jurusan : "Sistem Informasi",
    lulus : function cekKelulusan(){
        //aksi
    },
    'current address' : 'jambi, indonesia'
}

mahasiswa.ipk = 3.80;

console.log(mahasiswa.ipk); // Output 3.80;
```
>Disini kita memanggil object mahasiswa lalu melakukan assignment ke key yang tidak ada, maka secara otomatis key tersebut akan ditambahkan ke object mahasiswa.

## **Delete Data pada Object**
Kita dapat menghapus properti dari object menggunakan delete
operator.
### **Contoh :**
```
let mahasiswa {
    nama : "Fazlu Rachman",
    umur : 20,
    jurusan : "Sistem Informasi",
    lulus : function cekKelulusan(){
        //aksi
    },
    'current address' : 'jambi, indonesia'
}

delete mahasiswa['current address'];
delete mahasiswa.lulus;

console.log(mahasiswa); // Output current address, lulus is delete from mahasiswa.
```
>Gunakan keyword delete lalu dilanjutkan dengan nama object lalu key dari properti / method yang ingin dihapus.

## **Method**
Jika value yang kita masukkan pada property berupa function. Maka itu disebut sebagai method.

<br/>

# **Day 3 Rekursif Function**

## **Pengertian Rekursif**

<br/>

# **Day 4 Asyncronus JavaScript & Promise**
## **Pengertian Asyncronus pada JavaScript**
<br/>

# **Day 5 Local Storage**
## **Pengertian Local Storage**
