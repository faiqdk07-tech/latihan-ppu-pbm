# latihan-ppu-pbm

## Paket mini game mingguan
- Tiap minggu (Senin–Minggu) mini game mendapat bahan baru: paragraf tambahan untuk Menara Paragraf dan Tangkap Penyusup, kalimat pembawa Bengkel Kata Baku, kalimat Pangkas, dan pasangan Relasi Kilat.
- Halaman Game → "kelola" (`#mingguan`): salin prompt mingguan → jalankan di proyek Claude PPU-PBM → tempel JSON → Cek & simpan. Butir yang tidak lolos dilewati dengan keterangan; paket minggu depan bisa disiapkan lebih awal.
- Mulai Jumat muncul pengingat bila paket minggu depan belum ada; tanpa paket minggu ini game memakai isi bawaan.
- Status ditulis ke kunci `paketMingguan:latihan-ppu-pbm` untuk pengingat di Progres Harian.

## Error Book
- Menu **Error Book** (`#eb`) di navigasi bawah. Soal drill dan soal teks yang salah masuk otomatis ke antrean *Kerjakan*. Salinan soal dan bacaannya ikut disimpan, karena teks yang sudah selesai dihapus dari Bank soal.
- Halamannya berupa daftar ringkas dengan tab Kerjakan · Terjadwal · Lulus, satu baris per soal.
  1. *Coba lagi tanpa kunci*: soal dikerjakan ulang di tampilan CBT yang sama (drill dan teks terpisah, yang baru salah didahulukan, paling banyak 10 per putaran). Pembahasan baru tampil setelah menjawab.
  2. *Diagnosis tepat sesudah pembahasan*: pilih penyebab utama (kaidah belum kuasai, salah tangkap teks, salah baca perintah, ragu di dua opsi, pakai pendapat sendiri, terburu-buru, menebak) dan tulis aturan "Kalau …, aku …". Tombol "Simpan & lanjut" menggantikan "Selanjutnya" sampai diagnosis diisi.
  3. *Ulang berjarak*: soal muncul lagi 1, 3, 7, dan 14 hari kemudian. *Lulus* setelah benar 4 kali berjarak; salah lagi berarti mulai dari awal dan diagnosis diperbarui. Ulangan ini tidak masuk riwayat Progres dan tugas harian.
- *Pola 30 hari*: penyebab dan kaidah/pola soal yang paling sering salah, fokus minggu ini, dan prompt analisis pola untuk Claude. Kartu pengingat muncul di Hari ini. Saat pertama dibuka, soal yang jawaban terakhirnya salah dalam 14 hari terakhir ikut dimasukkan.
