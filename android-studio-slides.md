
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