---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
drawings:
  persist: false
transition: slide-left
title: Welcome to Introduction to Kotlin & Android Development
mdc: true
monaco: true
monacoTypesSource: local
---
 
# Tutorial Kotlin
## Laboratorium Teknik Fisika II

Oleh: Nafi Mulyo Kusumo

<div class="pt-12">
  <span @click="$slidev.nav.to(2)" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Table of Contents
  </span>
</div>


---

# Konten dari Seri Tutorial Android Development

Kemungkinan akan ada 2-4 sesi:

1. Introduction to Kotlin Programming Language
2. Introduction to Android Studio
3. Introduction to IoT Communication

Disclaimer: 
Apa yang diajarkan di tutorial memang tidak mencakup 100% apa yang ada di source pembelajaran (dipilah sesuai "keperluan")

---
class: text-center
background: https://source.unsplash.com/collection/94734566/1920x1080
title: Introduction to Kotlin
---
# Sesi 1: Introduction to Kotlin
---

# Contents
- Introduction
- Basic Concepts
  - Variable
  - Data Type
  - Operator
  - Control Flow
- Function and Lambda
- Collection
  - List
  - Set
  - Map
  - Basic Operations
::right::
- Introduction to OOP
  - Class & Object
  - Encapsulation
  - Inheritance
  - Polymorphism
- Android Studio Preview



Referensi:
- [Kotlin Official Documentation](https://kotlinlang.org/docs/home.html)
- [Kotlin for Android Developers](https://antonioleiva.com/kotlin-android-developers-book/)

---

# Introduction: Apa itu Kotlin?
Kotlin itu common language yang digunakan untuk membuat "native" android application. Selain kotlin, ada juga bahasa pemgrograman/framework yang dipake buat ngoding aplikasi mobile.
- Flutter using Dart programming language
- React Native using Javascript
- Swift (iOS)
- Java (predecessor-nya Kotlin, kebanyakan developer tidak menggunakan Java lagi di mobile development)

---

# Basic Concepts

---

# Hello World
```kotlin
fun main() {
    println("Hello, World!")
}
```
Disini kita bakal cobain running program di atas pake IntelliJ IDEA.


---

# Variables
Ada 3 cara inisialisasi variable di Kotlin
```kotlin
val a: String = "Raul"   
val b: Int = 25   
val c = 3.14
```
code di bawah bakal bikin error

```kotlin
val e Int   
println(e)
```


---

# Variables
Variable boleh dibaca kalau udah diassingn/initialized, terserah kapan/bagaimana
```kotlin
val d: Int

if (someCondition()) {
  d = 1
} else {
  d = 2
}

println(d)
```
---

# Data Types - Kotlin Data Types
Ada beberapa tipe data di Kotlin, diantaranya:
```kotlin
val myNum: Int = 5                // Int
val myDoubleNum: Double = 5.99    // Double
val myLetter: Char = 'D'          // Char
val myBoolean: Boolean = true     // Boolean
val myText: String = "Hello"      // String
```
---

# Data Types - Static Typing

Kotlin adalah bahasa pemrograman yang menggunakan static typing. Ini berarti tipe dari setiap variabel dan ekspresi ditentukan pada saat kompilasi dan tidak dapat berubah pada saat runtime. Static typing membantu mendeteksi kesalahan tipe data lebih awal dalam proses pengembangan, sering kali langsung di IDE (Integrated Development Environment) sebelum kode bahkan dijalankan.

---

# Data Types - Type Inference
Kotlin juga mendukung type inference, yang berarti kita tidak perlu menentukan tipe variabel jika kompiler dapat menentukannya sendiri. Ini membuat kode lebih bersih dan lebih mudah dibaca.

```kotlin
val message = "Hello, Kotlin!" // Tipe String diinferensikan
val number = 42 // Tipe Int diinferensikan
```

---

# Operator
Kotlin mendukung berbagai jenis operator, mirip dengan banyak bahasa pemrograman lainnya

## Operator Aritmetika
```kotlin
val sum = 10 + 5        // Hasil: 15
val difference = 10 - 5 // Hasil: 5
val product = 10 * 5    // Hasil: 50
val quotient = 10 / 5   // Hasil: 2
val remainder = 10 % 3  // Hasil: 1
```

---

# Operator
## Operator Perbandingan
```kotlin
val isEqual = 10 == 10   // Hasil: true
val isNotEqual = 10 != 5 // Hasil: true
val isGreater = 10 > 5   // Hasil: true
val isLess = 5 < 10      // Hasil: true
val isGreaterOrEqual = 10 >= 10 // Hasil: true
val isLessOrEqual = 5 <= 5      // Hasil: true
```

## Operator Logika
,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,
```kotlin
val andResult = true && false // Hasil: false
val orResult = true || false  // Hasil: true
val notResult = !true         // Hasil: false
```
---

# Operator
## Operator Assignment
```kotlin
var number = 10
number += 5  // number sekarang adalah 15
number -= 3  // number sekarang adalah 12
number *= 2  // number sekarang adalah 24
number /= 4  // number sekarang adalah 6
number %= 5  // number sekarang adalah 1
```

## Operator Increment dan Decrement
```kotlin
var counter = 0
counter++ // counter sekarang adalah 1
counter-- // counter sekarang adalah 0
```
---

# Control Flow - Conditionals
## When Statement
```kotlin
fun main() {
    cases("Hello")
    cases(1)
    cases(0L)
    cases("hello")
}

fun cases(obj: Any) {                                
    when (obj) {                                     // 1   
        1 -> println("One")                          // 2
        "Hello" -> println("Greeting")               // 3
        is Long -> println("Long")                   // 4
        !is String -> println("Not a string")        // 5
        else -> println("Unknown")                   // 6
    }   
}
```
---

# Control Flow - Conditionals
## If Statement

```kotlin
var i : Int = 16

if(i == 16) {
    println("enam belas")
} else {
    println("bukan enam belas")
}
```

---

# Control Flow - Looping
## For Statement
Digunakan untuk mengulang sebuah blok kode untuk setiap item dalam sebuah range atau koleksi.
```kotlin
for (item in collection) print(item)
```

## While Statement
Melakukan blok kode berulang kali selama kondisi yang diberikan bernilai true.
```kotlin
while (x > 0) {
    x--
}
```
---


# Control Flow - Looping
## Jump Expression
break: Menghentikan loop yang paling dekat.
continue: Melompat ke iterasi berikutnya dari loop yang paling dekat.
return: Mengakhiri eksekusi fungsi saat ini dan mengembalikan nilai (jika ada).
```kotlin
for (i in 1..10) {
    if (i == 3) continue // Skip the rest of the code in loop for i == 3.
    if (i > 5) break // Exit the loop when i is greater than 5.
    println(i)
}
```
---


# Function and Lambda - Basic Function
```kotlin
fun printMessage(message: String): Unit {                               
    println(message)
}
```
Dengan initial value:

```kotlin
fun printMessage(message: String, prefix: String = "Info"): Unit {                               
    println("[$prefix] $message")
}

printMessage("Test") // outputs: "[Info] Test"
printMessage("Code is not good", "Error") // outputs: "[Error] Code is not good"
```
Bisa juga dicobain langsung di IDEA

---


# Function and Lambda - Named Arguments
Functions bisa juga dipanggil menggunakan 'Named Arguments'.
```kotlin
fun printMessage(message: String, prefix: String = "Info"): Unit {                               
    println("[$prefix] $message")
}

// Order tidak penting
printMessage(prefix = "Test", message = "Test") // outputs: "[Test] Test"
```

---

# Function and Lambda - Lambda Function
Meringkas 'simple' functions.
```kotlin
fun multiply(x: Int, y: Int) {
    return x*y
}
```
equivalent dengan
```kotlin
fun multiply(x: Int, y: Int) = x*y
```
Bisa juga dicoba langsung di IDEA.

---

# Function and Lambda - Null Safety
```kotlin
fun printHello(name: String?) {
    if (name == null) {
        println("Hello!")
    } else {
        println("Hello $name!")
    }
}

printHello() // outputs: Hello!
printHello("Mazaya") // outputs: Hello Mazaya!
```
atau di variable biasa juga
```kotlin
var nama: String? = null

printHello(nama)

nama = "Mazaya"

printHello(nama)
```
---


# Collection - Array

---


# Introduction to OOP
---


# Apa itu OOP?
OOP (Object-Oriented Programming) adalah paradigma pemrograman yang berfokus pada objek dan data, bukan fungsi dan logika. OOP memungkinkan pengembang untuk membuat struktur yang lebih terorganisir dalam kode mereka.

Yang bakal kita pelajari:
- Encapsulation
- Inheritance
- Polymorphism

NOTE: Ini masih surface banget daro OOP, kalai semua bisa 3 SKS

---


# Kenapa OOP
Widely known concept di computer science dan dipake dengan ekstensif di Kotlin. Semua software engineer pasti expected untuk bisa dan mengerti konsep OOP secara baik.

As a mattaer of fact, companies berikut.
- GPT Labs
- Payable
- Glints Vetted Talent
- Tokopedia

Semuanya pas interview ada pertanyaan OOP (dari yang dasar sampe advance banget, misalnya design pattern)

---

# Encapsulation
Encapsulation itu easy to understand. Bayangin kita pengen bikin mahasiswa kayak berikut.

```kotlin
Mahasiswa punya: nama, nim, sama jurusan
```

Kalau mau bikin di program gimana?
```kotlin
var nama = "Mazaya"
var nim = "13320028"
var jurusan = "TF"

fun printMahasiswa(nama: String, nim: String, jurusan: String) {
    println("$nama adalah mahasiswa $jurusan dengan nim $nim")
}

printMahasiswa(nama, nim, jurusan)
```
Kalau ada mahasiswa lain gimana?

---


Kalau ada mahasiswa lain gimana?
```kotlin
var nama_mazaya = "Mazaya"
var nim_mazaya = "13320028"
var jurusan_mazaya = "TF"

var nama_deedat = "Deedat"
var nim_deedat = "1332072"
var jurusan_deedat = "TF"


fun printMahasiswa(nama: String, nim: String, jurusan: String) {
    println("$nama adalah mahasiswa $jurusan dengan nim $nim")
}

printMahasiswa(nama_mazaya, nim_mazaya, jurusan_mazaya)
printMahasiswa(nama_deedat, nim_deedat, jurusan_deedat)
```
Kalau N adalah **property** seorang mahasiswa dan M adalah jumlah mahasiswa, maka perlu N*M variable, atau pake array, tapi masih scattered datanya.

---


# Encapsulation using Class

```kotlin
class Mahasiswa(
    // namanya property:
    val nim: String,
    val nama: String,
    var jurusan: String,
) { 
    // namanya method:
    fun print() {
        println("$nama adalah mahasiswa $jurusan dengan nim $nim")
    }
}
```
Lebih enak buat dipake separasi data:
```kotlin
var mazaya = Mahasiswa("13320028", "Mazaya", "TF")
var deedat = Mahasiswa("13320072", "Deedat", "TF")

mazaya.print() // outputs: Mazaya adalah mahasiswa TF dengan nim 13320028
deedat.print() // outputs: Deedat adalah mahasiswa TF dengan nim 13320072
```
---

# Inheritance
Yak ini harus dijelasin pake diagram sih.

---

# Inheritance
Contoh:

```kotlin
class Mahluk {
    abstract fun bersuara() 
}

class Manusia(
    nama: String,
) : Shape() {
    override fun bersuara() {
        println("Nama aku $nama")
    }
}

class Kucing(
    nama: String,
) : Shape() {
    override fun bersuara() {
        println("Meow!")
    }
}
```

---

# Inheritance
Bagus karena sekarang kita punya ekspektasi sama mahluk apapun bahwa mereka bisa bersuara
```kotlin

val mahluk: Mahluk

val mazaya = Manusia("Mazaya")
val kucing = Kucing("Sugi") // nama kucingnya imam

mazaya.bersuara() // outputs: "Nama aku Mazaya"
kucing.bersuara() // outputs: "Meow!"
```

---
# Polymorphism
Berubah-ubahnya suatu data berdasarkan parent yang sama.
```kotlin

mahluk = Manusia("Nafi")

mahluk.bersuara() // outputs "Nama aku Nafi"

mahluk = Kucing("Sugi")

mahluk.bersuara() // outputs "Meong"

```

---


# More Learning Resources
- [Kotlin Official Documentation](https://kotlinlang.org/docs/home.html)
- [Kotlin for Android Developers](https://antonioleiva.com/kotlin-android-developers-book/)
- [Kotlin Course - Tutorial for Beginners](https://www.youtube.com/watch?v=F9UC9DY-vIU&t=4925s&pp=ygUGa290bGlu)

---
# Introduction to Android Studio 

---

# Contents
- Introduction to Android Studio
  - Installation & Setup
  - Project Structure
- Activity and Lifecycle
- UI Layouting
  - XML Layout
  - Constraint Layout
  - View Binding
  - Material Design
::right::
- Intents and Fragment
- Data Persistence

Referensi:
- [Android Developer Documentation](https://developer.android.com/docs)
- [Android Studio Documentation](https://developer.android.com/studio)
- [Android Fundamental for Beginners](https://www.youtube.com/watch?v=3Ri9PPsGCEg&list=PLQkwcJG4YTCTq1raTb5iMuxnEB06J1VHX)
 
---

# Coming Soon

---

# Introduction to IoT Communication
---

# Contents
- Introduction to IoT Communication
- IoT Communication Protocol
    - Bluetooth Low Energy (BLE)
    - Wi-Fi HTTP Communication
    - WebSocket
    - MQTT Communication
- Hands-on Project
    - BLE Device Scanning
    - HTTP GET Request
    - WebSocket Connection
    - MQTT Publish

Referensi:
- 

---

# Coming Soon

---
