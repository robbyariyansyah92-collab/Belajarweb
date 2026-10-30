<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GoFood Kantin SMK EXCELLENT 1</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arial, sans-serif;
}

body {
    background: #f5f5f5;
    color: #333;
}

header {
    background: #00aa5b;
    color: white;
    padding: 25px 7%;
}

header h1 {
    font-size: 30px;
}

header p {
    margin-top: 8px;
}

nav {
    background: white;
    padding: 15px 7%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 2px 8px #ddd;
    position: sticky;
    top: 0;
    z-index: 10;
}

nav h2 {
    color: #00aa5b;
}

nav a {
    text-decoration: none;
    color: #333;
    margin-left: 15px;
    font-weight: bold;
}

.hero {
    background: linear-gradient(120deg, #008c4b, #00cc70);
    color: white;
    padding: 55px 7%;
    text-align: center;
}

.hero h2 {
    font-size: 35px;
    margin-bottom: 15px;
}

.hero p {
    font-size: 17px;
}

.container {
    padding: 35px 7%;
}

.container h2 {
    margin-bottom: 25px;
}

.menu {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 22px;
}

.card {
    background: white;
    border-radius: 12px;
    overflow: hidden;
    box-shadow: 0 3px 10px #ddd;
    transition: 0.3s;
}

.card:hover {
    transform: translateY(-5px);
}

.card img {
    width: 100%;
    height: 160px;
    object-fit: cover;
}

.card-content {
    padding: 17px;
}

.card h3 {
    margin-bottom: 8px;
}

.price {
    color: #00aa5b;
    font-size: 18px;
    font-weight: bold;
    margin: 12px 0;
}

button {
    background: #00aa5b;
    color: white;
    border: none;
    padding: 11px 17px;
    border-radius: 7px;
    cursor: pointer;
    font-weight: bold;
}

button:hover {
    background: #008c4b;
}

.cart {
    background: white;
    padding: 25px;
    margin-top: 30px;
    border-radius: 12px;
    box-shadow: 0 3px 10px #ddd;
}

.cart-item {
    display: flex;
    justify-content: space-between;
    gap: 10px;
    padding: 12px 0;
    border-bottom: 1px solid #eee;
}

.cart-item button {
    padding: 5px 10px;
    background: #e53935;
}

.total {
    margin: 20px 0;
    font-size: 21px;
    font-weight: bold;
    color: #00aa5b;
}

input {
    width: 100%;
    padding: 13px;
    margin: 8px 0;
    border: 1px solid #ccc;
    border-radius: 7px;
}

footer {
    background: #222;
    color: white;
    padding: 30px;
    text-align: center;
    margin-top: 40px;
}

footer p {
    margin: 8px;
    color: #ccc;
}

@media(max-width:600px) {
    nav {
        flex-direction: column;
        gap: 12px;
    }

    nav a {
        margin: 5px;
    }

    .hero h2 {
        font-size: 25px;
    }
}
</style>
</head>

<body>

<header>
    <h1>🍔 GoFood Kantin Sekolah</h1>
    <p>SMK EXCELLENT 1 TANGERANG</p>
    <p>Website Project Kelas 12 TKJ E</p>
</header>

<nav>
    <h2>GoKantin</h2>
    <div>
        <a href="#home">Home</a>
        <a href="#menu">Menu</a>
        <a href="#keranjang">Keranjang 🛒</a>
    </div>
</nav>

<section class="hero" id="home">
    <h2>Selamat Datang di GoKantin!</h2>
    <p>Pesan makanan favoritmu dengan mudah dan praktis.</p>
    <p>Enak, Murah, dan Mengenyangkan!</p>
</section>

<section class="container" id="menu">
    <h2>🍟 Menu Makanan & Minuman</h2>

    <div class="menu" id="daftarMenu"></div>
</section>

<section class="container" id="keranjang">
    <div class="cart">
        <h2>🛒 Keranjang Belanja</h2>

        <div id="isiKeranjang">
            Keranjang masih kosong.
        </div>

        <div class="total" id="total">
            Total: Rp0
        </div>

        <h3>Data Pemesan</h3>
        <input type="text" id="nama" placeholder="Masukkan nama kamu">
        <input type="text" id="kelas" placeholder="Contoh: 12 TKJ E">

        <button onclick="checkout()">
            Pesan Sekarang
        </button>
    </div>
</section>

<footer>
    <h3>GoFood Kantin SMK EXCELLENT 1 TANGERANG</h3>
    <p>Dibuat oleh siswa kelas 12 TKJ E</p>
    <p>Project Website Toko Online Kantin Sekolah</p>
    <p>© 2026 GoKantin. All Rights Reserved.</p>
</footer>

<script>

const produk = [
    {
        nama: "Nasi Goreng",
        harga: 12000,
        gambar: "https://images.unsplash.com/photo-1603133872878-684f208fb84b?w=500"
    },
    {
        nama: "Mie Ayam",
        harga: 10000,
        gambar: "https://images.unsplash.com/photo-1569718212165-3a8278d5f624?w=500"
    },
    {
        nama: "Ayam Geprek",
        harga: 15000,
        gambar: "https://images.unsplash.com/photo-1626082927389-6cd097cdc6ec?w=500"
    },
    {
        nama: "Bakso",
        harga: 12000,
        gambar: "https://images.unsplash.com/photo-1563245372-f21724e3856d?w=500"
    },
    {
        nama: "Es Teh Manis",
        harga: 5000,
        gambar: "https://images.unsplash.com/photo-1556679343-c7306c1976bc?w=500"
    },
    {
        nama: "Jus Jeruk",
        harga: 8000,
        gambar: "https://images.unsplash.com/photo-1600271886742-f049cd451bba?w=500"
    },
    {   nama:"Nasi Uduk",
        harga:10000,
        gambar:"🍚"
    },
    {   nama: "Mie goreng isi 2 aceh",
        harga: 7000,
        gambar: "-"

    },
    {
        nama: "Mie goreng isi 2 Geprek",
        harga: 7000,
        gambar: "-"
    
    },
    {  
        nama: "Mie goreng isi 2 Rendang",
        harga: 7000,
        gambar: "-"
    },
    
];

let keranjang = [];

function rupiah(angka) {
    return "Rp" + angka.toLocaleString("id-ID");
}

function tampilkanMenu() {
    const daftar = document.getElementById("daftarMenu");

    produk.forEach((item, index) => {
        daftar.innerHTML += `
            <div class="card">
                <img src="${item.gambar}" alt="${item.nama}">
                <div class="card-content">
                    <h3>${item.nama}</h3>
                    <p>Makanan dan minuman kantin sekolah.</p>
                    <div class="price">${rupiah(item.harga)}</div>
                    <button onclick="tambahKeranjang(${index})">
                        + Tambah Keranjang
                    </button>
                </div>
            </div>
        `;
    });
}

function tambahKeranjang(index) {
    const item = produk[index];

    const ditemukan = keranjang.find(
        barang => barang.nama === item.nama
    );

    if (ditemukan) {
        ditemukan.jumlah++;
    } else {
        keranjang.push({
            nama: item.nama,
            harga: item.harga,
            jumlah: 1
        });
    }

    tampilkanKeranjang();
}

function hapusKeranjang(index) {
    keranjang.splice(index, 1);
    tampilkanKeranjang();
}

function tampilkanKeranjang() {
    const isi = document.getElementById("isiKeranjang");
    const totalElement = document.getElementById("total");

    isi.innerHTML = "";

    let total = 0;

    if (keranjang.length === 0) {
        isi.innerHTML = "Keranjang masih kosong.";
    }

    keranjang.forEach((item, index) => {
        total += item.harga * item.jumlah;

        isi.innerHTML += `
            <div class="cart-item">
                <span>
                    ${item.nama} x ${item.jumlah}
                    <br>
                    ${rupiah(item.harga * item.jumlah)}
                </span>
                <button onclick="hapusKeranjang(${index})">
                    Hapus
                </button>
            </div>
        `;
    });

    totalElement.innerHTML = "Total: " + rupiah(total);
}

function checkout() {
    const nama = document.getElementById("nama").value.trim();
    const kelas = document.getElementById("kelas").value.trim();

    if (nama === "" || kelas === "") {
        alert("Silakan isi nama dan kelas terlebih dahulu!");
        return;
    }

    if (keranjang.length === 0) {
        alert("Keranjang belanja masih kosong!");
        return;
    }

    let total = 0;

    let pesan = `Halo, saya ingin memesan makanan di GoKantin.\n\n`;
    pesan += `Nama: ${nama}\n`;
    pesan += `Kelas: ${kelas}\n\n`;
    pesan += `Pesanan:\n`;

    keranjang.forEach(item => {
        pesan += `- ${item.nama} x ${item.jumlah} = ${rupiah(item.harga * item.jumlah)}\n`;
        total += item.harga * item.jumlah;
    });

    pesan += `\nTotal pembayaran: ${rupiah(total)}`;

    // Ganti nomor berikut dengan nomor WhatsApp penjual.
    const nomorWhatsApp = "6281234567890";

    const url = "https://wa.me/" + nomorWhatsApp +
                "?text=" + encodeURIComponent(pesan);

    window.open(url, "_blank");
}

tampilkanMenu();

</script>

</body>
</html>
