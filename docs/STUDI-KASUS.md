# MedPair — studi kasus MistyDev

**MedPair** adalah prototipe Android untuk menelusuri referensi interaksi dua obat dan mengeksplorasi hipotesis model MLP. Fokus studi kasus ini adalah cara menyajikan asal informasi, membedakan keluaran referensi dari model, dan memberi ruang untuk membaca batas hasil.

Repositori publik ini berisi **dokumentasi, arsitektur, dan media demo**. Source aplikasi, tes, paket referensi, serta bobot model dipertahankan secara lokal. APK untuk unduhan publik belum disediakan dan masih memerlukan pemeriksaan paket distribusi. Ringkasan dan materi demo tersedia melalui [halaman utama](../README.md).

## Kebutuhan yang dieksplorasi

Pencarian interaksi dua obat melalui HP perlu menampilkan lebih dari satu hasil singkat. Pembaca juga perlu mengetahui dari mana catatan berasal, bagaimana identitas obat dicocokkan, dan apakah informasi tersebut merupakan catatan sumber atau dugaan model.

MedPair mengeksplorasi kebutuhan itu melalui paket referensi lokal dan halaman eksperimen MLP yang terpisah. Kebutuhan dan kemudahan penggunaannya masih perlu diuji bersama calon pengguna; keberadaan demo belum membuktikan bahwa alurnya sudah mudah dipahami.

## Alur yang ditampilkan

1. **Pilih dua obat.** Cari nama, alias, atau ID dari katalog, lalu tempatkan pilihan pada Obat A dan Obat B.
2. **Buka catatan referensi.** Tombol **Periksa interaksi** menampilkan informasi pasangan dari paket sumber, termasuk tingkat interaksi bila tersedia.
3. **Telusuri asal catatan.** Bagian **Sumber & data** memperlihatkan sumber, identitas obat, serta konteks dan batas informasi. Membuka situs sumber memerlukan internet.
4. **Jalankan model secara eksplisit.** Halaman **Model MLP** memiliki tombol **Jalankan MLP**. Inferensi TensorFlow Lite menghasilkan keluaran untuk dua susunan input, A–B dan B–A.
5. **Baca hasil sesuai jenisnya.** Keluaran model diberi label hipotesis. Jika tidak ada label yang memenuhi ambang pada suatu susunan, prediksi untuk susunan itu ditahan. Panduan membantu menjelaskan arti hasil tersebut.

Susunan A–B dan B–A adalah posisi input model, bukan urutan minum obat. Prediksi yang ditahan maupun catatan yang tidak ditemukan tidak berarti pasangan obat aman.

## Keputusan desain

Pencarian referensi tidak otomatis menjalankan model. Tombol MLP yang terpisah membuat perpindahan dari membaca sumber ke mengeksplorasi hipotesis menjadi tindakan yang disengaja. Hasil model tidak dipakai untuk mengganti catatan referensi, menentukan dosis, atau mengisi tingkat DDInter.

Asal catatan juga mendapat ruang tersendiri. Ringkasan dapat dibaca lebih dahulu, lalu rincian dibuka untuk melihat sumber dan konteksnya. Pada video demo, bagian rincian sumber diperpanjang agar pembaca mempunyai waktu untuk mengikutinya.

Pengembangan dilakukan secara iteratif: meninjau hasil, menentukan prioritas desain, dan memperbaiki alur pembacaan. Rekaman demo menunjukkan hasil iterasi pada pencarian obat, navigasi, dan penyajian sumber.

## Contoh dari rekaman aplikasi

Demo menggunakan **aspirin sebagai A** dan **warfarin sebagai B**. Hasil berikut berasal dari rekaman aplikasi, bukan hasil inferensi baru saat dokumen ini disusun.

| Bagian | Yang terlihat pada contoh |
| --- | --- |
| Referensi | Catatan TDC/DrugBank berjenis Y6; DDInter dari snapshot lama menampilkan tingkat Major |
| Rincian sumber | Asal catatan dan identitas pasangan dapat ditelusuri melalui aplikasi |
| Model, susunan A–B | Hipotesis Y6 |
| Model, susunan B–A | Prediksi ditahan karena tidak ada label yang memenuhi ambang |

Kesamaan label Y6 pada referensi dan model tidak membuktikan validasi klinis model. Perbedaan hasil dua susunan juga tidak menentukan keamanan kombinasi.

Video **v14** berdurasi **59,8 detik**, memakai rekaman HP asli, narasi rekaman suara, ilustrasi penjelas, dan subtitle Indonesia. Ilustrasi di samping layar membantu menjelaskan alur; tampilan aplikasi tetap berasal dari rekaman nyata.

## Bukti dan batas hasil

Penjelasan teknis diperbarui dari tinjauan kode internal pada 10 November 2026 dan bahan demo v14. Pada tanggal tersebut, pengujian lokal mencatat analisis statis tanpa temuan dan 64 tes unit/widget dengan fixture lulus. Source dan suite tes tidak didistribusikan dalam repo publik. Pemeriksaan tersebut tidak mencakup build Android, paket data asli, atau inferensi MLP native pada perangkat.

Rancangan memakai aset lokal; rekaman demo dan pengambilan dependensi dari cache tidak dijadikan bukti pengujian offline baru.

MedPair masih merupakan prototipe riset yang belum tervalidasi klinis. Draf teks Indonesia dan pencocokan identitas lintas sumber belum ditinjau apoteker. Skor model bukan probabilitas keamanan atau ukuran ketepatan klinis. Rincian implementasi dijelaskan dalam [arsitektur](ARSITEKTUR.md).

## Langkah berikutnya

Prioritas selanjutnya adalah memperoleh masukan calon pengguna: apakah catatan sumber, hipotesis, dan prediksi yang ditahan dapat dibedakan tanpa penjelasan tambahan? Temuan tersebut akan menjadi dasar perbaikan bahasa, urutan informasi, dan panduan.

Tinjauan identitas obat dan teks oleh pihak yang sesuai serta evaluasi model pada data independen tetap diperlukan sebelum memperluas klaim penggunaan. Belum ada hasil uji pengguna atau validasi klinis yang dilaporkan dalam showcase ini.
