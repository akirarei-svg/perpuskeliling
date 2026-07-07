# PerpusKeliling

**Tugas Akhir Web Statis (HTML, CSS, JavaScript)**
Tema: Sistem Perpustakaan Keliling (*Mobile Library System*)

PerpusKeliling adalah website profil dan sistem informasi perpustakaan keliling. Website ini dibuat sepenuhnya statis menggunakan HTML, CSS, dan JavaScript murni (Vanilla) tanpa tambahan framework atau library eksternal, kecuali Google Fonts.

Melalui web ini, pengunjung bisa melihat profil perpustakaan, mencari katalog buku, mengecek jadwal rute armada, hingga mengisi formulir pendaftaran anggota.

---

## Struktur Folder

```text
perpustakaan-keliling/
├── index.html       (Beranda)
├── koleksi.html     (Katalog & Pencarian Buku)
├── jadwal.html      (Jadwal & Rute Armada)
├── layanan.html     (Info Layanan & FAQ)
├── kontak.html      (Formulir Kontak & Pendaftaran)
├── css/
│   ├── style.css    (Desain sistem global)
│   └── index.css    (Gaya khusus halaman utama)
├── js/
│   └── main.js      (Logika interaktif utama)
└── README.md

```

---

## Daftar Halaman & Fitur

* **Beranda (`index.html`):** Halaman utama yang berisi perkenalan, video profil (embed YouTube), animasi angka statistik, dan berita terbaru.
* **Katalog Buku (`koleksi.html`):** Menampilkan daftar buku. Dilengkapi dengan fitur pencarian real-time dan filter kategori menggunakan JavaScript. Terdapat juga pop-up (modal) untuk melihat detail buku.
* **Jadwal & Rute (`jadwal.html`):** Menampilkan jadwal kunjungan armada per hari. Pengunjung bisa menggunakan sistem *tab* untuk mengganti hari, dan mencari lokasi terdekat menggunakan form pencarian.
* **Layanan (`layanan.html`):** Penjelasan layanan yang ada, alur peminjaman, dan bagian *Frequently Asked Questions* (FAQ) yang bisa di-klik buka-tutup (Accordion).
* **Kontak & Daftar (`kontak.html`):** Berisi informasi kontak, tabel jam operasional, dan dua formulir (hubungi kami & daftar anggota) yang dilengkapi validasi input sebelum disubmit.

---

## Fitur JavaScript (Interaktivitas)

Karena tidak menggunakan *backend*, semua interaksi diproses langsung di browser menggunakan JavaScript:

* **Manipulasi DOM Dinamis:** Katalog buku dan hasil pencarian rute dirender langsung tanpa perlu *reload* halaman.
* **Sistem Tab & Accordion:** Digunakan pada halaman jadwal (pindah hari) dan halaman layanan (FAQ).
* **Validasi Formulir:** Mengecek apakah email valid, input tidak kosong, dan format nomor telepon benar sebelum form disimulasikan terkirim.
* **Utilitas Visual:** Animasi *counter* angka di beranda, tombol *scroll-to-top*, dan navigasi menu *hamburger* untuk tampilan HP.

---

## Cara Menjalankan Project

Website ini sangat ringan dan tidak butuh instalasi database atau server khusus.

1. Unduh atau *clone* repository ini.
2. Buka folder `perpustakaan-keliling`.
3. Klik dua kali pada file `index.html` untuk membukanya di browser.
4. (Opsional/Rekomendasi) Gunakan ekstensi **Live Server** di VS Code agar lebih nyaman saat melihat perubahan kode.

---

## Checklist Pemenuhan Syarat Tugas Akhir

* Minimal 5 halaman HTML terhubung
* Minimal 3 blok logika JavaScript yang berfungsi
* Menggunakan elemen form (Input teks, dropdown, radio/checkbox)
* Menggunakan elemen tabel
* Terdapat gambar dan video (Iframe YouTube)
* Desain responsif (Bisa dibuka di HP, Tablet, dan Desktop)
* Murni statis (HTML, CSS, JS)

---

## Tim Pengembang

| Nama | NIM | Peran |
| --- | --- | --- |
| [Nama Anda] | [NIM Anda] | Front-end Developer |
| [Nama Teman] | [NIM Teman] | UI/UX & Content |
| [Nama Teman] | [NIM Teman] | JavaScript Logic & QA |