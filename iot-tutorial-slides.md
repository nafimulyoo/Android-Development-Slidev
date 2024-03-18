
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

===