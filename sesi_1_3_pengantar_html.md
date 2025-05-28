### Materi Pembelajaran Sesi 1-3: Pengantar HTML (±9 JP)

Berikut adalah contoh program untuk setiap poin materi yang Anda sebutkan:

---

#### 1. Struktur dasar dokumen HTML (`<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`)

Ini adalah fondasi dari setiap halaman web HTML.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Struktur Dasar HTML</title>
</head>
<body>
    <h1>Selamat Datang di Halaman Web Saya</h1>
    <p>Ini adalah contoh sederhana dari struktur dasar dokumen HTML.</p>
</body>
</html>
```

**Penjelasan:**
* `<!DOCTYPE html>`: Deklarasi tipe dokumen, memberitahu browser bahwa ini adalah dokumen HTML5.
* `<html lang="en">`: Elemen root dari semua halaman HTML. Atribut `lang="en"` menunjukkan bahasa utama konten adalah Inggris.
* `<head>`: Berisi metadata tentang halaman web, seperti judul halaman yang muncul di tab browser (`<title>`), set karakter (`<meta charset="UTF-8">`), dan pengaturan tampilan responsif (`<meta name="viewport">`). Konten di dalam `<head>` tidak terlihat langsung di halaman web.
* `<body>`: Berisi semua konten yang terlihat oleh pengguna, seperti teks, gambar, tautan, dll.

---

#### 2. Elemen-elemen HTML dasar (heading, paragraph, link, image, list, table)

Ini adalah elemen-elemen paling umum yang akan Anda gunakan untuk menampilkan konten.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Elemen-elemen Dasar HTML</title>
</head>
<body>
    <h1>Ini Adalah Heading Level 1</h1>
    <h2>Ini Adalah Heading Level 2</h2>
    <h3>Ini Adalah Heading Level 3</h3>

    <p>Ini adalah sebuah paragraf. Anda bisa menuliskan banyak teks di sini untuk menjelaskan sesuatu.</p>
    <p>Paragraf lainnya, menunjukkan bagaimana teks dipecah menjadi blok-blok terpisah.</p>

    <p>Kunjungi <a href="https://www.google.com" target="_blank">Google</a> untuk mencari informasi lebih lanjut.</p>
    <p>Ini adalah <a href="halaman-lain.html">tautan internal</a> ke halaman lain di situs ini (asumsikan ada halaman bernama halaman-lain.html).</p>

    <img src="https://via.placeholder.com/150" alt="Placeholder Gambar" width="150" height="150">
    <p>Gambar di atas adalah placeholder berukuran 150x150 piksel.</p>

    <h2>Daftar Belanja</h2>
    <ul>
        <li>Apel</li>
        <li>Roti</li>
        <li>Susu</li>
    </ul>

    <h2>Langkah-langkah Memasak Nasi</h2>
    <ol>
        <li>Cuci beras hingga bersih.</li>
        <li>Tambahkan air dengan perbandingan 1:2.</li>
        <li>Masak hingga matang.</li>
        <li>Diamkan sebentar sebelum disajikan.</li>
    </ol>

    <h2>Data Siswa</h2>
    <table border="1">
        <thead>
            <tr>
                <th>No.</th>
                <th>Nama</th>
                <th>Kelas</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>1</td>
                <td>Andi</td>
                <td>XII IPA 1</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Budi</td>
                <td>XII IPS 2</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Siti</td>
                <td>XII Bahasa 3</td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

**Penjelasan:**
* `<h1>` hingga `<h6>`: Digunakan untuk judul atau heading. `<h1>` adalah yang paling penting, `<h6>` paling tidak penting.
* `<p>`: Digunakan untuk membuat paragraf teks.
* `<a href="...">`: Digunakan untuk membuat tautan (hyperlink). Atribut `href` menentukan URL tujuan. `target="_blank"` membuka tautan di tab baru.
* `<img src="..." alt="...">`: Digunakan untuk menyisipkan gambar. Atribut `src` menentukan lokasi gambar, dan `alt` menyediakan teks alternatif jika gambar tidak bisa dimuat. `width` dan `height` untuk ukuran gambar.
* `<ul>` (unordered list): Digunakan untuk membuat daftar tidak berurutan (bullet points). Setiap item daftar diwakili oleh `<li>`.
* `<ol>` (ordered list): Digunakan untuk membuat daftar berurutan (bernomor). Setiap item daftar juga diwakili oleh `<li>`.
* `<table>`: Digunakan untuk membuat tabel.
    * `<thead>`: Bagian kepala tabel.
    * `<tbody>`: Bagian isi tabel.
    * `<tr>`: Mendefinisikan baris tabel.
    * `<th>`: Mendefinisikan sel header tabel.
    * `<td>`: Mendefinisikan sel data tabel.

---

#### 3. HTML semantik (`<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<footer>`)

Elemen semantik memberikan makna struktural pada konten, membuatnya lebih mudah dipahami oleh browser dan screen reader, serta lebih baik untuk SEO.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HTML Semantik</title>
</head>
<body>
    <header>
        <h1>Website Portofolio Saya</h1>
        <nav>
            <ul>
                <li><a href="#home">Beranda</a></li>
                <li><a href="#about">Tentang Saya</a></li>
                <li><a href="#portfolio">Portofolio</a></li>
                <li><a href="#contact">Kontak</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home">
            <h2>Selamat Datang</h2>
            <p>Ini adalah bagian pengantar dari website saya.</p>
        </section>

        <article id="about">
            <h2>Tentang Saya</h2>
            <p>Saya adalah seorang pengembang web yang bersemangat dalam membuat aplikasi yang inovatif.</p>
            <p>Dengan pengalaman lebih dari 5 tahun, saya telah mengerjakan berbagai proyek, mulai dari situs web pribadi hingga aplikasi enterprise.</p>
        </article>

        <section id="portfolio">
            <h2>Proyek-proyek Saya</h2>
            <article>
                <h3>Proyek 1: Aplikasi E-commerce</h3>
                <p>Deskripsi singkat tentang aplikasi e-commerce yang saya kembangkan.</p>
                <a href="#">Lihat Proyek</a>
            </article>
            <article>
                <h3>Proyek 2: Website Blog Pribadi</h3>
                <p>Deskripsi singkat tentang website blog pribadi yang saya bangun.</p>
                <a href="#">Lihat Proyek</a>
            </article>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 Nama Anda. Hak Cipta Dilindungi.</p>
        <p>Ikuti saya di: <a href="#">LinkedIn</a> | <a href="#">GitHub</a></p>
    </footer>
</body>
</html>
```

**Penjelasan:**
* `<header>`: Mewakili konten pengantar atau navigasi, seringkali berisi judul situs, logo, dan navigasi utama.
* `<nav>`: Berisi tautan navigasi utama ke bagian lain dari situs atau halaman lain.
* `<main>`: Mewakili konten utama dari dokumen. Hanya boleh ada satu elemen `<main>` per halaman, dan konten di dalamnya harus unik untuk dokumen tersebut.
* `<article>`: Mewakili konten yang berdiri sendiri dan dapat didistribusikan secara independen (misalnya, entri blog, artikel berita, komentar).
* `<section>`: Mewakili bagian generik dari dokumen, seringkali dengan heading. Ini mengelompokkan konten yang terkait secara tematik.
* `<footer>`: Mewakili bagian bawah dari dokumen atau bagian terdekat, seringkali berisi informasi hak cipta, tautan kontak, dan informasi terkait.

---

#### 4. Formulir HTML (input types, attributes)

Formulir digunakan untuk mengumpulkan input dari pengguna.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulir HTML</title>
    <style>
        form div {
            margin-bottom: 10px;
        }
        label {
            display: inline-block;
            width: 100px;
            margin-right: 10px;
        }
    </style>
</head>
<body>
    <h1>Contoh Formulir Pendaftaran</h1>
    <form action="/submit-form" method="post">
        <div>
            <label for="nama">Nama Lengkap:</label>
            <input type="text" id="nama" name="nama_lengkap" placeholder="Masukkan nama Anda" required>
        </div>

        <div>
            <label for="email">Email:</label>
            <input type="email" id="email" name="email_pengguna" placeholder="contoh@domain.com" required>
        </div>

        <div>
            <label for="password">Kata Sandi:</label>
            <input type="password" id="password" name="kata_sandi" minlength="8" required>
        </div>

        <div>
            <label for="usia">Usia:</label>
            <input type="number" id="usia" name="umur" min="1" max="100">
        </div>

        <div>
            <label for="tanggal_lahir">Tanggal Lahir:</label>
            <input type="date" id="tanggal_lahir" name="tgl_lahir">
        </div>

        <div>
            <label for="gender">Jenis Kelamin:</label>
            <input type="radio" id="pria" name="gender" value="pria">
            <label for="pria">Pria</label>
            <input type="radio" id="wanita" name="gender" value="wanita">
            <label for="wanita">Wanita</label>
        </div>

        <div>
            <label>Minat:</label>
            <input type="checkbox" id="membaca" name="minat[]" value="membaca">
            <label for="membaca">Membaca</label>
            <input type="checkbox" id="olahraga" name="minat[]" value="olahraga">
            <label for="olahraga">Olahraga</label>
            <input type="checkbox" id="musik" name="minat[]" value="musik">
            <label for="musik">Musik</label>
        </div>

        <div>
            <label for="negara">Negara:</label>
            <select id="negara" name="asal_negara">
                <option value="">Pilih Negara</option>
                <option value="id">Indonesia</option>
                <option value="us">Amerika Serikat</option>
                <option value="uk">Inggris</option>
            </select>
        </div>

        <div>
            <label for="komentar">Komentar:</label>
            <textarea id="komentar" name="pesan_komentar" rows="5" cols="30" placeholder="Tulis komentar Anda di sini..."></textarea>
        </div>

        <div>
            <label for="file_upload">Unggah File:</label>
            <input type="file" id="file_upload" name="dokumen_penting">
        </div>

        <div>
            <input type="submit" value="Kirim Formulir">
            <input type="reset" value="Reset Formulir">
        </div>
    </form>
</body>
</html>
```

**Penjelasan:**
* `<form action="..." method="...">`: Elemen kontainer untuk semua input formulir.
    * `action`: Menentukan URL di mana data formulir akan dikirim.
    * `method`: Menentukan metode HTTP untuk mengirim data (misalnya, `get` atau `post`).
* `<label for="...">`: Digunakan untuk memberi label pada kontrol formulir. Atribut `for` harus cocok dengan `id` dari kontrol formulir terkait.
* `<input type="...">`: Elemen input yang paling serbaguna. `type` menentukan jenis input:
    * `text`: Input teks satu baris.
    * `email`: Input untuk alamat email (dengan validasi format dasar).
    * `password`: Input untuk kata sandi (karakter tersembunyi).
    * `number`: Input untuk angka.
    * `date`: Input untuk tanggal.
    * `radio`: Tombol radio (hanya satu pilihan dari grup yang dapat dipilih).
    * `checkbox`: Kotak centang (beberapa pilihan dapat dipilih).
    * `file`: Untuk mengunggah file.
    * `submit`: Tombol untuk mengirim formulir.
    * `reset`: Tombol untuk mereset formulir.
* `name`: Atribut penting yang digunakan untuk mengidentifikasi data input saat formulir dikirim.
* `id`: Atribut unik untuk elemen, sering digunakan dengan `<label>`.
* `placeholder`: Teks petunjuk yang muncul di dalam input sebelum pengguna mengetik.
* `required`: Atribut boolean yang membuat input wajib diisi.
* `minlength`, `min`, `max`: Atribut untuk validasi input (misalnya, panjang minimum, nilai minimum/maksimum).
* `<select>`: Digunakan untuk membuat daftar drop-down. Setiap opsi didefinisikan oleh `<option>`.
* `<textarea>`: Digunakan untuk input teks multi-baris. `rows` dan `cols` menentukan ukuran tampilan.

---

#### 5. Embed media (audio, video)

HTML5 mempermudah penyematan media audio dan video langsung ke dalam halaman web.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Embed Media HTML</title>
</head>
<body>
    <h1>Contoh Embed Audio</h1>
    <audio controls>
        <source src="musik-contoh.mp3" type="audio/mpeg">
        <source src="musik-contoh.ogg" type="audio/ogg">
        Maaf, browser Anda tidak mendukung pemutaran audio.
    </audio>
    <p>Ini adalah contoh pemutaran file audio. Pastikan Anda memiliki file `musik-contoh.mp3` atau `musik-contoh.ogg` di direktori yang sama.</p>
    <p>Atribut 'controls' menampilkan kontrol pemutaran standar (play/pause, volume, dll).</p>

    <hr>

    <h1>Contoh Embed Video</h1>
    <video controls width="640" height="360">
        <source src="video-contoh.mp4" type="video/mp4">
        <source src="video-contoh.ogg" type="video/ogg">
        <source src="video-contoh.webm" type="video/webm">
        Maaf, browser Anda tidak mendukung pemutaran video.
    </video>
    <p>Ini adalah contoh pemutaran file video. Pastikan Anda memiliki file `video-contoh.mp4` (atau format lain) di direktori yang sama.</p>
    <p>Atribut 'controls' menampilkan kontrol pemutaran video standar.</p>
    <p>Anda juga bisa menambahkan atribut 'autoplay' (untuk memutar otomatis, meskipun tidak disarankan karena mengganggu pengguna) dan 'loop' (untuk memutar berulang).</p>

    <h2>Embed Video dari YouTube (menggunakan iframe)</h2>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    <p>Ini adalah contoh menyematkan video YouTube menggunakan elemen <code>&lt;iframe&gt;</code>.</p>
</body>
</html>
```

**Penjelasan:**
* `<audio controls>`: Digunakan untuk menyematkan file audio.
    * `controls`: Menambahkan kontrol pemutaran standar (play/pause, volume, dll.).
    * `<source src="..." type="...">`: Digunakan untuk menyediakan berbagai format audio agar kompatibel dengan berbagai browser. Browser akan memilih format pertama yang didukung.
* `<video controls width="640" height="360">`: Digunakan untuk menyematkan file video.
    * `controls`: Menambahkan kontrol pemutaran standar (play/pause, volume, dll.).
    * `width` dan `height`: Menentukan dimensi tampilan video.
    * `<source src="..." type="...">`: Mirip dengan audio, untuk menyediakan berbagai format video.
* Teks di antara tag `<audio>` atau `<video>` akan ditampilkan jika browser tidak mendukung elemen tersebut.
* `<iframe>`: Digunakan untuk menyematkan konten dari sumber eksternal, seperti video dari YouTube atau peta Google. Ini bukan bagian dari elemen media HTML5 native, tetapi sering digunakan untuk media pihak ketiga.
    * `src`: URL konten yang akan disematkan.
    * `frameborder`: Menentukan apakah bingkai di sekitar iframe akan ditampilkan (0 berarti tidak ada bingkai).
    * `allowfullscreen`: Mengizinkan video untuk ditampilkan dalam mode layar penuh.

---

**Catatan Penting:**

* Untuk contoh `audio` dan `video`, Anda perlu menyediakan file audio (`.mp3`, `.ogg`) dan video (`.mp4`, `.ogg`, `.webm`) di direktori yang sama dengan file HTML Anda agar contoh ini berfungsi. Jika tidak ada, browser akan menampilkan pesan "Maaf, browser Anda tidak mendukung pemutaran audio/video."
* Untuk contoh YouTube, saya menggunakan URL video Rick Astley "Never Gonna Give You Up" sebagai placeholder. Ganti `dQw4w9WgXcQ` dengan ID video YouTube yang ingin Anda sematkan.
* `action="/submit-form"` pada formulir adalah placeholder. Untuk formulir agar benar-benar berfungsi, Anda memerlukan *backend* (server-side script) untuk menerima dan memproses data yang dikirimkan.

Semoga contoh-contoh program ini membantu dalam memahami materi Pengantar HTML!
