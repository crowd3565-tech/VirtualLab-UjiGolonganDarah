# Draf Bagian 5 dan 6 — Storyboard Lab Virtual Uji Golongan Darah ABO dan Rhesus

> Draf ini disusun dari prototipe `index.html`. Kolom "Hasil uji" berisi pengujian otomatis yang dijalankan AI (Claude) di browser Chromium. **Kelompok wajib mengulang pengujian sendiri** (terutama di HP sungguhan) dan mengganti isi kolom itu dengan hasil kalian.

## Bagian 5. Spesifikasi Prototipe dan Pengujian

| Aspek | Isian kelompok |
|---|---|
| **Bentuk prototipe** | Website satu halaman (HTML, CSS, JavaScript tanpa pustaka luar). Tampilan 2D realistis: tabung darah EDTA, botol serum berpipet, plat keramik 4 sumur, dan tampilan mikroskop beranimasi. |
| **Fungsi wajib** | (1) Prediksi dan alasan di S1; (2) memilih/mengacak pasien dan meneteskan darah ke 4 sumur dengan seret-lepas atau ketuk; (3) meneteskan 4 serum ke sumur berlabel sama; (4) mengaduk dengan menahan tombol ≥3 detik, waktu reaksi 2 menit dipercepat; (5) mengamati perbesaran tiap sumur; (6) mengisi tabel observasi, golongan ABO, dan Rhesus dengan petunjuk dan tabel acuan setelah 2 kali salah; (7) 4 pertanyaan analisis dan kuis 3 soal dengan umpan balik; (8) kartu identitas golongan darah, kesimpulan, refleksi, laporan untuk guru, dan tombol "Pasien lain". |
| **Aset visual** | Semua digambar dengan kode (SVG dan Canvas), tanpa foto atau gambar dari internet: tabung darah, 4 botol reagen (Anti-A biru, Anti-B kuning, Anti-AB dan Anti-D bening), pipet, plat keramik, gumpalan aglutinasi, sel darah merah bikonkaf, antibodi berbentuk Y, kartu identitas. |
| **Data yang disimpan** | Nama, kelas, prediksi dan alasan, pasien dan golongan darahnya, pola 4 sumur, jumlah percobaan di S4, jumlah percobaan tiap pertanyaan analisis, jawaban dan skor kuis, kesimpulan, refleksi, daftar langkah yang diulang. Disimpan otomatis di browser siswa (localStorage), sehingga progres tidak hilang saat halaman di-refresh. |
| **Batasan simulasi** | Jumlah tetesan ditentukan sistem; waktu reaksi dipercepat 30 kali; pola reaksi berupa model visual, bukan foto; hanya 8 pola ABO–Rhesus standar (tanpa varian lemah seperti weak D atau subgrup A2); data hanya tersimpan di perangkat siswa dan tidak terkirim otomatis ke guru — siswa menyalin teks laporan lalu mengirimkannya; tidak menampilkan pengambilan darah dengan lancet, sterilisasi, maupun pembuangan limbah medis. |
| **Cara menjalankan** | Buka tautan prototipe di browser (Chrome, Edge, Firefox, atau Safari versi terbaru) di laptop atau HP. Tidak perlu instalasi. Berkas `index.html` juga bisa dibuka langsung dari komputer. |
| **Bukti pengujian** | Video demo alur lengkap S1–S6 (`Demo-Lab-Golongan-Darah.mp4`), tangkapan layar desktop dan HP mode gelap, serta tabel pengujian di bawah. |

### Tabel pengujian

| Aspek uji | Cara menguji | Hasil yang diharapkan | Hasil uji dan perbaikan |
|---|---|---|---|
| **Tombol dan navigasi** | Menekan setiap tombol "Lanjut", "Aduk", "Amati" sebelum syaratnya terpenuhi, lalu sesudahnya | Tombol abu-abu menampilkan alasannya; setelah syarat terpenuhi, layar berikutnya terbuka | Sesuai di Chromium desktop. Perbaikan: panel kanan yang terlalu panjang tidak bisa digulir sehingga tombol tidak terjangkau — diperbaiki dengan panel yang bisa digulir sendiri. |
| **Alur kegiatan** | Menjalankan S1 sampai S6, lalu "Pasien lain" | Semua layar bisa diselesaikan; "Pasien lain" kembali ke S2 dengan sampel berbeda dan prediksi tetap tersimpan | Sesuai, diuji untuk beberapa golongan darah acak (A Rh−, B Rh−, AB Rh+, O Rh−). Muat ulang halaman di tengah S3b memulihkan progres. |
| **Respons tindakan salah** | Pipet Anti-B ke sumur Anti-A; melepas tombol aduk sebelum 3 detik; memilih Rhesus atau ABO yang salah di S4 | Pesan sesuai Bagian 3 muncul; tindakan bisa diulang; tabel acuan tampil setelah salah 2 kali | Sesuai. Pesan yang muncul sama persis dengan teks di Bagian 3. |
| **Ketepatan konsep Biologi** | Membandingkan pola di plat dan mikroskop dengan tabel acuan 4b untuk tiap golongan | Sumur yang antibodinya cocok dengan antigen sel menggumpal; Anti-AB menggumpal untuk A, B, AB; Anti-D menentukan Rhesus | Sesuai tabel acuan. *Perlu diperiksa kelompok: pilihan jawaban (pengecoh) analisis dan kuis disusun AI.* |
| **Kesesuaian hasil** | Mencocokkan kartu identitas dan laporan guru dengan pasien yang diuji | Golongan darah, pola sumur, dan skor di kartu serta laporan sama dengan hasil uji | Sesuai. |
| **Tampilan dan perangkat** | Membuka di lebar desktop 1280–1360 px dan HP 390 px, mode terang dan gelap | Tidak ada teks terpotong atau halaman bergeser ke samping | Sesuai di emulasi Chromium. Perbaikan: label sumur tertimpa lingkaran penanda dan teks kartu identitas bertumpuk — diperbaiki. **Belum diuji di HP sungguhan (seret dengan jari dan tahan tombol aduk).** |

### Checklist pengujian

- [x] Konsep, istilah, alat, prosedur, dan hasil sesuai dengan Biologi SMA *(periksa ulang pengecoh soal)*
- [x] Semua tombol dan interaksi utama berfungsi; tidak ada layar yang buntu
- [x] Tindakan yang salah ditangani dengan umpan balik atau bisa diulang
- [x] Data hasil konsisten dan cukup untuk menjawab pertanyaan analisis
- [ ] Berjalan di browser yang ditentukan; tampilan terbaca di smartphone *(uji di HP sungguhan dulu)*
- [ ] Kode dari AI sudah diuji sendiri dan diperbaiki *(isi setelah kelompok menguji sendiri)*

## Bagian 6. Catatan Penggunaan AI dan Penyerahan

| Catatan | Isian kelompok |
|---|---|
| **AI / platform yang digunakan** | Claude (Anthropic) melalui Claude Code. |
| **Bagian yang dibantu AI** | Penyusunan storyboard slide per slide dari dokumen kelompok; penulisan seluruh kode prototipe (tampilan, interaksi, animasi mikroskop, logika penilaian, laporan guru); penyusunan pilihan jawaban (pengecoh) untuk pertanyaan analisis dan kuis; draf Bagian 5–6 ini; pengujian otomatis dan video demo. |
| **Pemeriksaan yang dilakukan** | *[Isi oleh kelompok]* Contoh: mencocokkan pola reaksi dengan buku Biologi kelas XI; memeriksa setiap pengecoh soal; menguji di HP Android dan iPhone; mencoba prototipe bersama beberapa siswa. |
| **Berkas yang diserahkan** | Storyboard (Word), tautan prototipe, berkas `index.html`, video demo `Demo-Lab-Golongan-Darah.mp4`. |

### Keputusan desain yang perlu disetujui kelompok

1. Pertanyaan analisis nomor 1 dan petunjuk di S4 menyesuaikan golongan darah sampel siswa.
2. Tombol yang belum aktif tetap bisa diketuk untuk menampilkan alasannya, sehingga semua pesan di Bagian 3 dapat muncul.
3. Kolom alasan prediksi di S1 boleh dikosongkan.
4. Empat kartu pasien diambil acak dari 8 pola setiap sesi; umur dan kode pasien acak.
5. Ditambahkan kolom nama dan kelas di S1, serta "Laporan untuk guru" di S6.
