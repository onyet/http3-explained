# Server Push di HTTP/3

**Server push di HTTP/3** mirip dengan apa yang dijelaskan dalam HTTP/2 ([RFC 7540](https://httpwg.org/specs/rfc7540.html)), tetapi menggunakan mekanisme yang berbeda.

Server push pada dasarnya adalah **respon terhadap permintaan yang tidak pernah dikirim oleh klien**!

Push dari server **hanya diperbolehkan jika klien telah menyetujuinya terlebih dahulu**. Dalam HTTP/3, klien bahkan menetapkan batas jumlah push yang diterima dengan memberi tahu server **ID stream push maksimum** yang diizinkan. Jika server melampaui batas itu, maka koneksi akan dianggap mengalami kesalahan (error).

Jika server merasa bahwa klien kemungkinan membutuhkan sumber daya tambahan yang belum diminta (tetapi seharusnya diperlukan), server bisa mengirim frame `PUSH_PROMISE` (melalui stream permintaan) yang menunjukkan bentuk permintaan seolah-olah klien mengirimnya, lalu mengirimkan respon sebenarnya lewat stream baru.

Meskipun klien sebelumnya sudah menyatakan bahwa push diperbolehkan, **setiap stream push individual tetap bisa dibatalkan kapan saja** jika klien menganggapnya tidak diperlukan. Klien cukup mengirim frame `CANCEL_PUSH` ke server.

## Permasalahan

Sejak fitur ini pertama kali dibahas dalam pengembangan HTTP/2, dan bahkan setelah protokolnya dirilis serta digunakan di Internet, fitur server push ini **telah banyak menuai kritik, perdebatan, dan modifikasi**, demi membuatnya benar-benar berguna.

Server push **tidak pernah benar-benar “gratis”**, karena meskipun menghemat satu kali round-trip, ia tetap menggunakan bandwidth.  
Selain itu, **server sering kali sulit — atau bahkan mustahil — untuk mengetahui secara pasti apakah sebuah sumber daya benar-benar perlu dipush atau tidak.**