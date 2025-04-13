## Lapisan Transport dan Aplikasi

Protokol QUIC versi IETF adalah **protokol transport**, yang dapat digunakan sebagai dasar untuk menjalankan **protokol aplikasi lainnya** di atasnya. Protokol aplikasi pertama yang digunakan di atas QUIC adalah **HTTP/3 (h3)**.

Lapisan transport ini mendukung **koneksi dan stream**.

Versi QUIC lama buatan Google menggabungkan lapisan transport dan HTTP menjadi satu kesatuan — sebuah protokol khusus yang secara spesifik dirancang untuk **mengirim frame HTTP/2 melalui UDP**.