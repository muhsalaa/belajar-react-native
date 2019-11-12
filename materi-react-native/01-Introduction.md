<h1 align="center">
  Mobile DevDay#1:<br>Pengenalan dan Instalasi React-Native
</h1>

<p align="center">
  <image src="https://i.ibb.co/Ss490SL/logo-color.png">
  <image src="https://i.ibb.co/c6Gm061/logoreact.png">
</p>

<h1 align="center">Komunitas Cipta Maya: Learn, Play, and Invent!</h1>

:rocket: Pertemuan pertama kali ini akan membahas apa itu React-Native, Bagaimana cara ia bekerja untuk membuat sebuah aplikasi, dan juga bagaimana instalasi _environment_ React-Native di operating system linux. 

:100: Setelah semua proses instalasi berjalan dengan lancar, dilanjutkan dengan membuat aplikasi sederhana 'Hello World' untuk menampilkan teks di android.

## Apa itu React-Native?

React-Native adalah _framework_ JavaScript untuk membuat aplikasi _mobile_ yang dapat digunakan diplatform seperti iOS atau Android. React-Native dikembangkan oleh Facebook untuk membuat aplikasi miliknya. Tidak seperti aplikasi webview, hasil dari _framework_ React-Native ini nantinya berupa _native code_ atau kode asli tiap platform. Hal ini menyebabkan performa dari aplikasi React-Native tidak berbeda jauh dari aplikasi _native_. berikut link menuju [Dokumentasi](https://facebook.github.io/react-native/)

## Aplikasi apa saja yang dibuat menggunakan React-Native?

<p align="center">
  <a href="https://play.google.com/store/apps/details?id=com.instagram.android&hl=en_IN">
    <img src="https://i.ibb.co/gPYwFQt/instagram.png" alt="instagram" />
  </a>
  <a href="https://play.google.com/store/apps/details?id=com.airbnb.android&hl=en_IN">
    <img src="https://i.ibb.co/QJJtcNk/airbnb.png" alt="airbnb" />
  </a>
  <a href="https://play.google.com/store/apps/details?id=com.discord&hl=en_IN">
    <img src="https://i.ibb.co/p2BZ7Kf/discord.png" alt="discord" />
  </a>
  <a href="https://play.google.com/store/apps/details?id=com.skype.raider&hl=en_IN">
    <img src="https://i.ibb.co/TqH7WzF/skype.png" alt="skype" />
  </a>
</p>

# Instalasi _Environment_ pengembangan aplikasi React-Native

## 1. Install node.js

Node.js is an open-source, cross-platform, JavaScript runtime environment that executes JavaScript code outside of a browser. [[1]](https://en.wikipedia.org/wiki/Node.js)

copy _command_ berikut satu persatu kedalam terminalmu

```bash
$ curl -sL https://deb.nodesource.com/setup_10.17.0 | sudo -E bash - # download installer nodejs

$ sudo apt-get install -y nodejs # install nodejs
```

###### Manjaro atau Arch Linux

```bash
$ sudo pacman -S nodejs
```

## 2. Install NPM

npm, short for Node Package Manager, is two things: first and foremost, it is an online repository for the publishing of open-source Node.js projects; second, it is a command-line utility for interacting with said repository that aids in package installation, version management, and dependency management. [[2]](https://nodejs.org/en/knowledge/getting-started/npm/what-is-npm/)

jalankan perintah ini diterminal
```bash
$ sudo npm install npm@latest -g # menginstall npm di secara global
```

###### Manjaro atau Arch Linux

```bash
$ sudo pacman -S npm
```

## 3. Install Java Development Kit (JDK)

The Java Development Kit (JDK) is one of three core technology packages used in Java programming, along with the JVM (Java Virtual Machine) and the JRE (Java Runtime Environment). [[3]](https://www.javaworld.com/article/3296360/what-is-the-jdk-introduction-to-the-java-development-kit.html)

Copy satu persatu command berikut di terminal
```bash
$ sudo add-apt-repository ppa:openjdk-r/ppa

$ sudo apt-get update
```

Jalankan perintah ini untuk memulai instalasi
```bash
$ sudo apt-get install openjdk-8-jdk
```

###### Manjaro atau Arch Linux

```bash
OpenJDK 8 sudah terinstall secara default
```

######
## 4. Install Android Studio

1. Download dan install Android Studio dari link [berikut](https://developer.android.com/studio/?gclid=Cj0KCQiA2ITuBRDkARIsAMK9Q7NRFAZTLLOugTuuIpx4C-YOJrVVpxsi3o8oL_MnqMUpr7Cjp3F0dQcaApKbEALw_wcB)

2. Ketikkan perintah berikut untuk mengekstrak file android studio

```bash
$ sudo tar -xvzf android-studio-ide-191.5977832-linux.tar.gz
```

3. Masuk ke direktori android studio dan jalankan perintah instalasi

```bash
$ cd android-studio/bin # pindah ke direktori bin dalam android studio

$ ./studio.sh # menjalankan bash script untuk instalasi 
```
4. Ikuti petunjuk yang muncul sampai instalasi selesai

###### Manjaro atau Arch Linux

```bash
$ sudo pacman -S yay

$ yay -S android-studio # menginstall Android Studio terbaru
```

## 5. Install Android System Development Kit (SDK)

Android SDK (software development kit) is a set of development tools used to develop applications for Android platform. [[4]](https://www.techopedia.com/definition/4220/android-sdk)

Secara _default_ Android Studio sudah menginstal Android SDK versi teranyar. Namun React-Native membutuhkan SDK minimal yaitu Android 6.0 (Marshmallow). SDK tambahan ini bisa diinstall melalui Android Studio. Ikuti langkah berikut:

1. Buka Android Studio
2. Pilih **Configure** pada antar muka awal
3. Pilih **SDK Platforms**
4. Checklist **Show Package Details** pada bagian kanan bawah
5. Lihat pada Android 6.0 (Marshmallow) lalu Checklist data berikut ini:

    - :heavy_check_mark: Google APIs
    - :heavy_check_mark: Android SDK Platform 23
    - :heavy_check_mark: Intel x86 Atom_64 System Image
    - :heavy_check_mark: Google APIs Intel x86 Atom_64 System Image

### **Mengkonfigurasi path untuk Direktori Android**

Setelah menginstall SDK,  kita perlu menambahkan _environment variables_ agar React-Native dapat bekerja/menggunakan _native code_.

Copy kode berikut

```bash
export ANDROID_HOME=$HOME/Android/Sdk 
export PATH=$PATH:$ANDROID_HOME/tools 
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

lalu jalankan perintah ini di terminal dan _paste_ kode sebelumnya dengan menggunakan mouse

```bash
$ sudo nano $HOME/.bash_profile
```
setelah  itu pencet

- **Ctrl - O** lalu **enter** -> untuk save data yang dirubah
- **Ctrl - X** -> Untuk keluar

## 6. Install React-Native CLI (Finally :tada:)

Jalankan _command_ berikut di terminal

```bash
sudo npm install -g react-native-cli
```
**Selamat kamu berhasil menginstall _environment_ React-Native di laptopmu** :tada: :tada: :tada: :tada:

# Membuat aplikasi android pertama

1. Buat folder baru bernama **apps** di home directory dan masuk ke folder tersebut
```bash
$ mkdir apps

$ cd apps
``` 

2. Inisiasi project React-Native dengan versi 0.59.9, dan masuk folder projek. awali dengan jalankan perintah berikut
```bash
$ react-native init helloWorld --version react-native@0.59.9

$ cd helloWorld
```

3. Siapkan emulator atau real device untuk menginstall aplikasi.
    - untuk menggunakan emulator silahkan ikuti tutorial [ini](https://linuxhint.com/install_genymotion_android_emuator_ubuntu/)
    - untuk menggunakan _real device_ atau smartphone android lebih mudah. masuk ke menu pengaturan di samrtphone mu dan pencet 7 kali pada opsi _Build Number_ , nanti akan muncul keterangan bahwa developer mode sudah diaktifkan. selanjutnya tinggal aktifkan _USB Debugging_ pada menu developer

4. Memulai building aplikasi React-Native dengan menjalankan perintah berikut di root folder projek
```bash
$ react-native start

# buka tab terminal baru (Ctrl+Shift+Tab) lalu jalankan kode berikut
$ react-native run-android
```

5. Setelah selesai akan muncul halaman default React-Native.

<p align="center">
  <img src="https://facebook.github.io/react-native/docs/assets/GettingStartedAndroidSuccessWindows.png">
</p>

6. Silahkan bereksperimen mandiri dengan membuka dokumentasi atau video tutorial lainya di youtube.

<hr>

# Referensi:
[1 - https://linux4one.com/how-to-install-android-studio-in-linux/](https://linux4one.com/how-to-install-android-studio-in-linux/)

[2 - https://www.techomoro.com/how-to-install-and-setup-react-native-on-ubuntu-18-04-1-lts-bionic-beaver/](https://www.techomoro.com/how-to-install-and-setup-react-native-on-ubuntu-18-04-1-lts-bionic-beaver/)
