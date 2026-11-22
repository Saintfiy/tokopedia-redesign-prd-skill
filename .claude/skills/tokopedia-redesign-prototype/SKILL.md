---
name: tokopedia-redesign-prototype
description: Membangun dan memverifikasi prototype mobile web konsep redesign alur belanja Tokopedia (Beranda sampai Detail Pesanan) berdasarkan PRD.md. Gunakan saat diminta membuat, melanjutkan, memperbaiki, atau menguji prototype tersebut, atau saat perlu memeriksa apakah sebuah layar memenuhi kebutuhan UX UX-01 sampai UX-07.
---

# Prototype Redesign Alur Belanja Tokopedia

Skill ini memandu pembuatan prototype dari `PRD.md` di akar repositori. Tujuan utamanya: pengguna yang sudah tahu produk yang dicari dapat menemukannya dengan cepat, memeriksa harga akhir, membayar, dan memantau pesanan, tanpa promo menutupi pencarian dan tombol utama.

## Sebelum menulis kode

1. Baca `PRD.md`: bagian 5 (kebutuhan UX dan kriteria penerimaan), bagian 8 (alur), bagian 9 (spesifikasi layar), bagian 10 (interaksi).
2. Baca `references/ux-checklist.md` untuk daftar pemeriksaan yang harus lolos.
3. Pakai `references/dummy-data.json` sebagai satu satunya sumber data. Jangan memakai API atau backend.
4. Jika ada hal di PRD yang bertentangan atau belum jelas, sebutkan di awal laporan dan pilih opsi paling sederhana yang tetap memenuhi kebutuhan UX.

## Teknologi default

HTML, CSS, dan JavaScript murni dalam folder `prototype/` (tanpa proses build), dengan navigasi berbasis hash agar tombol kembali bekerja. Pakai framework hanya jika pengguna memintanya. Prototype harus dapat dibuka langsung di browser atau lewat GitHub Pages.

## Langkah kerja

1. **Kerangka:** buat `prototype/index.html`, gaya dasar mobile first (lebar acuan 360 sampai 430 px), tab bar bawah dengan 5 menu (Beranda, Kategori, Keranjang, Pesanan, Akun), dan pemuat data dummy.
2. **Layar:** bangun sembilan layar sesuai PRD bagian 9 dengan urutan alur: Beranda, Pencarian dan Saran, Hasil Pencarian, Detail Produk, Keranjang, Checkout, Pembayaran dan Konfirmasi, Detail Pesanan, Pusat Promo.
3. **Interaksi:** hubungkan layar sesuai tabel PRD bagian 10. Keranjang, voucher terpilih, dan status pesanan disimpan di state (memori atau penyimpanan lokal).
4. **Cabang alur:** pastikan kelima cabang "Tidak" bekerja: ubah pencarian atau filter (K1), pilih produk lain (K2), ganti voucher lewat Pusat Promo (K3), ubah alamat atau pengiriman (K4), dan pembayaran gagal lalu ulangi atau ganti metode (K5, metode dengan `selalu_gagal` bernilai true).
5. **Pemeriksaan:** jalankan seluruh item di `references/ux-checklist.md`. Perbaiki kegagalan, lalu periksa ulang.
6. **Laporan:** ringkas apa yang dibuat, hasil checklist per kode UX, dan hal yang belum selesai atau diasumsikan.

## Aturan desain wajib

- Kolom pencarian selalu terlihat di bagian atas pada Beranda, Kategori, dan Hasil Pencarian, dan tidak pernah tertutup elemen lain.
- Tidak ada elemen yang melayang di atas konten (ikon atau tombol mengambang). Banner kampanye maksimal 1 dan tidak berada di atas pencarian.
- Pada Hasil Pencarian, produk pertama terlihat di layar pertama. Promo hanya tampil sebagai Promo Terkait setelah atau di sela produk, tidak menutupi produk.
- Harga akhir dan syarat promo ditulis dengan format seragam pada kartu produk, Detail Produk, dan Keranjang: harga coret, harga akhir, syarat singkat.
- Voucher Terbaik terpilih otomatis di Keranjang dengan indikator jelas, dan tombol Ganti membuka Pusat Promo.
- Tawaran tambahan di Checkout bersifat opsional dan berada di bawah tombol bayar, tidak di antara pengguna dan tombol bayar.
- Pembayaran gagal menampilkan pesan yang jelas dengan opsi Coba lagi dan Ganti metode.
- Area ketuk minimal 44 x 44 px. Istilah dan nama tombol konsisten dalam bahasa Indonesia.

## Batasan

- Jangan menambah layar atau fitur di luar PRD kecuali diminta.
- Jangan memakai logo, aset, atau data asli Tokopedia. Gunakan teks dan kotak placeholder.
- Jangan meminta atau menyimpan data pribadi nyata. Semua data adalah dummy.

## Selesai bila

- Semua item `references/ux-checklist.md` lolos.
- Alur 13 langkah dapat dijalankan dari Beranda sampai Detail Pesanan tanpa jalan buntu, termasuk kelima cabang "Tidak".
- Prototype dapat dibuka tanpa proses build.
