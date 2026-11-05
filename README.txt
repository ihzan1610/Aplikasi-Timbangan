PSM SAWIT FIX SETTINGS LOCKED

Isi paket penting saja:
- www
- assets
- scripts
- .github/workflows
- package.json
- capacitor.config.json
- .gitignore

Perbaikan utama:
1. Format Nota, Efek Suara, dan Ubah PIN dipindahkan ke Menu Setelan Lanjutan.
2. Menu Setelan Lanjutan wajib PIN sebelum bisa dibuka.
3. Default baru: logo nota gambar aktif, logo thermal hitam putih aktif, suara tombol aktif.
4. Backup dan fitur urgent tetap ada di halaman pengaturan utama.
5. Format thermal potongan lebih adaptif agar nominal rupiah tidak mudah turun baris.
6. Autocomplete pemilik/sopir tetap dipertahankan.
7. Monitoring data, RAWBT, simpan gambar, backup CSV, icon Android, dan fitur lama tetap dipertahankan.

Cara build:
1. Upload isi ZIP ke GitHub.
2. Jalankan Actions: Build Android Debug APK - PSM SAWIT FIX.
3. Download artifact APK.
4. Uninstall APK lama, restart HP, lalu install APK baru.

SINKRONISASI CLOUD OTOMATIS
- Simpan transaksi tetap dilakukan di penyimpanan lokal terlebih dahulu.
- Saat aplikasi aktif, sync.js mengirim antrean dan memverifikasi ID melalui doGet Cloud.
- Pada Android, antrean juga diserahkan ke WorkManager dengan syarat jaringan tersedia.
- WorkManager menyimpan salinan antrean pada SharedPreferences native dan mencoba ulang jika gagal.
- Tombol SINKRONISASI SEKARANG menjadi jalur manual saat antrean masih tertunda.
- WorkManager dapat tertunda oleh kebijakan baterai/Android; bukan jaminan eksekusi tepat saat jaringan pulih.

BUILD ANDROID
Workflow GitHub Actions memasang dependensi WorkManager dan menghasilkan kelas PsmCloudSyncWorker setiap kali folder android dibuat ulang. Jangan menghapus langkah "Install Android WorkManager background sync" dari workflow.


KONFIRMASI PENGHAPUSAN CLOUD (PERUBAHAN NOMOR 3)
- Saat transaksi dihapus pada Android, ID permanen dicatat dalam antrean lokal.
- Status awal ditampilkan sebagai menunggu konfirmasi Cloud.
- Setelah POST delete, aplikasi membaca ulang snapshot Cloud melalui doGet.
- Hanya jika semua ID yang dihapus tidak lagi ditemukan, antrean ditandai synced dan status menampilkan jumlah data terkonfirmasi terhapus di Cloud.
- Jika ID masih ditemukan atau GET gagal, status tetap tertunda/belum dikonfirmasi dan antrean dicoba ulang.
- Worker Android juga memverifikasi hasil hapus dengan GET sebelum membersihkan antrean native.
- Penghapusan di Cloud yang ditarik ke HP tetap mengikuti mekanisme tarik data lama; alur itu tidak diubah.
