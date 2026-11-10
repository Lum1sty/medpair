# Media dan aset MedPair

## Materi demonstrasi

| Berkas | Isi |
| --- | --- |
| [Sampul](../assets/medpair-cover.png) | Identitas MistyDev dengan dua tampilan aplikasi asli |
| [Video demo](../assets/medpair-demo.mp4?raw=true) | Versi v14, 59,8 detik, 1080p30, narasi dan subtitle Indonesia permanen |
| [Menu utama](../assets/screenshots/01-menu.png) | Potongan layar aplikasi dari detik 5,10 video final |
| [Pemilihan obat](../assets/screenshots/02-pilih-obat.png) | Potongan layar aplikasi dari detik 14,20 |
| [Catatan referensi](../assets/screenshots/03-referensi.png) | Potongan layar aplikasi dari detik 24,43 |
| [Hipotesis model](../assets/screenshots/04-model.png) | Potongan layar aplikasi dari detik 42,97 |

Rekaman penggunaan berasal dari HP Android. Screenshot adalah potongan area aplikasi dari video yang sama, dengan isi layar dipertahankan. Diagram di sisi kanan video merupakan ilustrasi penjelas, bukan bagian antarmuka aplikasi. Narasi menggunakan rekaman suara dengan jeda yang disusun mengikuti animasi.

## Diagram arsitektur yang dapat diedit

| Berkas | Kegunaan |
| --- | --- |
| [PNG arsitektur](../assets/medpair-architecture.png) | Pratinjau pada README dan dokumentasi |
| [PDF arsitektur](architecture/medpair-architecture.pdf) | Versi vektor untuk dibaca atau diekspor |
| [Source TeX](architecture/medpair-architecture.tex) | Sumber diagram delapan komponen yang dapat diedit |
| [Panduan diagram](architecture/README.md) | Petunjuk membangun kembali diagram dan keluaran |

Diagram arsitektur merujuk kelas yang ditinjau pada kode internal. Diagram menjelaskan jalur utama pemilihan pasangan, pembacaan referensi, dan inferensi eksplisit; bukan seluruh cabang kegagalan atau arsitektur layanan klinis. Source aplikasi tidak disertakan, sedangkan source TeX untuk diagram tetap dapat diedit.

## Identitas dan font

Identitas visual menggunakan logo MistyDev dan palet navy–cyan. Teks grafis dan diagram memakai **Plus Jakarta Sans**. Salinan font untuk diagram kini disertakan di [`docs/architecture/fonts/`](architecture/fonts), bersama [SIL Open Font License](architecture/fonts/OFL-Plus-Jakarta-Sans.txt).

Antarmuka aplikasi yang terlihat pada rekaman memakai **Nunito Sans**. Berkas font aplikasi dan lisensinya tetap bersama paket aplikasi lokal, terpisah dari font diagram yang disertakan di sini. Lisensi font diagram tidak menetapkan lisensi untuk seluruh repo atau data sumber.

## Cakupan portofolio

Repositori publik mencakup dokumentasi, diagram beserta source TeX dan fontnya, serta media demonstrasi. Source aplikasi, tes, dataset, paket referensi, bobot model, APK, kredensial, konfigurasi mesin, cache, serta catatan kerja internal tidak disertakan.

APK untuk unduhan publik belum disediakan. Ketersediaan video dan screenshot tidak berarti paket aplikasi sudah tersedia untuk diunduh; paket distribusi masih memerlukan pemeriksaan isi dan izin data/model.

Materi demo memperlihatkan alur perangkat lunak dan keputusan penyajian informasi. Video tidak membuktikan validasi klinis, ketepatan untuk semua pasangan obat, atau pengujian jaringan dalam mode pesawat.

Screenshot dan video dapat memperlihatkan kutipan catatan serta nama sumber pada aplikasi. Distribusi media ini tidak memberikan lisensi atas seluruh dataset atau materi pihak ketiga. Repositori belum menetapkan lisensi penggunaan ulang menyeluruh; atribusi sumber pada tampilan yang relevan tetap dipertahankan.
