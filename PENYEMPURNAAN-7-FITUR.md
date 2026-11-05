# PSM SAWIT — 7 Penyempurnaan

Paket ini menambahkan tujuh penyempurnaan tanpa mengubah modul laporan gambar, nota thermal lama, atau aset logo/header nota lama.

1. **Deteksi transaksi ganda** berdasarkan tanggal, jam (menit), pemilik, sopir, T1, dan T2. Hanya memberi peringatan; pengguna tetap dapat melanjutkan jika muatan memang berbeda.
2. **Indikator sinkronisasi** pada status Cloud menampilkan jumlah perubahan yang belum tersinkron serta tombol sinkronisasi manual.
3. **Validasi berat** memastikan T1/T2 positif, T1 lebih besar dari T2, serta menolak input berat yang tidak valid tanpa menetapkan batas maksimum sembarangan.
4. **Pencarian transaksi** berdasarkan nomor urut atau ID, ditambah filter pemilik, sopir, dan tanggal yang sudah tersedia.
5. **Konfirmasi dua tahap** untuk penghapusan, restore, tarik Cloud, dan tutup buku.
6. **Backup sebelum tindakan berisiko** sebelum restore dan tarik Cloud. Tindakan dibatalkan jika backup tidak dapat diverifikasi/disimpan.
7. **Optimasi tabel** memakai pemetaan ID sekali per render, tampilan awal 150 transaksi, dan hasil filter bertahap 250 transaksi per halaman.

## Pemeriksaan yang telah dijalankan

- `node --check` untuk seluruh JavaScript pada `www/js` dan `scripts`.
- Unit test dasar untuk deteksi duplikat dan validasi berat (`npm run test:enhancements`).
- Perbandingan hash: `www/js/report.js`, `www/js/thermal.js`, `www/assets/icons/logo-nota-default.png`, dan `www/assets/icons/header-nota-default.png` tetap identik dengan ZIP asal.

## Batas pengujian

Belum dilakukan build APK atau uji perangkat Android, koneksi Apps Script/Cloud sebenarnya, serta printer thermal fisik. Uji tersebut dilakukan pada tahap APK percobaan. Sebelum penggunaan operasional, lakukan backup manual tambahan dan uji restore dengan data salinan.
