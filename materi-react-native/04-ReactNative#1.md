<h1 align="center">
  Mobile DevDay#4:<br>React Native 101
</h1>

<p align="center">
  <image src="https://i.ibb.co/Ss490SL/logo-color.png">
  <image src="https://i.ibb.co/c6Gm061/logoreact.png">
</p>

<h1 align="center">Komunitas Cipta Maya: Learn, Play, and Invent!</h1>

:rocket: Pada pertemuan ini akan membahas dasar dari React-Native dan berbagai model lingkungan pengembanganya

:100: Setelah pertemuan ini selesai kamu diharapkan dapat memahami struktur folder dan syntax React-Native, component, JSX, props dan state. Selain itu kamu juga akan mencoba membuat aplikasi sederhana untuk mempraktekanya.

# Table of Contents

1. [React Native CLI & Expo :first_quarter_moon:](#1-react-native-cli--expo-first_quarter_moon)
    - [CLI](#1a-cli)
    - [_Expo_](#1b-expo)
2. [Project Structure :construction_worker:](#2-project-structure-construction_worker)
3. [JSX :ledger:](#3-jsx-ledger)
4. [React Components :gear:](#4-react-components-gear)
    - [_Functional Component_](#4a-functional-component)
    - [_Class Component_](#4b-class-component)
5. [_State_ dan _Props_ :books:](#5-state-dan-props-books)
    - [State](#5a-state)
    - [Props](#5b-props)
6. [React-Native Core component :seedling:](#6-react-native-core-component-seedling)
7. [Component Lifecycle :alarm_clock:](#7-component-lifecycle-alarm_clock)
8. [Flexbox :black_square_button:](#8-flexbox-black_square_button)
    - [Flex sizing](#8a-flex-sizing)
    - [flexDirection](#8b-flexdirection)
    - [justifyContent](#8c-justifycontent)
    - [alignItems](#8d-alignitems)
    - [alignSelf](#8e-alignself)
    - [flexWrap](#8f-flexwrap)
    - [alignContent](#8g-aligncontent)
    - [position](#8h-position)
    - [zIndex](#8i-zindex)

## 1. React-Native CLI & Expo :first_quarter_moon:

Dalam mengembangkan aplikasi menggunakan framework React-Native ada 2 lingkungan pengembangan yang dipakai. Pertama menggunakan **CLI** yang kemarin kita install pada pertemuan pertama, Kedua menggunakan platform **Expo**, berikut keterangan terkait keduanya.

### 1.a CLI

Mengmbangkan React-Native dengan CLI atau _command line interface_ adalah cara paling awal dalam pengembangan. Jika kita menginisiasi aplikasi kita menggunakan CLI, kita akan lebih mudah dalam pengembangan, dan leluasa menggunakan _native module_. Selain itu, menggunakan model ini, kita akan mendapatkan update yang lebih cepat. Berikut kelebihan dan kekurangan menggunakan CLI

#### Kelebihan CLI :gem:

- Bisa menggunakan _native modules_
- Mendapatkan update lebih cepat

#### Kekurangan CLI :bomb:

- Membutuhkan Android Studio/SDK untuk menjalankan
- Tidak mengembangkan iOS tanpa Mac
- Untuk share aplikasi harus mengirimkan file .apk atau .ipa
- Inisiasi projek memakan waktu relatif lebih lama

### 1.b Expo

Expo adalah suatu _tools_ yang dibuat diatas React-Native yang membantumu untuk lebih mudah dalam membuat project iOS dan Android. Expo menjadi terkenal karena kemudahan dan fasilitasnya seperti XDE, Expo CLI, Expo Client, Expo SDK. Berikut kelebihan dan kekurangan Expo

#### Kelebihan Expo :gem:

- Memulai project lebih mudah
- Kolaborasi dengan tim lebih mudah dengan adanya Expo Client
- Bisa di _Eject_ untuk menjadi React-Native CLI
- Expo bisa langsung membuat file .ipa dan .apk (serta mendeploynya ke store)

#### Kekurangan Expo :bomb:

- Tidak bisa menggunakan Native Module
- Ukuran Aplikasi untuk yang sederhana seperti "Hello world" minimal 25mb
- Ketika _Eject_ versi sesuai dengan Expokit
- Update React Native lebih lama karna membutuhkan banyak penyesuaian

Ikuti link [ini](https://itnext.io/set-up-react-native-with-expo-1e63a82d01ac) jika ingin menginstall Expo

# 2. _Project Structure_ :construction_worker:

project React-Natice yang diinisiasi dengan CLI memiliki strukture seperti gambar dibawah ini (RN@0.61.5)

<p align="center">
  <image src="https://i.ibb.co/7t39xqC/Screenshot-from-2019-12-01-07-42-10.png">
</p>

| Nama File/ Folder | Deskripsi |
| ---- | ---- |
| \_\_test__ | Folder tempat file untuk melakukan berbagai jenis testing terhadap aplikasi |
| android | Folder tempat berbagai script untuk menjalankan aplikasi android |
| ios | Folder tempat berbagai script untuk menjalankan aplikasi iOS |
| node_modules | folder tempat berbagai package node.js berada |
| .buckconfig | file yang memuat konfigurasi untuk [Buck](https://buck.build/), suatu sistem untuk membangun aplikasi yang dibuat oleh facebook |
| .eslintrc.js | Konfigurasi untuk [ESLint](https://eslint.org/), _Linter_ untuk JavaScript dan JSX (alat untuk kualitas kode) |
| .flowconfig | Konfigurasi untuk [Flow](https://flow.org/), alat untuk pengecekan _type_ untuk JavaScript |
| .gitignore & .[gitattributes](https://git-scm.com/docs/gitattributes) | Konfigurasi untuk file atau folder git yang tidak perlu di masukan dan version control yang unik untuk setiap mesin pengembangan |
| .prettierrc.js | Konfigurasi untuk styling kode |
| .watchmanconfig | Konfigurasi untuk [Watchman](https://facebook.github.io/watchman/), alat untuk mendeteksi perubahan dalam project directory |
| App.js | _Default_ Komponen utama dalam project React-Native |
| app.json | Tempat untuk edit nama aplikasi |
| babel.config.js | Konfigurasi untuk [Babel](https://babeljs.io/), _Compiler_ dan _Transpiler_ untuk JavaScript |
| index.js | File utama tempat kita meregistrasi komponen untuk di render |
| metro.config.js | Konfigurasi untuk [Metro](https://facebook.github.io/metro/), _Bundler_ JavaScript untuk React-Native |
| package.json | file tempat daftar _dependency_ yang project gunakan, juga command line untuk berinteraksi dengan project |
| yarn.lock | jika menginstall dengan yarn akan ada file ini yang berisi dependency untuk tiap package yang diinstal |

# 3. JSX :ledger:

JSX adalah singkatan dari _JavaScript eXtension_, merupakan ekstensi React yang membuat kita bisa menulis JavaScript yang _mirip_ seperti HTML [[1]](https://www.fullstackreact.com/30-days-of-react/day-2/). JSX dibuat untuk mempermudah pengembangan web dengan ReactJS atau aplikasi mobile dengan React-Native.

contoh JSX

```javascript
const a = <View />

const b = (
  <View
    foo='hello'
    bar={baz}>
    <Text>42</Text>
  </View>
)
```

JSX jika sudah dicompile oleh Babel

```javascript
var a = React.createElement(View, null);

var b = React.createElement(
  View,
  {
    foo: 'hello',
    bar: baz },
  React.createElement(
    Text,
    null,
    '42'
  )
);
```

# 4. _React Components_ :gear:

React Component adalah susunan kode yang dapat di render menjadi tampilan atau UI. Component dalam aplikasi React dapat berbentuk sebuah fungsi (functional component/ stateless component) ataupun _class_ (statefull component) JavaScript. 

## 4.a. functional component

```javascript
const Greeting = () => <h1>Hello World today!</h1>;
```

Komponen Fungsional dibuat dengan menggunakan fungsi dari JavaScript. Komponen ini simple dan tidak dapat memiliki _local state_

## 4.b. class component

```javascript
class Greeting extends React.Component {
  render(){
    return <h1>Hello World Today!</h1>;
  }
}
```

Komponen ini dibuat menggunakan syntax _class_ dari JavaScript ES6. Komponen tipe ini memiliki fitur tambahan seperti _local state_ dan _Life Cycle Method_.

### Notes: Memilih tipe komponen yang tepat

Gunakan Functional component jika:

- Component bentuknya sederhana
- Tidak memiliki logic yang kompleks
- Reusable

Gunakan Class Component jika:

- Component kompleks dan menampung komponen lainya
- Memiliki logic yang kompleks
- Membutuhkan local state
- Membutuhkan Life Cycle Method

# 5. _State_ dan _props_ :books:

React disebut begitu karena kemampuanya untuk bereaksi terhadap data[[2]](https://medium.com/coderupa/react-prop-state-apa-bedanya-7ee61df8257f). Props & State terkadang membuat bingung bagi yang baru masuk ke Dunia React. Kapan harus menggunakan props dan kapan menggunakan state.

## 5.a _State_

State adalah data _private_ milik sebuah komponen. Data ini tidak dapat diakses dari komponent lain. Selain itu state hanya ada pada Class based component. Mari kita praktekan dengan membuat aplikasi hitung sederhana:

```javascript
import React from 'react';
import { View, Button, Text, StyleSheet } from 'react-native';

export default class Hitung extends React.Component {
  state= {
    angka: 0,
  }

  render() {
    return (
      <View style={styles.container}>
        <Text style={styles.textStyle}>{this.state.angka}</Text>
        <View style={styles.row}>
          {/* penggunaan this.setState untuk merubah state */}
          <Button title='Tambah' onPress={() => this.setState({ angka: this.state.angka + 1 })} />
          <Button title='Kurang' onPress={() => this.setState({ angka: this.state.angka - 1 })} />
        </View>
      </View>
    );
  }
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
  },
  textStyle: {
    fontSize: 30,
  },
  row: {
    flexDirection: 'row'
  }
});

```

## 5.b _Props_

Props atau properties merupakan parameter yang diterima oleh komponen untuk melakukan suatu konfigurasi tertentu. Pada komponen `<View>` misalnya ada beberapa props yang bisa digunakan seperti `style`, `onLayout` atau `pointerEvents`. Lengkapnya dapat kamu lihat [disini](https://facebook.github.io/react-native/docs/view). Props nanti akan berguna saat kita membuat _child component_.

# 6. React-Native Core component :seedling:

_Core component_ merupakan komponen utama yang disediakan oleh React-Native untuk membangun UI yang diinginkan. berikut beberapa komponen utama yang paling sering digunakan:

| Nama Komponen | Deskripsi |
| ---- | ---- |
| `<View>` | [View](https://facebook.github.io/react-native/docs/view) adalah komponen paling fundamental dimana ia menjadi container bagi semua komponen lainya. View menggunakan flexbox pada prinsip desainya. |
| `<Text>` | [Text](https://facebook.github.io/react-native/docs/text) merupakan komponen untuk menampilkan text dalam berbagai tipe. |
| `<TextInput>` | [TextInput](https://facebook.github.io/react-native/docs/textinput) merupakan komponen untuk membuat form atau field input dengan berbagai tipe |
| `<Image>` | [Image](https://facebook.github.io/react-native/docs/image) merupakan komponen untuk merender gambar baik dari suatu url ataupun data dari local |
| `<Button>` | [Button](https://facebook.github.io/react-native/docs/button) komponen tombol untuk berinteraksi dengan user dan menjalankan suatu fungsi tertentu. Jika membutuhkan styling yang lebih fleksibel bisa menggunakan `<TouchableOpacity>` |
| `<ScrollView>` | [ScrollView](https://facebook.github.io/react-native/docs/scrollview) hampir sama dengan `View` namun memiliki kelebihan untuk dapat menampilkan data atau tampilan yang melebihi _Viewport_ device |
| `<FlatList>` | [FlatList](https://facebook.github.io/react-native/docs/flatlist) merupakan component untuk me-_render_ data yang banyak menjadi tampilan. FlatList memiliki kelebihan karena ada beberapa konfigurasi untuk optimasi proses mengolah data |

# 7. _Component Lifecycle_ :alarm_clock:

Suatu komponen memiliki siklus 'hidup' nya sendiri, dimulai dari inisiasi, _mounting_, render, diupdate, _unmounting_ sampai suatu komponen dihancurkan. _Lificeycle_ ini berguna untuk mengeksekusi suatu hal pada satu titik waktu tertentu. Perhatikan gambar berikut untuk mengetahui diagram _component lifecycle_

<p align="center">
  <image src="https://i.ibb.co/gznskv7/tutorial-react-native-component-lifecycle.png">
</p>

- **Initialization**

fase ini merupakan awal dimana props dan state yang ada dibaca dan disiapkan

- **Mounting**

_mounting_ adalah process pengaplikasian component yang ada untuk dapat ditampilkan. ada 3 fase disini:

1. `ComponentWillMount()`, fungsi ini hanya berjalan satu kali, pada saat sebelum component di render
2. `render`, ini adalah proses pengaplikasian komponen menjadi UI untuk ditampilkan
3. `ComponentDidMount()`, ketika komponen selesai di render, fungsi ini dijalankan, hanya satu kali saja. 

- **Updation**

_updation_ merupakan proses yang terus berlangsung pada saat komponen sudah di render, terjadi jika ada perubahan pada props atau state.

1. `componentWillReceiveProps()`, fungsi ini akan di eksekusi bila state yang ada di component akan di update atau di ubah dengan nilai props yang baru.
2. `shouldComponentUpdate()`, tugasnya adalah untuk menentukan apakah sebuah component akan di render ulang atau tidak.Method ini akan mengembalikan nilai boolean true & false, jika true maka component akan di render ulang atau sebaliknya.
3. `componentWillUpdate()`, fungsi ini akan di eksekusi jika fungsi shouldComponentUpdate mengembalikan nilai true.
4. `componentDidUpdate()`, fungsinya sama dengan componentDidMount yaitu untuk manipulasi DOM dan request data.

- **Unmounting**

`ComponentWillUnmount()`, fungsi ini berjalan sebelum user keluar atau komponen akan hancur. biasanya digunakan untuk menghapus listener atau continous function

# 8. _Flexbox_ :black_square_button:

Untuk dapat memahami bagaimana struktur layout dari tampilan React-Native kita harus memahami konsep Flexbox. Flexbox di React-Native hampir sama seperti `display: flex` pada css, hanya dengan sedikit perbedaan default. Berikut adalah konsep dasar Flexbox pada React-Native:

<p align="center">
  <image src="https://i.ibb.co/10Bx6YV/flex.jpg">
  <span>Left image {flex-direction: row}, Right image {flex-direction: column}</span>
</p>

component dalam flexbox akan mengikuti main-axis yang ditentukan lewat styling `flexDirection`. untuk lebih mempermudah kita akan bermain dengan kode berikut:

```javascript
import React, { Component } from 'react';
import { View, Text } from 'react-native';

export default class FlexDirectionBasics extends Component {
  render() {
    return (
      <View style={styles.container}>
        <View style={{width: 50, height: 50, backgroundColor: '#EE2C38'}} />
        <View style={{width: 50, height: 50, backgroundColor: '#FAA030'}} />
        <View style={{width: 50, height: 50, backgroundColor: '#32B76C'}} />
      </View>
    );
  }
}

const styles = {
  container: {
    flex: 1,
    backgroundColor: 'skyblue'
  },
}
```

## 8.a. Flex Sizing

`Flex: 1` dalam kode diatas dimaksudkan untuk mendapatkan luas kesetiap sudut dari layar device. Kita dapat juga merubah luasan komponen didalam kontainer dengan `flex` agar sesuai dengan prosentase yang diinginkan. misalkan untuk mendapatkan hasil seperti gambar dibawah, kita hanya butuh mengganti `width` dan `height` pada kode diatas menjadi `flex` 1 hingga 3.

<p align="center">
  <image src="https://miro.medium.com/max/2462/1*PhCFmO5tYX_sZSyCd4vO3w.png">
</p>

## 8.b. flexDirection

`flexDirection` membuat kita bisa memposisikan tiap komponen dalam container untuk mengikuti _main axis_ nya seperti gambar-gambar berikut

<p align="center">
  <image src="https://miro.medium.com/max/2462/1*rA7IbuUsJWsx6evKAsabVw.png">
</p>

## 8.c. justifyContent

Justify content mengatur komponen yang ada didalam flexbox untuk berada pada posisi yang ditentukan, mengikuti main-axis. Aplikasi dapat dilihat pada gambar berikut

<p align="center">
  <image src="https://miro.medium.com/max/3469/1*i5TVlme-TisAVvD5ax2yPA.png">
</p>

## 8.d. alignItems

sebaliknya, `alignItems`, ia memposisikan komponen pada _cross-axis_ nya

<p align="center">
  <image src="https://miro.medium.com/max/2321/1*evkM7zfxt-9p-HJ1M0Bh2g.png">
</p>

## 8.e. alignSelf

Jika konfigurasi sebelumnya memaparkan tata letak untuk child componen, atau komponen dalam flexbox, `alignself` mempengaruhi posisi dari child komponen sendiri terhadap flexbox. `alignself` memposisikan komponen pada _cross-axis_, mengungguli `alignItems` darai parentnya.

<p align="center">
  <image src="https://miro.medium.com/max/2321/1*J1JCoKwLCokX9JXVBvP71g.png">
</p>

## 8.f. flexWrap

flexWrap menetukan apakah beberapa komponen akan berada didalam flexBox ataukah keluar dari Viewport flexbox (yang membuatnya menjadi tidak kelihatan jika tidak berada didalam `ScrollView`)

<p align="center">
  <image src="https://miro.medium.com/max/2321/1*_7v4uQhSsuCn1cfeOMVfrA.png">
</p>

## 8.g alignContent

Jika kamu menggunakan `flexWrap: 'wrap'` maka `alignContent` akan membantumu mengatur posisi dari komponen pada _cross-axis_

<p align="center">
  <image src="https://miro.medium.com/max/3469/1*cC2XFyCF_igp20Ombt4wBw.png">
</p>

## 8.h. position

ada 2 jenis position dalam flexbox yaitu  `relative` dan `absoulute`. relative mengikuti luasan komponen yang sebelumnya, sedang absolute mengikuti sudut dari parent container atau flexbox utamanya. perhatikan gambar berikut. masing-masing kotak diberikan `marginTop` 5, 10 dan 15. yang sebelah kiri relative (default) yang kanan absolute.

<p align="center">
  <image src="https://miro.medium.com/max/2321/1*NlPeRQCQK3Vb5nyjL0Mqxw.png">
</p>

## 8.i. zIndex

zIndex berguna untuk menentukan komponen yang paling utama, atau yang dikehendaki ada paling atas diantara tumpukan komponen dengan `position 'absolute'`

<p align="center">
  <image src="https://miro.medium.com/max/2462/1*NIB9XzbUT788FhKDYBqnKQ.png">
</p>


# Reference:

[https://medium.com/the-andela-way/understanding-react-components-37f841c1f3bb](https://medium.com/the-andela-way/understanding-react-components-37f841c1f3bb)

[https://www.techiediaries.com/react-native-tutorial/create-project-using-react-native-cli/](https://www.techiediaries.com/react-native-tutorial/create-project-using-react-native-cli/)

[http://www.reactnativeexpress.com/jsx](http://www.reactnativeexpress.com/jsx)

[https://levelup.gitconnected.com/expo-vs-react-native-cli-a-guide-to-bootstrapping-new-react-native-apps-6f0fcafee58f](https://levelup.gitconnected.com/expo-vs-react-native-cli-a-guide-to-bootstrapping-new-react-native-apps-6f0fcafee58f)

[https://engineering.musefind.com/react-lifecycle-methods-how-and-when-to-use-them-2111a1b692b1](https://engineering.musefind.com/react-lifecycle-methods-how-and-when-to-use-them-2111a1b692b1)

[https://medium.com/wix-engineering/the-full-react-native-layout-cheat-sheet-a4147802405c](https://medium.com/wix-engineering/the-full-react-native-layout-cheat-sheet-a4147802405c)

