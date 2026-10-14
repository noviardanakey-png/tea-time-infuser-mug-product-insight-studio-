# TEA TIME Product Insight Studio

Website dashboard untuk proyek pengembangan produk TEA TIME Ceramic Tea Infuser Mug.

## Menjalankan secara lokal
1. Ekstrak folder `Tea_Time_Product_Insight_Studio`.
2. Buka folder tersebut di VS Code.
3. Jalankan server lokal (disarankan ekstensi Live Server) dari `index.html`.
4. Website menggunakan `data.json` untuk agregat penelitian; jangan membuka `index.html` langsung dengan `file://` karena browser dapat memblokir `fetch()`.

Alternatif dengan Python dari folder proyek:
```bash
python -m http.server 8000
```
Lalu buka `http://localhost:8000`.

## Struktur
- `index.html` — struktur halaman dan narasi.
- `styles.css` — identitas visual responsif.
- `script.js` — interaksi varian, filter tabel, Attribute Explorer, dan grafik.
- `data.json` — agregat demografi dan ringkasan Kano; tidak memuat nama responden.
- `` — render produk dan logo Teknik Industri.

## Sumber data dan batas interpretasi
Agregat demografi dibuat dari `Form Responses 1`; ringkasan klasifikasi, nilai Better/Worse, dan ranking atribut mengikuti worksheet `Ringkasan_Kano`. Worksheet workbook yang teridentifikasi: `Form Responses 1`, `Numbering`, `Sheet1`, `Matriks_Kano`, `Hasil_Kano`, dan `Ringkasan_Kano`.

Terdapat 100 baris respons dengan timestamp unik. Tidak ditemukan baris respons yang identik sepenuhnya. Kolom usia, jenis kelamin, dan kelompok pengguna terisi seluruhnya. Terdapat satu jawaban kosong pada pertanyaan dimensi produk, sehingga jumlah respons valid per atribut dapat berbeda. Label kelompok pengguna dipertahankan sesuai isian dan tidak digabungkan secara asumtif.

Nilai Better/Worse menggunakan denominator A + O + M + I sesuai workbook. Website mempertahankan nilai Worse sebagai negatif dan tidak menyajikannya sebagai pengukuran kepuasan aktual. Spesifikasi teknis produk yang belum tersedia tidak diisi dengan asumsi.

## Catatan
- Font dari Google Fonts memerlukan koneksi internet; jika offline, fallback font tetap digunakan.
- Tidak ada backend khusus. Seluruh komponen bekerja pada browser dengan HTML, CSS, JavaScript, dan file data lokal.
