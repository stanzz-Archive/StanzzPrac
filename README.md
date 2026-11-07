# PracByStanzz 2.0.0 (rekonstruksi source)

Target: Paper 1.21.4, Java 21. Citizens bersifat soft-depend untuk NPC player.

## Fitur yang disiapkan
- Kit bernomor: `/kit 1`, `/kit 2`, dst.
- Admin membuat/mengubah kit default dari inventory: `/kitadmin set <slot>`; hapus: `/kitadmin delete <slot>`; daftar: `/kitadmin list`.
- Member mengambil kit default dan menyimpan loadout pribadi: `/kit edit <slot>`, atur inventory, lalu `/kit save`.
- `/rtp` lokasi acak aman dengan cooldown.
- `/rtpq` antrean matchmaking dua pemain (memasangkan pemain di sekitar lokasi pemain pertama; belum memakai sistem arena terpisah).
- `/tpa`, `/tpaccept`, `/tpdeny`, `/tpacancel`.
- Scoreboard sidebar.
- `/practicebot spawn|remove`: NPC player Citizens, follow/serang dasar, dan refill totem.

## Build
Jalankan `mvn clean package` dengan Java 21 dan koneksi internet untuk mengambil Paper API. Output: `target/PracByStanzz-2.0.0.jar`.

## Instalasi
1. Pastikan server Paper 1.21.4 memakai Java 21.
2. Pasang Citizens versi yang kompatibel jika ingin NPC player.
3. Masukkan JAR hasil build ke `plugins/`.
4. Restart server.
5. Beri permission `pracbystanzz.admin` untuk admin.

## Catatan penting
Ini adalah rekonstruksi source berdasarkan JAR yang tersedia, bukan source asli. Build dan runtime belum dapat diverifikasi di lingkungan ini. NPC Citizens menggunakan API melalui reflection agar Citizens tetap opsional; kompatibilitas method perlu diuji dengan build Citizens yang dipakai. Antrean saat ini hanya matchmaking dasar dan belum menyediakan arena/round/reset/statistik seperti jaringan Practice besar.


## GitHub Actions
The workflow at `.github/workflows/build.yml` attempts a Maven build on pushes, pull requests, or manual runs. A successful run uploads the JAR as an Actions artifact.
