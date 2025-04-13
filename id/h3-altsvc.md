# Alt-svc

Header **Alt-svc:** (alternate service) dan frame `ALT-SVC` pada HTTP/2 **bukanlah fitur yang dibuat khusus untuk QUIC atau HTTP/3**. Keduanya merupakan bagian dari mekanisme yang telah dirancang sebelumnya, yang memungkinkan server memberi tahu klien:  
*"Hei, saya menyediakan layanan yang sama di HOST INI, menggunakan PROTOKOL INI, di PORT INI"*.  
Penjelasan lengkapnya bisa dilihat di [RFC 7838](https://tools.ietf.org/html/rfc7838).

Klien yang menerima respon Alt-svc disarankan, jika mendukung dan ingin, untuk **membuka koneksi ke host alternatif tersebut secara paralel di latar belakang**, menggunakan protokol yang ditentukan. Jika koneksi berhasil, klien akan **berpindah dan melanjutkan komunikasi melalui koneksi baru** tersebut, menggantikan koneksi awal.

Misalnya, jika koneksi awal menggunakan HTTP/2 atau bahkan HTTP/1, server bisa merespon dan memberi tahu klien bahwa mereka boleh mencoba beralih ke HTTP/3. Host-nya bisa tetap sama, atau bisa juga diarahkan ke host lain yang tahu cara melayani origin tersebut.  
Informasi dari header Alt-svc ini memiliki **masa berlaku (expiry)**, sehingga klien bisa mengarahkan koneksi dan permintaan berikutnya langsung ke host alternatif, menggunakan protokol yang disarankan, selama periode waktu tertentu.

## Contoh

Sebuah server HTTP menyertakan header `Alt-Svc:` dalam responnya:

```
Alt-Svc: h3=":50781"
```

Ini berarti bahwa **HTTP/3 tersedia melalui port UDP 50781** di host yang sama dengan yang digunakan untuk permintaan ini.

Klien kemudian bisa mencoba membangun koneksi QUIC ke alamat tersebut, dan jika berhasil, akan melanjutkan komunikasi menggunakan koneksi HTTP/3 itu sebagai pengganti koneksi HTTP awal.