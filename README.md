# 🎵 Flutter SizedBox, Spacer, dan Card

## 📝 Deskripsi Singkat

Project ini merupakan aplikasi Flutter yang mempelajari penggunaan widget `SizedBox`, `Spacer`, dan `Card` untuk membangun antarmuka aplikasi yang rapi dan proporsional.

Melalui project ini, penggunaan `SizedBox` untuk mengatur ukuran dan jarak tetap, `Spacer` untuk memberikan jarak berdasarkan proporsi ruang yang tersedia, serta `Card` untuk menyajikan informasi dalam bentuk kartu dipelajari melalui beberapa percobaan.

Penerapan widget tersebut digunakan untuk membuat kotak berwarna, mengatur jarak antarwidget, menampilkan informasi lokasi wisata, serta merancang tampilan kartu informasi musik yang sedang diputar.

## 📱 Tampilan Aplikasi

Project ini mencakup beberapa contoh penerapan widget Flutter:

- 🟨 Tiga kotak berwarna yang disusun menggunakan `Row`.
- 📏 Pengaturan ukuran kotak menggunakan `SizedBox`.
- ↔️ Pengaturan jarak proporsional menggunakan `Spacer`.
- 📍 Kartu informasi lokasi wisata dengan ikon, judul, dan deskripsi.
- 🎵 Kartu informasi musik dengan ikon cover album, judul lagu, dan nama artis.
- ❤️ Tombol like pada kartu musik.
- 🌙 Tampilan gelap menggunakan `ThemeData.dark()` pada tugas akhir.

## 🚀 Teknologi yang Digunakan

| Teknologi | Kegunaan |
|---|---|
| Flutter | Framework untuk membangun antarmuka aplikasi |
| Dart | Bahasa pemrograman aplikasi |
| Material Design | Komponen antarmuka Flutter |
| `SizedBox` | Mengatur ukuran widget atau memberikan jarak tetap |
| `Spacer` | Memberikan jarak fleksibel berdasarkan nilai `flex` |
| `Card` | Menampilkan informasi dalam bentuk kartu |
| `Row` | Menyusun widget secara horizontal |
| `Column` | Menyusun widget secara vertikal |
| `ListTile` | Menampilkan informasi berupa ikon, judul, dan deskripsi |
| `OutlinedButton` | Membuat tombol dengan garis tepi |
| `Icon` | Menampilkan ikon pada antarmuka |
| `ThemeData.dark()` | Mengatur tema aplikasi menjadi gelap |

## 🔄 Alur Kerja Aplikasi

Penggunaan widget dalam project ini dapat digambarkan melalui alur berikut:

```text
┌────────────────────────┐
│       main.dart        │
│    Titik Awal App      │
└───────────┬────────────┘
            ▼
┌────────────────────────┐
│      MaterialApp       │
│  Konfigurasi Aplikasi  │
└───────────┬────────────┘
            ▼
┌────────────────────────┐
│        Scaffold        │
│     Struktur Halaman   │
└───────────┬────────────┘
            ▼
┌────────────────────────┐
│     Row / Column       │
│   Menyusun Widget      │
└───────────┬────────────┘
            ▼
┌────────────────────────┐
│   SizedBox / Spacer    │
│   Mengatur Jarak       │
└───────────┬────────────┘
            ▼
┌────────────────────────┐
│         Card           │
│  Menampilkan Informasi │
└───────────┬────────────┘
            ▼
┌────────────────────────┐
│      GUI Aplikasi      │
│  Tampilan pada Layar   │
└────────────────────────┘
```

Widget `SizedBox` dan `Spacer` digunakan untuk mengatur tata letak, sedangkan `Card` menjadi wadah untuk menampilkan informasi secara terorganisir.

## 📂 Struktur Project

Struktur dasar project Flutter yang digunakan:

```text
demo_sizedbox/
│
├── android/
├── ios/
├── lib/
│   └── main.dart
│
├── test/
├── pubspec.yaml
├── pubspec.lock
└── README.md
```

Project berikutnya pada modul menggunakan nama `demo_card`, sedangkan tugas akhir dapat dibuat dalam project baru bernama `music_card`.

### `lib/main.dart`

Berisi kode utama aplikasi, mulai dari fungsi `main()`, class `MyApp`, konfigurasi `MaterialApp`, hingga penyusunan widget pada bagian `body`.

Pada percobaan SizedBox, file ini memuat method `kotakUji()` untuk membuat kotak berwarna.

Pada percobaan Card, file ini digunakan untuk menyusun kartu informasi lokasi menggunakan `Card`, `Column`, `ListTile`, dan `OutlinedButton`.

Pada tugas akhir, file ini digunakan untuk membangun kartu informasi musik dengan kombinasi `Card`, `SizedBox`, dan `Spacer`.

### `pubspec.yaml`

Berisi konfigurasi project dan dependency yang digunakan oleh Flutter.

### `README.md`

Berisi dokumentasi mengenai project, konsep widget, fitur, dan cara menjalankan aplikasi.

*Catatan: Struktur folder dapat berbeda sesuai project yang dibuat dan platform yang diaktifkan.*

## 📏 Percobaan 1 – SizedBox

Widget `SizedBox` digunakan untuk menentukan ukuran tertentu pada widget atau memberikan ruang kosong di antara beberapa widget.

Contoh penggunaan untuk memberikan jarak:

```dart
Row(
  mainAxisAlignment: MainAxisAlignment.center,
  children: [
    kotakUji(Colors.amber),
    const SizedBox(width: 25),
    kotakUji(Colors.green),
    const SizedBox(width: 25),
    kotakUji(Colors.blue),
  ],
)
```

Pada contoh tersebut, setiap kotak dipisahkan dengan jarak horizontal sebesar 25 piksel logis.

`SizedBox` juga dapat digunakan untuk mengatur ukuran widget:

```dart
SizedBox(
  width: 100,
  height: 100,
  child: kotakUji(Colors.green),
)
```

Kotak hijau ditempatkan dalam ruang berukuran 100 × 100 piksel logis, meskipun ukuran visual anaknya tetap dipengaruhi oleh batasan tata letak yang diberikan Flutter.

## ↔️ Percobaan 2 – Spacer

Widget `Spacer` digunakan untuk memberikan jarak fleksibel di antara widget. Besarnya ruang yang dialokasikan ditentukan oleh nilai `flex` dibandingkan dengan `Spacer` lain dalam susunan `Row` atau `Column` yang sama.

Contoh penggunaan:

```dart
Row(
  children: [
    kotakUji(Colors.amber),
    const Spacer(flex: 1),
    SizedBox(
      width: 100,
      height: 100,
      child: kotakUji(Colors.green),
    ),
    const Spacer(flex: 2),
    kotakUji(Colors.blue),
  ],
)
```

Pada contoh tersebut:

- `Spacer(flex: 1)` memperoleh satu bagian dari ruang fleksibel yang tersedia.
- `Spacer(flex: 2)` memperoleh dua bagian dari ruang fleksibel yang tersedia.
- Jarak menyesuaikan sisa ruang pada tata letak.

Dengan demikian, `Spacer` berbeda dari `SizedBox` kosong yang menggunakan ukuran tetap.

## 🃏 Percobaan 3 – Card

Widget `Card` digunakan untuk menampilkan informasi dalam bentuk panel yang terorganisir, biasanya dilengkapi sudut membulat dan bayangan.

Pada modul ini, Card digunakan untuk menampilkan informasi lokasi Taman Nasional Bromo Tengger Semeru.

Informasi yang ditampilkan meliputi:

- 📍 Ikon lokasi menggunakan `Icons.location_pin`.
- 🏞️ Judul lokasi wisata.
- 📌 Deskripsi wilayah.
- 🗺️ Tombol dengan ikon peta.
- ☎️ Tombol dengan ikon telepon.

Contoh struktur dasar:

```dart
Card(
  margin: const EdgeInsets.all(8),
  child: Column(
    mainAxisSize: MainAxisSize.min,
    children: [
      const ListTile(
        leading: Icon(
          Icons.location_pin,
          color: Colors.red,
        ),
        title: Text(
          'Taman Nasional Bromo Tengger Semeru',
          style: TextStyle(
            fontSize: 15,
            fontWeight: FontWeight.bold,
          ),
        ),
        subtitle: Text('Jawa Timur, Indonesia'),
      ),
    ],
  ),
)
```

Widget `ListTile` membantu menyusun ikon, judul, dan deskripsi secara rapi di dalam Card. Tombol tambahan dapat diletakkan di bawahnya menggunakan `Row` dan `OutlinedButton`.

## 🎵 Tugas – Kartu Informasi Musik

Tugas akhir pada modul adalah membuat UI aplikasi untuk menampilkan informasi musik yang sedang diputar menggunakan kombinasi `Card`, `SizedBox`, dan `Spacer`.

### Fitur utama

- 🎨 Tampilan gelap menggunakan `ThemeData.dark()`.
- 🎵 Judul halaman **Sedang memutar** pada AppBar.
- 💿 Ikon sebagai representasi cover album.
- 🎶 Judul lagu.
- 👤 Nama artis.
- ❤️ Tombol aksi untuk memberi tanda suka atau like.

### Pengaturan tata letak

- Menggunakan `AppBar` dengan `centerTitle: true`.
- Menempatkan Card di bagian tengah layar menggunakan `Center`.
- Mengatur `elevation: 4` untuk memberikan bayangan pada Card.
- Menggunakan `RoundedRectangleBorder` dengan `BorderRadius.circular(12)` untuk sudut membulat.
- Menggunakan padding 12 piksel logis agar isi Card tidak terlalu dekat dengan tepinya.
- Menggunakan `SizedBox` untuk memberikan jarak tetap antar elemen.
- Menggunakan `Spacer` untuk mengatur jarak secara proporsional.

Kombinasi widget tersebut menghasilkan tampilan informasi musik yang sederhana, terstruktur, dan selaras dengan tema gelap aplikasi.

## ▶️ Cara Menjalankan Project

Pastikan Flutter SDK dan Android Studio telah terpasang serta emulator atau smartphone sudah tersedia.

### 1. Masuk ke folder project

Untuk percobaan SizedBox:

```bash
cd demo_sizedbox
```

Untuk percobaan Card:

```bash
cd demo_card
```

Untuk tugas akhir, gunakan folder project `music_card` jika project tersebut sudah dibuat.

### 2. Install dependency

```bash
flutter pub get
```

### 3. Periksa perangkat

```bash
flutter devices
```

### 4. Jalankan aplikasi

```bash
flutter run
```

Aplikasi juga dapat dijalankan melalui tombol Run (▶) pada Android Studio setelah perangkat dipilih.

## 🎯 Konsep yang Dipelajari

Project ini membantu memahami beberapa konsep dasar pengembangan antarmuka Flutter:

- Penggunaan widget `SizedBox`.
- Penggunaan widget `Spacer`.
- Penggunaan widget `Card`.
- Perbedaan jarak tetap dan jarak fleksibel.
- Pengaturan ukuran widget.
- Penggunaan properti `flex`.
- Penyusunan widget menggunakan `Row` dan `Column`.
- Penggunaan `ListTile` untuk menampilkan informasi.
- Penggunaan `OutlinedButton` untuk membuat tombol.
- Pengaturan sudut membulat dan bayangan Card.
- Penerapan tema gelap menggunakan `ThemeData.dark()`.
- Kombinasi widget untuk membuat antarmuka yang rapi dan proporsional.

## 🛠️ Pengembangan Selanjutnya

Project ini dapat dikembangkan lebih lanjut dengan:

- Mengganti ikon cover album dengan gambar album.
- Menambahkan informasi durasi lagu.
- Membuat tombol like yang dapat berubah ketika ditekan.
- Menambahkan tombol Play dan Pause.
- Menambahkan informasi nama penyanyi dan album.
- Menyesuaikan ukuran Card untuk berbagai ukuran layar.
- Mengembangkan tampilan menjadi halaman pemutar musik sederhana.

## 📚 Tujuan Pembelajaran

Project ini bertujuan untuk memahami fungsi `SizedBox`, `Spacer`, dan `Card` dalam pengembangan antarmuka Flutter.

Melalui percobaan kotak berwarna, kartu informasi lokasi, dan kartu informasi musik, pengguna dapat memahami cara mengatur ukuran, jarak, dan penyajian informasi menggunakan widget Flutter.

```text
SizedBox
   ↓
Mengatur Ukuran dan Jarak Tetap
   ↓
Spacer
   ↓
Mengatur Jarak Proporsional
   ↓
Card
   ↓
Menyusun Informasi
   ↓
UI Informasi Musik
```

Dengan memahami ketiga widget tersebut, pengguna dapat membangun tata letak aplikasi yang lebih terstruktur dan menyesuaikan penggunaan ruang sesuai kebutuhan antarmuka.

## 👨‍💻 Project

**Flutter SizedBox, Spacer, dan Card**

Dibangun menggunakan:

**Flutter + Dart + Material Design**
