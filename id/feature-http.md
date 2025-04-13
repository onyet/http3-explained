## HTTP/3 di atas QUIC

Lapisan HTTP, yang disebut HTTP/3, melakukan pengiriman data dengan gaya HTTP, termasuk kompresi header HTTP menggunakan QPACK — yang mirip dengan metode kompresi pada HTTP/2 yang dikenal sebagai HPACK.

Algoritma HPACK bergantung pada pengiriman berurutan antar stream, sehingga tidak bisa langsung digunakan di HTTP/3 tanpa modifikasi, karena QUIC menyediakan stream yang bisa dikirim secara tidak berurutan.
QPACK bisa dianggap sebagai versi [HPACK](https://httpwg.org/specs/rfc7541.html) yang telah disesuaikan untuk QUIC.
