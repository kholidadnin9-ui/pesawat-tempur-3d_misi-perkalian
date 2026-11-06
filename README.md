# SPACE FIGHTER 3D — MISSION MULTIPLICATION

Game edukasi matematika 3D untuk latihan perkalian melalui misi pesawat luar angkasa. Proyek dibuat sebagai situs statis sehingga dapat langsung dipublikasikan menggunakan GitHub Pages.

## Fitur

- 5 level dengan 10 soal pada setiap level (total 50 soal per rangkaian permainan).
- Materi bertahap dari perkalian 1–5 hingga campuran perkalian 1–10.
- Tiga gerbang jawaban pada setiap soal; pemain harus menerbangkan pesawat melewati gerbang dengan jawaban yang benar.
- Skor, combo, akurasi, bonus waktu, bintang bonus, dan sistem nyawa.
- Lima pilihan warna pesawat serta dua mode kamera.
- Pengaturan sensitivitas, kualitas grafis, dan suara.
- Progres level, warna pesawat, dan skor terbaik disimpan pada `localStorage` browser.
- Tata letak responsif untuk desktop, tablet, dan ponsel.

## Kontrol permainan

| Aksi | Keyboard | Layar sentuh |
|---|---|---|
| Menggerakkan pesawat | `W A S D` atau tombol panah | Joystick virtual |
| Menembak | Tahan `SPACE` | Tahan tombol `FIRE` |
| Boost | Tahan `SHIFT` | Tahan tombol `BOOST` |
| Mengganti kamera | `C` | Tombol kamera |
| Jeda / lanjut | `P` atau `ESC` | Tombol jeda |

## Menjalankan di komputer

Karena browser dapat membatasi sebagian fitur ketika file dibuka langsung melalui `file://`, jalankan melalui server lokal sederhana.

**Python**

```bash
python -m http.server 8000
```

Kemudian buka `http://localhost:8000` pada browser.

Tidak ada proses build atau instalasi paket yang diperlukan untuk menjalankan versi situs ini.

## Publikasi melalui GitHub Pages

Workflow sudah disiapkan pada `.github/workflows/deploy.yml`. Secara otomatis, situs akan dipublikasikan setiap kali ada perubahan yang di-*push* ke branch `main`.

1. Buat repository baru di GitHub.
2. Ekstrak arsip proyek ini, lalu unggah seluruh isi folder proyek ke root repository. Pastikan `index.html`, `tailwind.css`, `.nojekyll`, `README.md`, dan folder `.github` ikut terunggah.
3. Buka **Settings → Pages** pada repository.
4. Pada bagian **Build and deployment → Source**, pilih **GitHub Actions**.
5. Pastikan file workflow berada di `main`, lalu buka tab **Actions** untuk melihat proses publikasi.
6. Setelah workflow berhasil, situs dapat dibuka pada alamat:

   `https://USERNAME.github.io/NAMA-REPOSITORY/`

Ganti `USERNAME` dan `NAMA-REPOSITORY` sesuai akun serta nama repository. Untuk pembaruan berikutnya, cukup *push* perubahan ke branch `main`; workflow akan menerbitkan ulang situs.

> Jika branch utama repository bukan `main`, ubah bagian `branches` pada workflow agar sesuai dengan nama branch tersebut.

## Dependensi eksternal

- [Three.js r128](https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js) untuk rendering 3D.
- [Google Fonts](https://fonts.google.com/) untuk font Orbitron dan Inter.
- Tailwind CSS 4.1.10 sudah dikompilasi menjadi `tailwind.css` dan disimpan di repository. Tidak ada ketergantungan pada Tailwind Play CDN saat situs dijalankan.

Game memerlukan koneksi internet agar Three.js dan Google Fonts dapat dimuat. Jika koneksi ke CDN tidak tersedia atau browser tidak mendukung WebGL, halaman akan menampilkan pesan kegagalan pemuatan.

## Penyimpanan progres

Progres tersimpan secara lokal di browser/perangkat yang digunakan. Data tidak otomatis tersinkron antarperangkat atau antarbrowser. Menghapus data situs pada browser dapat menghapus progres permainan.

## Berkas utama

```text
.
├── index.html
├── tailwind.css
├── README.md
├── .nojekyll
└── .github/
    └── workflows/
        └── deploy.yml
```
