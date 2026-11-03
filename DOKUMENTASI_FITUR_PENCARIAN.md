# Dokumentasi Implementasi Fitur Pencarian Profil

## Alur implementasi

1. **API Service** — `StudentApiService.searchUsers()` mendefinisikan endpoint `users/search` dengan query parameter `q`.
2. **Remote Data Source** — `StudentRemoteDataSource.searchUsers()` menjalankan request Retrofit secara asynchronous dan mengembalikan `Result<List<UserDto>>`.
3. **Repository** — `StudentRepository.searchStudents()` meneruskan pencarian dan memetakan `UserDto` menjadi model `Student`.
4. **State dan ViewModel** — `HomeUiState.searchQuery` menyimpan teks pencarian. `HomeViewModel` mengatur pemanggilan pencarian, loading, error, dan pemuatan daftar awal.
5. **UI** — `HomeScreen` menyediakan TextField dan tombol Cari. UI hanya menerima state dan callback, tidak mengakses Retrofit/API secara langsung.

## Pengujian manual

| Skenario | Langkah | Hasil yang diharapkan |
|---|---|---|
| Pencarian berhasil | Masukkan `John`, tekan Cari | Daftar pengguna yang cocok ditampilkan |
| Query kosong | Kosongkan kolom, tekan Cari | Daftar awal pengguna dimuat kembali |
| Hasil tidak ditemukan | Masukkan kata yang tidak cocok, tekan Cari | Pesan pengguna tidak ditemukan |
| Memilih hasil | Tekan salah satu kartu pengguna | Halaman Detail terbuka berdasarkan ID |
| Koneksi gagal | Matikan internet lalu cari | Pesan error dan tombol Coba Lagi ditampilkan |

## Screenshot laporan

Tambahkan screenshot aktual dari emulator setelah pencarian berhasil. Screenshot perlu memperlihatkan kolom pencarian berisi `John`, tombol Cari, dan daftar hasil pencarian.

**Caption:** Gambar. Hasil pencarian profil pengguna menggunakan endpoint DummyJSON.

> Screenshot aktual tidak disertakan dalam ZIP ini karena aplikasi belum dijalankan pada emulator/perangkat selama proses pengeditan.
