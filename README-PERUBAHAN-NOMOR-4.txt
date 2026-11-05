PSM SAWIT - PERUBAHAN NOMOR 4: SISIP TRANSAKSI TERLUPA

Fitur ini berada di Pengaturan > Menu Setelan Lanjutan (menu terkunci PIN).

CARA PAKAI:
1. Buka Pengaturan.
2. Masuk Menu Setelan Lanjutan menggunakan PIN.
3. Pada bagian 'Sisipkan Transaksi Terlupa', masukkan nomor urut tujuan.
   Nomor yang valid adalah 1 sampai jumlah transaksi saat ini + 1.
4. Tekan 'AKTIFKAN SISIP DATA'.
5. Kembali ke halaman utama, isi transaksi yang terlupa seperti transaksi baru,
   lalu simpan seperti biasa.
6. Transaksi baru akan disisipkan pada nomor tersebut. Transaksi sesudahnya
   bergeser satu nomor. Mode sisip otomatis dinonaktifkan setelah satu transaksi.
7. Jika batal, buka kembali menu tersebut dan tekan 'BATALKAN MODE SISIP'.

CATATAN TEKNIS:
- ID transaksi yang sudah ada tidak diubah.
- Mengedit tanggal/jam tidak mengubah posisi transaksi.
- __order disusun ulang setelah sisip/hapus.
- Transaksi yang bergeser ditandai belum tersinkron agar dikirim ulang ke Cloud.
- Sinkronisasi Cloud harus diuji bersama Apps Script aktual untuk memastikan
  server menyimpan dan mengembalikan field __order. Jangan lakukan tarik data
  Cloud sebelum pengujian akhir jika ada perubahan lokal yang belum tersinkron.
