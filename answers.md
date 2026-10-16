# Jawaban Praktikum: Nama Mahasiswa (NIM)

## Bagian 1: Pemanasan
1. Pada aturan `nav a.active:hover { color: red; }`:
   - Selector: `nav a.active:hover`
   - Deklarasi: `{ color: red; }`
   - Property: `color`
   - Value: `red`
   - Pseudo-class: `:hover`
2. Elemen:
   - Block: `p`, `li`, `h2`
   - Inline: `span`, `a`, `strong`
3. Paragraf yang menjadi hijau: **A dan B** (karena selector `.box p` menyeleksi semua elemen `p` di dalam kelas `.box`).
4. Warnanya **Merah (red)**. Spesifisitas ID selector (`#title`) paling tinggi dibanding class selector (`.heading`) atau type selector (`h1`).
5. Tag bertumpukan (*overlapping*). Tag `<strong>` harus ditutup sebelum `<p>`. Perbaikan: `<p>Hello <strong>world</strong></p>`.

## Bagian 3: Prediksi Selector Golf
P1.
(a) "Weekly hack nights.": Hijau (`section p`)
(b) "Bring your own laptop.": Oranye (`.note`)
(c) "© 2026 Student Affairs": Biru (`p`)

P2. Urutan spesifisitas (tertinggi ke terendah):
1. `#tech p`
2. `.club p`
3. `main section p`
4. `p`

Setelah diuji (hasil sebenarnya):
Hasil uji sesuai 100% dengan prediksi. Selector yang menggunakan ID atau class lebih spesifik daripada tag HTML biasa.

## Bagian 4: Box model
Q1 (content-box):
Lebar tampak = width + padding (kiri & kanan) + border (kiri & kanan)
= 300px + 16px + 16px + 1px + 1px = **334px**.

Q2 (border-box):
Lebar tampak tetap **300px**. Area konten otomatis menyusut jadi 266px.

Pengecekan DevTools:
- Content: 300px x 120px
- Padding: 16px
- Border: 1px
- Margin: 24px

## Bagian 5: Tabel debug
| # | Baris | Bug | Perbaikan | Cara menemukannya |
|---|-------|-----|-----------|-------------------|
| 1 | 9 | Salah ketik properti `colour` | Ubah jadi `color` | DevTools coret properti |
| 2 | 12 | Kurang titik koma `;` setelah `#dbe7f3` | Tambahkan `;` di akhir baris | CSS baris bawahnya eror |
| 3 | 15 | Nama class `.Card` kapital | Ubah jadi `.card` | Beda dengan di HTML |
| 4 | 19 | ID `#news-list` tidak cocok | Ubah jadi `#newsList` | Beda dengan di HTML |
| 5 | 20 | Spasi pada `18 px` | Ubah jadi `18px` | Nilai properti tidak valid |
| 6 | 23 | Nilai `centre` tidak valid | Ubah jadi `center` | DevTools coret properti |
| 7 | 29 | Tag penutup `</h2>` salah | Ubah jadi `</h1>` | W3C Validator |
| 8 | 32 | Kurang tanda petik penutup `href="about.html` | Tambahkan `"` | W3C Validator |
| 9 | 37 | Gambar kurang atribut `alt` | Tambahkan `alt="Berita Kampus"` | W3C Validator warning |

## Bagian 6: Tabel Code Review
| # | Baris | Masalah | Mengapa penting | Perbaikan saya |
|---|-------|---------|-----------------|----------------|
| 1 | 1 | Kurang `<!DOCTYPE html>` dan `lang` | Browser masuk quirks mode & aksesibilitas terganggu | Tambahkan `<!DOCTYPE html>` dan `<html lang="id">` |
| 2 | 4 | Properti `width: 1200px` statis | Tampilan rusak di layar HP | Gunakan `max-width` responsive |
| 3 | 5 | Penggunaan `!important` | Menyulitkan kustomisasi CSS ke depan | Hapus `!important` |
| 4 | 12-32 | Penggunaan `<div>` berlebihan | Tidak semantik dan buruk untuk SEO | Ganti dengan tag semantik (`header`, `main`, dll) |
| 5 | 13 | Judul pakai `<div>` | Pembaca layar tidak mengenali judul | Ganti dengan tag `<h1>` |
| 6 | 20, 26 | Inline style `style="..."` | Kode berantakan dan susah dirawat | Pindahkan styling ke CSS |
| 7 | 21, 25 | Menggunakan `<br>` untuk jarak | Tag `<br>` bukan untuk tata letak | Gunakan `margin` CSS |
| 8 | 27-29 | Form tanpa `<form>` dan `<label>` | Tidak dapat diakses keyboard/screen reader | Bungkus `<form>` dan beri `<label>` |

Refleksi:
1. Masalah penggunaan `div` berlebihan dan hilangnya `<label>` paling susah disadari cuma dari tampilan browser karena visualnya kelihatan normal-normal aja.
2. Walaupun halaman "berfungsi", struktur yang jelek bikin web susah diakses oleh penyandang disabilitas dan susah masuk halaman pertama Google (SEO).
3. Kebiasaan yang bakal aku lakuin adalah selalu cek kode pakai W3C Validator sebelum tugas dikumpulin.

## Bagian 7: Exit ticket
1. CSS terdiri dari **Selector** (elemen yang dipilih), lalu di dalam `{}` ada **Property** (sifat yang diubah) dan **Value** (nilainya), diakhiri titik koma `;`.
2. Cara menghitung poin spesifisitas CSS kalau selector-nya gabungan dan lumayan panjang.
3. Bikin struktur dasar HTML5 lengkap secara mandiri tanpa harus ngeliat contoh.