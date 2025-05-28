**Materi Pembelajaran Sesi 4-6: Pengantar CSS (±9 JP)**

Berikut adalah contoh program untuk setiap poin materi, disusun dalam format HTML dengan CSS inline atau internal untuk kemudahan demonstrasi. Untuk proyek yang lebih besar, disarankan untuk memisahkan CSS ke dalam file eksternal (`.css`).

---

### 1. Selector (element, class, ID)

**Penjelasan:**
* **Element Selector:** Memilih elemen HTML berdasarkan nama tag-nya (e.g., `p`, `h1`, `div`).
* **Class Selector:** Memilih elemen HTML berdasarkan atribut `class`-nya. Diawali dengan tanda titik (`.`) diikuti nama kelas (e.g., `.my-class`).
* **ID Selector:** Memilih elemen HTML berdasarkan atribut `id`-nya. Diawali dengan tanda pagar (`#`) diikuti nama ID (e.g., `#my-id`). ID harus unik dalam satu dokumen HTML.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contoh Selector CSS</title>
    <style>
        /* Element Selector */
        p {
            font-family: Arial, sans-serif;
            color: blue;
        }

        /* Class Selector */
        .highlight {
            background-color: yellow;
            font-weight: bold;
        }

        /* ID Selector */
        #main-heading {
            text-align: center;
            color: green;
        }
    </style>
</head>
<body>
    <h1 id="main-heading">Belajar Selector CSS</h1>
    <p>Ini adalah paragraf biasa.</p>
    <p class="highlight">Ini adalah paragraf yang di-highlight menggunakan class.</p>
    <div>
        <p>Paragraf di dalam div.</p>
        <span class="highlight">Span ini juga di-highlight.</span>
    </div>
</body>
</html>
```

---

### 2. Properti CSS Dasar (color, background, font, text)

**Penjelasan:**
* **`color`**: Mengatur warna teks.
* **`background`**: Mengatur latar belakang elemen (bisa warna, gambar, dll.).
* **`font`**: Mengatur properti font seperti `font-family`, `font-size`, `font-weight`, `font-style`.
* **`text`**: Mengatur properti teks seperti `text-align`, `text-decoration`, `text-transform`, `line-height`.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contoh Properti CSS Dasar</title>
    <style>
        body {
            background-color: #f0f0f0; /* Warna abu-abu muda */
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #333; /* Warna teks gelap */
        }

        .box {
            width: 80%;
            margin: 20px auto;
            padding: 20px;
            border: 1px solid #ccc;
            background-color: #fff;
            text-align: justify;
        }

        h2 {
            color: #8B0000; /* Warna merah marun */
            text-align: center;
            font-size: 2em; /* Ukuran font 2x dari ukuran default */
            text-decoration: underline; /* Garis bawah */
            text-transform: uppercase; /* Huruf besar semua */
        }

        p {
            line-height: 1.6; /* Jarak antar baris */
            letter-spacing: 0.5px; /* Jarak antar huruf */
        }

        .special-text {
            color: purple;
            font-weight: bold;
            font-style: italic;
        }
    </style>
</head>
<body>
    <div class="box">
        <h2>Judul Contoh Properti CSS</h2>
        <p>Ini adalah paragraf dengan <span class="special-text">teks khusus</span> yang menggunakan properti `color`, `font-weight`, dan `font-style`. Latar belakang body diatur dengan `background-color`, dan font secara keseluruhan menggunakan `font-family` tertentu.</p>
        <p>Properti `line-height` digunakan untuk mengatur jarak antar baris teks, membuat pembacaan menjadi lebih nyaman. Sedangkan `letter-spacing` mengatur jarak antar huruf.</p>
    </div>
</body>
</html>
```

---

### 3. Box Model (margin, padding, border, content)

**Penjelasan:**
Setiap elemen HTML dianggap sebagai sebuah "kotak" (box) yang terdiri dari empat bagian utama:
* **`content`**: Area di mana konten sebenarnya (teks, gambar, dll.) berada.
* **`padding`**: Ruang di antara konten dan batas (border) elemen. `padding` bersifat transparan.
* **`border`**: Garis yang mengelilingi `padding` dan `content`.
* **`margin`**: Ruang di luar batas (border) elemen, yang memisahkan elemen dari elemen lain. `margin` bersifat transparan.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contoh Box Model CSS</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: #f4f4f4;
        }

        .box-model-example {
            width: 200px; /* Lebar konten */
            height: 100px; /* Tinggi konten */
            background-color: lightblue; /* Warna background konten */
            text-align: center;
            line-height: 100px; /* Memposisikan teks di tengah vertikal */

            /* Padding */
            padding: 20px; /* Padding di semua sisi */

            /* Border */
            border: 5px solid darkblue; /* Ketebalan, gaya, dan warna border */

            /* Margin */
            margin: 30px; /* Margin di semua sisi */
            float: left; /* Untuk melihat efek margin antar box */
        }

        .another-box {
            width: 200px;
            height: 100px;
            background-color: lightcoral;
            text-align: center;
            line-height: 100px;
            padding: 15px;
            border: 3px dashed darkred;
            margin: 30px;
            float: left;
        }

        .clear-float {
            clear: both; /* Untuk membersihkan float */
        }
    </style>
</head>
<body>
    <div class="box-model-example">Konten Box 1</div>
    <div class="another-box">Konten Box 2</div>
    <div class="box-model-example">Konten Box 3</div>
    <div class="clear-float"></div>

    <p>Perhatikan bagaimana `padding` menambah ruang di dalam border, `border` menambah garis di sekeliling konten dan padding, dan `margin` menambah ruang di luar border, memisahkan antar elemen.</p>
</body>
</html>
```

---

### 4. Layouting (display: block/inline/inline-block, float, position, flexbox, grid)

**Penjelasan:**
Teknik-teknik untuk mengatur tata letak elemen di halaman web.

* **`display`**: Mengontrol bagaimana elemen ditampilkan.
    * `block`: Mengambil lebar penuh yang tersedia dan memulai baris baru (e.g., `div`, `p`, `h1`).
    * `inline`: Mengambil lebar sesuai konten dan tidak memulai baris baru (e.g., `span`, `a`, `img`).
    * `inline-block`: Mirip `inline` tetapi memungkinkan pengaturan `width` dan `height`.
* **`float`**: Menggeser elemen ke kiri atau kanan dan memungkinkan elemen lain mengelilinginya.
* **`position`**: Mengontrol penempatan elemen.
    * `static` (default): Elemen berada di posisi normal dalam aliran dokumen.
    * `relative`: Posisi relatif terhadap posisi normalnya. Properti `top`, `bottom`, `left`, `right` akan menggesernya.
    * `absolute`: Posisi relatif terhadap elemen `ancestor` terdekat yang diposisikan (non-static). Jika tidak ada, relatif terhadap dokumen.
    * `fixed`: Posisi relatif terhadap viewport browser (tetap di layar saat scroll).
    * `sticky`: Campuran `relative` dan `fixed`.
* **`flexbox` (CSS Flexible Box Layout)**: Metode tata letak satu dimensi untuk mendistribusikan ruang di antara item dalam kontainer. Ideal untuk baris atau kolom.
* **`grid` (CSS Grid Layout)**: Metode tata letak dua dimensi untuk mendistribusikan ruang di antara item dalam kontainer. Ideal untuk tata letak kompleks (baris dan kolom).

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contoh Layouting CSS</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f9f9f9;
        }

        h2 {
            border-bottom: 2px solid #ccc;
            padding-bottom: 10px;
            margin-top: 30px;
        }

        /* --- Display --- */
        .display-container div {
            background-color: #e0e0e0;
            margin: 5px;
            padding: 10px;
            border: 1px solid #bbb;
        }

        .display-block { display: block; width: 100px; height: 50px;}
        .display-inline { display: inline; background-color: lightgreen;}
        .display-inline-block { display: inline-block; width: 100px; height: 50px; background-color: lightcoral;}

        /* --- Float --- */
        .float-container {
            border: 1px solid #a0a0a0;
            padding: 10px;
            overflow: auto; /* Mengatasi parent collapse */
        }
        .float-left {
            float: left;
            width: 100px;
            height: 100px;
            background-color: #90ee90;
            margin-right: 10px;
            text-align: center;
            line-height: 100px;
        }
        .float-right {
            float: right;
            width: 100px;
            height: 100px;
            background-color: #add8e6;
            margin-left: 10px;
            text-align: center;
            line-height: 100px;
        }
        .clear-float {
            clear: both; /* Untuk membersihkan float */
            margin-top: 10px;
        }

        /* --- Position --- */
        .position-container {
            position: relative; /* Container untuk elemen absolute */
            width: 300px;
            height: 150px;
            border: 2px dashed #666;
            margin-top: 20px;
            padding: 10px;
        }
        .positioned-box {
            width: 80px;
            height: 50px;
            background-color: orange;
            text-align: center;
            line-height: 50px;
        }
        .position-static { position: static; background-color: lightgrey; }
        .position-relative {
            position: relative;
            top: 10px;
            left: 10px;
            background-color: lightgoldenrodyellow;
        }
        .position-absolute {
            position: absolute;
            top: 20px;
            right: 20px;
            background-color: lightsalmon;
        }
        .position-fixed {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: #4CAF50;
            color: white;
            padding: 10px;
            z-index: 1000; /* Agar di atas elemen lain */
        }

        /* --- Flexbox --- */
        .flex-container {
            display: flex; /* Mengaktifkan flexbox */
            border: 2px solid purple;
            padding: 10px;
            margin-top: 20px;
            justify-content: space-around; /* Menyebarkan item */
            align-items: center; /* Menyelaraskan item secara vertikal */
            height: 150px;
        }
        .flex-item {
            background-color: #c080ff;
            color: white;
            padding: 15px;
            margin: 5px;
            font-weight: bold;
        }

        /* --- Grid --- */
        .grid-container {
            display: grid; /* Mengaktifkan grid */
            grid-template-columns: 1fr 2fr 1fr; /* Tiga kolom dengan rasio lebar */
            grid-template-rows: auto auto; /* Dua baris, tinggi otomatis */
            gap: 10px; /* Jarak antar grid item */
            border: 2px solid teal;
            padding: 10px;
            margin-top: 20px;
        }
        .grid-item {
            background-color: #80ced6;
            color: white;
            padding: 15px;
            text-align: center;
        }
        .grid-item:nth-child(even) {
            background-color: #618685;
        }
    </style>
</head>
<body>
    <h2>1. Display</h2>
    <div class="display-container">
        <div class="display-block">Block</div>
        <span class="display-inline">Inline 1</span>
        <span class="display-inline">Inline 2</span>
        <div class="display-inline-block">Inline-Block</div>
        <div class="display-inline-block">Inline-Block 2</div>
    </div>

    <h2>2. Float</h2>
    <div class="float-container">
        <div class="float-left">Float Left</div>
        <div class="float-right">Float Right</div>
        <p>Ini adalah teks di samping elemen yang di-float. Teks ini akan mengelilingi elemen float. Float sering digunakan untuk membuat layout kolom atau memposisikan gambar di dalam teks.</p>
        <div class="clear-float"></div>
    </div>

    <h2>3. Position</h2>
    <p>Scroll ke bawah untuk melihat `position: fixed`.</p>
    <div class="position-container">
        <div class="positioned-box position-static">Static</div>
        <div class="positioned-box position-relative">Relative</div>
        <div class="positioned-box position-absolute">Absolute</div>
    </div>
    <div class="position-fixed">Fixed Box</div>
    <p style="height: 500px; margin-top: 50px;">Scroll ke bawah lagi untuk melihat efek fixed box.</p>

    <h2>4. Flexbox</h2>
    <div class="flex-container">
        <div class="flex-item">Item 1</div>
        <div class="flex-item">Item 2</div>
        <div class="flex-item">Item 3</div>
        <div class="flex-item">Item 4</div>
    </div>

    <h2>5. Grid</h2>
    <div class="grid-container">
        <div class="grid-item">Header</div>
        <div class="grid-item">Navigasi</div>
        <div class="grid-item">Side</div>
        <div class="grid-item">Content</div>
        <div class="grid-item">Content 2</div>
        <div class="grid-item">Footer</div>
    </div>
</body>
</html>
```

---

### 5. Responsif Design (media queries)

**Penjelasan:**
Desain responsif adalah pendekatan di mana desain dan pengembangan web merespons perilaku dan lingkungan pengguna berdasarkan ukuran layar, platform, dan orientasi. `Media queries` adalah fitur CSS3 yang memungkinkan konten yang disajikan disesuaikan dengan kondisi tertentu (misalnya, ukuran layar).

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contoh Responsif Design (Media Queries)</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f0f8ff;
            color: #333;
        }

        .container {
            width: 90%;
            margin: auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }

        .column {
            background-color: #afeeee;
            padding: 15px;
            margin-bottom: 10px;
            text-align: center;
            border-radius: 5px;
        }

        .message {
            text-align: center;
            font-size: 1.2em;
            margin-top: 20px;
            padding: 10px;
            border-radius: 5px;
            background-color: lightgreen;
        }

        /* Default styles for larger screens */
        .column {
            display: inline-block;
            width: 30%; /* Tiga kolom */
            margin-right: 2.3%;
            box-sizing: border-box; /* Padding dan border termasuk dalam lebar */
        }
        .column:last-child {
            margin-right: 0;
        }
        .message {
            background-color: lightblue;
            color: darkblue;
        }

        /* Media Query untuk layar <= 768px (Tablet) */
        @media screen and (max-width: 768px) {
            .column {
                width: 48%; /* Dua kolom */
                margin-right: 4%;
            }
            .column:nth-child(2n) { /* Setiap kolom kedua */
                margin-right: 0;
            }
            .message {
                background-color: orange;
                color: darkorange;
            }
        }

        /* Media Query untuk layar <= 480px (Smartphone) */
        @media screen and (max-width: 480px) {
            .column {
                width: 100%; /* Satu kolom penuh */
                margin-right: 0;
            }
            .message {
                background-color: salmon;
                color: darkred;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Responsif Design dengan Media Queries</h1>
        <p>Coba ubah ukuran jendela browser Anda untuk melihat bagaimana tata letak dan warna berubah.</p>

        <div class="column">Kolom 1</div>
        <div class="column">Kolom 2</div>
        <div class="column">Kolom 3</div>

        <div class="message">
            Anda sedang melihat tampilan untuk:
            <span class="desktop-msg">Desktop (lebar > 768px)</span>
            <span class="tablet-msg" style="display: none;">Tablet (lebar <= 768px)</span>
            <span class="mobile-msg" style="display: none;">Mobile (lebar <= 480px)</span>
        </div>
    </div>

    <script>
        // Sedikit JavaScript untuk menampilkan pesan yang sesuai
        function updateMessage() {
            const desktopMsg = document.querySelector('.desktop-msg');
            const tabletMsg = document.querySelector('.tablet-msg');
            const mobileMsg = document.querySelector('.mobile-msg');

            if (window.innerWidth <= 480) {
                desktopMsg.style.display = 'none';
                tabletMsg.style.display = 'none';
                mobileMsg.style.display = 'inline';
            } else if (window.innerWidth <= 768) {
                desktopMsg.style.display = 'none';
                tabletMsg.style.display = 'inline';
                mobileMsg.style.display = 'none';
            } else {
                desktopMsg.style.display = 'inline';
                tabletMsg.style.display = 'none';
                mobileMsg.style.display = 'none';
            }
        }

        window.addEventListener('resize', updateMessage);
        window.addEventListener('load', updateMessage);
    </script>
</body>
</html>
```

---

### 6. Transisi dan Animasi Sederhana

**Penjelasan:**
* **Transisi (`transition`)**: Memungkinkan Anda membuat perubahan halus antara dua status CSS. Anda menentukan properti yang akan diubah, durasi, dan fungsi waktu.
* **Animasi (`animation`)**: Memungkinkan Anda membuat urutan perubahan gaya CSS dari satu set keyframe ke set keyframe lainnya. Lebih kompleks daripada transisi dan memungkinkan kontrol yang lebih rinci atas urutan animasi.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contoh Transisi dan Animasi CSS</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f9f9f9;
        }

        h2 {
            border-bottom: 2px solid #ccc;
            padding-bottom: 10px;
            margin-top: 30px;
        }

        /* --- Transisi --- */
        .transition-box {
            width: 100px;
            height: 100px;
            background-color: dodgerblue;
            margin: 20px;
            text-align: center;
            line-height: 100px;
            color: white;
            font-weight: bold;
            font-size: 1.2em;

            /* Properti transisi */
            transition: background-color 0.5s ease-in-out, transform 0.5s ease-in-out;
            /* Properti, Durasi, Fungsi waktu (ease, linear, ease-in, ease-out, ease-in-out) */
        }

        .transition-box:hover {
            background-color: darkblue;
            transform: scale(1.2) rotate(10deg); /* Membesar dan berputar */
            cursor: pointer;
        }

        /* --- Animasi --- */
        @keyframes slideIn {
            0% {
                transform: translateX(-100%);
                opacity: 0;
            }
            50% {
                transform: translateX(20%);
                opacity: 0.5;
            }
            100% {
                transform: translateX(0);
                opacity: 1;
            }
        }

        @keyframes pulse {
            0% {
                transform: scale(1);
                box-shadow: 0 0 0 0 rgba(0, 128, 0, 0.7);
            }
            70% {
                transform: scale(1.05);
                box-shadow: 0 0 0 15px rgba(0, 128, 0, 0);
            }
            100% {
                transform: scale(1);
                box-shadow: 0 0 0 0 rgba(0, 128, 0, 0);
            }
        }

        .animated-box {
            width: 150px;
            height: 80px;
            background-color: mediumseagreen;
            margin: 20px;
            text-align: center;
            line-height: 80px;
            color: white;
            font-weight: bold;
            font-size: 1.1em;
            border-radius: 5px;

            /* Properti animasi */
            animation: slideIn 2s ease-out forwards, pulse 2s infinite alternate;
            /* Nama animasi, Durasi, Fungsi waktu, Mode isi (forwards mempertahankan status akhir), Iterasi, Arah (alternate bolak-balik) */
        }
    </style>
</head>
<body>
    <h2>1. Transisi Sederhana</h2>
    <p>Arahkan kursor Anda ke kotak di bawah ini:</p>
    <div class="transition-box">Hover Me</div>

    <h2>2. Animasi Sederhana</h2>
    <p>Kotak di bawah ini akan bergerak dari kiri dan berdenyut:</p>
    <div class="animated-box">I'm Animated!</div>
</body>
</html>
```
