# Stream QUIC dan HTTP/3

**HTTP/3 dibuat khusus untuk QUIC**, sehingga dapat memanfaatkan fitur **stream milik QUIC secara penuh**, berbeda dengan HTTP/2 yang harus merancang sistem stream dan multiplexing-nya sendiri di atas TCP.

Permintaan HTTP yang dilakukan melalui HTTP/3 menggunakan **kumpulan stream khusus**.

## Frame di HTTP/3

HTTP/3 bekerja dengan cara **membuka stream QUIC dan mengirimkan kumpulan frame** ke sisi lainnya.  
Jumlah frame yang dikenal di HTTP/3 relatif sedikit (pada 18 Desember 2018, hanya ada **sembilan jenis**!).  
Beberapa yang paling penting antara lain:

- `HEADERS` — mengirimkan header HTTP yang telah dikompresi  
- `DATA` — mengirimkan konten data biner  
- `GOAWAY` — memberi tahu untuk menutup koneksi ini

## Permintaan HTTP (HTTP Request)

Klien mengirimkan permintaan HTTP-nya melalui **stream QUIC dua arah** (bidirectional) yang dimulai dari sisi klien.

Satu permintaan terdiri dari **satu frame `HEADERS`**, dan bisa diikuti oleh satu atau lebih frame tambahan seperti:

- Satu atau beberapa frame `DATA`  
- Satu frame `HEADERS` tambahan di akhir untuk **trailer**

Setelah permintaan dikirim, klien akan **menutup stream pengiriman**.

## Respon HTTP (HTTP Response)

Server mengirimkan respon HTTP-nya **melalui stream dua arah yang sama**.  
Respon terdiri dari:

- Frame `HEADERS`  
- Satu atau beberapa frame `DATA`  
- Dan (jika ada) satu frame `HEADERS` tambahan untuk trailer

## Header QPACK

Frame `HEADERS` berisi header HTTP yang dikompresi menggunakan algoritma **QPACK**.  
QPACK mirip dengan kompresi HPACK pada HTTP/2 ([RFC 7541](https://httpwg.org/specs/rfc7541.html)), tetapi telah dimodifikasi agar **bisa bekerja dengan stream yang diterima tidak berurutan (out of order)**.

QPACK menggunakan **dua stream QUIC satu arah tambahan** antara dua titik koneksi. Stream ini digunakan untuk membawa **informasi tabel dinamis (dynamic table)** ke kedua arah.