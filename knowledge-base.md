# 💕 Wedding Invitation — Valentine Theme Template

> Template undangan pernikahan digital single-page HTML — Tema **Valentine Romantic**. Dominasi rose & blush pink dengan aksen merah hati. Hangat, penuh cinta, dan siap deploy.

---

## 📁 Project Structure

```
project-valentine/
├── index.html              # Main file — seluruh HTML, CSS, dan JS dalam satu file
├── firebase-config.js      # Konfigurasi Firebase (API keys)
├── music.mpeg              # Background music (looping) → ganti lagu romantis
├── .env                    # Environment variables (Firebase credentials)
├── .env.example            # Template .env untuk project baru
├── .gitignore              # Ignore .vercel, .env, firebase-config.js
└── .vercel/                # Vercel deployment config
```

---

## 🎨 Tema Valentine & Palet Warna

| Variabel      | Hex       | Tailwind Class          | Penggunaan                          |
| ------------- | --------- | ----------------------- | ----------------------------------- |
| **Rose**      | `#4a1a24` | `text-rose` / `bg-rose` | Teks utama, tombol, countdown       |
| **Blush 50**  | `#fdf2f4` | `bg-blush-50`           | Card background (akad, resepsi)     |
| **Blush 100** | `#fbe8eb` | `bg-blush-100`          | Background halaman                  |
| **Blush 200** | `#f5d0d7` | `text-blush-200`        | Elemen dekoratif (rings/hearts SVG) |
| **Love 300**  | `#f28b9e` | `text-love-300`         | Aksen ringan (badge konfirmasi)     |
| **Love 400**  | `#e85d75` | `bg-love-400`           | Selection highlight, elemen SVG     |
| **Love 500**  | `#d43d56` | `text-love-500`         | Focus outline                       |
| **Love 600**  | `#b71c3b` | `text-love-600`         | Badge teks konfirmasi               |

**Deskripsi Tema**: _Romantic Valentine — dominasi blush pink lembut dengan aksen rose-red yang passionate. Gradasi dari soft ke bold menciptakan nuansa cinta yang hangat dan elegan._

### Tailwind Config (Tema Valentine)

```js
tailwind.config = {
  theme: {
    extend: {
      colors: {
        rose: "#4a1a24",
        blush: {
          50: "#fdf2f4",
          100: "#fbe8eb",
          200: "#f5d0d7",
        },
        love: {
          300: "#f28b9e",
          400: "#e85d75",
          500: "#d43d56",
          600: "#b71c3b",
        },
      },
      fontFamily: {
        script: ['"Great Vibes"', "cursive"],
        serif: ['"Playfair Display"', "serif"],
        sans: ['"Raleway"', "sans-serif"],
      },
    },
  },
};
```

---

## 🔤 Tipografi Valentine

| Kelas Tailwind | Font Family                  | Penggunaan                   |
| -------------- | ---------------------------- | ---------------------------- |
| `font-script`  | **Great Vibes** (cursive)    | Nama mempelai, judul section |
| `font-serif`   | **Playfair Display** (serif) | Kutipan ayat / quotes        |
| `font-sans`    | **Raleway** (sans-serif)     | Body text, label, tombol     |

**Font Sizes**: Nama mempelai `text-5xl`–`text-7xl`, judul section `text-3xl`, body `text-[13px]`–`text-sm`.

### Google Fonts Import (Valentine)

```html
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
<link
  href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Playfair+Display:ital,wght@0,400;0,500;1,400;1,500&family=Raleway:wght@200;300;400;500;600&display=swap"
  rel="stylesheet"
/>
```

### CSS Overrides (Valentine)

```css
html {
  scroll-behavior: smooth;
  overflow-x: hidden;
}
body {
  background-color: #fbe8eb;
  font-family: "Raleway", sans-serif;
  overflow-x: hidden;
  cursor: default;
}
.eyebrow {
  letter-spacing: 0.35em;
}
.card-shadow {
  box-shadow: 0 10px 35px -12px rgba(74, 26, 36, 0.18);
}
.fade-panel {
  transition:
    opacity 1s ease,
    visibility 1s ease;
}

@keyframes drift {
  0%,
  100% {
    transform: translateY(0px) rotate(0deg);
  }
  50% {
    transform: translateY(-8px) rotate(3deg);
  }
}
.drift {
  animation: drift 6s ease-in-out infinite;
}

@media (prefers-reduced-motion: reduce) {
  .drift {
    animation: none;
  }
  html {
    scroll-behavior: auto;
  }
  [data-aos] {
    opacity: 1 !important;
    transform: none !important;
  }
}

::selection {
  background: #e85d75;
  color: #fff;
}

input:focus,
textarea:focus,
select:focus,
button:focus-visible,
a:focus-visible {
  outline: 2px solid #d43d56;
  outline-offset: 2px;
}

.opening-item {
  opacity: 0;
}

[data-aos] {
  pointer-events: none;
}
[data-aos].aos-animate {
  pointer-events: auto;
}

.mouse-layer,
.mouse-layer-slow,
.mouse-layer-fast {
  will-change: transform;
  transition: none;
}

@media (max-width: 640px) {
  .mouse-layer,
  .mouse-layer-slow,
  .mouse-layer-fast {
    transform: none !important;
  }
}
```

---

## 💖 Assets Dekoratif Valentine

### SVG Defs — Heart Swirl (ganti `#ink-swirl`)

```html
<symbol id="heart-swirl" viewBox="0 0 400 400">
  <g opacity="0.55" filter="url(#soft-blur)">
    <!-- Swirl garis romantis -->
    <path
      d="M20 60 C 90 10, 160 40, 190 100 C 220 160, 180 210, 230 250 C 280 290, 340 260, 370 310"
      stroke="#e8a0b0"
      stroke-width="10"
      fill="none"
      stroke-linecap="round"
      opacity="0.35"
    />
    <path
      d="M0 120 C 70 90, 110 150, 90 200 C 70 250, 130 260, 160 310 C 190 360, 260 340, 300 390"
      stroke="#f0c4d0"
      stroke-width="16"
      fill="none"
      stroke-linecap="round"
      opacity="0.3"
    />
    <path
      d="M40 20 C 110 60, 90 120, 150 140 C 210 160, 220 90, 280 80"
      stroke="#d4879a"
      stroke-width="7"
      fill="none"
      stroke-linecap="round"
      opacity="0.35"
    />
    <ellipse cx="140" cy="90" rx="90" ry="40" fill="#e8a0b0" opacity="0.12" />
    <ellipse cx="260" cy="230" rx="110" ry="55" fill="#d4879a" opacity="0.14" />
  </g>
  <!-- Bintik-bintik love (seperti confetti) -->
  <g fill="#e85d75">
    <circle cx="30" cy="40" r="3" opacity="0.9" />
    <circle cx="55" cy="70" r="1.6" opacity="0.7" />
    <circle cx="20" cy="95" r="2.2" opacity="0.8" />
    <circle cx="70" cy="30" r="1.4" opacity="0.6" />
    <circle cx="95" cy="60" r="2.6" opacity="0.85" />
    <circle cx="130" cy="20" r="1.8" opacity="0.7" />
    <circle cx="45" cy="130" r="1.5" opacity="0.6" />
    <circle cx="10" cy="150" r="2.4" opacity="0.75" />
    <circle cx="80" cy="150" r="1.3" opacity="0.55" />
    <circle cx="150" cy="70" r="2" opacity="0.7" />
    <circle cx="180" cy="40" r="1.4" opacity="0.6" />
    <circle cx="60" cy="180" r="1.7" opacity="0.65" />
  </g>
</symbol>

<filter id="soft-blur" x="-20%" y="-20%" width="140%" height="140%">
  <feGaussianBlur stdDeviation="4" />
</filter>
```

### SVG Defs — Romantic Heart (ganti `#gold-heart`)

```html
<symbol id="love-heart" viewBox="0 0 64 64">
  <path
    d="M32 56 C 10 40, 2 26, 8 15 C 13 6, 26 5, 32 16 C 38 5, 51 6, 56 15 C 62 26, 54 40, 32 56 Z"
    fill="url(#heart-grad)"
  />
  <defs>
    <linearGradient
      id="heart-grad"
      x1="0"
      y1="0"
      x2="64"
      y2="64"
      gradientUnits="userSpaceOnUse"
    >
      <stop offset="0" stop-color="#f28b9e" />
      <stop offset="0.5" stop-color="#e85d75" />
      <stop offset="1" stop-color="#b71c3b" />
    </linearGradient>
  </defs>
</symbol>
```

### SVG Defs — Intertwined Hearts (ganti `#rings`)

```html
<symbol id="twined-hearts" viewBox="0 0 100 60">
  <!-- Hati kiri -->
  <path
    d="M27 34 C 12 26, 10 16, 14 11 C 17 7, 23 7, 27 12 C 31 7, 37 7, 40 11 C 44 16, 42 26, 27 34 Z"
    fill="none"
    stroke="#f5d0d7"
    stroke-width="2.5"
  />
  <!-- Hati kanan -->
  <path
    d="M73 34 C 58 26, 56 16, 60 11 C 63 7, 69 7, 73 12 C 77 7, 83 7, 86 11 C 90 16, 88 26, 73 34 Z"
    fill="none"
    stroke="#f5d0d7"
    stroke-width="2.5"
  />
  <!-- Titik love -->
  <circle cx="50" cy="18" r="2.5" fill="#f28b9e" />
</symbol>
```

### Floating Hearts Decoration (tambahan CSS)

```css
@keyframes float-heart {
  0%,
  100% {
    transform: translateY(0px) rotate(0deg);
    opacity: 0.7;
  }
  25% {
    transform: translateY(-15px) rotate(5deg);
    opacity: 1;
  }
  50% {
    transform: translateY(-8px) rotate(-3deg);
    opacity: 0.9;
  }
  75% {
    transform: translateY(-20px) rotate(2deg);
    opacity: 0.6;
  }
}
.float-heart {
  animation: float-heart 8s ease-in-out infinite;
}
```

---

## 📄 Template Sections

Struktur konten di dalam `<main id="main">`:

| #   | Section ID / Class | Konten                                                                       |
| --- | ------------------ | ---------------------------------------------------------------------------- |
| 1   | `#opening`         | **Opening Overlay** — Nama tamu (dari `?kepada=`), tombol "Buka Undangan 💌" |
| 2   | `#hero-section`    | **Save the Date** — Nama mempelai, tanggal, lokasi ringkas                   |
| 3   | _(inline)_         | **Countdown Timer** — Hari/Jam/Menit/Detik + tombol "Save the Date 💕"       |
| 4   | _(inline)_         | **Ayat / Quotes** — Qs. Ar-Rum : 21 atau quotes cinta romantis               |
| 5   | _(inline)_         | **Kedua Mempelai** — Profil pengantin pria & wanita + IG/WA                  |
| 6   | _(inline)_         | **Acara** — Akad Nikah & Resepsi (tanggal, jam)                              |
| 7   | _(inline)_         | **Lokasi** — Alamat lengkap + link Google Maps                               |
| 8   | _(inline)_         | **Live Streaming** — Link Instagram Live                                     |
| 9   | `#ucapan-form`     | **Ucapan & Doa** — Form (nama, ucapan, konfirmasi) + Firebase real-time      |
| 10  | _(inline)_         | **Amplop Digital** — Nomor rekening + tombol salin                           |
| 11  | _(inline)_         | **Protokol Kesehatan** — 4 ikon (opsional, bisa dihapus)                     |
| 12  | `<footer>`         | **Footer** — "Made with love ❤️" + social links                              |

---

## ⚙️ Fitur & Teknologi

### Frontend

| Teknologi         | Versi        | Penggunaan                                                     |
| ----------------- | ------------ | -------------------------------------------------------------- |
| **Tailwind CSS**  | CDN (latest) | Utility-first + custom theme config (Valentine palette)        |
| **GSAP**          | 3.12.5       | Animasi opening overlay, hero entrance, digit countdown, toast |
| **ScrollTrigger** | 3.12.5       | Plugin GSAP                                                    |
| **AOS**           | 2.3.1        | Scroll-triggered animations (`data-aos`)                       |
| **Google Fonts**  | —            | Great Vibes, Playfair Display, Raleway                         |

### Backend / Database

| Teknologi                      | Penggunaan                                    |
| ------------------------------ | --------------------------------------------- |
| **Firebase Realtime Database** | Menyimpan & menampilkan ucapan tamu real-time |
| **Firebase SDK**               | v10.12.2 (ES modules dari CDN)                |

### Interaksi & UX

- 🎵 **Background Music** — Lagu romantis autoplay saat membuka undangan
- 👤 **Personalized Guest Name** — `?kepada=Nama Tamu`
- ⏳ **Countdown Timer** — Real-time countdown dengan animasi digit bump
- 📅 **Save the Date** — Download `.ics` untuk kalender
- 📋 **Copy to Clipboard** — Salin nomor rekening satu klik
- 🖱️ **Mouse Parallax** — Elemen dekoratif mengikuti kursor
- 💖 **Floating Hearts** — Animasi hati melayang sebagai background tambahan
- ♿ **Reduced Motion** — Hormati `prefers-reduced-motion`
- 📱 **Responsive** — Breakpoint mobile `max-width: 640px`

---

## 📦 Cara Setup Project Baru — Tema Valentine

### 1. Salin struktur file

```
project-valentine/
├── index.html
├── firebase-config.js
├── music.mpeg
├── .env
├── .env.example
└── .gitignore
```

### 2. Konfigurasi Firebase

```env
# .env
FIREBASE_API_KEY=AIzaSyXXXXXXXXXXXXXXXXXXXXXXXXX
FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
FIREBASE_DATABASE_URL=https://your-project-default-rtdb.firebaseio.com
FIREBASE_PROJECT_ID=your-project-id
FIREBASE_STORAGE_BUCKET=your-project.appspot.com
FIREBASE_MESSAGING_SENDER_ID=1234567890
FIREBASE_APP_ID=1:1234567890:web:xxxxxxxxxxxxxx
```

### 3. Checklist Customization Valentine

| Komponen           | Yang Diganti                                         |
| ------------------ | ---------------------------------------------------- |
| Judul halaman      | `Nama Wanita & Nama Pria — Our Love Story`           |
| Nama tamu default  | "My Dearest," / "Dear Guest,"                        |
| Nama mempelai      | Nama panggilan romantis                              |
| Orang tua          | Nama orang tua (dummy)                               |
| Tanggal pernikahan | Tanggal spesial (misal: 14 Februari 2027 💘)         |
| Countdown target   | `new Date("2027-02-14T09:00:00+07:00")`              |
| Quotes             | Qs. Ar-Rum : 21 atau "Love is patient, love is kind" |
| Lokasi             | Alamat venue + Google Maps link                      |
| Live streaming     | Link Instagram / YouTube Live                        |
| Nomor rekening     | Data dummy                                           |
| Music              | Lagu romantis (ganti `music.mpeg`)                   |

### 4. Deploy

- **Vercel**: Drag & drop ke [vercel.com](https://vercel.com) (recommended)
- **Netlify**: Drag & drop ke [netlify.com](https://netlify.com)
- **GitHub Pages**: Push repo, enable Pages di Settings

---

## 🎨 Perbandingan Tema: Klasik vs Valentine

| Aspek           | Tema Klasik (Template 1)   | Tema Valentine (Template 2)  |
| --------------- | -------------------------- | ---------------------------- |
| **Warna Utama** | `#2b2a28` (ink/earth-tone) | `#4a1a24` (rose/merah hati)  |
| **Background**  | `#f2efe9` (stone/beige)    | `#fbe8eb` (blush pink)       |
| **Aksen**       | `#c9a24e` (gold metallic)  | `#e85d75` (love/coral)       |
| **Font Script** | Alex Brush                 | Great Vibes                  |
| **Font Serif**  | Cormorant Garamond         | Playfair Display             |
| **Font Sans**   | Poppins                    | Raleway                      |
| **Dekorasi**    | Ink swirls + gold dots     | Heart swirls + love confetti |
| **Simbol**      | Cincin emas + hati gold    | Hati berpadu + hati romantic |
| **Suasana**     | Hangat, intimate, timeless | Passionate, romantis, sweet  |

---

## 📊 Data Dummy — Tema Valentine

| Field            | Contoh Dummy                                              |
| ---------------- | --------------------------------------------------------- |
| Nama Pria        | Adrian Valentino Putra                                    |
| Nama Wanita      | Bianca Rose Alexandra, S.Ds.                              |
| Orang Tua Pria   | Bapak Hendra Gunawan & Ibu Linda Kusuma                   |
| Orang Tua Wanita | Bapak David Pramono & Ibu Cynthia Wijaya                  |
| Tanggal Akad     | Minggu, 14 Februari 2027 💘                               |
| Jam              | 10.00 WIB — selesai                                       |
| Lokasi           | The Rose Garden Ballroom, Jl. Melati Indah No. 7, Bandung |
| Maps Link        | `https://maps.app.goo.gl/contoh-valentine`                |
| Rekening BCA     | 5202142027 a.n. Adrian Valentino Putra                    |
| Rekening BNI     | 14022027 a.n. Bianca Rose Alexandra                       |
| Live Stream      | `https://instagram.com/lovebirds-live`                    |
| No. WA Pria      | 0812-1402-2027                                            |
| No. WA Wanita    | 0877-0202-1427                                            |

---

## 💡 Tips Tema Valentine

- **Foto Pre-wedding**: Gunakan tone warna pink/rose untuk overlay foto
- **Musik**: Pilih lagu akustik romantis atau instrumen piano
- **Opening text**: Gunakan kata-kata manis seperti _"A love story written in the stars..."_
- **Countdown label**: Tambahkan emoji hati di setiap label (Hari 💕, Jam 💕, dll.)
- **Button text**: "Buka Undangan 💌", "Save the Date 💘", "Kirim Ucapan 💝"
- **Toast message**: "Ucapan terkirim, thank you for the love 💖"
- **Protokol Kesehatan**: Bisa diganti dengan **"Our Love Notes"** — pesan singkat dari kedua mempelai

---

_Template Valentine ini diadaptasi dari struktur PROJECT-TEMPLATE.md dengan penyesuaian penuh pada palet, font, dan aset dekoratif. Semua data bersifat dummy._
