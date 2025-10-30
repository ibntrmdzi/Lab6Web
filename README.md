# Lab6Web

Nama: Muhamad Rizki Wahyu Saputra

NIM: 312410534

Kelas: TI.24.A5

Mata Kuliah: Pemograman Web 1

## Langkah-langkah Praktikum 6 & 4

Satukan Filenya di dalam Folder agar bisa di run di browser
<img width="394" height="159" alt="Cuplikan layar 2025-10-30 221111" src="https://github.com/user-attachments/assets/8fbadf30-c2e5-41e9-ae9f-228b37147208" />

Pastikan di setiap file navbar-nya sudah saling terhubung seperti ini:
```html
<li class="nav-item"><a class="nav-link" href="home.html">Home</a></li>
<li class="nav-item"><a class="nav-link" href="portfolio.html">Portfolio</a></li>
<li class="nav-item"><a class="nav-link" href="contact.html">Kontak</a></li>
```
Penjelasan:

1. Saat kamu klik Home, akan membuka home.html:
<img width="1868" height="934" alt="Cuplikan layar 2025-10-30 233720" src="https://github.com/user-attachments/assets/bd4bf7ea-1abe-4bc1-a6f7-e9e75d4986fc" />

2. Klik Portfolio, menuju portfolio.html:
<img width="1874" height="895" alt="Cuplikan layar 2025-10-30 233739" src="https://github.com/user-attachments/assets/483516d0-6fe7-4ac2-abff-1ab571366440" />

4. Klik Kontak, menuju contact.html:
<img width="1872" height="877" alt="Cuplikan layar 2025-10-30 233758" src="https://github.com/user-attachments/assets/aa4251f0-da30-42da-8cea-2081c77f6837" />

Kemudian masukan file foto dan satukan dalam folder dan pastikan nama file dan huruf kapitalnya sama persis seperti di kode:
```html
<img src="Foto Saya.jpg" alt="Foto Saya" class="img-fluid rounded-circle shadow">
```
## Langkah-langkah Praktikum 5

Menentukan karakter, tampilan, dan styling halaman dan menyertakan Bootstrap dan JavaScript:
```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Praktikum 5 - JavaScript & Bootstrap Form</title>

  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">

  <style>
    body {
      background-color: #f8f9fa;
      font-family: 'Segoe UI', sans-serif;
    }
    footer {
      background-color: #0d6efd;
      color: white;
    }
  </style>
</head>
```
JavaScript digunakan untuk menambahkan logika dan interaksi. Semua fungsi dideklarasikan di awal agar bisa dipanggil di bawahnya:
```html
<script>
  function pesan() {
    alert("Memanggil JavaScript lewat body onload");
  }

  function validasiForm() {
    let bil = document.getElementById("bilangan").value;
    let hasil = document.getElementById("hasil");

    if (bil === "") {
      alert("Kolom bilangan tidak boleh kosong!");
      return false;
    }

    if (isNaN(bil)) {
      alert("Yang dimasukkan harus berupa angka!");
      return false;
    }

    if (bil % 2 === 0)
      hasil.value = "Bilangan Genap";
    else
      hasil.value = "Bilangan Ganjil";
  }

  function ubahWarnaLB(warna) {
    document.body.style.backgroundColor = warna;
  }

  function ubahWarnaLD(warna) {
    document.body.style.color = warna;
  }

  function hitung(ele) {
    let total = document.getElementById("total").value;
    total = total ? parseInt(total) : 0;
    let harga = parseInt(ele.value);

    if (ele.checked)
      total += harga;
    else
      total -= harga;

    document.getElementById("total").value = total;
  }
</script>
```

Berisi seluruh tampilan halaman yang muncul di browser:
``html
<body onload="pesan()" class="py-5">
```

Validasi Bilangan Genap/Ganjil:
```html
<div class="card shadow-sm mb-5">
  <div class="card-body">
    <h4 class="text-primary mb-4 text-center">Cek Bilangan Genap / Ganjil</h4>

    <form onsubmit="validasiForm(); return false;">
      <div class="mb-3">
        <label for="bilangan" class="form-label">Masukkan Bilangan</label>
        <input type="text" id="bilangan" class="form-control" placeholder="Contoh: 12">
      </div>

      <div class="mb-3">
        <label for="hasil" class="form-label">Hasil</label>
        <input type="text" id="hasil" class="form-control" readonly placeholder="Hasil akan muncul di sini">
      </div>

      <div class="d-grid">
        <button type="submit" class="btn btn-primary">Cek Bilangan</button>
      </div>
    </form>
  </div>
</div>
```

Ubah Warna Halaman:
```html
<div class="card shadow-sm mb-5">
  <div class="card-body text-center">
    <h4 class="text-primary mb-4">Ubah Warna Halaman</h4>

    <div class="mb-3">
      <h5 class="fw-semibold">Latar Belakang</h5>
      <div class="d-flex justify-content-center gap-2 flex-wrap">
        <button type="button" class="btn btn-success" onclick="ubahWarnaLB('lightgreen')">Hijau</button>
        <button type="button" class="btn btn-light border" onclick="ubahWarnaLB('white')">Putih</button>
        <button type="button" class="btn btn-warning" onclick="ubahWarnaLB('khaki')">Krem</button>
        <button type="button" class="btn btn-secondary" onclick="ubahWarnaLB('#e0e0e0')">Abu-Abu</button>
      </div>
    </div>

    <div class="mb-3 mt-4">
      <h5 class="fw-semibold">Warna Teks</h5>
      <div class="d-flex justify-content-center gap-2 flex-wrap">
        <button type="button" class="btn btn-primary" onclick="ubahWarnaLD('blue')">Biru</button>
        <button type="button" class="btn btn-danger" onclick="ubahWarnaLD('red')">Merah</button>
        <button type="button" class="btn btn-dark" onclick="ubahWarnaLD('black')">Hitam</button>
        <button type="button" class="btn btn-warning" onclick="ubahWarnaLD('orange')">Oranye</button>
      </div>
    </div>
  </div>
</div>
```

Daftar Menu Makanan:
```html
<div class="card shadow-sm">
  <div class="card-body">
    <h4 class="text-primary mb-4 text-center">Daftar Menu Makanan</h4>

    <form>
      <div class="form-check">
        <input class="form-check-input" type="checkbox" value="5000" id="menu1" onclick="hitung(this)">
        <label class="form-check-label" for="menu1">Ayam Goreng - Rp 5.000</label>
      </div>

      <div class="form-check">
        <input class="form-check-input" type="checkbox" value="500" id="menu2" onclick="hitung(this)">
        <label class="form-check-label" for="menu2">Tempe Goreng - Rp 500</label>
      </div>

      <div class="form-check">
        <input class="form-check-input" type="checkbox" value="2500" id="menu3" onclick="hitung(this)">
        <label class="form-check-label" for="menu3">Telur Dadar - Rp 2.500</label>
      </div>

      <div class="mt-4">
        <label for="total" class="form-label fw-bold">Total Bayar (Rp)</label>
        <input id="total" type="text" class="form-control" value="0" readonly>
      </div>
    </form>
  </div>
</div>
```

Footer dan Script Bootstrap:
```html
<footer class="text-center py-3 mt-5">
  <p class="mb-0">Refactor Praktikum 5 © 2025 - Muhamad Rizki Wahyu | Universitas Pelita Bangsa</p>
</footer>

<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
```
