PERUBAHAN NOMOR 5 - REKAP ONGKOS LANGSIR

- Menambahkan menu Rekap Ongkos Langsir di halaman monitoring.
- Halaman awal hanya meminta rentang tanggal dan pilihan satu/beberapa sopir.
- Nama sopir diambil dari transaksi lokal yang sudah ada; tidak membuat master sopir baru.
- Hasil dipisahkan per sopir dan dikelompokkan menurut pemilik buah.
- Netto memakai N1 (W1-T2) dan nilai ongkos memakai nilai tL tersimpan; jika tL tidak tersedia, dihitung dari N1 x fl. Ini mengikuti formula transaksi lama.
- Potongan tambahan dicatat per rekap pembayaran sopir (kasbon, BBM, dll), dan pembayaran setiap sopir berdiri sendiri.
- Rekap pembayaran yang disimpan dicatat lokal di perangkat; tidak mengubah database timbang atau Cloud.
- Pratinjau gambar dan cetak thermal belum ditambahkan pada tahap ini; keduanya masuk pekerjaan nomor 6 di menu lanjutan yang sama.

Catatan: ZIP ini belum menjalani pengujian integrasi di perangkat Android. Jalankan build dan uji bersama setelah pekerjaan nomor 6 selesai, sesuai arahan pengguna.
