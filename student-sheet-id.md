# Praktikum Web101: Halaman Profil Kampus (Dasar HTML & CSS)

**Durasi:** 120 menit  **Mode:** Individu, sesuai kecepatan masing-masing

Pada praktikum ini kamu akan membuat halaman profil untuk kampus kita, **STT Cipasung**. Setiap bagian saling berkaitan, jadi kerjakan secara berurutan. Setiap bagian mencantumkan perkiraan waktu pengerjaannya. Jika kamu buntu, lanjutkan dulu ke bagian berikutnya lalu kembali lagi nanti.

**Referensi yang boleh digunakan:** catatan kuliah, [MDN Web Docs](https://developer.mozilla.org/id/), DevTools browser, dan [W3C Validator](https://validator.w3.org/#validate_by_input).

---

## Bagian 0: Persiapan (5 menit)

Buat struktur folder berikut:

```
lab-html-css_<NIM>_<Nama>/
├── answers.md
├── profile.html
├── style.css
├── selector-golf.html
├── selector-golf.css
├── debug.html
├── review-fixed.html
└── checkpoints/
```

Salin template berikut ke `answers.md`. Isi sambil mengerjakan.

```markdown
# Jawaban Praktikum: <Nama> (<NIM>)

## Bagian 1: Pemanasan
1.
2.
3.
4.
5.

## Bagian 3: Prediksi Selector Golf
P1.
P2.
Setelah diuji (hasil sebenarnya):

## Bagian 4: Box model
Q1 (content-box):
Q2 (border-box):
Pengecekan DevTools:

## Bagian 5: Tabel debug
| # | Baris | Bug | Perbaikan | Cara menemukannya |
|---|-------|-----|-----------|-------------------|

## Bagian 6: Tabel Code Review
| # | Baris | Masalah | Mengapa penting | Perbaikan saya |
|---|-------|---------|-----------------|----------------|

Refleksi:
1.
2.
3.

## Bagian 7: Exit ticket
1.
2.
3.
```

---

## Bagian 1: Pemanasan (10 menit)

Jawab di `answers.md` **tanpa menjalankan kode apa pun**. Bagian ini dinilai dari usaha, bukan dari benar atau salahnya.

1. Pada aturan `nav a.active:hover { color: red; }`, tunjukkan mana **selector**, **deklarasi**, **property**, **value**, dan **pseudo-class**-nya.
2. Dari elemen berikut, mana yang secara default bersifat **block** dan mana yang **inline**? `span`, `p`, `a`, `li`, `h2`, `strong`
3. Dengan HTML di bawah dan aturan `.box p { color: green; }`, paragraf mana yang menjadi hijau? (A, B, C, atau D?)
   ```html
   <div class="box">
     <p>A</p>
     <section><p>B</p></section>
   </div>
   <p class="box">C</p>
   <p>D</p>
   ```
4. Sebuah `<h1 id="title" class="heading">` dikenai tiga aturan: `h1 { color: blue; }`, `.heading { color: green; }`, dan `#title { color: red; }`. Apa warnanya? Mengapa?
5. Apa yang salah pada HTML ini? `<p>Hello <strong>world</p></strong>`

---

## Bagian 2: Struktur HTML (25 menit)

Buat `profile.html` **hanya dengan HTML** (belum pakai CSS). Gunakan konten di bawah ini.

### Konten

> **STT Cipasung**
> *Sekolah Tinggi Teknologi Cipasung, Tasikmalaya*
>
> **Tentang Kami**
> STT Cipasung adalah sekolah tinggi teknologi di Tasikmalaya, Jawa Barat, yang didirikan pada tahun 1997 di bawah Yayasan Pondok Pesantren Cipasung.
> Kampus ini menyelenggarakan program sarjana di bidang teknik dan komputasi.
>
> **Program Studi**
> | Program Studi | Jenjang | Masa Studi | Fokus |
> |---|---|---|---|
> | Teknik Industri | Sarjana (S1) | 4 tahun | Sistem produksi, mutu, dan ergonomi |
> | Informatika | Sarjana (S1) | 4 tahun | Perangkat lunak, jaringan, dan data |
>
> **Fasilitas**
> Laboratorium komputer · Laboratorium teknik industri · Perpustakaan · Masjid · Sekretariat kegiatan mahasiswa
> Gambar: `https://placehold.co/600x300?text=STT+Cipasung` (tulis sendiri deskripsinya di `alt`)
>
> **Agenda Mendatang**
> *Informatics Coding Day*: 14 November 2026. Lomba pemrograman satu hari yang terbuka untuk semua mahasiswa.
> *Open House*: 5 Desember 2026. Kunjungi laboratorium kami dan bertemu dengan para dosen.
>
> **Kontak**
> Jalan Raya Cisinga KM 1, Cilampunghilir, Padakembang, Tasikmalaya, Jawa Barat 46466
> Email: info@sttcipasung.ac.id · Telepon: (0265) 2550424
> Formulir kontak: Nama, Email, Pesan, tombol Kirim
>
> © 2026 STT Cipasung

### Daftar periksa

- [ ] `<!DOCTYPE html>`, `<html lang="id">`, dan `<head>` yang berisi `<meta charset>`, `<meta>` viewport, dan `<title>`
- [ ] `<header>` dengan nama kampus sebagai **satu-satunya** `<h1>`, ditambah baris subjudul
- [ ] `<nav>` berisi `<ul>` dengan link yang menuju ke setiap section (`#about`, `#programs`, `#facilities`, `#events`, `#contact`)
- [ ] `<main>` dengan 5 `<section>`, masing-masing memiliki `id` dan `<h2>`
- [ ] Program studi ditampilkan sebagai `<table>` dengan `<thead>`/`<tbody>` dan header `<th>`
- [ ] Fasilitas ditampilkan sebagai `<ul>`, ditambah `<img>` dengan `alt` yang bermakna
- [ ] Setiap agenda berupa `<article>` dengan `<h3>`, `<time datetime="YYYY-MM-DD">`, dan `<p>`
- [ ] Info kontak di dalam `<address>`, dengan email sebagai link `mailto:`
- [ ] `<form>` di mana **setiap** input memiliki `<label for="...">`. Gunakan `type="email"` untuk kolom email dan `<textarea>` untuk pesan.
- [ ] `<footer>` dengan baris hak cipta

### Batasan

- ❌ **Tidak boleh ada `<div>` sama sekali.** Gunakan tag semantik.
- ❌ Tidak boleh ada inline `style=""`.
- ❌ Jangan melompati level heading (misalnya dari `h2` langsung ke `h4`).

### Validasi

Tempel kodemu ke [W3C Validator](https://validator.w3.org/#validate_by_input) dan perbaiki sampai **0 error**. Simpan screenshot hasilnya sebagai `checkpoints/validator.png`.

📌 **Checkpoint:** salin `profile.html` ke `checkpoints/part2-profile.html`.

---

## Bagian 3: Selector Golf (20 menit)

Buat `selector-golf.html` dengan kode di bawah. **Jangan ubah HTML-nya.** Tulis semua CSS di `selector-golf.css`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Selector Golf</title>
  <link rel="stylesheet" href="selector-golf.css">
</head>
<body>
  <header id="top">
    <h1>Student Clubs</h1>
    <p class="tagline">Find your people.</p>
  </header>
  <nav>
    <a href="#tech">Tech</a>
    <a href="#arts" class="active">Arts</a>
    <a href="#sports">Sports</a>
    <a href="https://example.com" target="_blank">External</a>
  </nav>
  <main>
    <section id="tech" class="club">
      <h2>Coding Club</h2>
      <p>Weekly hack nights.</p>
      <p class="note">Bring your own laptop.</p>
    </section>
    <section id="arts" class="club featured">
      <h2>Photography Club</h2>
      <p>Photo walks every Saturday.</p>
      <ul>
        <li>Beginner friendly</li>
        <li class="note">Camera optional</li>
        <li>Monthly exhibition</li>
      </ul>
    </section>
    <section id="sports" class="club">
      <h2>Futsal Club</h2>
      <p>Matches every Friday.</p>
    </section>
  </main>
  <footer>
    <p>&copy; 2026 Student Affairs</p>
  </footer>
</body>
</html>
```

### Prediksi dulu ✍️

Tulis jawabanmu di `answers.md` **sebelum** menulis CSS apa pun.

- **P1.** Misalkan sebuah stylesheet hanya berisi tiga aturan ini: `p { color: blue; }`, `section p { color: green; }`, dan `.note { color: orange; }`. Apa warna masing-masing teks berikut?
  (a) "Weekly hack nights."  (b) "Bring your own laptop."  (c) "© 2026 Student Affairs"
- **P2.** Urutkan selector berikut dari specificity **tertinggi ke terendah**: `p`, `#tech p`, `.club p`, `main section p`

Lalu uji P1 di **file terpisah** (misalnya `test.css` yang di-link sementara) agar CSS tantanganmu tidak memengaruhi hasilnya. Tuliskan hasil sebenarnya. **Prediksi yang salah tidak mengurangi nilai** selama kamu mencatat hasil sebenarnya dan menjelaskannya.

### Tantangan

Beri nomor setiap aturan dengan komentar, misalnya `/* 1 */`. Tulis satu aturan per tantangan (selector yang dikelompokkan dihitung sebagai satu aturan).

1. Semua elemen `h2` berwarna **navy**.
2. Setiap elemen dengan class `note` memiliki **background kuning**.
3. **Hanya** klub featured yang memiliki border `2px solid`.
4. **Hanya** note yang berupa *paragraf* (bukan item list) yang *miring* (italic).
5. Paragraf **di dalam section** memiliki `line-height: 1.6`. Paragraf di header dan footer tidak boleh berubah.
6. `h1` **dan** tagline menggunakan `Georgia, serif`, ditulis dalam **satu** aturan.
7. Link di dalam `nav` **tidak bergaris bawah**…
8. …tetapi **garis bawahnya muncul kembali saat di-hover**.
9. Link eksternal (yang membuka tab baru) berwarna **merah**. Tidak boleh menambah class. *(Petunjuk: attribute selector)*
10. Item list **pertama** dicetak **tebal**. *(Petunjuk: pseudo-class)*
11. Header memiliki **background abu-abu muda**. Gunakan `id`-nya.

📌 **Checkpoint:** salin `selector-golf.css` ke `checkpoints/part3-selector-golf.css`.

---

## Bagian 4: Styling Profil (25 menit)

Buat `style.css` dan hubungkan ke `profile.html`. Kamu **boleh** menambahkan atribut `class` ke HTML, tetapi tetap tidak boleh ada `<div>` dan inline style.

### Ketentuan

- [ ] **Halaman:** font sans-serif, lebar maksimum `960px`, posisi di tengah dengan `margin: 0 auto`, dan `line-height` yang nyaman dibaca
- [ ] **Header:** warna background, teks berwarna terang, dan padding
- [ ] **Nav:** list disusun horizontal dengan **flexbox** (`display: flex; gap: ...`), tanpa bullet, dan link berubah saat `:hover`
- [ ] **Section sebagai kartu:** background putih, `padding: 16px`, border `1px`, `border-radius: 8px`, dan `margin-bottom: 24px`
- [ ] **Tabel:** `border-collapse: collapse`, border pada sel, padding di dalam sel, dan warna background pada `th`
- [ ] **Gambar:** `max-width: 100%` agar tidak pernah melebihi lebar wadahnya
- [ ] **Formulir:** label berada di barisnya sendiri (`display: block`) dan input/textarea selebar penuh
- [ ] **Footer:** rata tengah, ukuran teks lebih kecil

### Variasi selector

Gunakan **minimal satu** dari setiap jenis selector berikut, dan tandai masing-masing dengan komentar, misalnya `/* class selector */`:
type · class · id · descendant · grouping · pseudo-class

❌ Tidak boleh menggunakan `!important`.

### Pertanyaan box model (answers.md)

Sebuah `.card` memiliki `width: 300px; padding: 16px; border: 1px solid; margin: 24px;`

- **Q1.** Dengan `box-sizing: content-box` (default), berapa **lebar yang terlihat** dari kartu tersebut (dari tepi border ke tepi border)? Tunjukkan perhitungannya.
- **Q2.** Apa yang berubah jika ditambahkan `box-sizing: border-box`?
- **Pengecekan DevTools:** Inspect salah satu section kartu milikmu, buka panel **Computed → box model**, lalu catat nilai content, padding, border, dan margin yang terlihat.

📌 **Checkpoint:** salin `profile.html` dan `style.css` ke `checkpoints/part4-profile.html` dan `checkpoints/part4-style.css`.

---

## Bagian 5: Debugging (10 menit)

Buat `debug.html` dengan kode di bawah. Kode ini memiliki **9 bug** (HTML dan CSS). Temukan dan perbaiki, lalu isi tabel debug di `answers.md`. Untuk kolom "Cara menemukannya", tulis misalnya *DevTools menampilkan property yang dicoret*, *validator*, atau *membaca kode*.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Campus News</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      colour: #333;
    }
    header {
      background: #dbe7f3
      padding: 20px;
    }
    .Card {
      border: 1px solid #ccc;
      padding: 16px;
    }
    #news-list {
      font-size: 18 px;
    }
    footer {
      text-align: centre;
    }
  </style>
</head>
<body>
  <header>
    <h1>Campus News</h2>
    <nav>
      <a href="index.html">Home</a>
      <a href="about.html>About</a>
    </nav>
  </header>
  <main>
    <section class="card">
      <img src="https://placehold.co/600x200?text=News">
      <ul id="newsList">
        <li>New library books have arrived</li>
        <li>Coding Day registration is open</li>
      </ul>
    </section>
  </main>
  <footer>
    <p>&copy; 2026 STT Cipasung</p>
  </footer>
</body>
</html>
```

---

## Bagian 6: Code Review (20 menit)

Seorang rekan satu tim menulis halaman kampus di bawah ini. Di browser halamannya **terlihat baik-baik saja**, tetapi melanggar banyak aturan yang sudah kamu latih hari ini. Review kode ini seperti seorang developer senior.

```html
<html>
<head>
<title>Campus</title>
<style>
.header { background-color: #003366; color: white; padding: 20px; width: 1200px; }
.nav a { color: #cccccc !important; margin-right: 10px; }
.content { font-size: 14px; color: #bbbbbb; }
.sidebar { float: right; width: 300px; }
.title { font-size: 32px; }
</style>
</head>
<body>
<div class="header">
  <div class="title"><b>STT Cipasung</b></div>
  <div class="nav">
    <a href="#">Home</a> | <a href="#">Programs</a> | <a href="#">Contact</a>
  </div>
</div>
<div class="content">
  <div style="font-size: 24px; font-weight: bold;">About Us</div>
  <br><br>
  <div>STT Cipasung is a technology college in Tasikmalaya.</div>
  <br>
  <img src="https://placehold.co/600x300?text=STT+Cipasung">
  <br><br>
  <div style="font-size: 24px; font-weight: bold;">Contact Us</div>
  <input type="text" placeholder="Name"><br>
  <input type="text" placeholder="Email"><br>
  <button onclick="alert('Sent!')">Send</button>
</div>
<div class="footer">Copyright 2026</div>
</body>
</html>
```

### Tugas

1. **Temukan minimal 8 masalah** dan isi tabel Code Review di `answers.md`. Perhatikan struktur dokumen, semantik, heading, aksesibilitas, praktik CSS, kode yang tidak terpakai, layout, dan keterbacaan.
2. **Perbaiki:** tulis ulang halaman tersebut sebagai `review-fixed.html` (CSS di dalam blok `<style>` atau di file terpisah). Hasilnya harus lolos W3C Validator dengan 0 error.
3. **Refleksi** (masing-masing 2–3 kalimat):
   1. Masalah mana yang **paling sulit disadari** hanya dengan melihat halamannya di browser? Mengapa?
   2. Halaman aslinya "berfungsi". Mengapa masalah-masalah ini tetap penting?
   3. Satu kebiasaan apa yang akan kamu lakukan untuk memeriksa HTML/CSS (milikmu atau milik orang lain) sebelum dikumpulkan?

---

## Bagian 7: Exit Ticket & Pengumpulan (5 menit)

Jawab di `answers.md`:

1. Jelaskan anatomi sebuah aturan CSS dengan kata-katamu sendiri.
2. Selector atau konsep apa dari hari ini yang **masih membingungkan** bagimu?
3. Satu hal apa yang sekarang bisa kamu lakukan **tanpa perlu mencarinya**?

### Pengumpulan

Kompres foldermu menjadi `lab-html-css_<NIM>_<Nama>.zip` dan unggah ke LMS sebelum waktu habis.

---

## Penilaian (100 poin)

| Bagian | Poin | Yang dinilai |
|---|---|---|
| 1. Pemanasan | 5 | Semua dijawab (dinilai dari usaha) |
| 2. Struktur HTML | 20 | Daftar periksa terpenuhi, tanpa `<div>`, 0 error validator |
| 3. Selector Golf | 20 | 11 tantangan benar (14), prediksi dibuat + hasil dijelaskan (6) |
| 4. Styling | 20 | Ketentuan terpenuhi (12), 6 jenis selector ditandai (4), jawaban box model (4) |
| 5. Debugging | 10 | Bug diperbaiki dan dijelaskan (sekitar 1 poin per bug) |
| 6. Code Review | 20 | ≥ 8 masalah ditemukan (8), halaman perbaikan valid (7), refleksi (5) |
| 7. Exit ticket | 5 | Jawaban yang dipikirkan dengan baik |

> **Tips:** File checkpoint menunjukkan progres kerjamu. Pekerjaan yang belum selesai tetapi memiliki checkpoint dan catatan yang jujur akan dinilai lebih baik daripada file akhir yang "sempurna" tanpa proses di baliknya.
