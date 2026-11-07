# Editorial Audit — KALKULATOR GOBLOK

**Tanggal:** 7 November 2026  
**Jenis dokumen:** catatan audit metodologis pascapublikasi  
**Artikel terkait:** [KALKULATOR GOBLOK](../investigations/2026-11-07-kalkulator-goblok-validasi-numerik.md)

## 1. Tujuan catatan

Catatan ini mempertahankan batas antara matematika formal, pengukuran empiris, validitas data, dan interpretasi. Tujuannya mencegah metafora “kalkulator goblok” dibaca sebagai klaim bahwa matematika tidak pasti atau bahwa semua kebenaran hanya bergantung pada kepercayaan manusia.

## 2. Koreksi penting terhadap metafora

### A. 2 + 2 = 4 bukan sekadar rantai kepercayaan

Dalam aritmetika standar, dengan definisi bilangan dan operasi yang ditetapkan, 2 + 2 = 4 adalah konsekuensi matematis. Kebenaran formal tersebut tidak ditentukan oleh siapa yang menekan tombol kalkulator atau siapa yang menyetujui hasilnya.

Yang perlu diperiksa ketika matematika diterapkan pada dunia empiris adalah apakah simbol dan angka yang dimasukkan benar-benar mewakili objek, besaran, periode, atau kejadian yang dimaksud.

### B. Notasi berbeda tidak berarti nilai berbeda

Bilangan dua ditulis 2 dalam desimal dan 10₂ dalam biner. Itu dua representasi untuk nilai yang sama. Hindari menyimpulkan bahwa nilai matematika berubah hanya karena bahasa atau basis penulisannya berbeda.

### C. Kalkulator tidak memvalidasi input empiris

Kalkulator standar menghitung berdasarkan input dan aturan operasi. Ia tidak otomatis memeriksa:
- asal-usul dokumen;
- ketepatan pengukuran;
- kesalahan transkripsi;
- definisi variabel;
- konsistensi satuan;
- periode pelaporan;
- kelengkapan populasi atau sampel;
- kelayakan interpretasi.

Ini adalah batas fungsi, bukan bukti bahwa matematika tidak dapat dipercaya.

## 3. Empat lapisan validasi

1. **Matematis:** operasi, formula, domain, dan aturan pembulatan benar.
2. **Pengukuran:** metode dan alat ukur sesuai dengan besaran yang dimaksud.
3. **Data/provenance:** sumber, tanggal, satuan, transkripsi, versi, dan transformasi dapat ditelusuri.
4. **Interpretasi:** kesimpulan tidak melampaui apa yang didukung data.

Audit dua lapis dalam artikel dapat dikembangkan menjadi empat lapisan ini dalam spesifikasi teknis kalkulator.

## 4. Rekalkulasi angka Bank Ina dari angka pembulatan

Input yang ditampilkan dalam catatan penelitian:
- Aset 2024: Rp24,44 triliun
- Aset 2025: Rp31,30 triliun
- Liabilitas 2024: Rp20,82 triliun
- Liabilitas 2025: Rp27,99 triliun
- Ekuitas 2024: Rp3,61 triliun
- Ekuitas 2025: Rp3,31 triliun

Hasil:
- Pertumbuhan aset: sekitar +28,07%.
- Pertumbuhan liabilitas: sekitar +34,44%.
- Perubahan ekuitas: sekitar -8,31%.

Angka-angka ini adalah hasil hitung ulang dari angka tampilan yang telah dibulatkan. Jangan menyebutnya sebagai rekalkulasi presisi penuh dari laporan audited jika angka dasarnya belum diambil dari laporan lengkap.

### Pemeriksaan persamaan neraca

- 2024: Rp20,82 triliun + Rp3,61 triliun = Rp24,43 triliun, sedangkan aset yang ditampilkan Rp24,44 triliun. Selisih tampilan Rp0,01 triliun.
- 2025: Rp27,99 triliun + Rp3,31 triliun = Rp31,30 triliun, sama dengan aset yang ditampilkan.

Selisih 2024 mungkin berasal dari pembulatan masing-masing komponen. Untuk memastikannya, gunakan angka dengan presisi penuh dari laporan keuangan.

### Pemeriksaan persentase kepemilikan

Enam persentase yang ditampilkan berjumlah 100,00%. Ini memvalidasi penjumlahan angka yang disajikan, bukan identitas, beneficial ownership, atau ketepatan daftar pemegang saham secara independen.

## 5. Rancangan validasi BLOON BANK CALCULATOR

Setiap hasil idealnya menyimpan:
- nilai input asli;
- unit dan periode;
- sumber dan lokasi dokumen;
- tanggal akses atau tanggal dokumen;
- transformasi yang diterapkan;
- formula dan versi formula;
- presisi dan aturan pembulatan;
- hasil;
- status verifikasi sumber;
- status pengujian kode.

### Prinsip implementasi

- Decimal membantu representasi dan operasi desimal yang eksplisit; ia tidak membuktikan validitas sumber.
- Pytest menguji perilaku kode terhadap kasus uji; ia tidak mengesahkan data eksternal.
- Validasi unit dan periode harus dilakukan sebelum operasi lintas-data.
- Rekonsiliasi neraca perlu toleransi yang dinyatakan eksplisit ketika hanya tersedia angka pembulatan.
- Simpan nilai mentah; jangan menimpa data sumber dengan nilai yang sudah dibersihkan atau dibulatkan.
- Catat setiap transformasi agar hasil dapat direproduksi.

## 6. Batas editorial

Jangan menggeneralisasi bahwa seluruh artikel SolitudeLabs membahas satu “rantai kepercayaan” yang sama. Kemiripan pertanyaan metodologis dapat menjadi pintu perbandingan, tetapi bukan bukti bahwa kasus-kasus berbeda saling berhubungan.

Contoh tanah, peta, folklore, ingatan lokal, dan data keuangan memiliki jenis bukti serta prosedur validasi yang berbeda. Perbandingan hanya sah pada tingkat pertanyaan metodologis yang dinyatakan secara terbatas.

Jangan pula menyatakan bahwa lembaga, profesi, atau platform tertentu menjamin kebenaran 100%. Sebut kewenangan dan batas verifikasi secara spesifik, berdasarkan sumber yang sesuai.

## 7. Kesimpulan audit

Metafora “Kalkulator Goblok” efektif untuk mengingatkan bahwa alat hitung tidak otomatis memvalidasi input empiris. Namun, metafora tersebut tidak boleh mengaburkan kepastian matematika formal.

Rumusan yang lebih presisi:

> Matematika menjamin konsekuensi dari premis dan aturan yang ditetapkan. Audit empiris memeriksa apakah premis, pengukuran, data, dan interpretasi memang layak digunakan.

**GOBLOK BOLEH. NGARANG JANGAN.**
