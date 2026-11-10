# Gambar arsitektur MedPair

Diagram dibuat dengan **LaTeX/TikZ**, memakai warna MistyDev dan font Plus Jakarta Sans. Teks dan bentuk pada PDF tetap berupa vektor; PNG dipakai agar gambar langsung tampil di GitHub.

- [PNG untuk README](../../assets/medpair-architecture.png)
- [PDF vektor](medpair-architecture.pdf)
- [Source LaTeX yang dapat diedit](medpair-architecture.tex)
- [Penjelasan arsitektur dan tautan kode](../ARSITEKTUR.md)

## Warna dan font

| Peran | Warna |
| --- | --- |
| Latar navy | `#061723` → `#10233F` |
| Aksen utama | `#00E5FF` |
| Turquoise | `#00B4D8` |
| Sky blue | `#4CC9F0` |
| Teks utama | `#EEF7FC` |

Plus Jakarta Sans Regular dan Bold tersedia di `fonts/`, bersama [SIL Open Font License](fonts/OFL-Plus-Jakarta-Sans.txt). XeLaTeX membaca kedua file langsung; tidak perlu memasang font ke sistem untuk membangun diagram ini.

## Membuat ulang

Siapkan XeLaTeX dengan paket `standalone`, `fontspec`, dan `tikz`, serta Poppler untuk ekspor PNG. Jalankan dari direktori ini:

```sh
xelatex -interaction=nonstopmode -halt-on-error medpair-architecture.tex
pdftoppm -png -singlefile -scale-to 2400 medpair-architecture.pdf ../../assets/medpair-architecture
```

Hasil PNG berukuran 2400 × 1543 piksel. Periksa visual setelah mengubah teks: isi kotak tidak boleh meluber, panah tidak boleh menimpa label, dan seluruh teks harus terbaca. File `.aux`, `.log`, serta file sementara kompilasi tidak disertakan ke Git.

Diagram menunjukkan alur implementasi yang didokumentasikan, bukan semua jalur kegagalan. Source aplikasi, dataset, dan model tetap privat; file TeX di sini hanya source gambar arsitektur.
