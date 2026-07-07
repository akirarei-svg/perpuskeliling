# 📚 PerpusKeliling — Sistem Perpustakaan Keliling

> **Final Project Web Statis — HTML, CSS, JavaScript**
> Tema: Sistem Perpustakaan Keliling (Mobile Library System)

---

## 📋 Daftar Isi

1. [Gambaran Umum](#gambaran-umum)
2. [Struktur Proyek](#struktur-proyek)
3. [Halaman-Halaman Web](#halaman-halaman-web)
4. [Fitur JavaScript](#fitur-javascript)
5. [Elemen HTML yang Digunakan](#elemen-html-yang-digunakan)
6. [Cara Menjalankan](#cara-menjalankan)
7. [Penjelasan Kode](#penjelasan-kode)
8. [Checklist Ketentuan](#checklist-ketentuan)
9. [Tim Pengembang](#tim-pengembang)

---

## 🌐 Gambaran Umum

**PerpusKeliling** adalah website profil sistem perpustakaan keliling yang menampilkan:
- Informasi dan profil perpustakaan keliling
- Katalog koleksi buku yang dapat dicari dan difilter
- Jadwal dan rute kunjungan armada setiap minggu
- Layanan yang tersedia (peminjaman, donasi, edukasi)
- Formulir kontak dan pendaftaran anggota

Website ini **sepenuhnya statis** — menggunakan HTML, CSS, dan JavaScript murni tanpa framework atau library eksternal apapun (selain Google Fonts untuk tipografi).

---

## 📁 Struktur Proyek

```
perpustakaan-keliling/
│
├── index.html          ← Halaman Beranda (Homepage)
├── koleksi.html        ← Halaman Katalog Buku
├── jadwal.html         ← Halaman Jadwal & Rute
├── layanan.html        ← Halaman Layanan
├── kontak.html         ← Halaman Kontak & Daftar Anggota
│
├── css/
│   ├── style.css       ← CSS Global (design system, navbar, footer, utilitas)
│   └── index.css       ← CSS khusus halaman Beranda
│
├── js/
│   └── main.js         ← JavaScript utama (dipakai semua halaman)
│
└── README.md           ← Dokumentasi proyek ini
```

---

## 📄 Halaman-Halaman Web

### 1. `index.html` — Beranda
**Fungsi:** Halaman utama yang memperkenalkan PerpusKeliling kepada pengunjung.

**Bagian-bagian:**
| Bagian | Keterangan |
|--------|-----------|
| **Hero Section** | Heading utama, deskripsi, tombol CTA, dan statistik animasi |
| **Fitur Unggulan** | 6 kartu fitur layanan yang ada |
| **Statistik** | Counter animasi jumlah buku, rute, anggota, armada |
| **Video Profil** | Video YouTube tertanam (embed) via iframe |
| **Berita Terkini** | 3 artikel/berita terbaru dari perpustakaan |
| **CTA Section** | Ajakan daftar anggota dengan tombol aksi |

---

### 2. `koleksi.html` — Katalog Buku
**Fungsi:** Menampilkan katalog buku dengan kemampuan pencarian, filter, dan detail buku.

**Bagian-bagian:**
| Bagian | Keterangan |
|--------|-----------|
| **Search Bar** | Input pencarian real-time berdasarkan judul/penulis |
| **Filter Sidebar** | Filter berdasarkan kategori dan status ketersediaan |
| **Grid Buku** | Kartu buku dengan cover, judul, penulis, rating, status |
| **Pagination** | Navigasi halaman untuk 20 data buku |
| **Modal Detail** | Pop-up detail buku lengkap + tombol pinjam |

**Data buku:** 20 judul disimpan sebagai array JavaScript.

---

### 3. `jadwal.html` — Jadwal & Rute
**Fungsi:** Menampilkan jadwal kunjungan armada perpustakaan per hari.

**Bagian-bagian:**
| Bagian | Keterangan |
|--------|-----------|
| **Selector Hari** | Tombol tab untuk memilih hari (Senin–Sabtu) |
| **Timeline** | Jadwal kunjungan dalam format timeline per hari |
| **Cari Rute** | Form pencarian lokasi terdekat berdasarkan keyword |
| **Tabel Rekap** | Tabel HTML lengkap semua jadwal mingguan |
| **Armada** | Kartu informasi 7 unit armada yang beroperasi |

---

### 4. `layanan.html` — Layanan
**Fungsi:** Menjelaskan semua layanan yang tersedia.

**Bagian-bagian:**
| Bagian | Keterangan |
|--------|-----------|
| **Layanan Utama** | 4 kartu layanan (peminjaman, edukasi, donasi, workshop) |
| **Proses Peminjaman** | 4 langkah peminjaman buku dengan visualisasi steps |
| **Donasi Buku** | Info program donasi + statistik animasi |
| **Testimoni** | 3 kartu testimoni dari anggota/mitra |
| **FAQ Accordion** | 6 pertanyaan umum dengan expand/collapse interaktif |

---

### 5. `kontak.html` — Kontak & Daftar
**Fungsi:** Formulir kontak dan pendaftaran anggota perpustakaan.

**Bagian-bagian:**
| Bagian | Keterangan |
|--------|-----------|
| **Info Kontak** | Telepon, email, WhatsApp, alamat |
| **Jam Operasional** | Tabel jam buka kantor |
| **Peta Lokasi** | Placeholder peta dengan link Google Maps |
| **Tab Form** | Dua tab: "Hubungi Kami" dan "Daftar Anggota" |
| **Validasi Form** | Validasi JavaScript real-time sebelum submit |

---

## ⚡ Fitur JavaScript

### JS Block 1 — Katalog Buku Interaktif (`koleksi.html`)
```javascript
// Di koleksi.html: Filter, pencarian, dan modal
var BUKU_DATA = [...]; // 20 buku dalam array

// Fungsi utama:
renderGrid()       // Render ulang grid buku sesuai filter aktif
renderPagination() // Render tombol halaman
openBookModal(id)  // Buka modal detail buku berdasarkan ID
pinjamBuku()       // Ubah status buku menjadi "Dipinjam"
```
**Yang terjadi:** Saat pengguna mengetik di search bar, mencentang filter, atau mengubah sorting → `renderGrid()` dipanggil ulang dan tampilan diperbarui secara real-time tanpa reload halaman.

---

### JS Block 2 — Jadwal Interaktif (`jadwal.html`)
```javascript
// Di jadwal.html: Tab hari, timeline, dan cari rute
var JADWAL = {
  senin:   [...], // Array jadwal hari Senin
  selasa:  [...],
  // dst.
};

showDay('senin')   // Tampilkan timeline untuk hari yang dipilih
renderTable()      // Render tabel rekap semua jadwal (IIFE)
// Event: cariRuteBtn → filter SEMUA_JADWAL berdasarkan keyword lokasi
```
**Yang terjadi:** Saat halaman dibuka, hari aktif otomatis terdeteksi dari `new Date().getDay()`. Klik tab hari → timeline diperbarui. Klik "Cari Rute" → hasil filter muncul di bawah form.

---

### JS Block 3 — FAQ Accordion (`layanan.html`)
```javascript
// Di layanan.html: FAQ expand/collapse
function toggleFaq(btn) {
  var item   = btn.closest('.faq-item');
  var isOpen = item.classList.contains('open');
  // Tutup semua item lain terlebih dahulu
  // Buka/tutup item yang diklik
}
```
**Yang terjadi:** Klik pertanyaan → jawaban muncul dengan animasi CSS (`max-height` transition). Hanya satu jawaban yang bisa terbuka sekaligus.

---

### JS Block 4 — Validasi Form (`kontak.html`)
```javascript
// Di kontak.html: Validasi 2 formulir berbeda
formHubungi.addEventListener('submit', function(e) {
  e.preventDefault(); // Cegah submit default browser
  // Validasi: nama, email (regex), subject, pesan (min 10 char)
  // Jika valid → simulasi kirim (setTimeout 1.5s) → tampilkan sukses
});

formDaftar.addEventListener('submit', function(e) {
  e.preventDefault();
  // Validasi: nama, email, tglLahir, telepon (regex), jenis, alamat, checkbox
  // Jika valid → generate nomor anggota → tampilkan sukses
});
```

---

### `main.js` — Utilitas Global (dipakai semua halaman)
```javascript
// 1. Navbar Hamburger Menu
initNavbar()        // Toggle mobile menu, tandai halaman aktif

// 2. Scroll to Top Button
initScrollTop()     // Tampilkan/sembunyikan tombol ↑ saat scroll > 400px

// 3. Counter Animasi
initCounters()      // Animasi angka dari 0 → target saat elemen terlihat
// Gunakan: <div data-target="5000" data-suffix="+">

// 4. Utilitas
showToast(msg, type) // Tampilkan notifikasi kecil di layar
formatTanggal(date)  // Format tanggal ke Bahasa Indonesia
toggleModal(id, open)// Buka/tutup modal overlay
```

---

## 🧩 Elemen HTML yang Digunakan

Checklist elemen HTML sesuai ketentuan:

| Elemen | Lokasi | Keterangan |
|--------|--------|-----------|
| `<a>` (Hyperlink) | Semua halaman | Navigasi, link footer, link kontak |
| `<table>` | `jadwal.html`, `kontak.html` | Tabel jadwal mingguan & jam operasional |
| `<img>` | Semua halaman | Logo brand (emoji-based) dan placeholder gambar |
| `<video>` / `<iframe>` | `index.html` | Embed YouTube via `<iframe>` dengan `allowfullscreen` |
| `<form>` | `kontak.html`, `jadwal.html` | Form hubungi kami, daftar anggota, cari rute |
| `<input>` | `koleksi.html`, `kontak.html` | Text, email, date, tel, checkbox, search |
| `<select>` | `koleksi.html`, `kontak.html` | Dropdown filter dan pilihan kategori |
| `<textarea>` | `kontak.html` | Area pesan dan alamat |
| `<button>` | Semua halaman | CTA, filter, submit form, pagination |

---

## 🚀 Cara Menjalankan

### Metode 1: Buka Langsung (Paling Mudah)
1. Buka folder `perpustakaan-keliling/`
2. Klik dua kali file `index.html`
3. Website terbuka di browser default Anda

### Metode 2: Live Server (Rekomendasi untuk Development)
Jika menggunakan VS Code:
1. Install extension **Live Server** (Ritwick Dey)
2. Klik kanan `index.html` → **Open with Live Server**
3. Browser otomatis terbuka di `http://127.0.0.1:5500`

### Metode 3: Python HTTP Server
```bash
# Masuk ke folder proyek
cd perpustakaan-keliling

# Python 3
python -m http.server 8080

# Buka browser: http://localhost:8080
```

> **Catatan:** Website ini tidak memerlukan server khusus, database, atau instalasi apapun. Semua berjalan di sisi client (browser).

---

## 📖 Penjelasan Kode untuk Presentasi

### Alur Navigasi
```
index.html ──┬──→ koleksi.html (Katalog Buku)
             ├──→ jadwal.html  (Jadwal & Rute)
             ├──→ layanan.html (Layanan)
             └──→ kontak.html  (Kontak & Daftar)
```

### Sistem CSS (Design System)
File `css/style.css` membangun **design system** menggunakan CSS Custom Properties (variabel):
```css
:root {
  --primary:    #2563EB;   /* Biru utama */
  --secondary:  #F59E0B;   /* Kuning aksen */
  --accent:     #10B981;   /* Hijau sukses */
  --dark:       #0F172A;   /* Warna gelap/teks */
  --radius:     12px;      /* Border-radius kartu */
  --shadow:     0 4px ...  /* Bayangan standar */
}
```
**Keuntungan:** Mengubah satu variabel akan mempengaruhi seluruh website secara konsisten.

### Komponen Reusable
Karena ini website statis (tanpa framework), komponen seperti navbar dan footer **ditulis ulang** di setiap halaman. Ini adalah trade-off yang wajar untuk proyek statis tanpa build tool.

### Responsivitas
Breakpoint yang digunakan:
```css
@media (max-width: 1024px) { /* Tablet landscape */ }
@media (max-width: 768px)  { /* Tablet portrait & mobile */ }
@media (max-width: 480px)  { /* Mobile kecil */ }
```

---

## ✅ Checklist Ketentuan Final Project

| Ketentuan | Status | Keterangan |
|-----------|--------|-----------|
| Minimal 5 halaman HTML | ✅ | index, koleksi, jadwal, layanan, kontak |
| Minimal 3 blok JavaScript | ✅ | Katalog, Jadwal, FAQ Accordion, Validasi Form, main.js |
| Mengandung hyperlink | ✅ | Navigasi, footer, link kontak |
| Mengandung table | ✅ | Tabel jadwal rute & jam operasional |
| Mengandung image | ✅ | Logo brand, emoji visual |
| Mengandung video | ✅ | Iframe YouTube di beranda |
| Mengandung form | ✅ | Form kontak, daftar anggota, cari rute |
| Layout modern CSS | ✅ | Design system, glassmorphism, gradient, animasi |
| Responsif | ✅ | Media query untuk mobile, tablet, desktop |
| Statis (HTML+CSS+JS) | ✅ | Tidak ada backend/database |
| Semua tombol berfungsi | ✅ | Filter, pinjam, FAQ, form validasi |

---

## 👥 Tim Pengembang

| Nama | NIM | Peran |
|------|-----|-------|
| [Nama Anda] | [NIM] | Front-end Developer |
| [Nama Anggota] | [NIM] | Designer & Content |
| [Nama Anggota] | [NIM] | JavaScript & QA |

---

## 📝 Catatan Teknis

- **Browser yang didukung:** Chrome 90+, Firefox 88+, Edge 90+, Safari 14+
- **Tidak memerlukan:** Node.js, npm, PHP, database, atau koneksi internet (kecuali Google Fonts & iframe YouTube)
- **Ukuran total proyek:** ~100KB (sangat ringan)
- **Aksesibilitas:** Menggunakan ARIA labels, role attributes, dan keyboard navigation

---

> Dibuat dengan ❤️ untuk tugas Final Project Web — Perpustakaan Keliling 2025
