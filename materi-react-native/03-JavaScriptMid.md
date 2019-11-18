<h1 align="center">
  Mobile DevDay#3:<br>JavaScript Mid
</h1>

<p align="center">
  <image src="https://i.ibb.co/Ss490SL/logo-color.png">
  <image src="https://i.ibb.co/c6Gm061/logoreact.png">
</p>

<h1 align="center">Komunitas Cipta Maya: Learn, Play, and Invent!</h1>

:rocket: Pada pertemuan ini akan membahas JavaScript lebih lanjut sebagai bahasa untuk menjalankan berbagai fungsi di _framework_ React-Native

:100: Setelah pertemuan ini selesai kamu akan mengetahui implementasi dari pemrograman JavaScript menengah mulai dari _Conditional_, _Function_, _Iteration_, _Class_, dan hal lainya. Pada pertemuan ini kita juga akan melakukan latihan sederhana dengan menggunakan bahasa ini.
      
# Table of Contents

condtional -> if else, else if, switch
function -> basic interaction in fucntion (break, continue etc), hoisting, closure, iife, pure function
iteration -> for of, for in, for, foreach, while

## 1. Conditional

Ketika membuat suatu program terkadang kita membutuhkan suatu aksi yang berbeda pada kondisi yang berbeda. semisal mengeksekusi pengurangan jika angka sekarang lebih dari 0 dan tidak akan kurang dari 0. Untuk melakukanya JavaScript menggunakan operator Kondisional `if` dan beberapa macam lainya seperti berikut:

### 1.a. `if`, `if else`, `if else if`

```javascript
// eksekusi sebuah perintah jika kondisi terpenuhi (true)
if (5 > 2) {
  console.log('benar');
} // => 'benar'

// `else` untuk memberikan alternatif hasil eksekusi jika kondisi pertama tidak terpenuhi
if (5 < 2) {
  console.log('benar');
} else {
  console.log('alternatif');
} // => 'alternatif'

// penggunaan `else if` untuk menghadapi berbagai kondisi
if (5 > 2) {
  console.log('benar');
} else if (6 > 8) {
  console.log('alternatif');
} else if (10 > 9) {
  console.log('yang lain');
} // => 'benar'
```

### 1.b. Ternary Operator

_Ternary operator_ memiliki fungsi yang hampir sama dengan `if` namun ia menggunakan simbol `?`

```javascript

```
