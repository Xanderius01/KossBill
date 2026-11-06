# Catatan sumber data KossBill

Data JSON memuat 32 listing yang terlihat pada hasil pencarian Mamikos di sekitar UNSOED dan UMP/Kembaran, Purwokerto. Ini merupakan sampel terverifikasi dari informasi yang tampil pada halaman sumber, bukan inventaris lengkap seluruh kos Purwokerto.

- [Mamikos — Kost Eksklusif dekat UNSOED Purwokerto](https://mamikos.com/kost/kost-eksklusif-dekat-unsoed-purwokerto-murah?gender=2&sort=price%2Casc)
- [Mamikos — Kost dekat UMP Purwokerto](https://mamikos.com/kost/kost-dekat-ump-purwokerto-murah)

Harga/fasilitas adalah data yang tampil saat penelusuran dan dapat berubah. Ketersediaan harus dikonfirmasi langsung. Data rating dan jarak tidak ditambahkan jika tidak dapat diverifikasi dari halaman listing yang digunakan. Semua foto yang ditampilkan oleh prototipe saat ini adalah ilustrasi lokal, bukan foto asli kos yang bersangkutan.


## Tautan Google Maps dari pengguna
Sebanyak 39 URL Google Maps unik ditambahkan sebagai entri awal. 18 nama pertama mengikuti daftar identifikasi awal, tetapi semua detail harga/fasilitas/ketersediaan tidak dianggap terverifikasi. Entri sisanya memakai label sementara sampai nama lokasi diperiksa manual. URL sumber disimpan pada setiap objek (`sourceUrl`/`mapsUrl`). Harga kosong (`null`) tidak ditampilkan sebagai Rp0 dan pemesanan simulasi dinonaktifkan untuk entri tanpa harga. Foto lokal adalah ilustrasi, bukan foto asli listing.

## Login dan daftar
Login/daftar pada versi ini adalah demo front-end yang menyimpan akun di localStorage dan melakukan hash SHA-256 bila Web Crypto tersedia. Ini BUKAN autentikasi produksi: jangan gunakan password penting; untuk website publik, pindahkan autentikasi ke backend tepercaya (misalnya Supabase Auth/Firebase Auth) dan jangan simpan kredensial di browser.


Catatan revisi: tautan Google Maps yang belum dapat diidentifikasi namanya dihapus dari dataset aktif, bukan diberi nama placeholder. Nomor kontak hanya digunakan jika tersedia dan dapat diverifikasi. Filter wilayah merupakan pencocokan teks area, bukan estimasi jarak kilometer.
