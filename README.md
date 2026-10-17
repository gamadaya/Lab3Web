# Dokumentasi Praktikum Web: HTML Lanjutan

**Identitas Mahasiswa:**
- **Nama:** Gama Daya Laksana
- **NIM:** 312510051
- **Kelas:** I253A
- **Program Studi:** Teknik Informatika
- **Dosen Pengampu:** Agung Nugroho, S.Kom., M.Kom.
- **Kampus:** Universitas Pelita Bangsa

---
## Panduan Screenshot Tugas

Semua file tangkapan layar (*screenshot*) tersimpan rapi di dalam direktori `screenshots/` dengan format penamaan angka (`1.png` sampai `6.png`) sesuai urutan pengerjaan pada modul:

| No File | Aplikasi / Lokasi | Yang Harus Di-Screenshot / Ditampilkan |
|:---|:---|:---|
| **`1.png`** | Browser | **Langkah 1 (Gambar 2 Modul):** Tampilan awal dokumen HTML murni tanpa gaya CSS. Seluruh elemen tampil polos (*default browser style*). |
| **`2.png`** | Browser | **Langkah 2 (Gambar 3 Modul):** Penambahan Internal CSS pada tag `<head>` (font *Open Sans*, border bawah pada `<header>`, dan perataan judul `<h1>` ke tengah berwarna biru). |
| **`3.png`** | Browser | **Langkah 3 (Gambar 4 Modul):** Penambahan Inline CSS pada tag `<p>` di dalam `#intro` (teks paragraf rata tengah dengan warna `#ccd8e4`). |
| **`4.png`** | Browser | **Langkah 4 (Gambar 5 Modul):** Pembuatan dan penyisipan file eksternal `style_eksternal.css` untuk mempercantik bilah navigasi `<nav>` berwarna hijau `#20A759` beserta efek tautannya. |
| **`5.png`** | Browser | **Langkah 5 (Gambar 6 Modul):** Penambahan ID Selector (`#intro`) dan Class Selector (`.button`, `.btn-primary`) pada `style_eksternal.css` sehingga membentuk kotak intro biru bergaris hijau dan tombol aksi merah. |
| **`6.png`** | Browser (`eksperimen.html`) | **Tugas & Evaluasi Modul:** Halaman interaktif implementasi eksperimen CSS modern serta pengujian nyata atas pertanyaan spesifitas dan prioritas CSS. |

---

## Struktur Direktori Proyek

```text
Lab3Web/
├── screenshots/
│   ├── 1.png               # Tampilan dokumen HTML dasar (Gambar 2)
│   ├── 2.png               # Penerapan Internal CSS (Gambar 3)
│   ├── 3.png               # Penerapan Inline CSS (Gambar 4)
│   ├── 4.png               # Penerapan External CSS navigasi (Gambar 5)
│   ├── 5.png               # Penerapan ID & Class Selector (Gambar 6)
│   └── 6.png               # Eksperimen CSS & pembuktian jawaban soal
├── index.html              # Landing page utama repositori (CSS Dasar terintegrasi)
├── lab2_css_dasar.html     # File latihan utama sesuai instruksi modul
├── lab2_css_eksternal.html # File demonstrasi implementasi CSS Eksternal
├── style_eksternal.css     # File stylesheet terpisah (Eksternal CSS)
├── eksperimen.html         # Halaman pengujian & pembuktian tugas modul
└── README.md               # Laporan dokumentasi lengkap praktikum
```

---

## Langkah-langkah Praktikum

### 1. Membuat Dokumen HTML Dasar (`lab2_css_dasar.html`)
Langkah awal adalah membuat struktur dokumen HTML5 standar yang memuat elemen `<header>`, menu `<nav>`, dan kontainer `<div id="intro">` dengan tombol tautan:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Dasar</title>
</head>
<body>
    <header>
        <h1>CSS Internal dan <i>Inline CSS</i></h1>
    </header>
    <nav>
        <a href="lab2_css_dasar.html">CSS Dasar</a>
        <a href="lab2_css_eksternal.html">CSS Eksternal</a>
        <a href="lab1_tag_dasar.html">HTML Dasar</a>
    </nav>
    <!-- CSS ID Selector -->
    <div id="intro">
        <h1>Hello World</h1>
        <p>Kami sedang belajar HTML dan CSS dasar, pada mata kuliah 
        <b>Pemrograman Web</b> di <i>Universitas Pelita Bangsa</i>. Pelajaran pertama 
        yang kami dapat adalah membuat tampilan web sederhana dalam rangka mengenal 
        tag-tag dasar HTML dan CSS.</p>
        <!-- CSS Class Selector -->
        <a class="button btn-primary" href="#intro">Informasi selengkapnya.</a>
    </div>
</body>
</html>
```

**Screenshot Hasil Langkah 1 (HTML Murni):**  
![Langkah 1 - Dokumen HTML Murni](./screenshots/1.png)

---

### 2. Mendeklarasikan Internal CSS
Menambahkan aturan CSS di dalam tag `<style>` pada bagian `<head>` dokumen untuk mengatur tipografi body, border header, dan perataan judul:

```html
<style>
    body {
        font-family: 'Open Sans', sans-serif;
    }
    header {
        min-height: 80px;
        border-bottom: 1px solid #77CCEF;
    }
    h1 {
        font-size: 24px;
        color: #0F189F;
        text-align: center;
        padding: 20px 10px;
    }
    h1 i {
        color: #6d6a6b;
    }
</style>
```

**Screenshot Hasil Langkah 2 (Internal CSS):**  
![Langkah 2 - Penambahan CSS Internal](./screenshots/2.png)

---

### 3. Menambahkan Inline CSS
Menyisipkan atribut `style` langsung pada tag `<p>` di dalam elemen `<div id="intro">`:

```html
<p style="text-align: center; color: #ccd8e4;">
    Kami sedang belajar HTML dan CSS dasar, pada mata kuliah ...
</p>
```

**Screenshot Hasil Langkah 3 (Inline CSS):**  
![Langkah 3 - Penambahan Inline CSS](./screenshots/3.png)

---

### 4. Membuat dan Mengintegrasikan CSS Eksternal (`style_eksternal.css`)
Membuat file terpisah bernama `style_eksternal.css` untuk mendeklarasikan penataan bilah navigasi:

```css
nav {
    background: #20A759;
    color: #fff;
    padding: 10px;
}
nav a {
    color: #fff;
    text-decoration: none;
    padding: 10px 20px;
}
nav .active, 
nav a:hover {
    background: #0B6B3A;
}
```

Kemudian dihubungkan pada bagian `<head>` berkas HTML menggunakan tag `<link>`:
```html
<link rel="stylesheet" href="style_eksternal.css" type="text/css">
```

**Screenshot Hasil Langkah 4 (Eksternal CSS):**  
![Langkah 4 - Tampilan Eksternal CSS](./screenshots/4.png)

---

### 5. Menambahkan CSS Selector (ID dan Class Selector)
Melengkapi file `style_eksternal.css` dengan aturan ID Selector (`#intro`) dan Class Selector (`.button`, `.btn-primary`):

```css
/* ID Selector */
#intro {
    background: #418fb1;
    border: 1px solid #099249;
    min-height: 100px;
    padding: 10px;
}
#intro h1 {
    text-align: left;
    border: 0;
    color: #fff;
}

/* Class Selector */
.button {
    padding: 15px 20px;
    background: #bebcbd;
    color: #fff;
    display: inline-block;
    margin: 10px;
    text-decoration: none;
}
.btn-primary {
    background: #E42A42;
}
```

**Screenshot Hasil Langkah 5 (ID & Class Selector Lengkap):**  
![Langkah 5 - Tampilan Lengkap ID dan Class Selector](./screenshots/5.png)
---

## Checklist Sebelum Dikumpulkan

Berdasarkan checklist pada modul praktikum:
- [x] Tabel berhasil ditampilkan dan memiliki header yang sesuai.
- [x] Form memiliki label dan beberapa jenis input.
- [x] Radio button dan checkbox sudah digunakan.
- [x] Select dan textarea sudah digunakan.
- [x] Validasi required dan validasi dasar lainnya sudah dicoba.
- [x] Semantic HTML sudah digunakan.
- [x] Audio dan/atau video berhasil ditampilkan.
- [x] Proyek mini biodata menggabungkan materi utama.
- [x] Screenshot dan README.md sudah tersedia.
- [x] Repository sudah di-commit dan URL siap dikirim.
