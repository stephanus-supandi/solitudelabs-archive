---
title: "GSV Audit — Handoff Spec & State"
project: "SolitudeLabs"
document_type: "audit-handoff"
version: "1.0"
status: "working"
last_batch: "B86"
last_updated: "2026-11-23"
language: "id"
canonical_source: true
---

# GSV Audit — Handoff Spec & State (SolitudeLabs)

> Dokumen handoff ringkas untuk model penerus dan peneliti. Isinya satu definisi aturan, tier pembuktian, state, katalog eskalasi, log batch, dan jebakan yang sudah dilewati. Laporan batch lengkap tetap menjadi jejak kerja terpisah. Prinsip utamanya: jangan menghakimi benar/salahnya koordinat hanya dari tampilan Street View.

**Status sumber:** Dokumen ini merangkum deskripsi dan hasil audit yang disampaikan pengguna sampai B86. Screenshot asli, koordinat, data listing mentah, dan catatan lapangan tidak diperiksa ulang dalam proses pengarsipan ini. Angka kumulatif di bawah adalah state yang dilaporkan, bukan hasil hitung ulang independen dari seluruh arsip mentah.

## 0. Tugas dan batas ruang lingkup

Audit marker (pin merah) dan metadata POI pada tangkapan layar Google Street View (SV): nama, kategori, rating, jam, durasi rute, AI summary, dan photo strip. Setiap frame dicatat menurut apa yang benar-benar terlihat. Hubungan antarfame diuji tanpa menganggap kemiripan nama, kedekatan, satu ruas jalan, atau objek latar sebagai bukti identitas maupun koordinat.

Tujuannya bukan memperbaiki peta atau menebak mekanisme Google, melainkan menjaga batas antara observasi, hipotesis, dan verifikasi.

## 1. Aturan inti — generatif

> **Pairing identitas visual boleh dilakukan; tetapi jangan menyimpulkan kesalahan spasial, perpindahan koordinat, atau re-appearance longitudinal tanpa bukti yang memenuhi syarat.** Untuk klaim longitudinal, diperlukan entitas/listing yang sama dan koordinat yang dapat dibandingkan pada pass berbeda, atau bukti record yang sama benar-benar hilang pada catatan lintas tanggal yang sebanding. Semua petunjuk lain tetap gejala, konteks, atau hipotesis—bukan vonis.

Syarat record-hilang tidak terpenuhi hanya karena pin tidak tampak dalam screenshot yang terpotong, frame berbeda, atau tampilan yang tidak sebanding. Identitas record, tanggal, cakupan, dan konteks pembanding harus dapat ditelusuri.

### Turunan aturan

- **Match identitas ≠ koordinat.** “Match-fisik-eksternal-kebaca-penuh” berarti nama pembeda terbaca pada media fisik eksternal yang tampak dalam frame (fasad, banner, atau signage). Itu mengonfirmasi identitas visual pada frame tersebut. Banyaknya match, media, atau pengulangan tidak mengubahnya menjadi verifikasi koordinat. Verifikasi koordinat memerlukan bukti independen yang sesuai, misalnya survei lapangan, koordinat yang dapat diperiksa, registri usaha yang relevan, atau konfirmasi operator.
- **Re-appearance ≠ uji longitudinal.** Dua atau lebih kemunculan baru dapat diuji secara longitudinal jika listing/entitas yang sama dapat diidentifikasi dan koordinatnya dapat dibandingkan pada pass yang berbeda. Kemunculan intra-batch, lintas-batch, scene identik atau berbeda total, ada/tidaknya objek pengikat, serta kombinasi status UNRESOLVED dan match satu-frame tidak menggantikan syarat tersebut.
- **Rekurensi background/generic/ad ≠ rekurensi listing.** Signage jauh, landmark, iklan-NPC, atau nama chain generik yang muncul di pixel tanpa pin aktif untuk listing yang sama bukan re-appearance listing dan bukan bukti koordinat.
- **Token-share ≠ entitas.** Kesamaan sebagian token—nama orang, brand, lokasi, kategori, material, angka, singkatan, honorifik, kutipan, atau keterangan dalam tanda kurung—tidak membuktikan satu entitas jika bagian pembeda berbeda. Ejaan mirip seperti “Ma'isa” dan “Mak Isa”, atau “Sabila” dan “Syahbila”, bukan konfirmasi identitas.
- **Mismatch ≠ vonis error.** Perbedaan pin dan signage/objek sekitar, termasuk beda total, dapat memiliki banyak penjelasan: co-tenancy, papan lama, listing duplikat, proyeksi, atau normalisasi tampilan. Catat mismatch sebagai observasi/gejala; jangan menyebut peta salah tanpa bukti spasial independen.
- **Metadata ≠ bukti spasial.** Kategori, jam, jumlah ulasan, durasi rute (misalnya “35 min”), price range, AI summary (“Know before you go…”), dan photo strip user-upload dicatat sebagai metadata. Salah kategori adalah isu kualitas data, bukan bukti pin salah tempat. Photo strip tanpa tanggal/koordinat yang terikat ke pixel SV tidak mengikat identitas ke scene live.
- **Informasi pada signage tetap perlu diklasifikasikan.** Alamat, email, telepon, daftar layanan, harga, atau teks umum pada papan tidak otomatis menjadi anchor identitas POI. Harus ada nama pembeda yang terbaca dan hubungan fisik yang jelas dengan objek yang dinilai.
- **Pin di infrastruktur = gejala, bukan putusan.** Pin yang tampak berada di bahu aspal, atap, kanopi, shutter, rak display, pot, gang, atau gerbang dapat mengindikasikan representasi/proyeksi, tetapi dua kemungkinan tetap terbuka: anchor lokasi valid atau ketidakakuratan. Mekanismenya tidak boleh ditebak sebagai fakta.
- **Label jalan = nomenklatur dalam-frame.** Kesamaan, perbedaan, pemotongan, atau beberapa rendering nama jalan lintas-frame tidak membuktikan satu stretch, perpindahan kamera terukur, atau dua jalan yang berbeda tanpa bukti tambahan.
- **Ko-lokasi = kondisi yang mungkin normal.** Beberapa POI dapat berbagi scene, objek pengikat, atap, gerbang, atau deretan warung. Itu tidak menjadikan POI satu entitas atau satu kompleks. Scene berbeda tanpa pengikat identik bahkan tidak cukup untuk memastikan satu momen pengambilan.
- **Objek pengikat ≠ sampel independen.** Frame yang berbagi objek identik dapat berasal dari scene/pass yang sama. Cluster-kan dahulu; jangan menghitung frame homogen sebagai sampel bebas.
- **Era/zona homogen ≠ observasi longitudinal.** Kontras bulan atau zona hanya menunjukkan perbedaan konteks waktu/area. Tanpa entitas yang sama, itu bukan uji perubahan listing.
- **Watermark © ≠ tanggal capture.** “© 2025/2026 Google” adalah metadata platform, bukan bukti tanggal pengambilan gambar atau cross-check temporal. Tanpa objek dunia nyata bertanggal yang dapat diverifikasi, jangan mengklaim cross-check internal.

## 2. Tier pembuktian dan plafon

| Tier | Makna | Batas |
|---|---|---|
| `VERIFIED` | Klaim spesifik didukung bukti independen yang dapat ditelusuri di luar tampilan SV semata | Tidak tercapai dalam state arsip yang dilaporkan sampai B86 |
| `OBSERVED-normal` | Identitas/tampilan fisik atau teks pembeda benar-benar terlihat dan cocok dalam frame | Bukan verifikasi koordinat |
| `SUSPECTED` | Gejala mismatch, penempatan tampak ganjil, atau kemungkinan representasi/proyeksi | Hipotesis dua-arah; bukan error terverifikasi |
| `UNRESOLVED-tipis` | Tidak ada nama pembeda yang terbaca pada signage fisik live, atau anchor identitas belum cukup | Jangan dipaksa menjadi match atau mismatch terverifikasi |

Tier berlaku pada klaim yang spesifik, bukan otomatis pada seluruh POI atau seluruh batch. Dari SV saja, plafon praktis adalah observasi visual dan gejala; koordinat tetap belum terverifikasi.

## 3. State terkini — per B86

- **Slot longitudinal (entitas/listing sama dengan koordinat yang dapat dibandingkan pada pass berbeda): n = 0**, dilaporkan kosong 31 batch/uji berturut-turut. Kontras bulan/zona tanpa entitas yang sama bukan longitudinal.
- **Slot uji proyeksi terverifikasi:** kosong. Tidak ada kasus `VERIFIED` yang dilaporkan (TASK 116A).
- **Counter match-fisik-eksternal-kebaca-penuh:** 9 terkonfirmasi sampai B84 menurut urutan counter sebelumnya. B86-Img4 (Mulia Cipta) disebut sebagai kandidat ke-10, tetapi deskripsi yang tersedia juga menyebut fasad-live “parsial”. Karena dua keterangan itu tidak konsisten, **kandidat ke-10 ditahan / pending review** dan tidak dimasukkan ke counter terkonfirmasi sampai screenshot atau kriteria keterbacaannya diperiksa ulang.
- **Counter mismatch (semua subtype): 11×**, angka kumulatif yang dilaporkan. Rincian sebelas kasus tidak seluruhnya direkonsiliasi dalam handoff ini; jangan menurunkan total baru dari tabel ringkas.
- **Zona/era yang dilaporkan:** B76–B83 May 2025 (Ciketing–Asem/Bayan 1/Sukatani/Narogong); B84 Mar 2025 (Mustika/Cibinong–Pulo Gadung); B85 Mar 2025 (Jatinegara); B86 memuat kontras bulan dalam satu batch (Img1 May 2025 vs Img2–5 Aug 2024; Narogong/Arema/Rawalumbu).
- **Batas sumber:** semua angka dan lokasi di atas merupakan state dari laporan pengguna; bukan hasil inspeksi ulang screenshot atau verifikasi koordinat dalam proses pembuatan handoff.

## 4. Katalog eskalasi dan perluasan

| ID | Batch | Isi ringkas | Batas/verdict |
|---|---|---|---|
| E26 | B74 | Re-appearance lintas-batch, dua scene berbeda total, keduanya UNRESOLVED-tipis | Tidak menjadi uji longitudinal |
| E30/E31 | B75 | Re-appearance intra-batch; sheet terpotong lalu terbaca penuh; pin tampak pada infrastruktur yang sama | Tidak menjadi uji koordinat |
| E32 | B76 | Re-appearance intra-batch; sheet terbaca penuh tanpa metadata; scene berbeda total | Tidak menjadi uji longitudinal |
| E34 | B78 | Token-share / ejaan mirip nama orang | Bukan bukti entitas sama |
| E35 | B79 | Re-appearance intra-batch; dua scene berbeda total; keduanya UNRESOLVED tanpa pengikat | Tidak menjadi uji |
| E36 | B80 | Re-appearance lintas-batch; scene berbeda total; satu UNRESOLVED dan satu match penuh; tanpa pengikat | Tidak menjadi uji |
| E37 | B81 | Re-appearance intra-batch pada scene/momen/zona/label jalan yang sama; satu UNRESOLVED dan satu match penuh dengan objek pengikat | Tidak menjadi baseline; match satu-frame bukan koordinat |
| E38 | B84 | Match penuh pada photo strip yang tidak terikat ke pixel live, bersamaan dengan mismatch fasad-live | Bukan VERIFIED dan bukan ERROR |
| E39 | B85 | Rekurensi landmark/nama generik lintas-frame dan lintas-batch tanpa pin aktif pada frame yang mengulang (Alfamart) | Bukan re-appearance listing/longitudinal |
| E40 | B85 | Billboard iklan-NPC pada frame A menyebut nama yang mirip dengan POI pin aktif di frame B | Bukan match atau link koordinat |
| Perluasan B84-pola #2 | B86 | Kontras bulan berdampingan dalam satu batch (May 2025 vs Aug 2024), tanpa entitas sama yang teridentifikasi | Bukan longitudinal |

## 5. Log ringkas per batch

| Batch | Zona/era yang dilaporkan | Kontribusi | Hasil uji |
|---|---|---|---|
| B78 | May 2025, Bayan 1 | Menolak re-appearance/match yang tidak benar-benar terlihat pada pixel; frame share-scene bukan identitas | 0 uji |
| B79 | May 2025, Bayan 1 | E35; match penuh ke-3 (double-media); mismatch share-token | 0 uji |
| B80 | May 2025, Bayan 1 | E36; match penuh ke-4; mismatch share-token nama orang lintas kategori | 0 uji |
| B81 | May 2025, Bayan 1 | E37; match penuh ke-5; mismatch beda-total + NPC infrastruktur; ko-lokasi lima frame | 0 uji |
| B82 | May 2025, Sukatani | Match penuh ke-6; mismatch beda-total; dua pin/POI berbeda tampak pada warung yang sama | 0 uji |
| B83 | May 2025, Sukatani/Narogong | Match penuh ke-7 dan ke-8; AI summary diperlakukan sebagai metadata; mismatch atap gudang; dua pin di atap sama tidak disatukan sebagai entitas | 0 uji |
| B84 | Mar 2025, Mustika | E38; kontras bulan/zona tanpa entitas sama bukan longitudinal; match penuh ke-9; anomali nama-vs-kategori pertama | 0 uji |
| B85 | Mar 2025, Jatinegara | E39/E40; background, nama chain generik, billboard iklan-NPC, dan label jalan tidak dinaikkan menjadi listing/match/perpindahan; 0 match penuh | 0 uji |
| B86 | May 2025 + Aug 2024, Narogong/Arema/Rawalumbu | Perluasan pola kontras bulan berdampingan; kandidat match ke-10 (Mulia Cipta) masih perlu pemeriksaan karena disebut parsial; anomali nama-vs-kategori kedua | 0 uji |

## 6. Jebakan yang sudah dilewati

1. **B78-type — pola yang tidak ada di pixel.** Jangan mengarang re-appearance/match hanya karena frame berbagi scene. Perlu pin/listing aktif yang sama dan koordinat yang dapat dibandingkan.
2. **B85-type — pola visual yang memang ada, tetapi bukan listing.** Background, landmark, nama chain generik, billboard iklan-NPC, dan label jalan bukan otomatis pin aktif, match, link antarfame, atau bukti perpindahan.
3. **B84/B86-type — dua tanggal bukan otomatis longitudinal.** Entitas/listing yang sama harus teridentifikasi. Kontras bulan atau zona tanpa entitas sama hanyalah kontras observasi.
4. **Match penuh berulang — identitas bukan koordinat.** Match ke-N tidak membuktikan pola koordinat sistematis. Match fasad-live juga berbeda medium dari match photo-strip yang tidak terikat ke scene; jangan menggabungkan keduanya ke counter yang sama tanpa definisi eksplisit.
5. **Anomali metadata — kategori bukan geometri.** Nama dan kategori yang bertentangan adalah anomali kualitas data, bukan error koordinat terverifikasi.
6. **Ko-lokasi dan objek pengikat — scene bukan entitas.** Objek pengikat dapat menunjukkan kesamaan scene/pass, tetapi tidak menyatukan listing yang berbeda dan tidak membuktikan satu kompleks atau satu koordinat.

## 7. Prosedur melanjutkan audit

1. Terima batch baru dan catat apa yang benar-benar terlihat; jangan mengisi bagian screenshot yang terpotong dengan tebakan.
2. Cluster frame berdasarkan objek pengikat identik dan konteks pass sebelum menghitung observasi independen.
3. Untuk setiap frame, pisahkan: pin aktif, signage fisik live, background/NPC, metadata panel, photo strip, label jalan, dan watermark.
4. Beri tier per klaim, bukan per batch. Plafon SV saja adalah `OBSERVED-normal`, `SUSPECTED`, atau `UNRESOLVED-tipis`.
5. Uji enam jebakan pada §6 sebelum menyusun narasi.
6. Perbarui counter hanya jika definisi counter terpenuhi. Simpan kandidat yang belum jelas sebagai pending, bukan dipaksakan masuk hitungan.
7. Jangan menambah klaim `VERIFIED` tanpa bukti independen yang relevan. Jangan memakai watermark © sebagai tanggal capture. Jangan menghitung frame homogen sebagai sampel bebas.
8. Simpan laporan batch mentah sebagai jejak audit terpisah; handoff ini hanya memuat aturan stabil, state kumulatif, katalog eskalasi, dan log satu baris.

## 8. Riwayat perubahan

- **2026-11-23 — v1.0:** Handoff pertama disusun dari state yang dilaporkan sampai B86. Aturan inti diperjelas agar pairing identitas visual tetap diperbolehkan tanpa mengubahnya menjadi klaim koordinat. Kandidat match ke-10 B86 ditahan untuk review karena deskripsi “match penuh” bertentangan dengan keterangan “fasad-live parsial”. Counter mismatch 11× dipertahankan sebagai angka yang dilaporkan, dengan catatan bahwa rincian kasus belum direkonsiliasi di dokumen ini.

---

**State ringkas:** B86; longitudinal n=0 (31× dilaporkan); VERIFIED=0; match penuh terkonfirmasi=9; kandidat ke-10 pending review; mismatch kumulatif=11× (dilaporkan, belum direkonsiliasi per kasus).
