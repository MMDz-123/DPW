# Laporan Jobsheet 2

Memberi *styling* dasar dengan CSS3. *Styling* masih hanya meliputi pemberian *font*, warna *background*, dan kartu statistik pada bagian yang ditandai dengan `<article>`

Sebelum memberi *styling*, semua file `.html` harus diberi satu baris yang merujuk pada file `style.css`. Baris tersebut diisi dengan:
```html
<link rel="stylesheet" href="assets/css/style.css">
```

## Reset
```css
*{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
```
digunakan untuk menghilangkan jarak default yang otomatis diberikan brower. Banyak elemen memiliki margin bawaan yang berbeda-beda tergantung dari browser yang dipakai.

## Gaya dasar
```css
body{
    font-family:'Segoe UI', Arial, sans-serif;
    color:#002a1f;
    background-color: #d1d1d1;
    line-height: 1.5;
}
```
- `font-family` dan `color` mengurutkan font berdasarkan prioritas. Browser akan mencoba font yang ditulis pertama, jika tidak aka maka browser memakai font kedua, dan seterusnya. `color: #2b2b2b` menentukan warna teks.
- `background color` menentukan warna latar belakang. `#f5f6f8` abu-abu muda.
- `line-height` jarak antar baris, 1.5 kali besar font.

## Tautan
- semua tautan menggunakan warna `#1d5b8a`
- Tautan diberi garis bawah **hanya** saat kursor diarahkan (hover) dengan `a:hover {text-decoration: underline}`

## Header dan Navbar
### Flexbox
Secara default elemen di dalam HTML disusun bertumpuk ke bawah. Flexbox berperan sebagai sistem tata letak yang mengatur bagaimana elemen anak disusun. 
```css
header{
    display: flex;
}
```
Potongan tersebut mengubah `<header>` menjadi *flex container* dan semua keturunannya menjadi *flex items* dan disusun sejajar secara horizontal

Flexbox dapat digunakan dua kali secara bertingkat. Pada jobsheet ini *flexbox* digunakan di `<header>` dan `<nav> <ul>` untuk list menu

## Layout `main` dan `section`
### main
```css
main{
    max-width: 1000px;
    margin: 2rem auto;
    padding: 0 1.5rem;
}
```
- `max-width` lebar maksimal 1000 piksel sehingga konten tidak melebar secara tidak wajar sehingga dapat dibaca dengan nyaman meskipun menggunakan monitor berukuran besar.
- `margin: 2rem auto` margin vertikal sebesar `2rem` dan horizontal dibuat otomatis dengan membagi rata ruang kosong di kiri dan kanan sehingga konten berada di tengah
- `padding` jarak dari tepi layar secara horizontal sebesar `1.5rem` sehingga konten tidak terlalu mepet ke tepi layar

### section
Setiap section dibagi menjadi beberapa kotak yang terlihat seperti kartu
```css
section {
    background-color: #fff;
    border-radius: 8px;
    padding: 1.5rem;
    margin-bottom: 1.5rem;
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.08);
}
```
pada bagian `box-shadow` kode warna tidak menggunakan kode *hexadecimal* tetapi menggunakan kode rgba. Mirip seperti *hexadecimal* tetapi dengan tambahan `a` yaitu *alpha* atau transparansi sehingga bayangan tidak terlihat hitam pekat