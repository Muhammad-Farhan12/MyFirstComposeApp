# Homework 6 — My First Compose App

## Task 3: Colour and Spacing
* **Colour used:** Color.LightGray
* **Padding kept:** [Isi dengan angka terakhir yang kamu pakai, misal: 24.dp]
* **What changed / what stayed the same:** Saat padding diubah menjadi 8.dp, elemen konten menjadi sangat dekat dengan tepi layar. Saat diubah menjadi 48.dp, jarak tepi menjadi sangat lebar sehingga menekan konten ke tengah. Yang tetap sama adalah ukuran *font* teks dan proporsi gambar di dalamnya.

## Task 4: Build Error
* **First error message:** File-based resource names must contain only lowercase a-z, 0-9, or underscore.
* **Cause:** Sistem Android memiliki aturan ketat di mana file *resource* (seperti gambar di folder drawable) tidak boleh menggunakan huruf kapital dan tanda strip/hubung (-).
* **Why other errors appear:** Karena gambar gagal diproses saat proses kompilasi, kelas referensi `R` menjadi tidak valid. Hal ini memicu *error* lanjutan (seperti "Unresolved reference") pada baris kode Kotlin yang memanggil gambar tersebut.
* **Fix:** Melakukan Refactor > Rename pada file gambar untuk mengubahnya kembali menggunakan huruf kecil semua tanpa tanda strip (yaitu `my_picture.png`).

## Task 5: Explore the Project
* **(a) MainActivity:** Terletak di `app/src/main/java/com/example/myfirstcomposeapp/MainActivity.kt`. File ini berfungsi sebagai titik awal (entry point) aplikasi di mana logika tampilan dan komponen UI dipanggil.
* **(b) Gradle file:** Terletak di `app/build.gradle.kts`. File ini berfungsi untuk mengelola konfigurasi kompilasi proyek, seperti mengatur versi Android dan mendaftarkan *library* eksternal yang dibutuhkan oleh Jetpack Compose.
* **(c) Launcher image line:** `painter = painterResource(id = R.drawable.my_picture)` — berfungsi untuk memuat dan menghubungkan sumber gambar dari folder `drawable` agar dapat ditampilkan oleh komponen `Image`.

## Task 6: Preview vs Run
Mode "Preview" memungkinkan kita untuk merender dan melihat pratinjau desain UI secara instan di dalam Android Studio tanpa harus mengompilasi seluruh aplikasi. Sebaliknya, tombol "Run" akan mengompilasi keseluruhan kode menjadi file instalasi aplikasi utuh dan memasangnya secara nyata ke dalam *smartphone* fisik atau Emulator.

## Task 7: Views vs Compose
* **1. Perbedaan Utama:** Pendekatan "Views" menggunakan metode imperatif (mendesain layar dengan file XML terpisah, lalu memanipulasinya di Kotlin). Sedangkan Jetpack "Compose" menggunakan metode deklaratif di mana seluruh antarmuka (UI) ditulis langsung menggunakan bahasa pemrograman Kotlin yang akan merender ulang dirinya sendiri secara otomatis jika ada perubahan data.
* **2. Komponen Tabel:**
  | Composable | Package | Library layer |
  |---|---|---|
  | Column | androidx.compose.foundation.layout | Foundation |
  | Text | androidx.compose.material3 | Material Design |
  | Image | androidx.compose.foundation | Foundation |