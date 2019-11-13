<h1 align="center">
  Mobile DevDay#2:<br>JavaScript Dasar 
</h1>

<p align="center">
  <image src="https://i.ibb.co/Ss490SL/logo-color.png">
  <image src="https://i.ibb.co/c6Gm061/logoreact.png">
</p>

<h1 align="center">Komunitas Cipta Maya: Learn, Play, and Invent!</h1>

:rocket: Pada pertemuan kedua ini akan membahas JavaScript sebagai bahasa untuk menjalankan berbagai fungsi di _framework_ React-Native

:100: Setelah pertemuan ini selesai kamu akan mengetahui dasar-dasar bahasa pemrograman JavaScript mulai dari sejarah, _syntax_, _data types_, iterasi, dan hal lainya. Pada pertemuan ini kita juga akan melakukan latihan sederhana dengan menggunakan bahasa ini.

# Table of Contents

- [Apa itu JavaScript?](#question-apa-itu-javascript)
- [:gear: bagaimana JavaScript Bekerja?](#gear-bagaimana-javascript-bekerja)

JavaScript dasar :eyes:

1. [Hello World :earth_asia:](#1-hello-world-earth_asia)
2. [Code structure :wrench:](#2-code-structure-wrench)
    - [Statements](#2a-statements)
    - [Semicolons](#2b-semicolons)
    - [Comments](#2c-comments)
3. [Variabel :bookmark:](#3-variabel-bookmark)
    - [Penamaan variabel](#3a-penamaan-variabel)
    - [_Keyword_ variabel](#3b-keyword-variabel)
4. [_Data Types_ / _Primitives_ :books:](#4-data-types--primitives-books)
    - [Number](#number)
    - [Boolean](#boolean)
    - [Undefined](#undefined)
    - [Null](#null)
    - [String](#string)
    - [Symbol](#symbol)
5. [Objects :cookie:](#5-objects-cookie)
    - [Object](#5a-object)
    - [Array](#5b-array)

## :question: Apa itu JavaScript

:tea: JavaScript adalah bahasa skrip yang digunakan untuk membuat tampilan website lebih hidup, melakukan perubahan terhadap web ataupun membuat fungsi-fungsi kompleks untuk sebuah web. Bisa dibilang JavaScript adalah bahasa yang menghidupi seluruh website yang ada.

:tea: Javascript diciptakan oleh Brendan Eich pada tahun 1995 sebagai bahasa untuk meningkatkan performa web pada browser Netscape. pada awalnya JavaScript bernama Mocha, kemudian berubah menjadi LiveScript dan berubah kembali menjadi JavaScript. [[1]](https://en.wikipedia.org/wiki/JavaScript)

:tea: Javascript adalah bahasa yang terstandardisasi oleh European Computer Manufacturers Association (ECMA). JavaScript adalah implementasi dari standar yang dibuat oleh ECMA [[2]](https://medium.com/@renopp/kenalan-dengan-es6-javascript-introduction-variable-arrow-function-part1-6bd5c148473b). Standardisasi terakhir JavaScript dilakukan pada Juni 2019. Hal yang perlu diingat, pada setiap versi standardisasi ada penambahan fitur pada bahasa ini.

<p align="center">
  <img src="https://miro.medium.com/max/1944/1*GPxahqSw02Houwa4VJt80w.png" alt="drawing" width="1000"/>
</p>

## :gear: bagaimana JavaScript Bekerja?

JavaScript sebagai _bahasa tingkat tinggi_ perlu _diintepretasi_ agar dapat dijalankan. Javascript memiliki _Intepreter_ yang ada disetiap Web Browser, atau lebih sering disebut _engine_. Chrome memiliki V8 Engine, Mozilla memiliki SpiderMonkey, Microsoft Edge memiliki Chakra, dll.

<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/V8_JavaScript_engine_logo_2.svg/1200px-V8_JavaScript_engine_logo_2.svg.png" alt="drawing" width="200"/>
</p>

Engine JavaScript independen dari browser yang ia tinggali (dalam kasus ini V8), maka disitulah Node.js mengambil keuntungan dengan mengambil engine V8 dan membuatnya menjadi _environment_ JavaScript yang dapat berjalan di _server side_.

# JavaScript Dasar :eyes:

## 1. Hello World! :earth_asia:

Pada console tuliskan kode berikut

```javascript
alert('Hello World');

console.log('Hello World');
```

## 2. Code Structure :wrench:

### 2.a. Statements

_Statement_ adalah "instruksi" untuk "dieksekusi" oleh komputer. [[3]](https://www.w3schools.com/js/js_statements.asp) Seperti `console.log('Hello World')` adalah sebuah _Statement_ yang jika dieksekusi akan menampilkan _log_ pada console

### 2.b. Semicolons

_Semicolon_ ( **;** ) berguna untuk memisahkan sebuah _Statement_ (Tidak wajib jika beda baris kode)

```javascript
console.log('Hello'); console.log('World'); // menampilkan 2 log

var a = 5 console.log('Error') // error, tidak ada pemisahan antara statement 1 dan statement 2
```

### 2.c. Comments

Saat program sudah mulai kompleks dan memiliki ratusan bahkan ribuan baris, penting untuk memberikan _comments_ yang mendeskripsikan apa yang kode itu lakukan

```javascript
console.log('Inline Comment') // Comment satu baris

/*
Comments lebih dari satu baris
digunakan untuk membuat comments yang panjang
agar mudah dibaca dan efisien
*/
var a = 5; console.log('Multiline Comments')
```

## 3. Variabel :bookmark:

PS: gunakan REPL [ini](https://stephengrider.github.io/JSPlaygrounds/) untuk menulis dan melihat hasil kodemu

Variabel adalah wadah yang diberi nama, untuk menyimpan suatu data. dalam bahasa pemrograman JavaScript, variabel mengalami dua fase yaitu deklarasi dan inisialisasi. Deklarasi terjadi saat kita membuat sebuah variabel, dan inisialisasi saat variabel diberi data.

```javascript
// deklarasi variabel message. variabel yang belum dinisiasi tidak memiliki data dan akan mencetak 'undefined' jika di console.log
let message;
console.log(message); // => undefined

// inisiasi variabel, menambahkan data
message = 'Hallo bro';

// deklarasi sekaligus inisiasi
let pesan = 'What\'s up?';
```

Kita bisa juga mendeklarasikan banyak variabel dalam satu baris dipisahkan oleh koma:

```javascript
let user = 'John', age = 25, message = 'Hello';

// bisa juga dibuat perbaris selama masih ada koma yang menyambung
let user = 'John',
  age = 25,
  message = 'Hello';
```

variabel yang sudah dideklarasikan dapat diganti datanya oleh data ataupun data dari variabel lainya:

```javascript
let hello = 'Hello world!';

let message;

// copy 'Hello world' dari hello ke message
message = hello;

// sekarang dua variabel memiliki data yg sama
console.log(hello); // => Hello world!
console.log(message); // => Hello world!
```

### 3.a. Penamaan variabel

Ada 2 batasan untuk penamaan variabel dalam bahasa JavaScript:

1. Nama hanya boleh tersusun dari huruf, digit (angka), atau simbol **$** dan **_**.
2. Karakter pertama tidak boleh angka

```javascript
let user; // => valid
let user223; // => valid

let $troya; // => valid
let _low_dash; // => valid

let 12juta; // => invalid
let tidur-malam; // => invalid
```

Selain itu ada daftar _reserved word_ yang tidak bisa digunakan sebagai nama variabel. list nya dapat dilihat [disini](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords) 

### 3.b. _Keyword_ variabel

Untuk mendeklarasikan variabel, JavaScript memiliki beberapa keyword khusus, yaitu **let, const dan var**:

<p align="center">
  <img src="https://miro.medium.com/max/461/1*sUBeBuOB8pAuMPfw9BQmvA.png" alt="drawing" width="500"/>
</p>

**var** merupakan _keyword_ yang paling awal dimiliki JvaScript, sedang **let** dan **const** baru muncul pada tahun 2015 bersamaan dengan keluarnya ECMAScript6 atau ES6

## 4. _Data Types_ / _Primitives_ :books:

JavaScript memiliki 5 (6 pada tahun 2015) tipe data primitif. data Primitif merupakan data yang tidak memiliki _methods_ sendiri dan juga _immutable_.

### Number

Seperti namanya, number adalah angka termasuk integer, floats, dll

```javascript
let number = 2;

typeof number; // => number
typeof infinity; // => number
typeof NaN; // => number, Lol
```

### Boolean

Boolean memiliki dua kondisi yaitu `True` dan `False` yang menyatakan kebenaran.

```javascript
let benar = false;

typeof benar; // => boolean
typeof true; // => boolean
```

### Undefined

tidak terdefinisi alias ghaib. Undefined muncul di saat variabel baru saja di deklarasi namun belum memiliki value, Juga pada saat mengambil _value_ dari _object_ namun tidak ada _key_ yang sesuai. 

```javascript
let ghoib;

typeof ghoib; // => undefined
typeof undefined; // => undefined
```

### Null

tipe data yang menyimbolkan ketidak adaan nilai, atau kosong?

```javascript
let hampa = null;

typeof hampa; // => 'object' wtf?? ini salah satu keanehan JavaScript, masih banyak lainya
```

Sebuah analogi

<p align="center">
  <img src="https://i.ibb.co/vktd3Zk/k-Yj-WGFhz-Sv-Y0-Fnwe7f7-Tok-Sk-Qiy-MD6-Gti06-ZEgf-Zy-Z0.jpg" alt="drawing" width="500"/>
</p>

### String

susunan karakter dengan berbagai tipe yang diapit oleh tanda petik

```javascript
let kata = 'hai';
let katakata = '12343@#%56^#*1';

typeof kata; // => string
typeof katakata; // => string

// escaping character
kata = 'ayo Da\`wah';
katakata = 'escaping escaper \\'
```

### Symbol

Symbol adalah tipe data baru yang muncul pada tahun 2015. Untuk lengkapnya, silahkan check link [ini](https://hacks.mozilla.org/2015/06/es6-in-depth-symbols/) untuk detail tentang symbol

## 5. _Objects_ :cookie:

_Object_ juga merupakan tipe data tapi lebih kompleks daripada _primitives_. Ada 2 Objects yang paling umum yaitu:

### 5.a. Object

Object adalah data tipe non-primitif dalam bahasa JavaScript. Object menyimpan banyak data dalam dalam satu wadah. tiap data memiliki _key_ untuk mengidentifikasi data yang disimpan.

#### objek literal

adalah objek yang dibuat langsung dengan mendeklarasikan variable yang datanya diapit kurung kurawal ( **{ }** ), dan didalamnya dapat diberi data yang berstruktur _key value pair_. 

```javascript
let obj = { nama: 'Andi', umur: 11 };

// menampilkan data dari objek
console.log(obj.nama); // => 'Andi'

// menambah data dalam objek
obj.asal = 'Solo';
console.log(obj.asal); // => 'Solo'
```

#### objek constructor

Cara lain untuk membuat objek adalah dengan menggunakan keyword **new**

```javascript
let obj = new Object;

// menambahkan data
obj.nama = 'Andi';
obj['umur'] = 18;

console.log(obj); // => { nama: 'Andi', umur: 18 }
```

#### methods

_methods_ adalah fungsi bawaan yang dimiliki oleh beberapa tipe data seperti Object dan Array. Beberapa contoh _methods_ dari Object

```javascript
let obj = { nama: 'Andi', umur: 11 };

// mendapatkan semua key dari objek
let objectKeys = Object.keys(obj);
console.log(objectKeys); // => ['nama', 'umur']

// mendapatkan semua value dari objek
let objectValues = Object.values(obj);
console.log(objectValues); // => ['Andi', 11']

typeof obj; // => object
```

### 5.b. Array

Array hampir mirip seperti object, namun data yang ia miliki dibungkus dengan karakter **[ ]**. Data dalam Array tidak memiliki _key_ yang deklaratif seperti object, melainkan menggunakan urutan (_index_) dari data yang ada dalam Array, juga, urutan dalam array dimulai dari 0.

<p align="center">
  <img src="https://www.tutorialsteacher.com/Content/images/js/js-array.png" alt="drawing" width="500"/>
</p>

```javascript
let arr = [12, 'hello', 'world', 34, 2.3, 87];

// mengambil data dari array
arr[0] // => 12
arr[4] // => 2.3
arr[10 - 6] // => 2.3 
```

#### methods

```javascript
let arr = [12, 'hello', 'world', 34, 2.3, 87];

// menambah data di akhir array
arr.push(1000);
console.log(arr); // => [12, 'hello', 'world', 34, 2.3, 87, 1000];

// mendapatkan data pada index tertentu
let slicedArray = arr.slice(2, 4);
console.log(slicedArray); // => ["world",34]
```

## 6. _Operators_ :heavy_plus_sign:

Javascript memiliki _operator_ seperti dalam bahasa lainya. Kita mengetahui beberapa operator matematika yang biasa digunakan sehari-hari seperti `+` penambahan, `-` pengurangan, `*` perkalian, dll. JavaScript memiliki 5 jenis operator yang masing-masing dapat dilihat dalam tabel dibawah:

#### Terminologi: "unary", "binary", "operand"

sebelum dilanjutkan, mari memahami beberapa terminologi berikut

- _operand_ adalah nilai asal yang digunakan dalam proses operasi. misal `5 * 2` memiliki dua _operand_, _operand_ kiri angka `5` dan operand kanan angka `2`.

- sebuah operator disebut _unary_ jika hanya punya satu operand, misal

```javascript
let x = 1;

x = -x; // x = -1, aplikasi negasi unary
```

- operator disebut _binary_ jika punya 2 _operand_

```javascript
let x = 1, y = 2;

let r = y - x; // r = 2, aplikasi pengurangan binary
```

### 6.a. Arithmatic Operator

Operator aritmatika digunakan untuk melakukan operasi matematika anatara _operand_ numerik

| Operator | Deskripsi |
| ---- | ---- |
| + | Menambahkan dua _operand_ numeric |
| - | Mengurangi _operand_ kanan dari _operand_ kiri |
| * | Mengalikan dua _operand_ numeric |
| / | Membagi _operand_ kiri dengan _operand_ kanan |
| % | [Modulus/ Modulo] mengembalikan hasil sisa bagi 2 _operand_ |
| ++ | [Increment] menambahkan nilai _operand_ satu angka |
| -- | [Decrement] Mengurangi _operand_ kanan dari _operand_ kiri |

#### contoh penggunaan

```javascript
5 + 10; // => 15

10 - 5; // => 5

5 * 10; // => 50

10 / 5; // => 2

5 % 2; // => 1

5++; // => 6

5--; // => 4
```

### 6.b. Comparison Operator

Operator perbandingan digunakan untuk membandingkan dua _operand_ dan menghasilkan nilai _boolean_

| Operator | Deskripsi |
| ---- | ---- |
| == | Membandingkan dua _operand_ tanpa memandang tipe |
| === | Membandingkan dua _operand_ dengan memandang tipe |
| != | Mengecek ketidaksamaan antar _operand_ |
| > | Mengecek apakah _operand_ kiri lebih besar dari kanan |
| < | Mengecek apakah _operand_ kanan lebih besar dari kiri |
| >= | Mengecek apakah _operand_ kiri lebih besar dari kanan atau sama |
| <= | Mengecek apakah _operand_ kanan lebih besar dari kiri atau sama |

#### contoh penggunaan

```javascript
5 == '5'; // => true

5 === '5'; // => false

5 == 5; // => true

5 != 10; // => true

5 > 10; // => false

5 < 10; // => true

5 >= 10; // => false

5 <= 10; // => true

5 >= '5'; // => true

5 <= '5'; // => true
```

### 6.c. Logical Operator serta nilai _falsy_ dan _truthy_

Operator logika digunakan untuk menggabungkan dua atau lebih kondisi, ia menghasilkan nilai `true` bila benar dan `false` bila salah

untuk memahami lebih baik tentang operator logika kita harus mengetahui tentang **_falsy_** dan **_truthy_**

- **_falsy_** adalah nilai kesalahan, mencakup:
    -  `false`, nilai boolean false
    - `0`, nol
    - `''` atau `""`, string kosong
    - `null`
    - `undefined`
    - `NaN`

- **truthy** selain _falsy_ adalah nilai kebenaran, mencakup
    - `true`
    - `'0'`, string berisi angka 0
    - `'false'`, string berisikan boolean false
    - `[]`, array kosong
    - `{}`, object kosong
    - `function(){}`, fungsi kosong

| Operator | Deskripsi |
| ---- | ---- |
| && | Disebut juga Operator AND. Ia memastikan apakah dua atau lebih _operand_ memiliki nilai **_truthy_**  |
| \|\| | Disebut juga Operator OR. Jika hanya salah satu dari dua atau lebih _operand_ bernilai **_truthy_** menghasilkan nila `true` |
| ! | Menegasi nilai kebenaran |

#### contoh penggunaan

```javascript
(5 < 8) && (6 > 5); // => true

(20 < 8) && (6 > 5); // => false

(5 < 8) || (6 > 5); // => true

(20 < 8) && (6 > 5); // => true

(20 < 8) && (6 > 50); // => false

!(6 < 8); // => false
```

### 6.d. Assignment Operator

Operator penetapan digunakan untuk menginisialisasi nilai dari sebuah variabel

| Operator | Deskripsi |
| ---- | ---- |
| = | Menetapkan nilai dari _operand_ kanan ke _operand_ kiri |
| += | Menambahkan nilai kedua _operand_ secara langsung dan menjadikanya nilai _operand_ kanan |
| -= | Mengurangkan nilai kedua _operand_ secara langsung dan menjadikanya nilai _operand_ kanan |
| *= | Mengalikan nilai kedua _operand_ secara langsung dan menjadikanya nilai _operand_ kanan |
| /= | Membagi nilai kedua _operand_ secara langsung dan menjadikanya nilai _operand_ kanan |
| %= | Menjadikan hasil modulus sebgai nilai dari _operand_ kanan |

#### contoh penggunaan

```javascript
let x = 5, y = 10, z = 15;

x = y; //x menjadi 10

x += 1; //x menjadi 6

x -= 1; //x menjadi 4

x *= 5; //x menjadi 25

x /= 5; //x menjadi 1

x %= 2; //x menjadi 1
```

### 6.e. Bitwise Operator

Bitwise Operator merubah _operand_ menjadi susunan 32 bit (`0` dan `1`) kemudian membandingkanya, dan mengembalikan hasil berupa angka `1` jika benar dan `0` jika salah. Operator ini tidak terlalu sering digunakan, untuk melihat detail nya bisa membuka link [ini](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Bitwise_Operators)

## 7. _Type Conversion_ dan _Type Coercion_



# Referensi:
[1 - https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript)

[2 - https://en.wikipedia.org/wiki/ECMAScript](https://en.wikipedia.org/wiki/ECMAScript)

[3 - https://nodejs.dev/the-v8-javascript-engine](https://nodejs.dev/the-v8-javascript-engine)

[4 - https://medium.com/coderupa/es6-var-let-const-apa-bedanya-1cd4daaee9f0](https://medium.com/coderupa/es6-var-let-const-apa-bedanya-1cd4daaee9f0)

[5 - https://codeburst.io/javascript-essentials-types-data-structures-3ac039f9877b](https://codeburst.io/javascript-essentials-types-data-structures-3ac039f9877b)

[6 - https://www.tutorialsteacher.com/javascript](https://www.tutorialsteacher.com/javascript)

