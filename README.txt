NAVIGATIONLAB - MODUL PRAKTIKUM 07

Project ini merupakan kelanjutan NavigationLab Modul 06. Aplikasi mengambil
data pengguna dari REST API DummyJSON menggunakan Retrofit 3 dan Gson.

CARA MENJALANKAN
1. Ekstrak ZIP dan buka folder NavigationLab_Modul06 melalui Android Studio.
2. Pastikan komputer/emulator memiliki koneksi internet.
3. Lakukan Gradle Sync.
4. Jalankan aplikasi pada emulator/perangkat Android.
5. Home mengambil 10 pengguna dari https://dummyjson.com/users?limit=10.
6. Masukkan nama pada kolom pencarian, misalnya John, lalu tekan tombol Cari.
7. Untuk memuat kembali daftar awal, kosongkan kolom pencarian lalu tekan Cari.
8. Pilih salah satu hasil untuk melihat detail berdasarkan ID pengguna.

FITUR PENCARIAN
- Endpoint: GET https://dummyjson.com/users/search?q={query}
- StudentApiService menyediakan searchUsers(@Query("q") query: String).
- StudentRemoteDataSource menangani request Retrofit dan callback.
- StudentRepository mengubah UserDto menjadi model Student.
- HomeUiState menyimpan searchQuery, daftar pengguna, loading, dan error.
- HomeViewModel mengatur pencarian dan pemuatan ulang daftar.
- HomeScreen hanya berkomunikasi dengan callback ViewModel; UI tidak memanggil
  StudentApiService atau RetrofitClient secara langsung.
- Pencarian hanya berjalan ketika tombol Cari ditekan (tanpa debounce).
- Loading, error, dan hasil kosong ditampilkan pada UI.

SCREENSHOT UNTUK LAPORAN
Arsip sumber ini tidak menyertakan screenshot emulator karena aplikasi belum
dijalankan pada perangkat/emulator di sesi pengerjaan ini. Setelah menjalankan
aplikasi di Android Studio:
1. Buka aplikasi dan ketik John pada kolom pencarian.
2. Tekan tombol Cari hingga hasil pengguna tampil.
3. Ambil screenshot emulator yang memperlihatkan kolom pencarian dan hasilnya.
4. Masukkan gambar tersebut ke bagian implementasi/pengujian fitur pencarian
   pada laporan praktikum, dengan caption:
   "Gambar. Hasil pencarian profil pengguna menggunakan endpoint DummyJSON."

CATATAN
- Permission INTERNET telah ditambahkan pada AndroidManifest.xml.
- Home dan Detail memiliki tampilan loading, error, dan tombol Coba Lagi.
- Halaman Profile dan About serta navigasi dari Modul 06 tetap dipertahankan.
- Jika request gagal, periksa koneksi internet lalu tekan Coba Lagi.
