## TLS 1.3

Keamanan transport yang digunakan dalam QUIC adalah **TLS 1.3** ([RFC 8446](https://tools.ietf.org/html/rfc8446)), dan **tidak ada koneksi QUIC yang tidak dienkripsi**.

TLS 1.3 memiliki beberapa keunggulan dibandingkan versi TLS yang lebih lama, namun alasan utama penggunaannya dalam QUIC adalah karena TLS 1.3 mengubah proses handshake menjadi **lebih ringkas dengan jumlah round-trip yang lebih sedikit**. Ini secara langsung membantu **mengurangi latensi protokol**.

Versi lama QUIC yang dikembangkan oleh Google menggunakan sistem kriptografi khusus (custom crypto) milik mereka sendiri.