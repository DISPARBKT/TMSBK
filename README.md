Berikut adalah file `README.md` yang sesuai berdasarkan informasi yang diberikan:

```markdown
# TMSBK - Alpaka 🦙

## 📌 Deskripsi
Repositori ini berisi kode sumber untuk halaman web yang menampilkan informasi tentang berbagai hewan, khususnya Alpaka. Proyek ini mencakup **HTML, CSS, dan JavaScript** untuk memberikan tampilan interaktif dengan fitur seperti **tema gelap/terang**, **pemilihan bahasa**, serta **navigasi responsif**.

---

## 📂 Struktur Proyek

```
📁 TMSBK-Alpaka
│── 📁 assets
│   ├── 📁 css
│   │   └── styles.css  # File CSS utama
│   ├── 📁 js
│   │   └── main.js     # File JavaScript utama
│── 📝 Alpaka.html      # Halaman utama tentang Alpaka
│── 📝 README.md        # Dokumentasi proyek
```

---

## 🌍 Teknologi yang Digunakan
- **HTML5** → Struktur halaman
- **CSS3** → Gaya tampilan dan responsivitas
- **JavaScript (ES6)** → Interaksi dan fitur dinamis

---

## 📜 Dokumentasi Kode

### 1️⃣ File **HTML** (`Alpaka.html`)
Dokumen HTML berisi struktur utama halaman, termasuk **navigasi**, **konten utama**, dan **footer**.

#### 🔹 Struktur Umum
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="assets/css/styles.css">
    <title>TMSBK - Alpaka</title>
</head>
<body>
    <!-- Konten halaman -->
</body>
</html>
```
📌 **Penjelasan:**
- `<!DOCTYPE html>` → Menentukan HTML5 sebagai versi dokumen.
- `<head>` → Berisi metadata dan link ke CSS.
- `<body>` → Tempat untuk seluruh konten halaman.

#### 🔹 Header (Navigasi)
```html
<header class="l-header" id="header">
    <nav class="nav bd-container">
        <a href="index.html" class="nav__logo">TMSBK</a>
        <div class="nav__menu" id="nav-menu">
            <ul class="nav__list">
                <li class="nav__item"><a href="#home" class="nav__link active-link">Home</a></li>
                <li class="nav__item"><a href="#about" class="nav__link">About</a></li>
                <li class="nav__item"><a href="#contact" class="nav__link">Contact</a></li>
                <li class="nav__item">
                    <select id="language-switch" class="nav__link">
                        <option value="id">🇮🇩</option>
                        <option value="en">🇬🇧</option>
                    </select>
                </li>
                <li><i class='bx bx-moon change-theme' id="theme-button"></i></li>
            </ul>
        </div>
        <div class="nav__toggle" id="nav-toggle">
            <i class='bx bx-menu'></i>
        </div>
    </nav>
</header>
```
📌 **Fitur:**
- **Navigasi** dengan tautan ke berbagai bagian halaman.
- **Pemilihan bahasa** (ID & EN).
- **Mode gelap/terang** dengan ikon `bx-moon`.

#### 🔹 Konten Utama
**Home Section**
```html
<section class="home" id="home">
    <div class="home__container bd-container bd-grid">
        <div class="home__data">
            <h1 class="home__title">Alpaka</h1>
            <a href="#about" class="button">Lihat Selengkapnya</a>
        </div>
        <img src="https://i.pinimg.com/736x/22/3e/df/223edf2daf39210b24f97c2f8257a1cd.jpg" alt="Alpaka" class="home__img">
    </div>
</section>
```
📌 **Fitur:**
- **Judul utama** dengan nama hewan.
- **Tombol navigasi** ke bagian "Tentang".
- **Gambar Alpaka** untuk visualisasi.

#### 🔹 Footer
```html
<footer class="footer section bd-container">
    <p class="footer__copy">Hak Cipta &copy; 2024 TMSBK</p>
</footer>
```
📌 **Fitur:**
- Informasi hak cipta.

---

### 2️⃣ File **CSS** (`styles.css`)
Menentukan gaya tampilan halaman.

#### 🔹 Variabel CSS (Global)
```css
:root {
    --first-color: #069C54;
    --text-color: #707070;
    --body-font: 'Poppins', sans-serif;
    --h1-font-size: 1.5rem;
}
```
📌 **Kegunaan:**
- Mengatur **warna utama**, **font**, dan **ukuran teks**.

#### 🔹 Gaya Dasar
```css
body {
    font-family: var(--body-font);
    font-size: var(--normal-font-size);
    background-color: #FBFEFD;
    color: var(--text-color);
}
```
📌 **Fitur:** Menentukan **font**, **warna latar**, dan **warna teks**.

#### 🔹 Responsivitas
```css
@media screen and (min-width: 768px) {
    body {
        margin: 0;
    }
    .nav {
        height: calc(var(--header-height) + 1.5rem);
    }
}
```
📌 **Fitur:** Mengatur tampilan pada **layar di atas 768px**.

---

### 3️⃣ File **JavaScript** (`main.js`)
Menambahkan interaktivitas pada halaman.

#### 🔹 Menampilkan Menu Navigasi (Mobile)
```js
const showMenu = (toggleId, navId) => {
    const toggle = document.getElementById(toggleId),
          nav = document.getElementById(navId);

    if (toggle && nav) {
        toggle.addEventListener('click', () => {
            nav.classList.toggle('show-menu');
        });
    }
};
showMenu('nav-toggle', 'nav-menu');
```
📌 **Fitur:** Menampilkan/menyembunyikan **menu navigasi** pada perangkat mobile.

#### 🔹 Mode Gelap/Terang
```js
const themeButton = document.getElementById('theme-button');
const darkTheme = 'dark-theme';

themeButton.addEventListener('click', () => {
    document.body.classList.toggle(darkTheme);
});
```
📌 **Fitur:** **Mengubah tema** halaman dengan sekali klik.

#### 🔹 Mengubah Bahasa
```js
const languageSwitcher = document.getElementById('language-switch');

function changeLanguage(lang) {
    const elements = document.querySelectorAll('[data-lang-id], [data-lang-en]');
    elements.forEach(element => {
        element.textContent = lang === 'id' ? element.getAttribute('data-lang-id') : element.getAttribute('data-lang-en');
    });
}

languageSwitcher.addEventListener('change', (e) => {
    changeLanguage(e.target.value);
});
```
📌 **Fitur:** **Mengubah teks** berdasarkan bahasa yang dipilih.

---

## 🎨 Kustomisasi
1. **Menambahkan Hewan Baru**: 
   - Duplikat `Alpaka.html`, ganti nama & sesuaikan konten.
2. **Mengubah Gaya**:
   - Edit warna & font di `styles.css`.
3. **Menambahkan Fitur Interaktif**:
   - Tambahkan fungsi baru di `main.js`.

---

## 📢 Kontribusi
Jika ingin berkontribusi, silakan buat **Pull Request** atau laporkan masalah di **Issues**.

---

## 🏆 Kesimpulan
Proyek ini menyediakan **struktur yang modular**, **tampilan interaktif**, dan **dukungan multi-bahasa** untuk halaman informasi hewan. Dengan memahami dokumentasi ini, pengembang dapat dengan mudah menyesuaikan atau mengembangkan proyek lebih lanjut.

---

🔗 **Dibuat dengan ❤️ oleh TMSBK Team**  
