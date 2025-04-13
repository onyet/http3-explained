# Penjelasan HTTP/3

Penulisan buku ini dimulai pada Maret 2018. Rencananya adalah mendokumentasikan HTTP/3 dan protokol dasar yang mendasarinya: QUIC. Mengapa protokol ini ada, bagaimana cara kerjanya, detail protokol, implementasi, dan lainnya.

Buku ini sepenuhnya gratis dan dimaksudkan sebagai upaya kolaboratif yang melibatkan siapa pun yang ingin membantu.

## Prasyarat

Pembaca buku ini diharapkan memiliki pemahaman dasar tentang jaringan TCP/IP, dasar-dasar HTTP, dan web. Untuk wawasan lebih lanjut dan detail tentang HTTP/2, kami merekomendasikan untuk terlebih dahulu membaca [http2 explained](https://daniel.haxx.se/http2/).

## Penulis

Buku ini dibuat dan ditulis oleh [Daniel Stenberg](https://daniel.haxx.se/). Daniel adalah pendiri dan pengembang utama dari [curl](https://curl.haxx.se/), perangkat lunak klien HTTP yang paling banyak digunakan di dunia. Daniel telah bekerja dengan HTTP dan protokol internet selama lebih dari dua dekade dan merupakan penulis dari [http2 explained](https://daniel.haxx.se/http2/).

## Halaman Utama

Halaman utama untuk buku ini dapat ditemukan di
[daniel.haxx.se/http3-explained](https://daniel.haxx.se/http3-explained).

## Ikut Berkontribusi

Jika Anda menemukan kesalahan, kekurangan, atau ketidakakuratan dalam dokumen ini, silakan kirimkan versi paragraf yang telah diperbaiki dan kami akan membuat versi yang diperbarui. Kami akan memberikan kredit yang pantas kepada semua orang yang membantu. Saya berharap dokumen ini akan menjadi lebih baik seiring waktu.

Sebisa mungkin, kirimkan [laporan kesalahan](https://github.com/bagder/http3-explained/issues) atau [pull requests](https://github.com/bagder/http3-explained/pulls) di halaman GitHub buku ini.

## Lisensi

Dokumen ini dan seluruh isinya dilisensikan di bawah [Creative Commons Attribution 4.0 license](https://creativecommons.org/licenses/by/4.0/).
