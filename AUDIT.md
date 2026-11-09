# Repository Audit — Ripanrz/Ripanrz

**Tanggal audit:** 9 November 2026  
**Cakupan:** profile README, aset yang direferensikan, dan GitHub Actions workflows pada branch `main`.  
**Metode:** static repository review melalui isi file dan metadata GitHub. Bukan penetration test atau pengujian runtime menyeluruh.

## Ringkasan Eksekutif

Repository ini adalah GitHub profile repository. Fondasinya sudah berfungsi: README berisi identitas, teknologi, tautan sosial, serta workflow otomatis untuk contribution snake dan metrics.

Sebelum pembaruan, presentasi terlalu padat badge, hierarki informasi belum kuat, dan workflow belum sepenuhnya deterministik. Branch ini merapikan README, menambahkan hero samurai pixel-art lokal, serta memperketat konfigurasi workflow.

## Temuan

| ID | Tingkat | Temuan | Dampak |
|---|---|---|---|
| A-01 | Medium | README sebelumnya memuat daftar badge teknologi yang sangat panjang dan kategori yang saling tumpang tindih. | Sinyal kompetensi utama tenggelam; recruiter perlu memindai terlalu banyak elemen. |
| A-02 | Medium | Markup README sebelumnya memiliki elemen `div` pada bagian analytics yang tidak ditutup sebelum bagian berikutnya. | Struktur HTML berisiko ditafsirkan berbeda antar-renderer. |
| A-03 | Medium | Workflow snake menggunakan `actions/checkout@v2` dan `crazy-max/ghaction-github-pages@v3.1.0`. | Dependensi aksi lama menambah beban pemeliharaan dan ketidakjelasan runtime. |
| A-04 | Medium | Workflow publikasi branch `output` tidak mendeklarasikan `permissions` secara eksplisit. | Workflow bergantung pada default permission repository. |
| A-05 | Low | Workflow metrics menggunakan tag bergerak `lowlighter/metrics@latest`. | Implementasi action dapat berubah tanpa perubahan workflow, sehingga build kurang reproducible. |
| A-06 | Low | `github-metrics.svg` tersimpan di root tetapi tidak ditampilkan aktif pada README sebelumnya; SVG memakai `foreignObject`. | Aset tidak berkontribusi pada profil aktif; dukungan `foreignObject` berbeda antar-image renderer. |

## Perubahan pada Branch Ini

1. **README dirancang ulang**: identitas, ringkasan profesional, bidang fokus, teknologi, eksplorasi, aktivitas, dan kontak.
2. **Hero samurai pixel-art** dibuat sebagai SVG lokal. Tidak memakai remote image host, JavaScript eksternal, atau font eksternal. Animasi CSS menghormati `prefers-reduced-motion`.
3. **Contribution snake workflow** diperbarui ke `actions/checkout` v7.0.1 dan `crazy-max/ghaction-github-pages` v5.0.0 yang dipin menggunakan commit SHA, disertai `contents: write` dan concurrency control.
4. **Metrics workflow** dipin ke commit SHA rilis v3.34 dan diberi izin `contents: write` eksplisit.

## Risiko dan Batas Audit

- Status dan nilai secret `METRICS_TOKEN` tidak dapat diperiksa dari audit file publik. Pastikan secret tersedia serta memiliki akses minimum yang diperlukan.
- Keberhasilan workflow perlu dikonfirmasi pada tab **Actions** setelah perubahan digabungkan atau dijalankan manual.
- Rendering animasi SVG dapat berbeda menurut browser, mode preview, dan sanitizer platform. Browser modern yang mendukung CSS animation akan menampilkan gerakan; preferensi reduced-motion menonaktifkannya.
- Pinning commit SHA meningkatkan repeatability, tetapi versi action tetap perlu diperbarui berkala melalui Dependabot atau review manual.
- Klaim kompetensi README harus sesuai pengalaman yang dapat dibuktikan. Badge dan logo bukan bukti tingkat kemahiran.

## Rekomendasi Lanjutan

### Prioritas Tinggi
- Aktifkan Dependabot untuk GitHub Actions.
- Pastikan repository Actions permission mengikuti prinsip least privilege.
- Jalankan kedua workflow secara manual setelah merge dan periksa hasilnya.
- Tambahkan validasi otomatis sederhana untuk struktur Markdown/HTML README.

### Prioritas Menengah
- Tambahkan 2–3 pinned projects berisi masalah, kontribusi, teknologi, serta hasil yang terukur.
- Pisahkan teknologi yang pernah digunakan dari teknologi yang dikuasai secara praktis.
- Tambahkan tautan demo atau dokumentasi proyek paling relevan dengan AI Engineering, Embedded Systems, dan Industrial Automation.

### Prioritas Rendah
- Hapus atau regenerasi `github-metrics.svg` apabila tidak lagi digunakan.
- Tinjau layanan statistik eksternal secara berkala agar gangguan pihak ketiga tidak mendominasi halaman profil.

## Kesimpulan

Perubahan meningkatkan keterbacaan, konsistensi visual, dan maintainability workflow. Repository **belum** dinyatakan lolos penetration test atau runtime validation; keduanya memerlukan pengujian terpisah setelah perubahan diterapkan.
