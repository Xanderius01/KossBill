# KossBill — Modul 8: Data Dinamis & Logika Aplikasi

KossBill adalah prototipe web responsif pencarian dan pemesanan kos mahasiswa. Versi ini melanjutkan proyek Modul 7 dengan sumber data JSON terpisah, pencarian/filter, validasi formulir, UX states, dan dokumentasi pengujian. Teknologi: HTML5, CSS3, JavaScript murni, JSON, dan `localStorage` untuk data demo di browser.

## Menjalankan proyek

1. Ekstrak ZIP dan buka folder `KossBill-Modul8` di VS Code.
2. Jalankan `index.html` dengan ekstensi **Live Server**. Jangan membuka file HTML langsung (`file://`) karena browser membatasi `fetch()` ke JSON lokal.
3. Pastikan `data/properties.json` tetap berada pada struktur folder yang sama.

## Struktur proyek

```text
KossBill-Modul8/
├── index.html
├── style.css
├── script.js
├── data/
│   └── properties.json
├── assets/
├── README.md
├── TESTING.md
├── AI-PROMPT-LOG.md
├── GIT-CHECKLIST.txt
└── PRD-Modul-7.pdf
```

## Fitur dan pengujian

- Data kos dibaca dari `data/properties.json` dengan `fetch()`; kartu dirender melalui fungsi yang digunakan ulang, bukan menyalin markup kartu secara manual.
- Pencarian berdasarkan nama, lokasi, tipe penghuni, dan fasilitas.
- Filter kategori dan pengurutan harga/.
- Loading skeleton saat data dimuat, empty state ketika hasil tidak ditemukan, error state beserta tombol coba lagi ketika data gagal dimuat, dan toast untuk umpan balik.
- Wishlist, profil, dan riwayat pemesanan demo tersimpan di `localStorage`.
- Form pemesanan memeriksa nama, nomor telepon, dan tanggal; tombol menampilkan status “Mengirim...” selama pengajuan diproses.
- Layout tetap responsif dan mempertahankan identitas visual proyek Modul 7.

Lihat [TESTING.md](TESTING.md) untuk checklist pengujian manual.

## Keterbatasan dan privasi

Ini tetap prototipe front-end untuk pembelajaran. `localStorage` hanya menyimpan data pada browser/perangkat yang digunakan; pemesanan tidak dikirim ke server, tidak ada autentikasi aman, dan pembayaran tidak diproses. Jangan masukkan informasi pribadi sensitif. Data properti adalah data demo.

## Deployment

Dapat di-deploy sebagai situs statis ke Netlify, Vercel, atau GitHub Pages. Setelah deploy, uji link publik: file JSON harus berhasil dimuat, filter bekerja, dan form menghasilkan konfirmasi. Jika menggunakan layanan pihak ketiga di tahap selanjutnya, jangan menaruh secret/API key di repository publik.

## Git workflow Modul 8

Buat branch `feat/dynamic-data` dari repository Modul 7, commit perubahan bertahap, lalu buat Pull Request ke branch utama setelah tes. Jangan commit file `.env` atau credential. Panduan perintah tersedia di `GIT-CHECKLIST.txt`.

## Referensi

- Brief Penugasan Mahasiswa Modul 8 — VINIX Batch 5 (data dinamis, form/validasi, UX states, Git, deployment dan dokumentasi).
- Desain KossBill Kelompok 12: https://www.figma.com/design/Dx8VDSRZpiPoAKlEYEJIcb/KossBill-Kelompok12?node-id=35-3454


## Dataset listing kos Purwokerto (referensi Mamikos)

Folder `data/properties.json` memuat 32 listing yang disusun dari halaman hasil pencarian Mamikos untuk area sekitar UNSOED dan UMP/Kembaran. Nama listing, harga bulanan, tipe penghuni, dan fasilitas hanya dicantumkan jika terlihat pada halaman sumber yang dirujuk per entri. Daftar ini **bukan seluruh kos di Purwokerto**; hasil pencarian Mamikos mencakup banyak halaman, area, dan listing yang dapat berubah.

- Sumber area UNSOED: https://mamikos.com/kost/kost-eksklusif-dekat-unsoed-purwokerto-murah?gender=2&sort=price%2Casc
- Sumber area UMP/Kembaran: https://mamikos.com/kost/kost-dekat-ump-purwokerto-murah
- Harga dan ketersediaan dapat berubah; periksa tautan sumber dan konfirmasi langsung ke pengelola sebelum mengambil keputusan.
- Informasi yang tidak tersedia tidak dibuat-buat; harga dan ketersediaan perlu dikonfirmasi melalui sumber.
- Foto pada prototipe masih menggunakan aset ilustrasi bawaan proyek, **bukan foto asli yang diverifikasi untuk setiap kos**. Jangan menyajikannya sebagai foto properti sebenarnya.
- Dataset ini untuk demonstrasi akademik dan tidak berafiliasi dengan Mamikos.


## Tambahan data Google Maps dan autentikasi demo
Dataset mencakup 33 listing sumber Mamikos yang sudah ada dan 39 tautan Google Maps unik dari pengguna. Entri Google Maps tanpa nama yang dapat dikonfirmasi diberi label sementara dan `dataStatus: needs_review`; harga/fasilitas tidak ditebak. Entri tanpa harga dapat dibuka detailnya dan menuju sumber Google Maps, tetapi tidak dapat masuk alur booking. Login/daftar bersifat demo browser (localStorage), bukan autentikasi aman untuk produksi.


## Fitur tambahan revisi
- Pemesanan mensyaratkan pengguna masuk/daftar terlebih dahulu (demonstrasi localStorage).
- Filter wilayah terdekat berbasis nama area yang dimasukkan pengguna; jarak kilometer tidak dihitung tanpa koordinat listing yang tervalidasi.
- Metode pembayaran ditampilkan sebagai pilihan simulasi; tidak ada transaksi nyata.
- Tombol kontak membuka WhatsApp hanya jika nomor properti tersedia; jika tidak, membuka sumber Google Maps.
- Listing Google Maps tanpa nama properti yang berhasil diidentifikasi tidak dimasukkan sebagai data aktif.

## Tambahan UI/UX (Chat, Dark Mode, Tombol Kembali)
- Tombol bulan/bintang di header beralih antara mode terang dan gelap; preferensi disimpan di `localStorage`.
- Tombol kembali global muncul pada halaman selain Beranda dan mengikuti riwayat navigasi internal. Halaman detail, booking, dan chat juga memiliki tombol kembali.
- Chat pengelola dibuka di dalam KossBill (bukan dialihkan ke aplikasi lain), menyimpan percakapan demo per properti pada browser.
- **Batasan:** chat saat ini adalah simulasi lokal. Pesan tidak diterima pengelola secara nyata hingga ada backend/API, identitas pengelola, dan sistem pengiriman pesan.


## Revisi Stage 1–2 (20 Oktober 2026)
- Memperkuat pembacaan `localStorage` agar satu nilai lokal yang rusak tidak menghentikan seluruh skrip.
- Memvalidasi struktur record sebelum listing dirender dan menampilkan status pemuatan data.
- Memperluas pencarian ke nama, alamat, deskripsi, sumber, tipe kamar, dan fasilitas.
- Menambahkan filter harga minimum/maksimum, tipe penghuni, dan fasilitas.
- Memperbaiki Reset pencarian agar membersihkan kata kunci, wilayah, kategori, pengurutan, dan semua filter lanjutan.
- Menambahkan validasi rentang harga serta pesan status hasil pencarian.
- Detail data dengan harga yang belum tersedia tetap tidak dianggap Rp0; bila memakai filter harga, listing tanpa harga tidak dapat dipastikan memenuhi rentang tersebut dan tidak dimasukkan ke hasil filter harga.

## Pengembangan Tahap 3–5 (20 Oktober 2026)
- **Bandingkan kos:** pilih maksimal tiga listing dari kartu Cari Kos, bandingkan harga awal, lokasi, tipe penghuni, fasilitas, jumlah tipe kamar, dan sumber. Pilihan disimpan di `localStorage` browser.
- **Peta interaktif:** menggunakan Leaflet dan OpenStreetMap. Peta hanya memberi penanda untuk listing yang memiliki koordinat `coordinates: { lat, lng }` terverifikasi. Data saat ini belum memiliki koordinat, sehingga peta menjelaskan keterbatasan itu dan tetap menyediakan tautan ke sumber/lokasi listing; tidak ada koordinat yang dibuat-buat.
- **Dark mode riwayat:** kartu riwayat, judul, metadata, total simulasi, dan status sekarang menggunakan warna yang sesuai tema gelap.
- **Penyempurnaan pengalaman pengguna:** tombol akses cepat ke peta/perbandingan, status pemesanan dan nomor referensi di riwayat, layout responsif, serta keadaan kosong yang lebih jelas.

Catatan: fitur ini adalah prototipe front-end. Wishlist, riwayat, chat, perbandingan, dan akun disimpan lokal di browser; belum ada backend atau transaksi nyata. Peta dasar memerlukan koneksi internet untuk memuat library/tiles.


## Listing foto asli dari pengguna
- Yellow Kost Purwokerto: foto asli lokal `assets/yellow-kost-purwokerto.png`, harga Rp500.000/bulan.
- Kost Puri Pertiwi Purwokerto: foto asli lokal `assets/kost-puri-pertiwi-purwokerto.png`, harga ditampilkan sebagai `infoselengkapnya hubungi penjual`, tipe Campur, fasilitas ditampilkan sebagai `info selengkapnya hubungi penjual`.
- Foto asli yang diunggah pengguna disalin byte-for-byte tanpa pengeditan.


### Listing foto asli dari pengguna
- Rens Home Kost dekat UNSOED (Khusus Mahasiswi): foto asli tersimpan di `assets/rens-home-kost-unsoed.png` tanpa pengeditan. Harga dan fasilitas ditampilkan sebagai “info selengkapnya hubungi penjual”.


### Data listing KOST HIRO
- Listing KOST HIRO ditambahkan berdasarkan informasi pengguna.
- Foto asli disimpan sebagai `assets/kost-hiro-purwokerto.jpeg` tanpa perubahan.
- Harga dan detail fasilitas belum tersedia; halaman menampilkan keterangan untuk menghubungi penjual.
