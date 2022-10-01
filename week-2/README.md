# **Writting & Presentation Test Week 2**
# **Day 1 Scope Variabel & Function**
## **Scope**
### **Apa itu Scope dalam Variabel?**


Yaitu adalah suatu konsep dalam flow data variabel yang menentukan bahwa variabel tersebut dapat diakses pada scope tertentu atau tidak. Scope disini bisa diartikan sebagai lingkup block code.

### **Apa itu Blocks?**

Blocks adalah code yang 
berada didalam curly braces {}.
Conditional, function, dan 
looping menggunakan blocks.


### **Analoginya seperti :**

Kita semua bisa melihat bintang-bintang
dilangit karena bumi bersifat global.
Namun jika kamu tinggal di Bandung, kamu 
tidak akan bisa melihat monas yang berada 
di jakarta. Monas bersifat local yaitu hanya 
berada di Jakarta.

### **Global Scope**

Global Scope adalah bagian scope yang berada diluar dari blocks, yang artinya disini jika kita mendeklarasikan variabel dengan global scope maka variabel tersebut dapat diakses dimanapun dalam suatu file.

**Contoh Global Scope :**
```
let myName = 'Fazlu'; // Global Scope

function greeting() {
    return myName; // Fazlu
}

console.log(greeting()) // Output Fazlu
```
>Disini dapat terlihat kalau variabel yang kita deklarasikan di luar bloks dapat di akses walaupun di dalam bloks sekalipun
### **Local Scope**
Local Scope adalah bagian scope yang berada di dalam blocks, yang artinya jika kita mendeklarasikan variabel didalam suatu blocks seperti function, conditional, loop, dll. Maka kita tidak bisa mengakses variabel tersebut diluar dari blocks.

**Contoh Local Scope :**
```
function greeting() {
    let myName = 'Fazlu';
    return myName;
}

console.log(greeting()); // Output Fazlu
console.log(myName); // Output uncaught ReferenceError: myName is not defined because local scope
```
>Sedangkan untuk local variabel yang kita deklarasikan di dalam bloks tidak dapat kita akses dari luar dan akan menyebabkan error.
## **Function**
### **Pengertian Function**
Function adalah sub program yang terdiri dari sekumpulan perintah dalam blok kode yang biasanya digunakan untuk menyelesaikan suatu task.

**Contoh Function :**
```
function greetWorld() {
    return 'Hello World!';
}
```
<img src="img/anatomiFunction.png" alt="function" />

### **Cara memanggil Function**
```
greetWorld();   // Memanggil Function
console.log(greetWorld());    // Output: 'Hello World'
```

<img src="img/callFunction.png" alt="call function" />

### **Parameter**
Dengan menggunakan parameter, function dapat menerima sebuah inputan data dan menggunakannya untuk keperluan task yang akan dikerjakan. Kita harus tau data-data apa saja yang kita perlukan jika kita ingin membuat function untuk menyelesaikan suatu task, sehingga kita bisa menginputkan nilai ke parameter dari function yang kita buat.

<img src="img/parameterFunction.png" alt="parameter" />

**Contoh :**
```
function penambahan(a, b) {
    return a + b;
}
```
>Jika kita ingin membuat function berupa penjumlahan dua buah nilai, maka kita harus menyiapkan 2 parameter yang siap diinput ke dalam function, sehingga dapat diproses dan dikembalikan nilainya.

### **Argument Function**
Argument adalah nilai yang kita inputkan ke dalam function saat melakukan pemanggilan, sehingga dari inputan tersebut nilai akan ditampung ke dalam parameter. 

<img src="img/argumentFunction.png" alt="argument function" />

**Contoh :**
```
function penambahan(a, b) {
    return a + b;
}

console.log(penambahan(5, 5)); // Output: 10
```
>Dari contoh kode diatas, perlu kita perhatikan bahwa nilai argument yang kita inputkan harus sesuai dengan parameter yang kita siapkan, guna sebagai wadah yang dapat menampung nilai tersebut.

### **Default Parameter**
Default parameter bisa digunakan jika kita ingin memberikan nilai awal/default pada parameter function. Dengan begitu kita bisa menjaga agar function tidak error saat kita panggil walaupun tanpa argument.

**Contoh :**
```
function greetOnWebsite(name = 'Stranger') {
    return 'Hello ' + name;
}

console.log(greetOnWebsite('David')); // Output: 'Hello David'
console.log(greetOnWebsite()); // Output: 'Hello Stranger'
```
>Kita bisa melakukan assignment pada parameter kita sehingga jika kita tidak menginputkan argument saat pemanggilan function, secara otomatis parameter dari function akan mengambil nilai default yang sudah kita tetapkan.

### **Jenis - Jenis Function yang dapat digunakan sesuai kebutuhan**
- Declaration Function / Regular Function

**Contoh :**
```
function greeting() {
    return 'Hello World!';
}
```
>Mendeklarasikan function dengan memberi keyword function beserta nama function yang ingin kita berikan.

- Function Expression

**Contoh :**
```
let greeting = function() {
    return 'Hello World!';
}
```
>memasukan function ke dalam variabel sehingga nama function akan mengikuti nama variabel tersebut.
- Arrow Function

**Contoh :**
```
let greeting = () => {
    return 'Hello World!';
}
```
Jika hanya mengembalikan return 1 baris kita bisa menggunakan short syntax dengan cara :
```
let greeting = () => 'Hello World`;
```
>Arrow function adalah cara pemanggilan function baru dari ES6, dengan menggunakan arrow function kita bisa membuat syntax function kita menjadi lebih sederhana.



