# Prioritas dalam HTTP/3

Spesifikasi dasar HTTP/3 **tidak secara langsung mendefinisikan sistem prioritas**. Pendekatan prioritas yang digunakan di HTTP/2 dianggap **terlalu rumit** dan telah dinyatakan usang dalam revisi terbaru spesifikasi HTTP/2 [RFC 9113](https://www.rfc-editor.org/rfc/rfc9113.html).

Sebagai gantinya, diperkenalkan **skema prioritas yang lebih sederhana**, yaitu **Extensible Prioritization Scheme for HTTP** ([RFC 9218](https://www.rfc-editor.org/rfc/rfc9218.html)), yang bisa digunakan baik pada HTTP/2 maupun HTTP/3.

Di HTTP/3, sinyal prioritas dikirim dalam bentuk **field header `Priority`** dan/atau frame **`PRIORITY_UPDATE`** yang dikirim melalui **HTTP/3 Control Stream**. Server dapat memanfaatkan sinyal ini untuk mengatur jadwal pengiriman konten respon HTTP.

[RFC 9218](https://www.rfc-editor.org/rfc/rfc9218.html) juga memberikan panduan penjadwalan yang bertujuan untuk **meningkatkan performa aplikasi web pada sisi klien**.