**Materi Pembelajaran Sesi 10-12: Pengenalan Bahasa Pemrograman Server-Side (±9 JP)**

---

### **1. Konsep Dasar Server-Side (HTTP Request/Response Cycle)**

**Penjelasan:**
Pada dasarnya, ketika Anda mengakses sebuah website, browser (client) Anda mengirimkan sebuah **HTTP Request** ke server. Server kemudian memproses request tersebut (misalnya, mengambil data dari database, menjalankan skrip, dll.), dan mengirimkan kembali **HTTP Response** yang berisi kode HTML, CSS, JavaScript, gambar, dll., yang kemudian ditampilkan oleh browser Anda. PHP adalah bahasa yang berjalan di sisi server untuk memproses request ini.

**Contoh Program (Simulasi Sederhana):**

Buat file `index.php`:

```php
<?php
// index.php

// 1. Server menerima HTTP Request
//    Kita bisa mengakses informasi dari request menggunakan superglobal seperti $_SERVER.
//    $_SERVER['REQUEST_METHOD'] akan berisi metode HTTP (GET, POST, dll.)
//    $_SERVER['REQUEST_URI'] akan berisi path yang diminta

if ($_SERVER['REQUEST_METHOD'] === 'GET') {
    // Ini adalah contoh ketika browser meminta halaman ini (GET request)
    $name = isset($_GET['name']) ? htmlspecialchars($_GET['name']) : 'Tamu';

    // 2. Server memproses Request (misalnya, menyiapkan konten)
    $message = "Halo, " . $name . "! Selamat datang di halaman server-side sederhana.";

    // 3. Server mengirimkan HTTP Response (dalam bentuk HTML)
    echo "<!DOCTYPE html>";
    echo "<html lang='en'>";
    echo "<head>";
    echo "    <meta charset='UTF-8'>";
    echo "    <meta name='viewport' content='width=device-width, initial-scale=1.0'>";
    echo "    <title>HTTP Request/Response Cycle</title>";
    echo "</head>";
    echo "<body>";
    echo "    <h1>" . $message . "</h1>";
    echo "    <p>Ini adalah contoh sederhana dari bagaimana server memproses permintaan GET.</p>";
    echo "    <p>Coba tambahkan `?name=NamaAnda` di URL, misalnya: <code>http://localhost/index.php?name=Budi</code></p>";
    echo "</body>";
    echo "</html>";

} elseif ($_SERVER['REQUEST_METHOD'] === 'POST') {
    // Ini adalah contoh ketika browser mengirimkan data melalui form (POST request)
    $post_data = isset($_POST['data']) ? htmlspecialchars($_POST['data']) : 'Tidak ada data';

    echo "<!DOCTYPE html>";
    echo "<html lang='en'>";
    echo "<head>";
    echo "    <meta charset='UTF-8'>";
    echo "    <meta name='viewport' content='width=device-width, initial-scale=1.0'>";
    echo "    <title>HTTP POST Request</title>";
    echo "</head>";
    echo "<body>";
    echo "    <h1>Anda mengirimkan data melalui POST!</h1>";
    echo "    <p>Data yang diterima: " . $post_data . "</p>";
    echo "    <p>Ini menunjukkan bagaimana server menerima dan memproses data dari form POST.</p>";
    echo "</body>";
    echo "</html>";
}
?>
```

**Cara Menjalankan:**
Simpan file ini di direktori web server Anda (misalnya `htdocs` jika Anda menggunakan XAMPP/WAMPP). Buka browser dan akses `http://localhost/index.php` (sesuaikan jika nama filenya berbeda).

---

### **2. Variabel, Tipe Data, Struktur Kontrol di Bahasa yang Dipilih (PHP)**

**Penjelasan:**
Bagian ini mencakup dasar-dasar sintaksis PHP yang penting untuk menulis program.

**Contoh Program:**

Buat file `basic_syntax.php`:

```php
<?php
// basic_syntax.php

// --- Variabel ---
// Variabel di PHP diawali dengan tanda $.
$nama = "John Doe"; // String
$umur = 30; // Integer
$tinggi_badan = 175.5; // Float/Double
$is_aktif = true; // Boolean
$hobi = ["Membaca", "Berenang", "Memasak"]; // Array
$null_variable = null; // Null

echo "<h2>Variabel dan Tipe Data</h2>";
echo "Nama: " . $nama . "<br>";
echo "Umur: " . $umur . " tahun<br>";
echo "Tinggi Badan: " . $tinggi_badan . " cm<br>";
echo "Status Aktif: " . ($is_aktif ? "Ya" : "Tidak") . "<br>"; // Ternary operator untuk boolean
echo "Hobi pertama: " . $hobi[0] . "<br>";
echo "Variabel null: " . (is_null($null_variable) ? "NULL" : "Tidak NULL") . "<br>";

echo "<hr>";

// --- Tipe Data (Lanjutan) ---
// Objek (akan dibahas lebih lanjut di OOP)
class Person {
    public $name;
    function __construct($name) {
        $this->name = $name;
    }
}
$person_obj = new Person("Jane Smith");
echo "Nama dari objek: " . $person_obj->name . "<br>";

echo "<hr>";

// --- Struktur Kontrol: Conditional Statements (if, elseif, else) ---
echo "<h2>Struktur Kontrol: Conditional Statements</h2>";

$nilai = 75;

if ($nilai >= 90) {
    echo "Nilai Anda A<br>";
} elseif ($nilai >= 80) {
    echo "Nilai Anda B<br>";
} elseif ($nilai >= 70) {
    echo "Nilai Anda C<br>";
} else {
    echo "Nilai Anda D<br>";
}

// Switch-Case
$hari = "Senin";
echo "Hari ini adalah ";
switch ($hari) {
    case "Senin":
        echo "hari kerja<br>";
        break;
    case "Sabtu":
    case "Minggu":
        echo "akhir pekan<br>";
        break;
    default:
        echo "hari biasa<br>";
}

echo "<hr>";

// --- Struktur Kontrol: Looping Statements ---
echo "<h2>Struktur Kontrol: Looping Statements</h2>";

// For Loop
echo "For Loop (1-5): ";
for ($i = 1; $i <= 5; $i++) {
    echo $i . " ";
}
echo "<br>";

// While Loop
echo "While Loop (1-5): ";
$j = 1;
while ($j <= 5) {
    echo $j . " ";
    $j++;
}
echo "<br>";

// Do-While Loop
echo "Do-While Loop (1-5): ";
$k = 1;
do {
    echo $k . " ";
    $k++;
} while ($k <= 5);
echo "<br>";

// Foreach Loop (untuk array)
echo "Foreach Loop (Hobi): ";
foreach ($hobi as $item_hobi) {
    echo $item_hobi . ", ";
}
echo "<br>";

// Foreach Loop dengan Key (untuk associative array)
$siswa = [
    "nama" => "Ali",
    "umur" => 15,
    "kelas" => "X"
];
echo "Data Siswa: ";
foreach ($siswa as $key => $value) {
    echo $key . ": " . $value . ", ";
}
echo "<br>";
?>
```

**Cara Menjalankan:**
Simpan file ini sebagai `basic_syntax.php` di direktori web server Anda. Akses `http://localhost/basic_syntax.php` di browser.

---

### **3. Fungsi dan Modul**

**Penjelasan:**
Fungsi memungkinkan Anda mengelompokkan blok kode yang dapat digunakan kembali. Modul (dalam konteks PHP, sering diartikan sebagai file PHP lain yang berisi fungsi atau kelas yang di-include) membantu mengatur kode Anda menjadi bagian-bagian yang lebih kecil dan mudah dikelola.

**Contoh Program:**

Buat dua file: `functions.php` dan `main.php`.

**File: `functions.php` (Modul / Kumpulan Fungsi)**

```php
<?php
// functions.php - Ini adalah modul berisi fungsi-fungsi

function sayHello($name) {
    return "Halo, " . $name . "!";
}

function addNumbers($num1, $num2) {
    return $num1 + $num2;
}

function calculateArea($length, $width) {
    return $length * $width;
}

// Fungsi dengan parameter opsional dan nilai default
function greet($name, $greeting = "Selamat datang") {
    return $greeting . ", " . $name . "!";
}

// Fungsi yang mengembalikan array
function getUserInfo($userId) {
    // Simulasi pengambilan data user dari database
    $users = [
        1 => ["name" => "Budi", "email" => "budi@example.com"],
        2 => ["name" => "Siti", "email" => "siti@example.com"]
    ];
    return isset($users[$userId]) ? $users[$userId] : null;
}
?>
```

**File: `main.php` (Menggunakan Fungsi dari Modul)**

```php
<?php
// main.php - Menggunakan fungsi-fungsi dari functions.php

// Meng-include file functions.php agar fungsi-fungsi di dalamnya bisa digunakan
include 'functions.php'; // Atau require 'functions.php';

echo "<h2>Fungsi dan Modul</h2>";

// Memanggil fungsi dari functions.php
echo sayHello("Dunia") . "<br>";

$sum = addNumbers(10, 5);
echo "Hasil penjumlahan 10 + 5 = " . $sum . "<br>";

$area = calculateArea(7, 8);
echo "Luas persegi panjang (7x8) = " . $area . "<br>";

echo greet("Andi") . "<br>"; // Menggunakan nilai default
echo greet("Dewi", "Hai") . "<br>"; // Menggunakan nilai parameter

$userInfo = getUserInfo(1);
if ($userInfo) {
    echo "User Info: Nama - " . $userInfo['name'] . ", Email - " . $userInfo['email'] . "<br>";
} else {
    echo "User tidak ditemukan.<br>";
}

echo "<hr>";

// Fungsi Anonim (Closure) - PHP 5.3+
$multiply = function($a, $b) {
    return $a * $b;
};
echo "Hasil perkalian (fungsi anonim) 6 * 4 = " . $multiply(6, 4) . "<br>";

echo "<hr>";

// Fungsi Callbacks
function processArray($array, $callback) {
    $result = [];
    foreach ($array as $item) {
        $result[] = $callback($item);
    }
    return $result;
}

$numbers = [1, 2, 3, 4, 5];
$squaredNumbers = processArray($numbers, function($n) {
    return $n * $n;
});

echo "Angka-angka kuadrat: " . implode(", ", $squaredNumbers) . "<br>";

?>
```

**Cara Menjalankan:**
Simpan kedua file di direktori yang sama di web server Anda. Akses `http://localhost/main.php` di browser.

---

### **4. Menghubungkan ke Database (MySQL/PostgreSQL)**

**Penjelasan:**
Bagian ini akan menunjukkan cara PHP berinteraksi dengan database. Kita akan fokus pada MySQL menggunakan ekstensi `mysqli` (MySQL Improved Extension), yang direkomendasikan karena lebih aman dan modern dibandingkan `mysql_*` functions yang sudah deprecated. Untuk PostgreSQL, konsepnya serupa, hanya berbeda di fungsi koneksi (`pg_connect()`) dan fungsi-fungsi query lainnya.

**Persiapan (MySQL):**
1.  Pastikan Anda memiliki server MySQL yang berjalan (biasanya disertakan dengan XAMPP/WAMPP).
2.  Buat sebuah database, misalnya `db_belajar_php`.
3.  Buat tabel di dalamnya, misalnya `users` dengan kolom `id`, `name`, `email`.

**Contoh SQL untuk MySQL:**

```sql
CREATE DATABASE IF NOT EXISTS db_belajar_php;

USE db_belajar_php;

CREATE TABLE IF NOT EXISTS users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

INSERT INTO users (name, email) VALUES ('Budi Santoso', 'budi@example.com');
INSERT INTO users (name, email) VALUES ('Siti Aminah', 'siti@example.com');
```

**Contoh Program (Koneksi MySQL - `mysqli`):**

Buat file `db_connection.php`:

```php
<?php
// db_connection.php

$servername = "localhost"; // Biasanya localhost
$username = "root"; // Username default XAMPP/WAMPP
$password = ""; // Password default XAMPP/WAMPP (kosong)
$dbname = "db_belajar_php"; // Nama database yang sudah dibuat

// Membuat koneksi
$conn = new mysqli($servername, $username, $password, $dbname);

// Memeriksa koneksi
if ($conn->connect_error) {
    die("Koneksi ke database gagal: " . $conn->connect_error);
}

echo "Koneksi ke database berhasil!<br>";

// Penting: Tutup koneksi setelah selesai (walaupun PHP akan menutup otomatis di akhir skrip)
// $conn->close();

?>
```

**Cara Menjalankan:**
Simpan file ini sebagai `db_connection.php` di direktori web server Anda. Pastikan MySQL berjalan dan database `db_belajar_php` sudah dibuat. Akses `http://localhost/db_connection.php` di browser. Anda seharusnya melihat pesan "Koneksi ke database berhasil!".

---

### **5. Basic CRUD Operations (Create, Read, Update, Delete)**

**Penjelasan:**
CRUD adalah empat operasi dasar yang bisa dilakukan pada data di database.

* **Create (C):** Menambahkan data baru.
* **Read (R):** Mengambil/membaca data.
* **Update (U):** Mengubah data yang sudah ada.
* **Delete (D):** Menghapus data.

Kita akan menggunakan `mysqli` dengan prepared statements untuk keamanan (melindungi dari SQL injection).

**Contoh Program (CRUD dengan MySQLi Prepared Statements):**

Buat file `crud_operations.php`:

```php
<?php
// crud_operations.php

// Include file koneksi database
include 'db_connection.php'; // Pastikan db_connection.php sudah ada dan berisi kode koneksi

echo "<h2>CRUD Operations (MySQLi)</h2>";

// --- 1. CREATE (Tambah Data) ---
echo "<h3>1. CREATE (Tambah Data)</h3>";
$new_name = "Faisal Ramadhan";
$new_email = "faisal@example.com";

// Prepared Statement untuk INSERT
$stmt = $conn->prepare("INSERT INTO users (name, email) VALUES (?, ?)");
$stmt->bind_param("ss", $new_name, $new_email); // "ss" berarti dua string

if ($stmt->execute()) {
    echo "Data baru berhasil ditambahkan: " . $new_name . "<br>";
} else {
    echo "Error: " . $stmt->error . "<br>";
}
$stmt->close(); // Tutup statement

// --- 2. READ (Baca Data) ---
echo "<h3>2. READ (Baca Data)</h3>";

$sql_read = "SELECT id, name, email, created_at FROM users";
$result = $conn->query($sql_read);

if ($result->num_rows > 0) {
    echo "<table border='1'><tr><th>ID</th><th>Nama</th><th>Email</th><th>Created At</th></tr>";
    // Output data dari setiap baris
    while($row = $result->fetch_assoc()) {
        echo "<tr><td>" . $row["id"]. "</td><td>" . $row["name"]. "</td><td>" . $row["email"]. "</td><td>" . $row["created_at"]. "</td></tr>";
    }
    echo "</table>";
} else {
    echo "Tidak ada data user.<br>";
}

echo "<hr>";

// --- 3. UPDATE (Ubah Data) ---
echo "<h3>3. UPDATE (Ubah Data)</h3>";
$user_id_to_update = 3; // ID user yang ingin diupdate
$updated_name = "Faisal Ramadhan Terbaru";
$updated_email = "faisal.new@example.com";

// Prepared Statement untuk UPDATE
$stmt = $conn->prepare("UPDATE users SET name = ?, email = ? WHERE id = ?");
$stmt->bind_param("ssi", $updated_name, $updated_email, $user_id_to_update); // "ssi" berarti dua string, satu integer

if ($stmt->execute()) {
    if ($stmt->affected_rows > 0) {
        echo "Data user ID " . $user_id_to_update . " berhasil diupdate.<br>";
    } else {
        echo "Tidak ada data yang diupdate (mungkin ID tidak ditemukan atau data sama).<br>";
    }
} else {
    echo "Error updating record: " . $stmt->error . "<br>";
}
$stmt->close();

// Baca lagi setelah update untuk verifikasi
echo "<h4>Data setelah Update:</h4>";
$sql_read_after_update = "SELECT id, name, email FROM users WHERE id = " . $user_id_to_update;
$result_after_update = $conn->query($sql_read_after_update);
if ($result_after_update->num_rows > 0) {
    while($row = $result_after_update->fetch_assoc()) {
        echo "ID: " . $row["id"]. " - Nama: " . $row["name"]. " - Email: " . $row["email"]. "<br>";
    }
} else {
    echo "User ID " . $user_id_to_update . " tidak ditemukan.<br>";
}

echo "<hr>";

// --- 4. DELETE (Hapus Data) ---
echo "<h3>4. DELETE (Hapus Data)</h3>";
$user_id_to_delete = 2; // ID user yang ingin dihapus

// Prepared Statement untuk DELETE
$stmt = $conn->prepare("DELETE FROM users WHERE id = ?");
$stmt->bind_param("i", $user_id_to_delete); // "i" berarti satu integer

if ($stmt->execute()) {
    if ($stmt->affected_rows > 0) {
        echo "Data user ID " . $user_id_to_delete . " berhasil dihapus.<br>";
    } else {
        echo "Tidak ada data yang dihapus (mungkin ID tidak ditemukan).<br>";
    }
} else {
    echo "Error deleting record: " . $stmt->error . "<br>";
}
$stmt->close();

// Baca lagi semua data setelah delete untuk verifikasi
echo "<h4>Semua Data setelah Delete:</h4>";
$sql_read_after_delete = "SELECT id, name, email FROM users";
$result_after_delete = $conn->query($sql_read_after_delete);
if ($result_after_delete->num_rows > 0) {
    echo "<table border='1'><tr><th>ID</th><th>Nama</th><th>Email</th></tr>";
    while($row = $result_after_delete->fetch_assoc()) {
        echo "<tr><td>" . $row["id"]. "</td><td>" . $row["name"]. "</td><td>" . $row["email"]. "</td></tr>";
    }
    echo "</table>";
} else {
    echo "Tidak ada data user.<br>";
}

// Tutup koneksi database di akhir skrip
$conn->close();

?>
```

**Cara Menjalankan:**
1.  Pastikan Anda sudah menjalankan MySQL dan membuat database `db_belajar_php` serta tabel `users` dengan data awal seperti yang dijelaskan di bagian "Menghubungkan ke Database".
2.  Simpan file `db_connection.php` dan `crud_operations.php` di direktori yang sama di web server Anda.
3.  Akses `http://localhost/crud_operations.php` di browser. Anda akan melihat output dari operasi CRUD. Perhatikan bahwa setiap kali Anda me-refresh halaman, operasi CREATE akan dijalankan lagi (kecuali email sudah ada karena UNIQUE constraint).

---

**Catatan Penting:**

* **Keamanan:** Selalu gunakan Prepared Statements (`mysqli::prepare()`, `PDO::prepare()`) saat berinteraksi dengan database untuk mencegah SQL Injection. Contoh di atas sudah menggunakan ini.
* **Error Handling:** Dalam aplikasi nyata, error handling harus lebih robust, misalnya menggunakan `try-catch` blocks jika Anda menggunakan PDO.
* **Struktur Proyek:** Untuk aplikasi yang lebih besar, pisahkan kode menjadi file-file yang lebih terstruktur (misalnya, file untuk koneksi, file untuk fungsi-fungsi CRUD, file untuk tampilan HTML).
* **Front-end:** Contoh di atas adalah PHP murni yang langsung mencetak HTML. Dalam aplikasi web modern, seringkali ada pemisahan antara back-end (PHP) dan front-end (HTML, CSS, JavaScript framework seperti React, Vue, Angular) yang berkomunikasi via API.
* **Framework:** Untuk pengembangan yang lebih cepat dan terstruktur, pertimbangkan untuk belajar PHP framework seperti Laravel atau Symfony.

Semoga contoh-contoh program ini membantu Anda memahami materi Pengenalan Bahasa Pemrograman Server-Side (PHP) dengan lebih baik!
