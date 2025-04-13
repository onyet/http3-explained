# Handshake Cepat

QUIC menawarkan dua jenis proses koneksi: 0-RTT dan 1-RTT. Artinya, dalam kondisi terbaiknya, QUIC bisa membangun koneksi tanpa perlu bolak-balik (round-trip) tambahan sama sekali. Yang paling cepat di antara keduanya adalah 0-RTT handshake, yang hanya bisa digunakan jika sebelumnya sudah pernah ada koneksi ke host yang sama, dan rahasia (secret) dari koneksi sebelumnya masih tersimpan.

## Early Data (Data Dini)

QUIC memungkinkan klien untuk langsung menyertakan data saat melakukan 0-RTT handshake. Fitur ini memungkinkan klien mengirim data ke server secepat mungkin, sehingga server juga bisa langsung merespon dan mengirim balik data dengan lebih cepat lagi.
