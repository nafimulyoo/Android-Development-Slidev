---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
fonts:
  # basically the text
  sans: Roboto
  # use with `font-serif` css class from UnoCSS
  serif: Robot Slab
  # for code blocks, inline code, etc.
  mono: Fira Code
drawings:
  persist: false
transition: slide-left
title: Introduction to Android Development
mdc: true
monaco: true
monacoTypesSource: local
---
 
# Tutorial Android Development
## Laboratorium Teknik Fisika II

Oleh: Nafi Mulyo Kusumo

---

# Konten dari Seri Tutorial Android Development

Kemungkinan akan ada 2-3 sesi:

1. Introduction to Kotlin Programming Language
2. Introduction to Android Studio
3. Introduction to IoT Communication

Disclaimer: 
Kalau tidak memungkinkan offline, akan diadakan sesi asinkron (berupa video tutorial) sebagai pengganti sesi offline 
Apa yang diajarkan di tutorial memang tidak mencakup 100% apa yang ada di source pembelajaran (dipilah sesuai "keperluan")

---
layout: cover
background: https://source.unsplash.com/collection/94734566/1920x1080
title: Introduction to Kotlin
---

# Sesi 1: Introduction to Kotlin

---
layout: two-cols
---

# Contents
- Introduction
- Hello World & Basic Concept
- Variable & Data Types
- Operators
- Functions
- When & If Expression
- Loops
- Ranges
- Null Safety
- Lambda Expression

::right::
- Introduction to OOP
  - Class & Object
  - Encapsulation
  - Inheritance
  - Polymorphism
- Android Studio Preview
#
#
### Referensi:
- [Kotlin Official Documentation](https://kotlinlang.org/docs/home.html)
- [Kotlin for Android Developers](https://antonioleiva.com/kotlin-android-developers-book/)

---
layout: image-right
image: ./images/kotlin-logo.png
---

# Introduction: Apa itu Kotlin?
##

Kotlin itu common language yang digunakan untuk membuat "native" android application. Selain kotlin, ada juga bahasa pemrograman/framework yang dipake buat ngoding aplikasi mobile.
- Flutter using Dart programming language
- React Native using Javascript
- Swift (iOS)
- Java (predecessor-nya Kotlin, kebanyakan developer tidak menggunakan Java lagi di mobile development)

---
layout: image-right
image: ./images/kotlin-logo.png
---

# Kenapa Belajar Kotlin?
##

Alasan untuk belajar Kotlin:
- Mainly used for Android App Development
- Also becoming more popular for other types of software (e.g. desktop & backend)
- Java code can be used in Kotlin programs
- Kotlin doesn't need many lines of code compared to Java

---

# Hello World
```kotlin
fun main() {
    println("Kumaha damang?")
}
```

- Disini kita bakal cobain running program di atas pake IntelliJ IDEA.

- Perhatikan, dimana "`;`"???

---

# Basic Concept
```kotlin
fun main() {
    print("Kumaha")
    println(", damang?")
}
```

- Entry point dalam Kotlin adalah fungsi `main`
- `print` itu buat ngeprint tanpa newline
- `println` itu buat ngeprint dengan akhiran newline

---

# Variables
##

Cara mendeklarasikan variabel di Kotlin:
```kotlin
val/var myValue: Type = someValue
```

- var - mutable (bisa diubah)
- val - immutable (tidak bisa diubah)
- Type bisa diinferensikan dalam banyak kasus
- Assigment bisa ditunda

Contoh:
```kotlin
val a: Int = 1	// immediate assignment

var b = 2		// 'Int' type is inferred
b = a 			// Reassigning to 'var' is okay

val c: Int		// Type required when no initializer is provided
c = 3			// Deferred assignment
a = 4			// Error: Val cannot be reassigned
```

---

# Variables
##

Variable boleh dibaca kalau udah diassign/initialized, terserah kapan/bagaimana
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
##

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
##

Kotlin adalah bahasa pemrograman yang menggunakan static typing. Ini berarti tipe dari setiap variabel dan ekspresi ditentukan pada saat kompilasi dan tidak dapat berubah pada saat runtime. Static typing membantu mendeteksi kesalahan tipe data lebih awal dalam proses development, sering kali langsung di IDE (Integrated Development Environment) sebelum kode bahkan dijalankan.

---

# Data Types - Type Inference
Kotlin juga mendukung type inference, yang berarti kita tidak perlu menentukan tipe variabel jika kompiler dapat menentukannya sendiri. Ini membuat kode lebih bersih dan lebih mudah dibaca.

```kotlin
val message = "Hello, Kotlin!" // Tipe String diinferensikan
val number = 42 // Tipe Int diinferensikan
```

---

# Operator
##
Kotlin mendukung berbagai jenis operator, mirip dengan banyak bahasa pemrograman lainnya

### Operator Aritmetika
```kotlin
val sum = 10 + 5        // Hasil: 15
val difference = 10 - 5 // Hasil: 5
val product = 10 * 5    // Hasil: 50
val quotient = 10 / 5   // Hasil: 2
val remainder = 10 % 3  // Hasil: 1
```

### Operator Perbandingan
```kotlin
val isEqual = 10 == 10   // Hasil: true
val isNotEqual = 10 != 5 // Hasil: true
val isGreater = 10 > 5   // Hasil: true
val isLess = 5 < 10      // Hasil: true
val isGreaterOrEqual = 10 >= 10 // Hasil: true
val isLessOrEqual = 5 <= 5      // Hasil: true
```

---

# Operator

### Operator Logika

```kotlin
val andResult = true && false // Hasil: false
val orResult = true || false  // Hasil: true
val notResult = !true         // Hasil: false
```

### Operator Assignment
```kotlin
var number = 10
number += 5  // number sekarang adalah 15
number -= 3  // number sekarang adalah 12
number *= 2  // number sekarang adalah 24
number /= 4  // number sekarang adalah 6
number %= 5  // number sekarang adalah 1
```

### Operator Increment dan Decrement
```kotlin
var counter = 0
counter++ // counter sekarang adalah 1
counter-- // counter sekarang adalah 0
```

---

# Functions
```kotlin
fun sum(a: Int, b: Int): Int {
	return a + b
}

fun mul(a: Int, b: Int) = a * b

fun printMul(a: Int, b: Int): Unit {
	println(mul(a, b))
}

fun printMul1(a: Int = 1, b: Int) {
	println(mul(a, b))
}

fun printMul2(a: Int, b: Int = 1) = println(mul(a, b))
```

---

# If Expression

```kotlin
var i : Int = 16

if(i == 16) {
    println("enam belas")
} else {
    println("bukan enam belas")
}
```

---

# When Expression
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

# Loops - For Statement
```kotlin
val items = listOf("apple", "banana", "kiwifruit")

for (item in items) {
    println(item)
}

for (index in items.indices) {
    println("item at $index is ${items[index]}")
}

for ((index, item) in items.withIndex()) {
    println("item at $index is $item")
}

```

---

# Loops - While Statement
```kotlin
val items = listOf("apple", "banana", "kiwifruit")

var index = 0
while (index < items.size) {
    println("item at $index is ${items[index]}")
    index++
}

var toComplete: Boolean
do {
    ...
    toComplete = ...
} while(toComplete)
```

---

# Ranges
```kotlin
val x = 10
if (x in 1..10) {
    println("fits in range")
}

for (x in 1..5) {
    print(x)
}

for (x in 9 downTo 0 step 3) {
    print(x)
}
```

---

# Null Safety
```kotlin

val notNullText: String = "Definitely not null"
val nullableText1: String? = "Might be null"
val nullableText2: String? = null

fun funny(text: String?) {
	if (text != null)
		println(text)
	else
		println("Nothing to print :(")
}

fun funnier(text: String?) {
	val toPrint = text ?: "Nothing to print :("
	println(toPrint)
}


```

---

# Elvis Operator ?:
```kotlin

fun loadInfoById(id: String): String? {
	val item = findItem(id) ?: return null
	return item.loadInfo() ?: throw Exception("...")
}

```

---
layout: cover
---

# Introduction to OOP

---


# Apa itu OOP?
##
Paradigma pemrograman yang didasarkan pada representasi program sebagai sekumpulan objek dan interaksi di antara mereka

Yang bakal kita pelajari:
- Encapsulation
- Inheritance
- Polymorphism

NOTE: Ini masih surface banget dari OOP, kalau dibahas semua bisa 3 SKS

---

# Contoh Pengaplikasian OOP

```kotlin
// Define a Car class with properties and a method
class Car(val make: String, val model: String, var fuelLevel: Int) {
    // Method to drive the car, decreasing fuel level
    fun drive() {
        if (fuelLevel > 0) {
            fuelLevel -= 10 // decrease fuel level by 10
            println("Driving the $make $model. Fuel level: $fuelLevel")
        } else {
            println("Can't drive. The tank is empty!")
        }
    }

    // Method to refuel the car
    fun refuel(amount: Int) {
        fuelLevel += amount
        println("Refueling... New fuel level: $fuelLevel")
    }
}

```

---

# Contoh Pengaplikasian OOP

```kotlin
fun main() {
    // Create an instance of the Car class
    val myCar = Car("Toyota", "Corolla", 50)

    // Use the methods of the Car class
    myCar.drive() // Driving the car uses some fuel
    myCar.refuel(20) // Refueling the car increases fuel level
    myCar.drive() // Drive again with the new fuel level
}
```

---

# Kenapa OOP
##
Widely known concept di computer science dan dipake dengan ekstensif di Kotlin. Semua software engineer pasti expected untuk bisa dan mengerti konsep OOP secara baik.

As a matter of fact, companies berikut.
- GPT Labs
- Payable
- Glints Vetted Talent
- Tokopedia

Semuanya pas interview ada pertanyaan OOP (dari yang dasar sampe advance banget, misalnya design pattern)

---
layout: two-cols
---

# Class dan Object
##
- Class – A set of attributes (fields, properties, data) and related methods (functions, procedures) that together represent some abstract entity. 
- Attributes store state, while procedures express behavior. 

Classes are sometimes called prototypes.
Object – An instance of a class, which has its own specific state.

::right::
##
##
##
```kotlin

class Person:
- String attribute name
- Boolean attribute married
- Method greet

Person x: 
name = "Raul", 
married = false

x.greet()
```

---

# Encapsulation
##
Encapsulation itu easy to understand. Bayangin kita pengen bikin mahasiswa kayak berikut.

```kotlin
Mahasiswa punya: nama, nim, sama jurusan
```

Kalau mau bikin di program gimana?
```kotlin
var nama = "Nafi"
var nim = "13321029"
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
var nama_raul = "Raul"
var nim_raul = "13321010"
var jurusan_raul = "TF"

var nama_hazet = "Hazet"
var nim_hazet = "13321045"
var jurusan_hazet = "TF"


fun printMahasiswa(nama: String, nim: String, jurusan: String) {
    println("$nama adalah mahasiswa $jurusan dengan nim $nim")
}

printMahasiswa(nama_raul, nim_raul, jurusan_raul)
printMahasiswa(nama_hazet, nim_hazet, jurusan_hazet)
```
Kalau N adalah `property` seorang mahasiswa dan M adalah jumlah mahasiswa, maka perlu N*M variable, atau pake array, tapi masih scattered datanya.

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
var raul = Mahasiswa("13321010", "Raul", "TF")
var hazet = Mahasiswa("13321045", "Hazet", "TF")

raul.print() // outputs: Raul adalah mahasiswa TF dengan nim 13321010
hazet.print() // outputs: Hazet adalah mahasiswa TF dengan nim 13321045
```
---

# Inheritance

![Local Image](/images/inheritance.png)
---

# Inheritance
##
Inheritance – The possibility to define a new class based on an already existing one, keeping all or some of the base class functionality (state/behavior).

- The class that is being inherited from is called a base or parent class 
- The new class is called a derived class, a child, or an inheritor 
- The derived class fully satisfies the specification of the base class, but it may have some extended features (state/behavior)

---

# Inheritance
##
Contoh:

```kotlin
abstract class Mahluk {
    abstract var nama: String
    abstract fun bersuara()
}

class Manusia(
    override var nama: String,
) : Mahluk() {
    override fun bersuara() {
        println("Nama aku $nama")
    }
}

class Kucing(
    override var nama: String,
    var pemilik: String,
) : Mahluk() {
    override fun bersuara() {
        println("Meow! pemilik aku $pemilik")
    }
}
```

---

# Inheritance
Bagus karena sekarang kita punya ekspektasi sama mahluk apapun bahwa mereka bisa bersuara
```kotlin
fun main() {
    val manusia = Manusia("Raul")
    manusia.bersuara()

    val kucing = Kucing("Rahwel", "Raul")
    kucing.bersuara()
}
```

---


# Polymorphism
![](/images/polymorphism.png)

---

# Polymorphism
##
Berubah-ubahnya suatu data berdasarkan parent yang sama.
```kotlin
raul = Manusia("Raul")

raul.bersuara() // outputs "Nama aku Raul"

rahwal = Kucing("Rahwal")

rahwal.bersuara() // outputs "Meow! pemilik aku Raul"

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
