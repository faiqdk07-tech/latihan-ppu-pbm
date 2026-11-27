# latihan-ppu-pbm

## Paket mini game mingguan
- Tiap minggu (Senin–Minggu) mini game mendapat bahan baru: paragraf tambahan untuk Menara Paragraf dan Tangkap Penyusup, kalimat pembawa Bengkel Kata Baku, kalimat Pangkas, dan pasangan Relasi Kilat.
- Halaman Game → "kelola" (`#mingguan`): salin prompt mingguan → jalankan di proyek Claude PPU-PBM → tempel JSON → Cek & simpan. Butir yang tidak lolos dilewati dengan keterangan; paket minggu depan bisa disiapkan lebih awal.
- Mulai Jumat muncul pengingat bila paket minggu depan belum ada; tanpa paket minggu ini game memakai isi bawaan.
- Status ditulis ke kunci `paketMingguan:latihan-ppu-pbm` untuk pengingat di Progres Harian.

## Error Book
- Menu **Error Book** (`#eb`) di navigasi bawah. Soal drill dan soal teks yang salah masuk otomatis, lengkap dengan jawabanmu, kunci, dan waktu. Salinan soal dan bacaannya ikut disimpan, karena teks yang sudah selesai dihapus dari Bank soal.
- Tiga langkah supaya tidak sekadar daftar:
  1. *Diagnosis*: pilih penyebab utama (kaidah belum kuasai, salah tangkap teks, salah baca perintah, ragu di dua opsi, pakai pendapat sendiri, terburu-buru, menebak), lalu tulis satu aturan "Kalau …, aku …" dengan kata sendiri. Aturan yang terlalu umum ("lebih teliti") diberi peringatan. Ada tombol ke materi kaidahnya.
  2. *Ulang berjarak tanpa kunci*: mulai besok, lalu 3, 7, dan 14 hari (paling banyak 10 per putaran, drill dan teks terpisah). Aturanmu baru ditampilkan setelah menjawab. Ulangan ini tidak masuk riwayat Progres dan tugas harian.
  3. *Lulus* setelah benar 4 kali berjarak; salah lagi berarti mulai dari awal dan diagnosis diperbarui.
- *Pola 30 hari*: penyebab dan kaidah/pola soal yang paling sering salah, fokus minggu ini, dan prompt analisis pola untuk Claude. Kartu pengingat muncul di Hari ini. Saat pertama dibuka, soal yang jawaban terakhirnya salah dalam 14 hari terakhir ikut dimasukkan.

## Soal teks harian
- Setiap hari: 8 soal PPU + 6 soal PBM (±14 menit dengan waktu resmi 45/75 detik per soal), lewat satu prompt "2 · Teks PPU + PBM".
- App menentukan kode bentuk Brief untuk setiap soal (PPU-1–16, PBM-1–14, dan tambahan 2026), lengkap dengan kerangka pertanyaan dan pengecoh khasnya. Rotasinya berbobot menurut Peta Pola: makin sering pola muncul 2019–2026, makin sering dilatih; pola baru 2024–2026 diberi tambahan.
- Konsep EYD hari ini selalu mendapat satu slot PBM, konsep kebahasaan hari ini satu slot di subtes yang sesuai, dan kode yang lemah dalam 30 hari menggantikan slot rotasi.
- Kode bentuk setiap soal ikut tersimpan di riwayat (`kode`). JSON lama tanpa `kode` tetap diterima.

## Opsi acak dan pemeriksaan anti-tebak
- Opsi pilihan ganda soal teks diacak setiap sesi (urutannya tetap selama sesi). Tidak diacak: opsi berurutan (nomor kalimat, urutan, pengelompokan kalimat), soal bertanda `"acak": false` (opsi baku), dan soal yang pembahasannya masih menyebut huruf opsi.
- Bank soal memisahkan dua jenis temuan. **Merah** = paket belum bisa disimpan: kunci jauh lebih panjang, tiga kunci sama berturut-turut, opsi "semua benar/semua salah/tidak ada", nomor isian tidak ada di bacaan, nomor kalimat ditulis manual, kunci terpanjang di lebih dari 40% soal. **Oranye** = boleh disimpan tetapi mudah ditebak: selisih panjang opsi lebih dari 30%, hanya kunci yang berhati-hati, hanya kunci yang mengulang kata dari perintah, kunci terpanjang di lebih dari 1 dari 5 soal, pembahasan menyebut huruf.
- Tombol **Salin prompt perbaikan** membuat prompt untuk chat Claude yang sama: perbaiki hanya soal yang ditandai, lalu kirim ulang seluruh paket.

## Jenis soal L/G/B/M dan format J1–J7 (kesiapan-2027)
- Sejak hari pertama setiap paket memakai komposisi Kesiapan 2027: per hari sekitar 4 L (bentuk lama), 6 G (geseran), 3 B (bentuk baru), 1 M (migrasi; bergantian PPU/PBM). Simulasi 20 soal: 6/8/4/2.
- App menentukan jenis dan format setiap soal di Rancangan soal. G mendapat satu tuas bergiliran (stimulus, arah tanya, format jawaban). M berupa tabel benar/salah (J2, sesekali J5/J6 ditulis sebagai J2) atau definisi dua syarat untuk makna kata PPU. Setiap subtes minimal 2 soal di luar J1.
- Kemampuan resmi (PPU-A–E, PBM-A–C) yang akurasi soal L-nya di bawah 70% (dari sekitar 20 soal terakhir, minimal 5 soal L) kembali memakai L saja.
- PPU boleh punya satu bacaan pendek satu soal untuk soal B; PBM selalu berupa bacaan bernomor.
- JSON memakai `"jenis_soal"` dan `"format"`; `"mode"` lama diisi otomatis (L→dasar, G→geser, B/M→2027). Riwayat menyimpan `jenis_soal` dan `format`.

## PBM: bacaan, isian, urutkan kalimat, kata tebal bernomor
- PBM selalu berupa bacaan bernomor; soal PBM dalam jenis "pendek" atau "lepas" ditolak validator. Kalimat sumbang (bentuk 2019–2022) tidak lagi dibuat.
- Isian nomor kalimat di PBM dijaga 2–4 per 10 soal (6 soal → 1–2).
- Tambahan 2026 aktif: **urutkan 5 kalimat** (`"jenis": "urutan"`, tepat 5 kalimat, format J7 = PG berisi urutan, opsi tidak diacak) dan **kata bercetak tebal bernomor** (`"tebal_bernomor": true`; nomor kecil tampil di samping kata tebal; jawaban = nomor kata).
