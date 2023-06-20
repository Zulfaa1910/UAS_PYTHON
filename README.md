Script ini merupakan contoh  pengambilan data produk menggunakan API Bukalapak berdasarkan kata kunci yang dimasukkan oleh pengguna. 
1. memasukkan kata kunci melalui input `key`. Kata kunci ini akan digunakan untuk mencari produk pada API Bukalapak.
2. file CSV dibuka dengan mode write (`'w'`) dengan nama file yang sesuai dengan kata kunci yang dimasukkan oleh pengguna.
3. Header file CSV ditentukan sebagai `['Nama', 'Harga', 'Alamat']` yang akan menjadi kolom-kolom pada file CSV.
4. `url = 'https://api.bukalapak.com/multistrategy-products'`. Ini adalah URL yang akan digunakan untuk mengirim permintaan API ke Bukalapak.
5. variabel `count` diinisialisasi dengan nilai awal 0. Variabel ini akan digunakan untuk menghitung jumlah produk yang berhasil diambil.
6. Dilakukan perulangan `for` dengan rentang 1 hingga 2. Ini menunjukkan bahwa kita akan mengambil data produk dari dua halaman pertama hasil pencarian.
7. Parameter permintaan API ditentukan dalam variabel `parameter` dengan nilai seperti 'keywords', 'limit', 'offset', 'facet', 'page', 'shouldUseSeoMultistrategy', 'isLoggedIn', dan 'show_search_contexts'. Nilai-nilai ini akan digunakan untuk memfilter dan membatasi hasil pencarian sesuai dengan kebutuhan.
8. Dilakukan permintaan GET ke URL API Bukalapak dengan parameter yang ditentukan sebelumnya. Hasil respons dari permintaan ini diterjemahkan ke dalam format JSON menggunakan metode `.json()`.
9. Data produk diambil dari respons JSON dengan mengakses kunci 'data'. Ini adalah daftar produk yang ditemukan berdasarkan kata kunci.
10. Dilakukan perulangan `for` untuk setiap produk dalam daftar produk. Untuk setiap produk, nama, harga, dan alamat toko diambil dari atribut yang sesuai pada objek produk.
11. `count` ditingkatkan untuk menghitung jumlah produk yang telah diambil.
12. Informasi produk seperti nomor, nama, harga, dan alamat dicetak ke konsol untuk ditampilkan kepada pengguna.
13. File CSV dibuka kembali dengan mode append (`'a'`) dan data produk ditulis ke dalam file CSV menggunakan metode `writerow()` dari objek penulis CSV.
14. Proses diulangi dengan memperbarui halaman permintaan API menggunakan nilai `page` untuk mendapatkan data produk dari halaman berikutnya.
15. Setelah selesai mengambil semua data produk, file CSV ditutup untuk menyimpan perubahan yang telah dilakukan.
