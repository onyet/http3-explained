## Beberapa Stream dalam Satu Koneksi

Mirip dengan SCTP, SSH, dan HTTP/2, QUIC mendukung **stream logis yang terpisah** di dalam satu koneksi fisik. Beberapa stream dapat berjalan **secara paralel dan mengirim data secara bersamaan** dalam satu koneksi tanpa saling memengaruhi.

Sebuah koneksi adalah hasil negosiasi antara dua titik komunikasi, mirip seperti koneksi TCP. Koneksi QUIC dibangun melalui **port UDP dan alamat IP**, namun setelah tersambung, koneksi akan diidentifikasi melalui **"connection ID"**.

Dalam koneksi yang telah terjalin, kedua sisi (klien dan server) bisa membuat stream dan mengirim data satu sama lain. Data di setiap stream akan dikirim secara berurutan dan andal, **namun antar stream bisa saja diterima tidak dalam urutan yang sama** seperti saat dikirim.

QUIC menyediakan **pengaturan aliran (flow control)** baik di tingkat koneksi maupun di tingkat stream.

Lihat penjelasan lebih lanjut di detail [koneksi](quic-connections.md) dan bagian [stream](quic-streams.md).
