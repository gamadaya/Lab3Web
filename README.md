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

Simpan semua file tangkapan layar (screenshot) di dalam folder `screenshots/` dengan format nama angka (`ss1.png` sampai `ss8.png`) sesuai tabel berikut:

| No File | Aplikasi / Lokasi | Yang Harus Di-Screenshot |
|---|---|---|
| **`ss1.png`** | Browser | Tampilan tabel data mahasiswa dan nilai dengan `<thead>`, `<tbody>`, `<tfoot>`, serta penggunaan `colspan`. |
| **`ss2.png`** | Browser | Tampilan Form Registrasi Mahasiswa (Input Teks, Email, Password, Date). |
| **`ss3.png`** | Browser | Tampilan elemen Pilihan (Radio Button Jenis Kelamin & Checkbox Keahlian). |
| **`ss4.png`** | Browser | Tampilan elemen Dropdown (`<select>`) dan Input Teks Area (`<textarea>`). |
| **`ss5.png`** | Browser | Tampilan pesan peringatan/pop-up validasi HTML5 saat form dikirim kosong (`required`). |
| **`ss6.png`** | Browser | Tampilan layout struktur halaman web berbasis Semantic HTML. |
| **`ss7.png`** | Browser | Tampilan pemutar Multimedia (Elemen `<audio>` dan `<video>`). |
| **`ss8.png`** | Browser | Tampilan Proyek Mini (`biodata.html`) yang menggabungkan Semantic HTML, Tabel, Form, dan Multimedia. |

---

## Struktur Folder

```text
Lab2Web/
├── index.html
├── biodata.html
├── media/
│   ├── audio.mp3
│   └── video.mp4
├── screenshots/
│   ├── ss1.png
│   ├── ss2.png
│   ├── ss3.png
│   ├── ss4.png
│   ├── ss5.png
│   ├── ss6.png
│   ├── ss7.png
│   └── ss8.png
└── README.md
```

---

## Pendahuluan

**HTML Lanjutan** memperdalam kemampuan pengembangan web dengan menghadirkan interaktivitas pengumpulan data pengguna, penyajikan struktur data kompleks, serta integrasi media. Praktikum ini berfokus pada lima pilar utama:

1. **Tabel HTML:** Menyajikan data terstruktur dalam bentuk baris dan kolom beserta hierarki header, body, dan footer.
2. **Form & Input:** Elemen interaktif untuk menerima data pengguna mulai dari teks, kata sandi, tanggal, hingga pilihan.
3. **Validasi Form Dasar:** Memastikan integritas data yang dimasukkan sebelum dikirimkan menggunakan atribut bawaan HTML5.
4. **Semantic HTML:** Menggunakan tag bermakna khusus untuk membangun tata letak web yang akurat bagi browser, *screen reader*, dan SEO.
5. **Multimedia:** Mengintegrasikan pemutar audio dan video native tanpa perlu dependensi library eksternal.

---

## Implementasi Kode & Dokumentasi

### 1. Tabel HTML & Struktur Kompleks

**Penjelasan Konseptual:**
Tabel digunakan untuk mengelompokkan data berulang. Struktur `<thead>`, `<tbody>`, dan `<tfoot>` memisahkan bagian-bagian tabel secara semantik. Atribut `colspan` digunakan untuk menggabungkan dua atau lebih kolom dalam satu baris.

**Input Code:**

```html
<!-- 1. Tabel Data & Nilai Mahasiswa -->
<table border="1">
    <caption>Data & Nilai Praktikum Mahasiswa</caption>
    <thead>
        <tr>
            <th>NIM</th>
            <th>Nama</th>
            <th>Nilai</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>312510051</td>
            <td>Gama Daya Laksana</td>
            <td>95</td>
        </tr>
        <tr>
            <td>31241001</td>
            <td>Andi</td>
            <td>85</td>
        </tr>
        <tr>
            <td>31241002</td>
            <td>Budi</td>
            <td>90</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="2">Rata-rata Nilai</td>
            <td>90.0</td>
        </tr>
    </tfoot>
</table>
```

**Capture Output:**

> ![Output Tabel Data Mahasiswa](./screenshots/ss1.png)

---

### 2. Form Registrasi Mahasiswa

**Penjelasan Konseptual:**
Tag `<form>` berfungsi sebagai wadah untuk menampung berbagai tipe kontrol input. Atribut `type` menentukan perilaku dan tampilan dari tag `<input>` (misalnya `text`, `email`, `password`, dan `date`).

**Input Code:**

```html
<!-- 2. Form Registrasi Dasar -->
<h1>Form Registrasi Mahasiswa</h1>
<form>
    <label for="nama">Nama Lengkap:</label><br>
    <input type="text" id="nama" name="nama"><br><br>

    <label for="email">Email:</label><br>
    <input type="email" id="email" name="email"><br><br>

    <label for="password">Password:</label><br>
    <input type="password" id="password" name="password"><br><br>

    <label for="tanggal">Tanggal Lahir:</label><br>
    <input type="date" id="tanggal" name="tanggal"><br><br>

    <button type="submit">Daftar</button>
    <button type="reset">Reset</button>
</form>
```

**Capture Output:**

> ![Output Form Registrasi](./screenshots/ss2.png)

---

### 3. Pilihan Pilihan: Radio Button & Checkbox

**Penjelasan Konseptual:**
Input tipe `radio` digunakan ketika pengguna hanya boleh memilih **satu** opsi dari kelompok pilihan yang memiliki nama atribut (`name`) yang sama. Sedangkan `checkbox` mengizinkan pengguna memilih **satu atau lebih** opsi secara independen.

**Input Code:**

```html
<!-- 3. Radio Button dan Checkbox -->
<h2>Jenis Kelamin</h2>
<input type="radio" id="laki" name="jk" value="L">
<label for="laki">Laki-laki</label>
<input type="radio" id="perempuan" name="jk" value="P">
<label for="perempuan">Perempuan</label>

<h2>Keahlian</h2>
<input type="checkbox" id="html" name="skill" value="HTML">
<label for="html">HTML</label>
<input type="checkbox" id="css" name="skill" value="CSS">
<label for="css">CSS</label>
<input type="checkbox" id="js" name="skill" value="JavaScript">
<label for="js">JavaScript</label>
```

**Capture Output:**

> ![Output Radio dan Checkbox](./screenshots/ss3.png)

---

### 4. Dropdown List (`<select>`) & Textarea

**Penjelasan Konseptual:**
Tag `<select>` membuat menu *dropdown* berisi opsi-opsi yang didefinisikan oleh tag `<option>`. Tag `<textarea>` digunakan untuk menginputkan teks multibaris yang panjang, seperti masukan alamat atau uraian deskripsi.

**Input Code:**

```html
<!-- 4. Select dan Textarea -->
<label for="prodi">Program Studi:</label>
<select id="prodi" name="prodi">
    <option value="">-- Pilih Prodi --</option>
    <option value="ti">Teknik Informatika</option>
    <option value="si">Sistem Informasi</option>
</select>
<br><br>

<label for="alamat">Alamat Lengkap:</label><br>
<textarea id="alamat" name="alamat" rows="5" cols="40"></textarea>
```

**Capture Output:**

> ![Output Select dan Textarea](./screenshots/ss4.png)

---

### 5. Validasi Form Dasar HTML5

**Penjelasan Konseptual:**
Atribut validasi seperti `required` memaksa pengguna untuk mengisi field sebelum dikirim. Atribut `minlength`, `maxlength`, `min`, dan `max` membatasi rentang nilai atau panjang karakter yang dimasukkan.

**Input Code:**

```html
<!-- 5. Form dengan Validasi HTML5 -->
<form>
    <label for="nama_val">Nama:</label>
    <input type="text" id="nama_val" name="nama" required minlength="3"><br><br>

    <label for="email_val">Email:</label>
    <input type="email" id="email_val" name="email" required><br><br>

    <label for="umur_val">Umur:</label>
    <input type="number" id="umur_val" name="umur" min="17" max="60" required><br><br>

    <button type="submit">Kirim Data</button>
</form>
```

**Capture Output:**

> ![Output Validasi Form](./screenshots/ss5.png)

---

### 6. Struktur Layout Semantic HTML

**Penjelasan Konseptual:**
Penggunaan elemen semantik seperti `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, dan `<footer>` memperjelas peranan visual maupun fungsional dari blok dokumen web.

**Input Code:**

```html
<!-- 6. Layout Halaman Semantic -->
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Portal Mahasiswa</title>
</head>
<body>
    <header>
        <h1>Portal Mahasiswa Universitas Pelita Bangsa</h1>
    </header>

    <nav>
        <a href="#">Beranda</a> |
        <a href="#">Profil</a> |
        <a href="#">Kontak</a>
    </nav>

    <main>
        <section>
            <h2>Informasi Akademik</h2>
            <article>
                <h3>Praktikum HTML Lanjutan</h3>
                <p>Mahasiswa mempelajari tabel, form, semantic HTML, multimedia, dan validasi.</p>
            </article>
        </section>

        <aside>
            <h4>Informasi Tambahan</h4>
            <p>Jadwal ujian akan diumumkan minggu depan.</p>
        </aside>
    </main>

    <footer>
        <p>&copy; 2026 Teknik Informatika - Universitas Pelita Bangsa</p>
    </footer>
</body>
</html>
```

**Capture Output:**

> ![Output Semantic HTML](./screenshots/ss6.png)

---

### 7. Integrasi Multimedia (`<audio>` & `<video>`)

**Penjelasan Konseptual:**
Elemen `<audio>` dan `<video>` menyematkan berkas media secara langsung. Atribut `controls` menambahkan bilah navigasi pemutar seperti tombol *play*, *pause*, dan *volume*.

**Input Code:**

```html
<!-- 7. Elemen Multimedia -->
<h2>Pemutar Audio</h2>
<audio controls>
    <source src="media/audio.mp3" type="audio/mpeg">
    Browser Anda tidak mendukung pemutar audio.
</audio>

<h2>Pemutar Video</h2>
<video controls width="480">
    <source src="media/video.mp4" type="video/mp4">
    Browser Anda tidak mendukung pemutar video.
</video>
```

**Capture Output:**

> ![Output Multimedia Audio & Video](./screenshots/ss7.png)

---

### 8. Proyek Mini: Halaman Biodata Mahasiswa (`biodata.html`)

**Penjelasan Konseptual:**
Penerapan menyeluruh dari konsep *Semantic Structure*, *Tabel Data*, *Form Input Validasi*, dan *Multimedia* dalam satu kesatuan file halaman web (`biodata.html`).

**Input Code (`biodata.html`):**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Biodata Mahasiswa - Proyek Mini</title>
</head>
<body>
    <header>
        <h1>Biodata Mahasiswa</h1>
    </header>

    <nav>
        <a href="index.html">Beranda</a> |
        <a href="#biodata">Biodata</a> |
        <a href="#form">Form Mini</a> |
        <a href="#media">Media</a>
    </nav>

    <main>
        <section id="biodata">
            <h2>Data Pribadi</h2>
            <table border="1">
                <tr>
                    <th>Atribut</th>
                    <th>Keterangan</th>
                </tr>
                <tr>
                    <td>NIM</td>
                    <td>312510051</td>
                </tr>
                <tr>
                    <td>Nama</td>
                    <td>Gama Daya Laksana</td>
                </tr>
                <tr>
                    <td>Program Studi</td>
                    <td>Teknik Informatika</td>
                </tr>
            </table>
        </section>

        <section id="form">
            <h2>Form Update Biodata</h2>
            <form>
                <label for="nama_mhs">Nama Lengkap:</label><br>
                <input type="text" id="nama_mhs" name="nama" required><br><br>

                <label for="email_mhs">Email:</label><br>
                <input type="email" id="email_mhs" name="email" required><br><br>

                <label for="prodi_mhs">Program Studi:</label><br>
                <select id="prodi_mhs" name="prodi" required>
                    <option value="">-- Pilih Prodi --</option>
                    <option value="ti">Teknik Informatika</option>
                    <option value="si">Sistem Informasi</option>
                </select><br><br>

                <label for="alamat_mhs">Alamat:</label><br>
                <textarea id="alamat_mhs" name="alamat" required></textarea><br><br>

                <button type="submit">Simpan</button>
                <button type="reset">Reset</button>
            </form>
        </section>

        <section id="media">
            <h2>Sapaan Video</h2>
            <video controls width="360">
                <source src="media/video.mp4" type="video/mp4">
                Browser tidak mendukung video.
            </video>
        </section>
    </main>

    <footer>
        <p>&copy; 2026 Teknik Informatika - Universitas Pelita Bangsa</p>
    </footer>
</body>
</html>
```

**Capture Output:**

> ![Output Proyek Mini Biodata](./screenshots/ss8.png)

---

## Jawaban Pertanyaan Evaluasi

**1. Apa fungsi `<table>`, `<tr>`, `<th>`, dan `<td>`?**  
- `<table>`: Berfungsi sebagai kontainer utama untuk mendefinisikan struktur tabel.
- `<tr>` (*Table Row*): Berfungsi untuk membuat baris di dalam tabel.
- `<th>` (*Table Header*): Berfungsi mendefinisikan sel sebagai kepala kolom (secara default teks dicetak tebal dan rata tengah).
- `<td>` (*Table Data*): Berfungsi mendefinisikan sel data standar di dalam baris.

**2. Apa perbedaan `<th>` dan `<td>`?**  
`<th>` digunakan khusus untuk sel judul/header kolom yang membuat teks berformat tebal (*bold*) dan terpusat (*center*), sedangkan `<td>` digunakan untuk menampung nilai data biasa dengan tampilan teks normal rata kiri.

**3. Apa fungsi `colspan` pada tabel?**  
`colspan` (*column span*) berfungsi untuk menggabungkan dua atau lebih kolom horizontal menjadi satu sel besar.

**4. Apa fungsi `<form>` dalam HTML?**  
`<form>` berfungsi sebagai wadah untuk menampung elemen-elemen input interaktif guna mengumpulkan data dari pengguna dan mengirimkannya ke server.

**5. Apa perbedaan radio button dan checkbox?**  
- **Radio Button:** Pengguna hanya dapat memilih **satu** opsi dari grup opsi yang tersedia.
- **Checkbox:** Pengguna dapat memilih **beberapa** opsi sekaligus atau tidak memilih sama sekali dari daftar opsi yang ada.

**6. Mengapa `<label>` sebaiknya terhubung dengan `id` input melalui atribut `for`?**  
Agar meningkatkan aksesibilitas dan kemudahan navigasi pengguna. Ketika pengguna mengklik teks `<label>`, kursor/fokus browser akan otomatis mengaktifkan elemen `<input>` yang terhubung.

**7. Apa perbedaan `<textarea>` dengan `input type="text"`?**  
- `input type="text"` hanya menyediakan satu baris area pengisian teks pendek.
- `<textarea>` menyediakan area pengisian teks multibaris yang lebarnya dan tingginya dapat disesuaikan untuk memasukkan paragraf atau teks yang panjang.

**8. Apa fungsi semantic HTML seperti `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, dan `<footer>`?**  
Fungsinya adalah untuk memberikan makna dan hierarki terstruktur pada halaman web, sehingga mesin pencari (SEO), browser, dan *screen reader* dapat memahami fungsi setiap blok halaman secara jelas.

**9. Apa fungsi `required`, `min`, `max`, dan `minlength`?**  
- `required`: Memastikan input tidak boleh dikosongkan saat dikirim.
- `min`: Menentukan nilai minimum numerik/tanggal yang diizinkan.
- `max`: Menentukan nilai maksimum numerik/tanggal yang diizinkan.
- `minlength`: Menentukan jumlah panjang karakter minimum yang harus diketikkan.

**10. Apa perbedaan elemen `<audio>` dan `<video>`?**  
- `<audio>` digunakan untuk memutar berkas suara saja (seperti MP3 atau WAV) tanpa tampilan visual selain kontrol pemutar audio.
- `<video>` digunakan untuk memutar gambar bergerak berserta suara (seperti MP4 atau WebM) dan memerlukan area visual layar untuk merender datanya.

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
