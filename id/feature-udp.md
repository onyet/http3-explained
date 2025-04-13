## Protokol Transfer di atas UDP

**QUIC adalah protokol transfer data yang dibangun di atas UDP.** Jika kamu mengamati lalu lintas jaringanmu secara kasual, kamu akan melihat QUIC muncul sebagai paket-paket UDP.

Karena berbasis UDP, QUIC juga menggunakan **nomor port UDP** untuk mengidentifikasi layanan jaringan tertentu pada alamat IP tertentu.

Semua implementasi QUIC yang diketahui saat ini berjalan di **user-space**, bukan di kernel. Hal ini memungkinkan pengembangan yang lebih cepat dibandingkan implementasi yang berada di kernel-space.

## Apakah akan berfungsi?

Ada perusahaan dan konfigurasi jaringan tertentu yang **memblokir lalu lintas UDP** pada port selain 53 (yang digunakan untuk DNS). Ada juga yang membatasi jenis data ini dengan cara yang membuat performa QUIC **lebih buruk** dibandingkan protokol berbasis TCP. Tidak ada batasan atas apa yang mungkin dilakukan oleh beberapa operator jaringan.

Untuk saat ini dan waktu dekat, penggunaan protokol berbasis QUIC kemungkinan besar harus **mampu melakukan fallback secara mulus** ke alternatif lain yang berbasis TCP. Para insinyur Google sebelumnya menyebutkan bahwa tingkat kegagalan koneksi QUIC yang mereka ukur berada di angka **satu digit persen yang rendah**.

## Apakah akan membaik?

Kemungkinannya besar. Jika QUIC terbukti menjadi tambahan yang berharga bagi dunia Internet, orang-orang akan tertarik menggunakannya dan ingin agar QUIC bisa berjalan di jaringan mereka. Ketika hal itu terjadi, perusahaan dan penyedia jaringan mungkin akan mulai mempertimbangkan ulang hambatan-hambatan yang mereka pasang.

Selama beberapa tahun perkembangan QUIC berlangsung, **tingkat keberhasilan dalam membangun dan menggunakan koneksi QUIC di seluruh Internet terus meningkat.**