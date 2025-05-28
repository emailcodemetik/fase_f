### Materi Pembelajaran Sesi 7-9: Pengantar JavaScript (±9 JP)

Berikut adalah contoh program untuk setiap poin materi yang Anda sebutkan:

---

#### 1. Variabel, Tipe Data, Operator

**Penjelasan:**
* **Variabel:** Wadah untuk menyimpan nilai. Dideklarasikan dengan `var`, `let`, atau `const`.
* **Tipe Data:** Jenis nilai yang bisa disimpan variabel (contoh: `string`, `number`, `boolean`, `object`, `null`, `undefined`).
* **Operator:** Simbol untuk melakukan operasi pada nilai (contoh: `+`, `-`, `*`, `/`, `==`, `===`, `&&`, `||`).

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Variabel, Tipe Data, Operator</title>
</head>
<body>
    <h1>Contoh Variabel, Tipe Data, dan Operator</h1>
    <p id="output"></p>

    <script>
        // Deklarasi Variabel
        let nama = "Budi"; // Tipe data: string
        const umur = 30; // Tipe data: number (konstanta, tidak bisa diubah)
        var isMahasiswa = true; // Tipe data: boolean (hindari var untuk proyek baru)

        // Tipe Data Lain
        let harga = 25000.50; // number (floating point)
        let dataKosong = null; // null
        let tidakTerdefinisi; // undefined

        // Operator Aritmatika
        let a = 10;
        let b = 5;
        let tambah = a + b; // 15
        let kurang = a - b; // 5
        let kali = a * b; // 50
        let bagi = a / b; // 2
        let sisaBagi = a % b; // 0

        // Operator Perbandingan
        let samaDengan = (a == '10'); // true (membandingkan nilai saja)
        let identik = (a === '10'); // false (membandingkan nilai dan tipe data)
        let lebihBesar = (a > b); // true

        // Operator Logika
        let kondisi1 = (umur > 20 && isMahasiswa); // true && true -> true
        let kondisi2 = (nama === "Andi" || umur < 25); // false || false -> false

        // Menampilkan hasil di halaman HTML
        let outputElement = document.getElementById('output');
        outputElement.innerHTML = `
            Nama: ${nama} (tipe: ${typeof nama})<br>
            Umur: ${umur} (tipe: ${typeof umur})<br>
            Apakah Mahasiswa: ${isMahasiswa} (tipe: ${typeof isMahasiswa})<br>
            Harga: ${harga} (tipe: ${typeof harga})<br>
            Data Kosong: ${dataKosong} (tipe: ${typeof dataKosong})<br>
            Tidak Terdefinisi: ${tidakTerdefinisi} (tipe: ${typeof tidakTerdefinisi})<br>
            <br>
            Hasil Tambah: ${tambah}<br>
            Hasil Kurang: ${kurang}<br>
            Hasil Kali: ${kali}<br>
            Hasil Bagi: ${bagi}<br>
            Sisa Bagi: ${sisaBagi}<br>
            <br>
            Sama Dengan (==): ${samaDengan}<br>
            Identik (===): ${identik}<br>
            Lebih Besar (>): ${lebihBesar}<br>
            <br>
            Kondisi Logika 1 (AND): ${kondisi1}<br>
            Kondisi Logika 2 (OR): ${kondisi2}
        `;
    </script>
</body>
</html>
```

---

#### 2. Struktur Kontrol (if-else, switch, loop)

**Penjelasan:**
* **`if-else`:** Mengeksekusi blok kode berdasarkan kondisi.
* **`switch`:** Alternatif untuk `if-else` bertingkat, memeriksa satu nilai terhadap beberapa kasus.
* **Loop (`for`, `while`, `do-while`, `for...of`, `for...in`):** Mengulang eksekusi blok kode.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Struktur Kontrol</title>
</head>
<body>
    <h1>Contoh Struktur Kontrol</h1>
    <h2>If-Else</h2>
    <p id="ifElseOutput"></p>

    <h2>Switch Case</h2>
    <p id="switchOutput"></p>

    <h2>Loop (For, While, Do-While)</h2>
    <p id="loopOutput"></p>

    <script>
        // If-Else
        let nilai = 75;
        let ifElseOutput = document.getElementById('ifElseOutput');
        if (nilai >= 90) {
            ifElseOutput.innerHTML = `Nilai Anda A (${nilai})`;
        } else if (nilai >= 80) {
            ifElseOutput.innerHTML = `Nilai Anda B (${nilai})`;
        } else if (nilai >= 70) {
            ifElseOutput.innerHTML = `Nilai Anda C (${nilai})`;
        } else {
            ifElseOutput.innerHTML = `Nilai Anda D (${nilai}). Anda perlu belajar lebih giat!`;
        }

        // Switch Case
        let hari = "Senin";
        let switchOutput = document.getElementById('switchOutput');
        switch (hari) {
            case "Senin":
                switchOutput.innerHTML = "Hari ini adalah awal minggu.";
                break;
            case "Jumat":
                switchOutput.innerHTML = "Selamat datang akhir pekan!";
                break;
            case "Minggu":
                switchOutput.innerHTML = "Waktunya bersantai.";
                break;
            default:
                switchOutput.innerHTML = "Hari biasa.";
        }

        // Loop
        let loopOutput = document.getElementById('loopOutput');
        let loopContent = "<h3>Loop For:</h3>";
        for (let i = 1; i <= 5; i++) {
            loopContent += `Angka: ${i}<br>`;
        }

        loopContent += "<h3>Loop While:</h3>";
        let j = 0;
        while (j < 3) {
            loopContent += `Iterasi While: ${j}<br>`;
            j++;
        }

        loopContent += "<h3>Loop Do-While:</h3>";
        let k = 0;
        do {
            loopContent += `Iterasi Do-While: ${k}<br>`;
            k++;
        } while (k < 2);

        loopContent += "<h3>Loop For...of (untuk array):</h3>";
        const buah = ["Apel", "Jeruk", "Mangga"];
        for (const itemBuah of buah) {
            loopContent += `Buah: ${itemBuah}<br>`;
        }

        loopContent += "<h3>Loop For...in (untuk object):</h3>";
        const orang = { nama: "Alice", usia: 25 };
        for (const key in orang) {
            loopContent += `${key}: ${orang[key]}<br>`;
        }

        loopOutput.innerHTML = loopContent;
    </script>
</body>
</html>
```

---

#### 3. Fungsi

**Penjelasan:**
Blok kode yang dapat digunakan kembali untuk melakukan tugas tertentu. Membantu dalam mengorganisir kode dan menghindari pengulangan.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Fungsi JavaScript</title>
</head>
<body>
    <h1>Contoh Fungsi JavaScript</h1>
    <p id="hasilFungsi1"></p>
    <p id="hasilFungsi2"></p>
    <p id="hasilFungsiAnonim"></p>
    <p id="hasilArrowFunction"></p>

    <script>
        // Deklarasi Fungsi Biasa
        function sapa(nama) {
            return `Halo, ${nama}! Selamat datang.`;
        }

        // Memanggil Fungsi
        let pesan1 = sapa("Dian");
        document.getElementById('hasilFungsi1').innerHTML = pesan1;

        // Fungsi dengan lebih dari satu parameter dan operasi
        function hitungLuasPersegiPanjang(panjang, lebar) {
            return panjang * lebar;
        }

        let luas = hitungLuasPersegiPanjang(10, 5);
        document.getElementById('hasilFungsi2').innerHTML = `Luas persegi panjang: ${luas}`;

        // Fungsi Anonim (dideklarasikan tanpa nama, sering digunakan sebagai callback)
        const tampilkanPesan = function() {
            document.getElementById('hasilFungsiAnonim').innerHTML = "Ini adalah pesan dari fungsi anonim.";
        };
        tampilkanPesan();

        // Arrow Function (ES6 - sintaks lebih ringkas)
        const kalikan = (a, b) => a * b;
        let hasilKali = kalikan(7, 8);
        document.getElementById('hasilArrowFunction').innerHTML = `Hasil perkalian (arrow function): ${hasilKali}`;

        // Fungsi yang memanggil fungsi lain
        function prosesData(nilai1, nilai2, operasi) {
            if (operasi === 'tambah') {
                return nilai1 + nilai2;
            } else if (operasi === 'kurang') {
                return nilai1 - nilai2;
            } else {
                return "Operasi tidak dikenal";
            }
        }
        // Contoh penggunaan (tidak ditampilkan di HTML, hanya untuk ilustrasi)
        let hasilProses = prosesData(20, 10, 'tambah'); // 30
        console.log("Hasil proses data:", hasilProses);
    </script>
</body>
</html>
```

---

#### 4. DOM Manipulation (menambahkan, mengubah, menghapus elemen)

**Penjelasan:**
Document Object Model (DOM) adalah representasi terstruktur dari dokumen HTML yang memungkinkan JavaScript untuk mengakses dan memanipulasi konten, struktur, dan gaya halaman web.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DOM Manipulation</title>
    <style>
        .highlight {
            color: blue;
            font-weight: bold;
        }
        #kontainer-elemen {
            border: 1px solid black;
            padding: 10px;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <h1>Contoh DOM Manipulation</h1>

    <p id="teksAwal">Ini adalah teks awal.</p>
    <button onclick="ubahTeks()">Ubah Teks</button>
    <button onclick="ubahWarna()">Ubah Warna</button>

    <div id="kontainer-elemen">
        <h2>Daftar Item</h2>
        <ul id="daftar">
            <li>Item 1</li>
            <li>Item 2</li>
        </ul>
    </div>

    <button onclick="tambahItem()">Tambah Item Baru</button>
    <button onclick="hapusItemTerakhir()">Hapus Item Terakhir</button>

    <script>
        // Mengubah Konten Elemen
        function ubahTeks() {
            let teksElement = document.getElementById('teksAwal');
            teksElement.textContent = "Teks ini telah diubah oleh JavaScript!";
        }

        // Mengubah Atribut/Style Elemen
        function ubahWarna() {
            let teksElement = document.getElementById('teksAwal');
            teksElement.classList.add('highlight'); // Menambahkan class CSS
            // teksElement.style.backgroundColor = 'yellow'; // Mengubah style langsung
        }

        // Menambahkan Elemen Baru
        function tambahItem() {
            let daftar = document.getElementById('daftar');
            let newItem = document.createElement('li'); // Membuat elemen <li> baru
            newItem.textContent = "Item Baru Ditambahkan!"; // Mengisi konten teks
            daftar.appendChild(newItem); // Menambahkan ke dalam <ul>
        }

        // Menghapus Elemen
        function hapusItemTerakhir() {
            let daftar = document.getElementById('daftar');
            if (daftar.children.length > 0) {
                let lastItem = daftar.lastElementChild; // Mendapatkan elemen terakhir
                daftar.removeChild(lastItem); // Menghapus elemen
            } else {
                alert("Tidak ada item untuk dihapus!");
            }
        }
    </script>
</body>
</html>
```

---

#### 5. Event Handling

**Penjelasan:**
Merespon interaksi pengguna atau kejadian lain di halaman web (contoh: klik tombol, submit form, mouse over).

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Event Handling</title>
    <style>
        #kotak {
            width: 100px;
            height: 100px;
            background-color: lightgray;
            border: 1px solid black;
            margin-top: 20px;
            text-align: center;
            line-height: 100px;
        }
    </style>
</head>
<body>
    <h1>Contoh Event Handling</h1>

    <button id="klikSaya">Klik Saya</button>
    <p id="pesanKlik"></p>

    <input type="text" id="inputNama" placeholder="Ketik nama Anda">
    <p id="pesanInput"></p>

    <div id="kotak">Mouse Over/Out</div>
    <p id="pesanKotak"></p>

    <script>
        // Event Listener untuk Klik Tombol
        const tombolKlik = document.getElementById('klikSaya');
        const pesanKlik = document.getElementById('pesanKlik');

        tombolKlik.addEventListener('click', function() {
            pesanKlik.textContent = "Tombol telah diklik!";
        });

        // Event Listener untuk Input (Keyup)
        const inputNama = document.getElementById('inputNama');
        const pesanInput = document.getElementById('pesanInput');

        inputNama.addEventListener('keyup', function() {
            pesanInput.textContent = `Anda mengetik: ${inputNama.value}`;
        });

        // Event Listener untuk Mouse Over/Out
        const kotak = document.getElementById('kotak');
        const pesanKotak = document.getElementById('pesanKotak');

        kotak.addEventListener('mouseover', function() {
            pesanKotak.textContent = "Mouse berada di atas kotak!";
            kotak.style.backgroundColor = 'lightblue';
        });

        kotak.addEventListener('mouseout', function() {
            pesanKotak.textContent = "Mouse keluar dari kotak.";
            kotak.style.backgroundColor = 'lightgray';
        });

        // Event Listener untuk Submit Form (akan dibahas lebih detail di Basic Form Validation)
        // Ini hanya contoh sederhana
        document.addEventListener('DOMContentLoaded', function() {
            console.log("Dokumen selesai dimuat!");
            // Biasanya, event listener untuk form akan diletakkan di sini
        });
    </script>
</body>
</html>
```

---

#### 6. Basic Form Validation

**Penjelasan:**
Memastikan data yang dimasukkan pengguna ke dalam formulir sesuai dengan kriteria yang ditentukan sebelum dikirim ke server.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic Form Validation</title>
    <style>
        .error {
            color: red;
            font-size: 0.9em;
        }
        form div {
            margin-bottom: 10px;
        }
        input[type="text"], input[type="email"] {
            width: 200px;
            padding: 5px;
        }
    </style>
</head>
<body>
    <h1>Contoh Basic Form Validation</h1>

    <form id="myForm">
        <div>
            <label for="nama">Nama:</label><br>
            <input type="text" id="nama" name="nama">
            <span class="error" id="errorNama"></span>
        </div>
        <div>
            <label for="email">Email:</label><br>
            <input type="email" id="email" name="email">
            <span class="error" id="errorEmail"></span>
        </div>
        <div>
            <label for="password">Password:</label><br>
            <input type="password" id="password" name="password">
            <span class="error" id="errorPassword"></span>
        </div>
        <button type="submit">Submit</button>
    </form>

    <p id="pesanSubmit"></p>

    <script>
        const myForm = document.getElementById('myForm');
        const namaInput = document.getElementById('nama');
        const emailInput = document.getElementById('email');
        const passwordInput = document.getElementById('password');
        const errorNama = document.getElementById('errorNama');
        const errorEmail = document.getElementById('errorEmail');
        const errorPassword = document.getElementById('errorPassword');
        const pesanSubmit = document.getElementById('pesanSubmit');

        myForm.addEventListener('submit', function(event) {
            event.preventDefault(); // Mencegah form dari submit default (reload halaman)

            // Reset pesan error
            errorNama.textContent = '';
            errorEmail.textContent = '';
            errorPassword.textContent = '';
            pesanSubmit.textContent = '';

            let isValid = true;

            // Validasi Nama
            if (namaInput.value.trim() === '') {
                errorNama.textContent = 'Nama tidak boleh kosong.';
                isValid = false;
            }

            // Validasi Email
            if (emailInput.value.trim() === '') {
                errorEmail.textContent = 'Email tidak boleh kosong.';
                isValid = false;
            } else if (!isValidEmail(emailInput.value)) {
                errorEmail.textContent = 'Format email tidak valid.';
                isValid = false;
            }

            // Validasi Password
            if (passwordInput.value.length < 6) {
                errorPassword.textContent = 'Password minimal 6 karakter.';
                isValid = false;
            }

            // Jika semua validasi berhasil
            if (isValid) {
                pesanSubmit.textContent = 'Form berhasil disubmit!';
                pesanSubmit.style.color = 'green';
                // Di sini Anda bisa mengirim data form ke server (misalnya dengan AJAX)
                console.log("Data form:", {
                    nama: namaInput.value,
                    email: emailInput.value,
                    password: passwordInput.value
                });
                myForm.reset(); // Mengosongkan form setelah submit
            } else {
                pesanSubmit.textContent = 'Mohon perbaiki kesalahan pada form.';
                pesanSubmit.style.color = 'red';
            }
        });

        // Fungsi bantu untuk validasi format email
        function isValidEmail(email) {
            const re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
            return re.test(String(email).toLowerCase());
        }
    </script>
</body>
</html>
```

---

#### 7. Asynchronous JavaScript (Callbacks, Promises - Pengenalan)

**Penjelasan:**
JavaScript secara default adalah *single-threaded*, artinya hanya bisa menjalankan satu tugas pada satu waktu. Asynchronous JavaScript memungkinkan tugas-tugas yang membutuhkan waktu lama (misalnya, mengambil data dari server) untuk berjalan di latar belakang tanpa memblokir eksekusi kode utama.

* **Callbacks:** Fungsi yang diteruskan sebagai argumen ke fungsi lain, dan akan dieksekusi setelah tugas selesai.
* **Promises:** Objek yang merepresentasikan hasil akhir dari sebuah operasi asinkron. Mereka menyediakan cara yang lebih terstruktur dan lebih baik untuk menangani asynchronicity dibandingkan callback hell.

**Contoh Program:**

```html
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Asynchronous JavaScript</title>
</head>
<body>
    <h1>Contoh Asynchronous JavaScript</h1>

    <h2>Callbacks</h2>
    <p id="callbackOutput"></p>
    <button onclick="jalankanCallback()">Jalankan Callback</button>

    <h2>Promises</h2>
    <p id="promiseOutput"></p>
    <button onclick="jalankanPromise()">Jalankan Promise</button>

    <script>
        // --- Callbacks ---
        function ambilDataDariServer(callback) {
            // Simulasi operasi yang membutuhkan waktu (misal, request ke API)
            console.log("Mulai mengambil data...");
            setTimeout(() => {
                const data = {
                    nama: "John Doe",
                    usia: 28,
                    status: "sukses"
                };
                console.log("Data berhasil diambil.");
                callback(data); // Panggil callback setelah data siap
            }, 2000); // Simulasi penundaan 2 detik
        }

        function tampilkanData(data) {
            const callbackOutput = document.getElementById('callbackOutput');
            callbackOutput.textContent = `Data dari server: Nama ${data.nama}, Usia ${data.usia}`;
        }

        function jalankanCallback() {
            document.getElementById('callbackOutput').textContent = "Mengambil data...";
            ambilDataDariServer(tampilkanData); // Meneruskan tampilkanData sebagai callback
        }


        // --- Promises ---
        function ambilDataDariServerDenganPromise() {
            return new Promise((resolve, reject) => {
                console.log("Mulai mengambil data dengan Promise...");
                setTimeout(() => {
                    const sukses = true; // Ganti false untuk melihat reject

                    if (sukses) {
                        const data = {
                            produk: "Laptop",
                            harga: 12000000
                        };
                        console.log("Data Promise berhasil diambil.");
                        resolve(data); // Data berhasil, panggil resolve
                    } else {
                        const error = "Gagal mengambil data produk.";
                        console.error("Data Promise gagal diambil.");
                        reject(error); // Ada kesalahan, panggil reject
                    }
                }, 1500); // Simulasi penundaan 1.5 detik
            });
        }

        function jalankanPromise() {
            const promiseOutput = document.getElementById('promiseOutput');
            promiseOutput.textContent = "Mengambil data dengan Promise...";

            ambilDataDariServerDenganPromise()
                .then(data => {
                    // Ketika Promise berhasil (resolve)
                    promiseOutput.textContent = `Data produk: ${data.produk}, Harga: Rp${data.harga.toLocaleString()}`;
                    promiseOutput.style.color = 'green';
                })
                .catch(error => {
                    // Ketika Promise gagal (reject)
                    promiseOutput.textContent = `Error: ${error}`;
                    promiseOutput.style.color = 'red';
                })
                .finally(() => {
                    // Selalu dieksekusi, baik sukses maupun gagal
                    console.log("Operasi Promise selesai.");
                });
        }
    </script>
</body>
</html>
```

---

**Cara Menjalankan Program:**

1.  Simpan setiap contoh program di atas sebagai file `.html` (misalnya, `variabel.html`, `struktur_kontrol.html`, dll.).
2.  Buka file `.html` tersebut di browser web Anda (Chrome, Firefox, Edge, dll.).
3.  Anda akan melihat hasilnya di halaman web, dan untuk beberapa contoh, Anda bisa melihat output di **Console** browser (biasanya bisa diakses dengan menekan `F12` atau `Ctrl+Shift+I` lalu pilih tab "Console").

Semoga contoh-contoh program ini membantu Anda dalam memahami materi Pengantar JavaScript!
