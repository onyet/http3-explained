## Pengiriman Berurutan

QUIC menjamin pengiriman data secara berurutan untuk setiap stream, tetapi tidak antar stream. Artinya, setiap stream akan menjaga urutan datanya sendiri, namun antar stream bisa saja sampai ke tujuan dengan urutan yang berbeda dari saat dikirim oleh aplikasi!

Sebagai contoh: stream A dan B dikirim dari server ke klien. Stream A dimulai lebih dulu, lalu disusul oleh stream B. Dalam QUIC, jika ada paket yang hilang, hanya stream tempat paket itu berasal yang terpengaruh. Jadi jika stream A kehilangan paket tapi stream B tidak, maka stream B tetap bisa melanjutkan pengiriman hingga selesai, sementara stream A akan menunggu paket yang hilang dikirim ulang. Hal ini tidak bisa dilakukan pada HTTP/2.

Ilustrasi berikut menunjukkan satu stream berwarna kuning dan satu lagi biru yang dikirim antara dua titik QUIC dalam satu koneksi. Keduanya bekerja secara independen dan bisa sampai dalam urutan berbeda, namun masing-masing tetap diterima oleh aplikasi dengan urutan data yang benar.

![two QUIC streams between two computers](../images/quic-chain-streams.png)
