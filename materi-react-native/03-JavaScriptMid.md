<h1 align="center">
  Mobile DevDay#3:<br>JavaScript Mid
</h1>

<p align="center">
  <image src="https://i.ibb.co/Ss490SL/logo-color.png">
  <image src="https://i.ibb.co/c6Gm061/logoreact.png">
</p>

<h1 align="center">Komunitas Cipta Maya: Learn, Play, and Invent!</h1>

:rocket: Pada pertemuan ini akan membahas JavaScript lebih lanjut sebagai bahasa untuk menjalankan berbagai fungsi di _framework_ React-Native

:100: Setelah pertemuan ini selesai kamu akan mengetahui implementasi dari pemrograman JavaScript menengah mulai dari _Conditional_, _Function_, _Iteration_, dan hal lainya. Pada pertemuan ini kita juga akan melakukan latihan sederhana dengan menggunakan bahasa ini.

# Table of Contents

1. [_Conditional_ :first_quarter_moon:](#1-conditional)
    - [if, if else, if else if](#1a-if-if-else-if-else-if)

## 1. _Conditional_

Ketika membuat suatu program terkadang kita membutuhkan suatu aksi yang berbeda pada kondisi yang berbeda. semisal mengeksekusi pengurangan jika angka sekarang lebih dari 0 dan tidak akan kurang dari 0. Untuk melakukanya JavaScript menggunakan operator Kondisional `if` dan beberapa macam lainya seperti berikut:

### 1.a. `if`, `if else`, `if else if`

```javascript
// eksekusi sebuah perintah jika kondisi terpenuhi (true)
if (5 > 2) {
  console.log("benar");
} // => 'benar'

// `else` untuk memberikan alternatif hasil eksekusi jika kondisi pertama tidak terpenuhi
if (5 < 2) {
  console.log("benar");
} else {
  console.log("alternatif");
} // => 'alternatif'

// penggunaan `else if` untuk menghadapi berbagai kondisi
if (5 > 2) {
  console.log("benar");
} else if (6 > 8) {
  console.log("alternatif");
} else if (10 > 9) {
  console.log("yang lain");
} // => 'benar'
```

### 1.b. Ternary Operator

_Ternary operator_ memiliki fungsi yang hampir sama dengan `if` namun ia menggunakan simbol `?` dan `:` untuk memisahkan hasil benar dan salah.

```javascript
15 > 10 ? true : false; // => true

// nested ternary is work but not recommended
// readability of code is important
false ? 10 : true ? 11 : 12;
```

### 1.c. _Switch_

_Switch_ adalah tipe lain dari _conditional_ untuk mengani kondisi yang lebih banyak. _Swtich_ bekerja mirip seperti `if else if` namun lebih cepat karena untuk setiap _case_ yang ada akan memiliki _access time_ yang sama [[1]](https://stackoverflow.com/questions/767821/is-else-if-faster-than-switch-case/767849#767849)

```javascript
const fruit = "Apple";

switch (fruit) {
  case "apple": // case mencocokan data dengan input
    console.log("apel");
    break; // untuk menghentikan fungsi jika sudah benar
  case "banana":
    console.log("pisang");
    break;
  default:
    console.log("buah");
} // => apel

// switch menggunakan strict comparison '==='
switch ("0") {
  case 0:
    console.log("kosong");
    break;
  default:
    console.log("buah");
} // => buah
```

## 2. _Function_

_Fungsi_ dalam bahasa pemrograman merupakan sebuah blok kode yang dibuat untuk menjalankan sebuah tugas tertentu.

```javascript
function multiplier(p1, p2) {
  // p1 dan p2 adalah parameter
  return p1 * p2; // return mengeluarkan hasil dari invokasi fungsi, yaitu hasil kali parameter 1 dan 2
}

// fungsi di invokasi dengan menulis nama fungsi diikuti parameter
console.log(multiplier(10, 20)); // => 200

// fungsi dapat dijadikan variable
const tambahin = function(p1, p2) {
  return p1 + p2;
};

tambahin(1, 5); // => 6

// bisa juga dieksekusi dalam variabel
const hasil = tambahin(10, 20);
console.log(hasil); // => 30

// fungsi tanpa nama disebut anonymous function
// default value
const tambahin = function(p1, p2 = 10000) {
  return p1 + p2;
};

tambahin(1); // => 10001
```

### 2.a. _Arrow Function_

_Arrow Function_ adalah fitur terbaru pada JavaScript ES6 yang mempermudah penulisan fungsi dengan simbol `=>`.

```javascript
// ini fungsi
const bagi = (p1, p2) => p1 / p2;
console.log(bagi(20, 10)); // => 10

// jika hanya ada satu parameter, 'kurung' dapat dihilangkan
const kuadrat = p1 => p1 * p1;
console.log(bagi(10)); // => 100
```

### 2.b. _Pure Function_

_Pure Function_ merupakan istilah untuk sebuah fungsi yang hasil invokasinya semata-mata berasal dari parameter yang ia miliki. Ada 2 hal yang menjadikan suatu _pure function_ [[2]](https://www.freecodecamp.org/news/what-is-a-pure-function-in-javascript-acb887375dfe/)

#### 1. _Same input same output_

```javascript
// pure, masukan paramter apa saja hasilnya akan sama
const add = (x, y) => x + y;
add(2, 4); // => 6

/**
 * impure, bergantung pada variabel diluar fungsi
 * fungsi ini tidak menghasilkan apa2 selain menambah nilai variabel x
 * fungsi ini tidak sesuai hukum input sama menghasilkan nilai sama
 * jika kita jalankan fungsi dengan parameter value 4 sebanyak 5x
 * nilai x akan terus bertambah
 */
let x = 2;

const add = y => {
  x += y;
};

add(4); // x === 6, menggunakan variabel diluar fungsi
```

#### 2. _No Side-Effects_

yang dimaksud _efek samping_ adalah:

- Mutating your input
- console.log
- HTTP calls (AJAX/fetch)
- Changing the filesystem (fs)
- Querying the DOM

```javascript
// impure ada console.log, tapi hasil input dan output akan selalus sama
const impureDouble = x => {
  console.log("doubling", x);

  return x * 2;
};

const result = impureDouble(4);
console.log({ result });

// impure karna melakukan mutasi (perubahan) variabel diluarnya
const impureAssoc = (key, value, object) => {
  object[key] = value;
};

const person = {
  name: "Bobo"
};

const result = impureAssoc("shoeSize", 400, person);

console.log({
  person,
  result
});
```

#### Keuntungan _Pure function_

- lebih mudah untuk dipikirkan
- lebih mudah digabungkan
- lebih mudah untuk diuji
- lebih mudah di-debug
- lebih mudah diparalelkan

### 2.c. _Immediately Invoked Function Expression_ (IIFE)

Sesuai namanya IIFE berarti fungsi yang tereksekusi secara langsung, dan fungsi ini akan mati setelah ia baru saja hidup

```javascript
// normal function
function addTogether() {
  var x = 20;
  var y = 20;
  var answer = x + y;
  console.log(answer);
}

addTogether(); // => 40

// IIFE
(function() {
  var x = 20;
  var y = 20;
  var answer = x + y;
  console.log(answer);
})();
```

## 3. _Looping_

_Looping_ atau iterasi adalah suatu proses dimana kita mengeksekusi suatu kode secara berulang sampai batas tertentu. Ada beberapa jenis _looping_ pada bahasa pemrograman JavaScript:

### 3.a. _For loop_

```javascript
const arr = ['hai', 'apa', 'kabar'];
// nilai awal ; batas nilai atau pengulangan ; operasi pada variabel num
for (let num = 0; num < arr.length; num++) {
  console.log(arr[num])
}; // => 'hai', 'apa', 'kabar'

// menghentikan iterasi secara paksa
const arr2 = [1, 2, 3, 4, 5];

for (let num = 0; num < arr2.length; num++) {
  if (arr2[num] === 3) {
    console.log(arr[num]);
    break; // hentikan iterasi
  }
  
}; // => 1, 2, 3
```

### 3.b. _For/In loop_

for in loop akan mengambil key dari tiap item dalam object atau array

```javascript
// object
const person = {fname:"John", lname:"Doe", age:25};

let text = "";
for (let x in person) {
  text += person[x]; // x === fname, lname, age
}
```

### 3.c. _For/of loop_

berkebalikan dengan _for in_, _for of_ loop akan mengambil value dari tiap item dalam object atau array

```javascript
// object
const person = {fname:"John", lname:"Doe", age:25};

let text = "";
for (let x of person) {
  x; // x === John doe 25
}
```

### 3.d. _While loop_

While loop mengiterasi setiap kode didalamnya sampai titik yang ditentukan

```javascript
let i = '';
let text = '';

while (i < 10) {
  text = "The number is " + i;
  i++;
  console.log(text)
} // => 'The number is 9'
```
## 4. _Hoisting_ dan _Closure_

### 4.a. _Hoisting_

hoisting adalah penarikan deklarasi variabel (`var`) ataupun fungsi ke bagian paling awal sutau program JavaScript.

```javascript

// state dapat diakses duluan karna ditarik keatas, namun memiliki nilai undefined
console.log(state); // => undefined

// error karena belum terdeklarasi
console.log(halo); // => Reference error

var state = "Ready";

// fungsi juga ditarik diatas, dapat dieksekusi dahulu, dan nilai didalamnya dapat diambil
hoisting();

function hoisting() {
  // dalam scope sebuah fungsi, jika ada variabel yg sama akan mengikuti variabel dalam scope
  console.log(state); // => undefined

  var state = "Idle";

  console.log(state); // => Idle
}
```

### 4.b. _Closure_

_Closure_ adalah fungsi yang memiliki akses ke variabel dari lingkup fungsi lain. Ini dilakukan dengan membuat fungsi di dalam suatu fungsi. Tentu saja, fungsi luar tidak memiliki akses ke lingkup dalam. [[3]](https://www.codingame.com/playgrounds/6516/closures-in-javascript-for-beginners)

```javascript
function buildName(name) { 
    var greeting = "Hello, " + name + "!"; 
    var sayName = function() {
        // fungsi ini dapat mengambil variable di parent function nya
        var welcome = greeting + " Welcome!";
        console.log(welcome); 
    };
    return sayName; 
}

var sayMyName = buildName("John");
sayMyName();  // Hello, John! Welcome!
```

Hal lain yang sangat penting untuk dipahami adalah bahwa _Closure_ dibuat pada setiap pemanggilan fungsi. Setiap kali kita menggunakan _closure_, itu akan merujuk lingkup luar yang sama. Jika ada variabel yang berubah di lingkup luar, maka perubahan akan terlihat di panggilan berikutnya juga.

```javascript
function buildContor(i) { 
    var contor = i;
    var displayContor = function() {
        console.log(contor++);
        contor++;
    };
    return displayContor; 
}

var myContor = buildContor(1);
myContor(); // 1
myContor(); // 2
myContor(); // 3

// closure baru - scope luar - variabel contor baru
var myOtherContor = buildContor(10);
myOtherContor(); // 10 
myOtherContor(); // 11

// myContor was not affected 
myContor(); // 4
```