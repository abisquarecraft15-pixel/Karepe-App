# Karepe-App
Sell Animal
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#173f35">
<title>Rimba Pet - Toko Hewan</title>

<style>
:root {
  --green:#173f35;
  --green2:#285c4c;
  --mint:#e8f1eb;
  --cream:#fbf8f1;
  --ink:#202923;
  --muted:#6c776f;
  --orange:#e69a55;
  --line:#e5e9e3;
}

* { box-sizing:border-box; }

body {
  margin:0;
  background:var(--cream);
  color:var(--ink);
  font-family:Arial,sans-serif;
}

button,input,select,textarea { font:inherit; }
button { cursor:pointer; }

.topbar {
  background:var(--green);
  color:white;
  text-align:center;
  padding:10px;
  font-size:13px;
}

.nav {
  display:flex;
  justify-content:space-between;
  align-items:center;
  padding:15px 5%;
  background:white;
  position:sticky;
  top:0;
  z-index:5;
  border-bottom:1px solid var(--line);
}

.brand {
  font-size:23px;
  font-weight:bold;
  color:var(--green);
}

.navlinks {
  display:flex;
  gap:20px;
}

.navlinks a {
  text-decoration:none;
  color:var(--ink);
}

.btn {
  border:0;
  border-radius:10px;
  padding:11px 15px;
  font-weight:bold;
}

.btn-dark {
  background:var(--green);
  color:white;
}

.btn-light {
  background:var(--mint);
  color:var(--green);
}

.btn-orange {
  background:var(--orange);
  color:#222;
}

.hero {
  max-width:1200px;
  margin:25px auto;
  padding:50px;
  border-radius:25px;
  background:linear-gradient(120deg,#173f35,#49775c);
  color:white;
  display:grid;
  grid-template-columns:1fr 1fr;
  align-items:center;
}

.hero h1 {
  font-size:45px;
}

.hero p {
  line-height:1.7;
}

.hero-art {
  font-size:140px;
  text-align:center;
}

.wrap {
  max-width:1200px;
  margin:auto;
  padding:20px;
}

.benefits {
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:15px;
  margin-bottom:45px;
}

.benefit {
  background:white;
  padding:20px;
  border-radius:15px;
}

.section-head {
  margin-bottom:20px;
}

.tools {
  display:flex;
  gap:10px;
  margin-bottom:20px;
  flex-wrap:wrap;
}

.field {
  padding:12px;
  border:1px solid var(--line);
  border-radius:10px;
  background:white;
}

.tools input {
  flex:1;
}

.products {
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:18px;
}

.product {
  background:white;
  border-radius:15px;
  overflow:hidden;
  border:1px solid var(--line);
}

.pet-photo {
  height:150px;
  display:grid;
  place-items:center;
  font-size:75px;
  background:var(--mint);
}

.product-info {
  padding:15px;
}

.product-info p {
  color:var(--muted);
  font-size:13px;
}

.product-bottom {
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:8px;
}

.price {
  color:var(--green);
  font-weight:bold;
}

.add {
  background:var(--green);
  color:white;
  border:0;
  border-radius:8px;
  padding:9px;
}

.care {
  margin:50px 0;
  padding:25px;
  background:#f0eee4;
  border-radius:18px;
}

.footer {
  background:var(--green);
  color:white;
  padding:30px;
  text-align:center;
}

.overlay {
  display:none;
  position:fixed;
  inset:0;
  background:#0009;
  z-index:10;
  justify-content:flex-end;
}

.overlay.show {
  display:flex;
}

.drawer {
  width:min(450px,100%);
  background:white;
  padding:20px;
  overflow:auto;
}

.drawer .field {
  width:100%;
  margin:7px 0;
}

.cart-row {
  display:flex;
  justify-content:space-between;
  padding:12px 0;
  border-bottom:1px solid var(--line);
}

.qty {
  display:flex;
  gap:8px;
  align-items:center;
}

.total {
  display:flex;
  justify-content:space-between;
  font-size:20px;
  font-weight:bold;
  margin:20px 0;
}

.admin {
  display:none;
  max-width:1200px;
  margin:25px auto;
  padding:20px;
}

.admin.show {
  display:block;
}

.stats {
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:12px;
}

.stat,.panel {
  background:white;
  border:1px solid var(--line);
  border-radius:14px;
  padding:17px;
  margin-bottom:15px;
}

.stat strong {
  display:block;
  color:var(--green);
  font-size:22px;
  margin-top:8px;
}

.admin-grid {
  display:grid;
  grid-template-columns:1fr 1fr;
  gap:15px;
}

.admin-form {
  display:grid;
  gap:10px;
}

.admin table {
  width:100%;
  border-collapse:collapse;
}

.admin th,.admin td {
  padding:10px;
  border-bottom:1px solid var(--line);
  text-align:left;
}

.mini-btn {
  border:0;
  background:var(--mint);
  color:var(--green);
  padding:7px;
  border-radius:7px;
}

.notice {
  font-size:12px;
  color:var(--muted);
}

.hidden {
  display:none!important;
}

@media(max-width:800px) {
  .products { grid-template-columns:repeat(2,1fr); }
  .stats { grid-template-columns:repeat(2,1fr); }
  .hero { margin:15px; padding:25px; }
  .navlinks { display:none; }
}

@media(max-width:500px) {
  .hero { grid-template-columns:1fr; }
  .hero h1 { font-size:32px; }
  .hero-art { font-size:90px; }
  .benefits,.admin-grid { grid-template-columns:1fr; }
  .products { gap:10px; }
  .pet-photo { height:110px; }
}
</style>
</head>

<body>

<div class="topbar">
🐾 Sahabat hewan kesayangan - Selamat datang di Rimba Pet
</div>

<header class="nav">
  <div class="brand">🐾 Rimba Pet</div>

  <nav class="navlinks">
    <a href="#beranda">Beranda</a>
    <a href="#produk">Katalog Hewan</a>
    <a href="#tentang">Tentang Kami</a>
  </nav>

  <div>
    <button class="btn btn-light" onclick="toggleAdmin()">Admin</button>
    <button class="btn btn-dark" onclick="openCart()">
      Keranjang <span id="cartCount">0</span>
    </button>
  </div>
</header>

<main id="store">

<section class="hero" id="beranda">
  <div>
    <p>🐾 TEMAN BARU, CERITA BARU</p>
    <h1>Temukan Sahabat Kecil Untuk Keluarga</h1>
    <p>
      Temukan hewan peliharaan kesayanganmu di Rimba Pet.
      Pilih hewan dengan informasi yang jelas dan perawatan yang baik.
    </p>
    <button class="btn btn-orange"
      onclick="document.getElementById('produk').scrollIntoView()">
      Jelajahi Hewan
    </button>
  </div>
  <div class="hero-art">🐶 🐱</div>
</section>

<div class="wrap">

<section class="benefits">
  <div class="benefit">🩺 Info kondisi transparan</div>
  <div class="benefit">🏡 Adopsi bertanggung jawab</div>
  <div class="benefit">💬 Konsultasi langsung</div>
</section>

<section id="produk">
  <div class="section-head">
    <h2>Katalog Hewan</h2>
    <p id="productCount"></p>
  </div>

  <div class="tools">
    <input class="field" id="search"
      placeholder="Cari hewan..."
      oninput="renderProducts()">

    <select class="field" id="category" onchange="renderProducts()">
      <option value="">Semua kategori</option>
      <option>Kucing</option>
      <option>Anjing</option>
      <option>Kelinci</option>
      <option>Burung</option>
      <option>Ikan</option>
      <option>Reptil</option>
    </select>
  </div>

  <div class="products" id="products"></div>
</section>

<section class="care" id="tentang">
  <h2>Hewan bukan sekadar produk.</h2>
  <p>
    Pastikan kamu siap memenuhi kebutuhan ruang, pakan,
    kesehatan, dan perhatian jangka panjang.
  </p>
  <button class="btn btn-dark" onclick="contactSeller()">
    Hubungi Penjual
  </button>
</section>

</div>
</main>

<!-- DASHBOARD ADMIN -->
<section class="admin" id="admin">

  <h2>Dashboard Rimba Pet</h2>
  <button class="btn btn-light" onclick="toggleAdmin()">
    Kembali ke Toko
  </button>

  <div class="stats">
    <div class="stat">
      Total pemasukan
      <strong id="revenue">Rp0</strong>
    </div>
    <div class="stat">
      Pesanan selesai
      <strong id="ordersCount">0</strong>
    </div>
    <div class="stat">
      Stok hewan
      <strong id="stockCount">0</strong>
    </div>
    <div class="stat">
      Jumlah produk
      <strong id="catalogCount">0</strong>
    </div>
  </div>

  <div class="admin-grid">

    <div class="panel">
      <h3>Tambah / Edit Hewan</h3>

      <form id="productForm" class="admin-form"
        onsubmit="saveProduct(event)">

        <input class="field" id="pName"
          placeholder="Nama hewan" required>

        <select class="field" id="pCategory">
          <option>Kucing</option>
          <option>Anjing</option>
          <option>Kelinci</option>
          <option>Burung</option>
          <option>Ikan</option>
          <option>Reptil</option>
        </select>

        <input class="field" id="pPrice"
          type="number" placeholder="Harga" required>

        <input class="field" id="pAge"
          placeholder="Usia hewan">

        <input class="field" id="pEmoji"
          placeholder="Emoji" value="🐾">

        <input class="field" id="pStock"
          type="number" placeholder="Stok" required>

        <textarea class="field" id="pDesc"
          placeholder="Deskripsi hewan"></textarea>

        <input type="hidden" id="pId">

        <button class="btn btn-dark" type="submit">
          Simpan Produk
        </button>

        <button class="btn btn-light" type="button"
          onclick="resetProductForm()">
          Bersihkan Form
        </button>
      </form>
    </div>

    <div class="panel">
      <h3>Daftar Produk</h3>
      <div id="inventory"></div>
    </div>

  </div>

  <div class="panel">
    <h3>Riwayat Pesanan</h3>
    <div id="orderTable"></div>
  </div>

  <div class="panel">
    <h3>Penarikan Saldo</h3>
    <input class="field" id="bankName" placeholder="Nama Bank">
    <input class="field" id="bankOwner" placeholder="Nama Pemilik Rekening">
    <input class="field" id="bankNumber" placeholder="Nomor Rekening">
    <input class="field" id="withdrawAmount"
      type="number" placeholder="Nominal Penarikan">

    <button class="btn btn-dark" onclick="requestWithdrawal()">
      Ajukan Penarikan
    </button>

    <div id="withdrawals"></div>
  </div>

  <div class="panel">
    <h3>Pengaturan Desain Toko</h3>

    <input class="field" id="designBrand"
      placeholder="Nama toko">

    <label>Warna utama</label>
    <input class="field" id="designPrimary" type="color">

    <label>Warna aksen</label>
    <input class="field" id="designAccent" type="color">

    <input class="field" id="designHeadline"
      placeholder="Judul banner">

    <textarea class="field" id="designSubtitle"
      placeholder="Deskripsi banner"></textarea>

    <button class="btn btn-dark" onclick="saveDesign()">
      Terapkan Desain
    </button>

    <button class="btn btn-light" onclick="resetDesign()">
      Reset Desain
    </button>
  </div>

  <div class="panel">
    <h3>Ekspor Data</h3>
    <button class="btn btn-dark" onclick="exportData()">
      Download Data JSON
    </button>
  </div>

</section>

<footer class="footer">
  <h2>🐾 Rimba Pet</h2>
  <p>Temukan teman terbaikmu.</p>
  <p>© 2026 Rimba Pet</p>
</footer>

<!-- KERANJANG -->
<div class="overlay" id="cartOverlay">
  <aside class="drawer">
    <h2>Keranjang Belanja</h2>

    <button class="btn btn-light" onclick="closeCart()">Tutup</button>

    <div id="cartItems"></div>

    <div class="total">
      <span>Total</span>
      <span id="cartTotal">Rp0</span>
    </div>

    <h3>Data Pemesan</h3>

    <input class="field" id="buyerName"
      placeholder="Nama lengkap">

    <input class="field" id="buyerPhone"
      placeholder="Nomor WhatsApp">

    <textarea class="field" id="buyerNote"
      placeholder="Alamat / catatan"></textarea>

    <label>Metode Pembayaran</label>

    <select class="field" id="paymentMethod">
      <option>Transfer Bank</option>
      <option>QRIS</option>
      <option>E-Wallet</option>
      <option>COD</option>
    </select>

    <button class="btn btn-dark"
      style="width:100%;margin-top:10px"
      onclick="checkout()">
      Checkout WhatsApp
    </button>

  </aside>
</div>