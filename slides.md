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
val a: String = "Mul"   
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

# Introduction to Android Studio
## Apa itu Android Studio?
Android Studio adalah IDE (Integrated Development Environment) resmi untuk pengembangan aplikasi Android. Android Studio dibangun di atas IntelliJ IDEA, yang merupakan IDE Java dan Kotlin yang kuat dan fleksibel yang dikembangkan oleh JetBrains.

## Mengapa Android Studio?
- Integrasi langsung dengan Android SDK
- Emulator built-in untuk testing aplikasi
- disupport langsung oleh Google dan komunitas Android Developer

---

# Introduction to Android Studio
## Langkah Instalasi
- Download dari [situs resmi Android Developer](https://developer.android.com/studio)
- Ikuti petunjuk instalasi yang sesuai dengan OS kalian (Windows, macOS, Linux)

## Setup Awal
- Konfigurasi Android SDK.
- Setup AVD (Android Virtual Device) untuk simulasi perangkat

## Verifikasi Instalasi
- Membuat proyek baru dan menjalankannya pada emulator ato device kalian

---

# Struktur Proyek
## Folders Penting:
- app/src/main/java/: Kode sumber Java/Kotlin.
- app/src/main/res/: Resources aplikasi (layout, string, images).
## Gradle Scripts:
- build.gradle (Module: app): Konfigurasi dependencies, versi aplikasi.
- build.gradle (Project): Konfigurasi untuk seluruh proyek.
## AndroidManifest.xml:
- Mendefinisikan komponen aplikasi, permissions, dan fitur hardware yang digunakan.

---

# Activity and Lifecycle
## Apa itu Activity?
Activity adalah komponen aplikasi yang menyediakan layar dengan UI untuk user. Activity biasanya berinteraksi dengan pengguna, menerima input, dan menampilkan hasilnya. Setiap activity mewakili satu hal yang bisa dilakukan user.

Satu aplikasi bisa memiliki banyak activity, tapi setiap activity harus di-declare di AndroidManifest.xml.

---

# Activity dan Lifecycle
## Activity Lifecyle
Ada beberapa activity lifecycle: 
- onCreate(): Dimulai saat inisialisasi activity. Dipakai untuk UI setup dan data binding
```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.activity_main)
    // Initialize your components here
}

```
- onStart(): Di saat Activity menjadi visible untuk user.
- onResume(): Di saat activity mulai berinteraksi dengan pengguna.
- onPause(): Di saat activity sedang diminimize Menyimpan perubahan yang tidak.permanen atau melepaskan resources. Activity masih terlihat tapi tidak di foreground.
- onStop(): Di saat activity tidak lagi terlihat untuk pengguna.
onDestroy(): Di saat activity dihancurkan. Bersihkan semua resources.

---

# Activity Lifecycle

---

# UI Layouting - XML
- Penggunaan XML
    - Mendesain UI dengan menggunakan XML
    - Struktur hierarki view dan view groups.
- Tools
    - Android Studio Layout Editor untuk drag-and-drop komponen UI.

---

# UI Layouting - Constraint Layout
- Keunggulan Constraint Layout
    - Memudahkan pembuatan layout yang kompleks dengan flat view hierarchy
- Fitur-fitur Utama:
    - Constraint untuk posisi dan ukuran views.
    - Chain, Guidelines, Barrier untuk pengaturan layout yang lebih kompleks

---

# UI Layouting - View Binding
- Pengenalan View Binding:
    - Mengakses views dalam kode tanpa findViewById.
- Implementasi:
    - Aktifkan viewBinding di file build.gradle.
    - Gunakan objek binding untuk mengakses views.

---

# UI Layouting - Material Design

- Prinsip Material Design:
    - Desain berbasis intuisi, inspirasi dari dunia nyata.
- Komponen Material Design:
    - Buttons, Cards, Text Fields dengan efek visual, motion, dan interaksi yang konsisten.

---

# Intents and Fragment
## Intent
- Apa itu Intent?
    - Intent adalah objek pesan yang digunakan untuk meminta aksi dari komponen app lainnya, baik di dalam app Anda sendiri atau dari app lain.

- Jenis Intent
    - Explicit Intents: Menentukan komponen yang akan diaktivasi. Digunakan untuk internal app navigation.
    - Implicit Intents: Tidak menyebutkan komponen spesifik; memungkinkan komponen dari app lain menangani aksi tersebut.

---

# Intents and Fragment
## Contoh Intent
Contoh explicit Intent:
Digunakan untuk memulai activity baru dalam aplikasi kalian

```kotlin
val intent = Intent(this, DetailActivity::class.java).apply {
    putExtra("EXTRA_KEY", "Some Data")
}
startActivity(intent)
```

Contoh implicit Intent:
Digunakan untuk memulai activity dari aplikasi lain, misalnya membuka browser


```kotlin
val url = Uri.parse("https://www.example.com")
val intent = Intent(Intent.ACTION_VIEW, url)
startActivity(intent)

```

Mengirim Data antar komponen
```kotlin
val url = Uri.parse("https://www.example.com")
val intent = Intent(Intent.ACTION_VIEW, url)
startActivity(intent)
```

---

# Intents and Fragment
## Fragment
- Apa itu Fragment?
    - Fragment mewakili bagian dari UI atau perilaku yang bisa ditempatkan dalam Activity. Mereka memungkinkan pendekatan modular untuk membangun UI yang kompleks dan reusable.

---

# Intents and Fragment
## Membuat Fragment

- Membuat Fragment Baru
    - Kode untuk fragment `ExampleFragment.kt`

```kotlin
class ExampleFragment : Fragment() {
    override fun onCreateView(
        inflater: LayoutInflater, container: ViewGroup?,
        savedInstanceState: Bundle?
    ): View? {
        return inflater.inflate(R.layout.fragment_example, container, false)
    }
}
```
- Menambah Fragment ke Activity
Menambahkan `ExampleFragment` ke dalam activity
```kotlin
if (savedInstanceState == null) {
    supportFragmentManager.beginTransaction()
        .replace(R.id.fragment_container, ExampleFragment())
        .commitNow()
}
```

---

# Data Persistence
## Opsi Penyimpanan Data
- Opsi Penyimpanan Data:
    - SharedPreferences untuk data kecil.
    - SQLite untuk penyimpanan database.
    - File I/O untuk menyimpan data pada filesystem.
    - Cloud storage untuk penyimpanan online.

-Best Practices:
    - Pilih metode penyimpanan berdasarkan kebutuhan data (ukuran, struktur, akses).

---

# Data Persistence
## Shared Preference
Menyimpan data ke SharedPreferences
```kotlin
val sharedPref = getSharedPreferences("MyPref", Context.MODE_PRIVATE)
with (sharedPref.edit()) {
    putString("my_key", "Some value")
    apply()
}
```
Membaca data dari SHaredPreferences
```kotlin
val defaultValue = "DefaultName"azQWQEWS    2A
val name = sharedPref.getString("my_key", defaultValue)
```

---

# More Learning Resources
Referensi:
- [Android Developer Documentation](https://developer.android.com/docs)
- [Android Studio Documentation](https://developer.android.com/studio)
- [Android Fundamental for Beginners](https://www.youtube.com/watch?v=3Ri9PPsGCEg&list=PLQkwcJG4YTCTq1raTb5iMuxnEB06J1VHX)
 
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

# Introduction to IoT Communication
## Apa itu IoT
Internet of Things merujuk pada jaringan perangkat fisik yang terhubung, yang dapat mengumpulkan dan berbagi data melalui internet.

Komunikasi efektif antar perangkat adalah kunci untuk mengumpulkan data, mengontrol perangkat, dan mengotomatisasi proses.

---

# IoT Communication Protocol
Ada beberapa protokol komunikasi IoT yang dapat digunakan untuk menghubungkan perangkat mobile ke perangkat IoT. Di antaranya:
- Bluetooth Low Energy (BLE)
- Wi-Fi Basic HTTP Communication
- WebSocket
- MQTT Communication

---

# IoT Communication Protocol
## Bluetooth Low Energy (BLE)
- Apa itu BLE?
    -BLE adalah standar nirkabel yang dirancang untuk komunikasi jarak pendek dengan konsumsi daya yang sangat rendah.
- Use Cases:
    - Perangkat wearable, beacons untuk retail dan navigasi indoor, perangkat kesehatan.
- Contoh Kode:
    - Memindai perangkat BLE di sekitar menggunakan Kotlin:

---

# IoT Communication Protocol
## Bluetooth Low Energy (BLE) - Example
```kotlin
val bluetoothAdapter: BluetoothAdapter? = BluetoothAdapter.getDefaultAdapter()
bluetoothAdapter?.bluetoothLeScanner?.startScan(scanCallback)
Slide 3: Wi-Fi HTTP Communication
```

---

# IoT Communication Protocol
## Wi-Fi HTTP Communication
- Penggunaan HTTP dalam IoT:
    -Memungkinkan perangkat IoT untuk mengirim atau menerima data melalui protokol HTTP menggunakan Wi-Fi.
- Use Cases:
    - Kontrol perangkat dari jarak jauh, update firmware, kirim data sensor ke server.

---

# IoT Communication Protocol
## Wi-Fi HTTP Communication - Example
Mengirim request HTTP GET menggunakan Kotlin:
```kotlin
val url = URL("http://yourapi.com/data")
with(url.openConnection() as HttpURLConnection) {
    requestMethod = "GET"
    inputStream.bufferedReader().use {
        it.lines().forEach { line ->
            println(line)
        }
    }
}
```

---

# IoT Communication Protocol
## WebSocket
- Apa itu WebSocket?
    - Protokol yang menyediakan saluran komunikasi full-duplex melalui satu koneksi TCP.

- Use Cases:
    - Aplikasi real-time seperti chatting, game online, dan notifikasi live.

---

# IoT Communication Protocol
## WebSocket - Example
Membuat koneksi WebSocket menggunakan Kotlin:
```kotlin
Copy code
val client = OkHttpClient()
val request = Request.Builder().url("ws://yourwebsocketserver.com").build()
val webSocketListener = object : WebSocketListener() {
    override fun onMessage(webSocket: WebSocket, text: String) {
        println("Received message: $text")
    }
}
client.newWebSocket(request, webSocketListener)
```

---

# IoT Communication Protocol
## MQTT Communication
- Apa itu MQTT
    - Protokol messaging ringan yang dirancang untuk komunikasi terbatas bandwidth dan perangkat dengan sumber daya terbatas.
- Use cases
    - Monitoring sensor, home automation, messaging dalam skenario konektivitas yang tidak stabil.

---

# IoT Communication Protocol
## MQTT Communication - Example
Mempublish pesan ke topik MQTT menggunakan Kotlin:
```kotlin
val mqttClient = MqttClient("tcp://yourmqttbroker.com:1883", MqttClient.generateClientId())
mqttClient.connect()
val message = MqttMessage("Hello, MQTT!".toByteArray())
mqttClient.publish("iot/data", message)
mqttClient.disconnect()
```

---

# More Learning Resources
- [Android Developer Connectivity Documentation](https://developer.android.com/develop/connectivity)
-
-

---
