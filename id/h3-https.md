# URL `HTTPS://`

HTTP/3 akan digunakan dengan **URL berawalan `HTTPS://`**. Karena dunia saat ini sudah dipenuhi dengan URL seperti ini, maka dianggap **tidak praktis dan tidak masuk akal** untuk memperkenalkan skema URL baru hanya demi protokol baru. Seperti halnya HTTP/2 yang juga tidak memerlukan skema baru, HTTP/3 pun demikian.

Namun, ada sedikit tambahan kompleksitas dalam kasus HTTP/3. Kalau HTTP/2 merupakan cara baru dalam mentransfer HTTP lewat jaringan, **ia tetap menggunakan TLS dan TCP seperti HTTP/1**. Sedangkan HTTP/3 dibangun di atas **QUIC**, yang membuat ada beberapa aspek penting yang berubah.

URL warisan yang masih menggunakan `HTTP://` secara teks-jelas (clear-text) akan tetap seperti apa adanya. Seiring dengan masa depan yang semakin mengarah pada transfer data yang aman, penggunaan `HTTP://` kemungkinan akan semakin jarang.  
Permintaan ke URL seperti itu **tidak akan di-upgrade** ke HTTP/3. Faktanya, URL jenis ini juga jarang di-upgrade ke HTTP/2, meskipun alasannya berbeda.

## Koneksi Awal

Koneksi pertama ke host yang masih baru (belum pernah dikunjungi sebelumnya) dengan URL `HTTPS://` kemungkinan besar harus dilakukan melalui **TCP terlebih dahulu** (dengan kemungkinan upaya paralel juga ke QUIC). Bisa jadi server tersebut masih merupakan server lama yang **belum mendukung QUIC**, atau ada **perangkat di tengah (middle box)** yang menghalangi koneksi QUIC.

Dalam kasus yang ideal, klien dan server modern akan dinegosiasikan menggunakan **HTTP/2** saat handshake pertama. Setelah koneksi terbentuk dan server merespon permintaan HTTP dari klien, server kemudian dapat memberi tahu bahwa ia **mendukung dan lebih memilih HTTP/3**.