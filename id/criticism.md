# Kritik Umum

## UDP tidak akan pernah berhasil

Banyak perusahaan, operator, dan organisasi memblokir atau membatasi lalu lintas UDP di luar port 53 (yang digunakan untuk DNS), karena dalam beberapa tahun terakhir UDP lebih sering disalahgunakan untuk serangan. Secara khusus, beberapa protokol UDP yang ada dan implementasi server yang populer rentan terhadap serangan amplifikasi, di mana seorang penyerang dapat menyebabkan lalu lintas keluar dalam jumlah besar ke korban yang tidak bersalah.

QUIC memiliki perlindungan bawaan terhadap serangan amplifikasi dengan mensyaratkan bahwa paket awal harus berukuran minimal 1200 byte dan juga dengan adanya aturan dalam protokol yang menetapkan bahwa server tidak boleh mengirimkan respon yang ukurannya melebihi tiga kali ukuran permintaan, kecuali telah menerima paket respon dari klien.

## UDP lambat di kernel

Hal ini tampaknya benar, setidaknya pada awalnya. Tentu saja kita tidak bisa memastikan bagaimana perkembangan ke depannya, dan seberapa besar hal ini merupakan akibat dari kurangnya fokus pengembangan pada performa transfer UDP selama bertahun-tahun.

Namun bagi sebagian besar klien, "kelambatan" ini mungkin bahkan tidak terasa sama sekali.

## QUIC memakan terlalu banyak CPU

Mirip dengan kritik "UDP lambat" sebelumnya, hal ini sebagian besar karena penggunaan TCP dan TLS telah lebih matang, mengalami banyak perbaikan, dan bahkan mendapat dukungan perangkat keras selama bertahun-tahun.

Ada alasan untuk percaya bahwa ini akan membaik seiring waktu. Bahkan [kita sudah mulai melihat peningkatan di bidang ini](https://www.fastly.com/blog/measuring-quic-vs-tcp-computational-efficiency).
Pertanyaannya adalah, seberapa besar penggunaan CPU tambahan ini akan menjadi beban bagi para penyedia layanan.

## Ini hanya proyek Google

Bukan. Google memang membawa spesifikasi awal ke IETF setelah sebelumnya membuktikan, dalam skala Internet yang besar, bahwa menerapkan protokol seperti ini melalui UDP memang bisa dilakukan dan memberikan performa yang baik.

Sejak itu, individu dari berbagai perusahaan dan organisasi telah bekerja di bawah naungan IETF—organisasi netral vendor—untuk menyusun protokol transportasi standar dari spesifikasi tersebut. Dalam proses itu, tentu saja karyawan Google ikut terlibat, tetapi begitu juga karyawan dari banyak perusahaan lain yang tertarik memajukan protokol transport di Internet, termasuk Mozilla, Fastly, Cloudflare, Akamai, Microsoft, Facebook, dan Apple.

## Peningkatannya terlalu sedikit

Ini sebenarnya bukan kritik, melainkan opini. Mungkin benar, dan mungkin peningkatannya terlalu kecil mengingat HTTP/2 baru saja dirilis belum lama ini.

HTTP/3 diperkirakan akan memberikan performa jauh lebih baik di jaringan yang rawan kehilangan paket. Ia juga menawarkan proses handshake yang lebih cepat sehingga akan mengurangi latensi baik secara nyata maupun yang dirasakan. Namun, apakah manfaat tersebut cukup besar untuk mendorong orang mengaktifkan dukungan HTTP/3 di server dan layanan mereka? Waktu dan hasil pengujian performa di masa depan akan menjawabnya!
