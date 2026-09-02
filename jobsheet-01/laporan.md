# Laporan Jobsheet 1

Menyusun struktur dasar web dengan HTML. Pada jobsheet ini, masih belum menggunakan CSS dan Javascript sehingga fokusnya murni pada struktur sematic dan tidak dengan `<div>`.

## Membuat laman beranda
pada file awal yang diberi nama `index.html` terdapat beberapa bagian yang masing-masing memiliki fungsi tertentu.

### `<header>` sebagai kepala halaman

- Bagian `<h1>` adalah judul utama aplikasi dan merupaka heading dengan *tier* tertinggi.

- Bagian `<nav>` adalah menu navigasi untuk berpindah laman dari beranda (`<index.html>`). Di dalamnya terdapat `<ul>` yang menandakan **Unordered List** atau daftar tidak urut. Terdapat pula `<li>` yang menandakan item yang di-list. Di dalam elemen `<li>` terdapat bagian `<a href>` yang merujuk pada laman tujuan.

### `<main>` Isi Halaman
- `<main>` dapat berisi beberapa bagian atau `<section>`. Pada jobsheet ini, hanya ada dua bagian saja yaitu sambutan dan ringkasan statistik.

- Pada bagian ringkasan statistik, masih menggunakan data statis atau telah ditentukan sebelumnya karena masih belum ada *database* aktif.

- Bagian `<article>` mewakili bagian yang nantinya akan menjadi kartu statistik setelah diberi styling

### `<footer>` Kaki halaman
- teks kecil yang menandakan pemilik web

## `Buku-List.html`
Berisi daftar buku perpustakaan (data statis 5 baris)

### Kerangka/dasar halaman
Pada bagian `<header>` dan `<footer>` sama dengan `index.html`, hanya pada bagian `href` yang berbeda karena lokasi file yang berbeda
```html
<li><a href="../index.html">Beranda</a></li>
<li><a href="list.html">Daftar Buku</a></li>
<li><a href="tambah.html">Tambah Buku</a></li>
<li><a href="../anggota/list.html">Daftar Anggota</a></li>
```

### Anatomi Tabel
```html
<table>
    <thead>
        <tr>
            <th>Judul</th>
            <th>Pengarang</th>
            <th>Tahun</th>
            <th>Stok</th>
            <th>Aksi</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Laskar Pelangi</td>
            <td>Andrea Hirata</td>
            <td>2005</td>
            <td>4</td>
            <td>
                <button type="button">Edit</button>
                <button type="button">Hapus</button>
            </td>
        </tr>
    </tbody>
</table>
```

- `<table>` menandai seluruh tabel
- `<thead>` kepala tabel, nama dari kolom-kolom
- `<tbody>` isi tabel
- `<tr>` baris tabel
- `<tc>` kolom tabel

### Tombol Aksi
```html
    <td>
        <button type="button">Edit</button>
        <button type="button">Hapus</button>
    </td>
```
- `type="button"` berarti tombol biasa, bukan untuk mengirim
- tombol masih tidak memiliki fungsi. Belum ada JavaScript untuk mengatur

## `buku/tambah.html`
Berisi form pengisian buku menggunakan `<form>` dan `<input>`

```html
            <form>
                <p>
                    <label for="judul">Judul</label><br>
                    <input type="text" id="judul" name="judul" required>
                </p>
                <p>
                    <label for="pengarang">Pengarang</label><br>
                    <input type="text" id="pengarang" name="pengarang" required>
                </p>
                <p>
                    <label for="tahun">Tahun Terbit</label><br>
                    <input type="number" id="judul" name="judul" min="1900" max="2026" required>
                </p>
                <p>
                    <label for="isbn">ISBN</label><br>
                    <input type="text" id="isbn" name="isbn">
                </p>
                <p>
                    <label for="stok">Stok</label><br>
                    <input type="number" id="judul" name="judul" min="0" required>
                </p>
                <p>
                    <label for="kategori">Kategori</label><br>
                    <select name="kategori" id="kategori">
                        <option value=""></option>
                        <option value="fiksi">Fiksi</option>
                        <option value="nin-Fiksi">Non-Fiksi</option>
                        <option value="referensi">Referensi</option>
                    </select>
                </p>

                <p>
                    <button type="submit">Kirim</button>
                </p>

            </form>
```

```html
<p>
    <label for="abd">ABC</label><br>
    <input type="text" id="abc" name="abc" required>
</p>
```
- `<label for="abd">ABC</label>` Keterangan "ABC" yang akan ditampilkan. Atribut `for="abc" 

### `<select>` untuk dropdown
```html
        <p>
            <label for="kategori">Kategori</label><br>
            <select name="kategori" id="kategori">
                <option value=""></option>
                <option value="fiksi">Fiksi</option>
                <option value="nin-Fiksi">Non-Fiksi</option>
                <option value="referensi">Referensi</option>
            </select>
        </p>
```

- `<select>` untuk seluruh menu *dropdown*
- `<option>` menandakan setiap pilihan yang didaftarkan, berisi nilai yang akan diproses (`value`) dan teks yang akan ditampilkan. Nilai `value` dan teks tidak harus sama namun disarankan untuk disamakan agar konsistensi terjaga.
- `<option value=""></option>` pada nilai pertama sengaja dikosongkan sebagai nilai default karena pada pilihan tidak ada `required` dan pilihan secara default memilih pilihan pertama
