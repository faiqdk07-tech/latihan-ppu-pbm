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
