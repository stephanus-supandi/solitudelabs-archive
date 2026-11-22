---
title: "GSV Audit — Handoff Spec & State"
project: "SolitudeLabs"
document_type: "audit-handoff"
version: "1.2"
status: "working"
last_batch: "B140"
last_updated: "2026-11-23"
language: "id"
canonical_source: true
---

# GSV Audit — Handoff Spec & State (SolitudeLabs)

> Dokumen handoff ringkas untuk model penerus dan peneliti. Isinya satu definisi aturan, tier pembuktian, state, katalog eskalasi, log batch, dan jebakan yang sudah dilewati. Laporan batch lengkap tetap menjadi jejak kerja terpisah. Prinsip utamanya: jangan menghakimi benar/salahnya koordinat hanya dari tampilan Street View.

**Status sumber:** Dokumen ini memuat state lama sampai B93 serta tambahan B139–B140 berdasarkan deskripsi audit pengguna. Batch B94–B138 belum dimasukkan ke log handoff ini; jangan menganggap rentang itu telah direkonstruksi atau diaudit ulang di sini. Screenshot asli, koordinat, data listing mentah, dan catatan lapangan B139–B140 tidak diperiksa ulang dalam proses pengarsipan ini. Angka kumulatif yang belum direkonsiliasi tetap berstatus laporan, bukan hasil hitung ulang independen.

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
| `VERIFIED` | Klaim spesifik didukung bukti independen yang dapat ditelusuri di luar tampilan SV semata | Tidak tercapai dalam state arsip yang dilaporkan sampai B93 |
| `OBSERVED-normal` | Identitas/tampilan fisik atau teks pembeda benar-benar terlihat dan cocok dalam frame | Bukan verifikasi koordinat |
| `SUSPECTED` | Gejala mismatch, penempatan tampak ganjil, atau kemungkinan representasi/proyeksi | Hipotesis dua-arah; bukan error terverifikasi |
| `UNRESOLVED-tipis` | Tidak ada nama pembeda yang terbaca pada signage fisik live, atau anchor identitas belum cukup | Jangan dipaksa menjadi match atau mismatch terverifikasi |

Tier berlaku pada klaim yang spesifik, bukan otomatis pada seluruh POI atau seluruh batch. Dari SV saja, plafon praktis adalah observasi visual dan gejala; koordinat tetap belum terverifikasi.

## 3. State terkini — per B140 (sementara; counter belum direkonsiliasi)

- **Lensa spasial terverifikasi:** 0 pada B139–B140 menurut laporan pengguna; tidak ada koordinat pembanding atau bukti lapangan baru yang disampaikan. Ini bukan audit ulang seluruh rentang B94–B138.
- **Slot longitudinal:** baseline terakhir dalam handoff lama adalah n=0 sampai B93 (38× dilaporkan). B139–B140 tidak menambah uji yang memenuhi syarat: tidak ada identitas listing dan koordinat yang dapat dibandingkan pada pass independen. Rentang B94–B138 belum direkonsiliasi dalam dokumen ini; jangan mengubah angka kumulatif tanpa meninjau batch tersebut.
- **VERIFIED:** tidak ada klaim baru. B139–B140 tetap pada plafon observasi tampilan/metadata dan hipotesis.
- **Counter match fisik dan mismatch:** tetap belum direkonsiliasi setelah B86/B93. Tidak ada angka total baru yang diadopsi dari B139–B140.
- **B139:** koridor Jakarta Pusat/Samanhudi–Krekot Bunder–Pasar Baru dilaporkan homogen Apr 2025. Label jalan yang lebih lengkap pada beberapa frame dibanding B138 tidak membuktikan resolusi database atau koordinat; sudut pandang/crop merupakan penjelasan yang mungkin. Suffix Romawi dicatat sebagai bagian label ruas yang tampil, bukan designator blok yang telah diverifikasi.
- **B140:** tiga pasangan record lintas-batch dilaporkan berulang dengan teks/angka panel identik: B137 f3 ↔ B140 f4; B138 f5 ↔ B140 f2; B139 f2 ↔ B140 f5. Catat sebagai exact rendered-record recurrence menurut laporan pengguna. Pengulangan tidak membuktikan observasi independen, tetapi juga belum cukup untuk memastikan mekanisme cache atau satu sesi yang sama.
- **Koreksi status klaim lama:** headline B137–B139 tidak boleh diperlakukan sebagai breakthrough independen hanya berdasarkan tampilan yang dilaporkan. B137 tetap inkonsistensi nama/kategori pada panel yang tampil; B138 tetap metadata usia citra relatif yang referensi waktunya belum diverifikasi; B139 tetap perbedaan keterbacaan label jalan. B140 menurunkan keyakinan pada independensi pengulangan, bukan membuktikan mekanisme teknis tertentu.
- **Aturan mismatch diperjelas:** nama dan kategori harus sama-sama terlihat dan saling bertentangan untuk dicatat sebagai inkonsistensi semantik internal pada listing yang dirender. Jika kategori terpotong/tidak terlihat (B140 f1 “Gs Astra”), statusnya unresolvable, bukan mismatch. Inkonsistensi nama-kategori (B140 f4 “Nasi Uduk…” vs “Motorcycle repair shop”) tetap bukan bukti salah koordinat.
- **Batas sumber:** semua rincian B139–B140 berasal dari deskripsi pengguna. Screenshot asli, koordinat, metadata listing mentah, dan catatan lapangan tidak diperiksa ulang. Log B94–B138 belum diperbarui di handoff ini.

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
| E41 | B87 | Match pada objek Y tidak memvalidasi pin yang tampak pada objek X dalam frame yang sama | Identitas signage dan penempatan pin adalah observasi terpisah |
| E42 / B92-#14 | B92 | Brand-core cocok tetapi pembeda cabang/tier/lokasi tidak cocok dua-arah (Yamaha; BCA; kemudian Scuto Platinum vs Signature dan Indomaret Samanhudi vs fasad brand-only) | `UNRESOLVED-tipis-cabang`; jangan hitung sebagai match penuh hanya karena brand-core terlihat |
| E43 / B93-#16 | B93 | Nama entitas penuh yang mirip lintas-batch: “Indomaret Samanhudi” vs “Indomaret Samanhudi 27A TS1S” | Belum terbukti cabang/entitas sama; tanpa kode cabang dan koordinat pembanding, bukan re-appearance longitudinal |
| E44 / B93-#17 | B93 | Perluasan konflik pembeda cabang/tier dua-arah: Scuto “Platinum” vs fasad “Signature”; Indomaret “Samanhudi” vs fasad logo “Indomaret” saja | Brand-core connect tidak cukup; status unresolved, bukan match penuh |
| Perluasan E39/B92-#13 | B90–B93 | Token lokasi “Samanhudi” dipakai pada beberapa POI berbeda; “Pasar Baru/Pasarbaru” juga muncul lintas listing | String-share lintas POI/batch bukan identitas entitas atau bukti longitudinal |
| Ko-lokasi bersih | B93 | Img4 Indomaret dan Img5 Hotel Banyuwangi Sintera berbagi scene/objek pengikat yang sama | Satu scene/momen, dua POI berbeda; ko-lokasi bukan re-appearance |
| Ghost marker subtype | B93 | Ikon/ghost ✝, 🔒, 🛏 dilaporkan muncul di sekitar POI lain | Catat sebagai observasi UI; bukan anchor identitas atau koordinat |

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
| B87 | Aug 2024 + May 2025, koridor industri | Dua match fisik penuh dilaporkan (PT Fajar Bumi Harmoni; PT EBJ); ASEAN BAJA tanpa “Cemerlang” tetap parsial; match pada objek Y tidak memvalidasi pin objek X (E41) | 0 uji |
| B88 | May 2025 + Apr 2025 | Pangkas Rambut Asgar Jaya dilaporkan sebagai match fisik; “Sehat Kogeak” adalah signage NPC; kategori Clothing store pada Toko Susu Baim dicatat sebagai anomali metadata ketiga menurut laporan | 0 uji |
| B89 | Apr 2025, Samanhudi/Krekot | BNI KLN Krekot pin aktif muncul pada dua frame berbeda tanpa objek pengikat identik; logo BNI saja tidak mengonfirmasi cabang; mengulang pola E35 tanpa uji | 0 uji |
| B90 | Apr 2025, Samanhudi/Krekot | Img1 RPTRA Pintu Air dilaporkan duplikat persis B89-Img1; “Samanhudi” muncul pada beberapa POI berbeda; signage kompleks/tenant sekitar tetap NPC | 0 uji |
| B91 | Apr 2025, Samanhudi/Krekot | RPTRA Pintu Air Img1 dilaporkan sama dengan B89/B90; duplikasi satu frame lintas tiga batch, bukan tiga pass; “Samanhudi” bertambah sebagai token lintas POI | 0 uji |
| B92 | Apr 2025, Samanhudi/Pasar Baru/Krekot | GKI Samanhudi dilaporkan sebagai match identitas melalui padanan nama; Scuto/Indomaret/Yamaha memperjelas aturan pembeda cabang/tier dua-arah (B92-#14); Domino’s dan Baru Toko memerlukan pemisahan sumber teks/field | 0 uji |
| B93 | Apr 2025, Samanhudi/Pasar Baru/Krekot | Motor Mahkota satu match identitas (banner + thumbnail); Scuto Platinum dan Indomaret Samanhudi unresolved-tipis-cabang; kemiripan nama penuh Indomaret B90↔B93 bukan re-appearance; Img4/5 ko-lokasi dua POI | 0 uji |
| B139 | Apr 2025, Jakarta Pusat: Samanhudi/Krekot Bunder/Pasar Baru | Label “Jl. Krekot Bunder IV” terbaca lebih lengkap dibanding potongan label B138; Bank Sinarmas tampil dalam dua pose dengan cluster sekitar berbeda; banner Laba-Laba terlihat lintas-tile; token “Sinar” muncul pada kategori berbeda; nama POI memuat beberapa toponym | Tidak ada lensa spasial baru; keterbacaan, rekurensi token, multi-tenant, dan metadata tetap belum memverifikasi koordinat |
| B140 | Apr 2025, Jakarta Pusat: Samanhudi/Pecenongan | Tiga record panel dilaporkan berulang persis dari B137–B139; satu fasad memuat banyak signage/tenant; kategori Muay Thai gym; “Gs Astra” panel kategori tersembunyi; “Nasi Uduk” vs “Motorcycle repair shop” tampak inkonsisten | Exact recurrence bukan observasi independen atau bukti cache; hidden category bukan mismatch; inkonsistensi listing bukan salah koordinat |

## 6. Jebakan yang sudah dilewati

1. **B78-type — pola yang tidak ada di pixel.** Jangan mengarang re-appearance/match hanya karena frame berbagi scene. Perlu pin/listing aktif yang sama dan koordinat yang dapat dibandingkan.
2. **B85-type — pola visual yang memang ada, tetapi bukan listing.** Background, landmark, nama chain generik, billboard iklan-NPC, dan label jalan bukan otomatis pin aktif, match, link antarfame, atau bukti perpindahan.
3. **B84/B86-type — dua tanggal bukan otomatis longitudinal.** Entitas/listing yang sama harus teridentifikasi. Kontras bulan atau zona tanpa entitas sama hanyalah kontras observasi.
4. **Match penuh berulang — identitas bukan koordinat.** Match ke-N tidak membuktikan pola koordinat sistematis. Match fasad-live juga berbeda medium dari match photo-strip yang tidak terikat ke scene; jangan menggabungkan keduanya ke counter yang sama tanpa definisi eksplisit.
5. **Anomali metadata — kategori bukan geometri.** Nama dan kategori yang bertentangan adalah anomali kualitas data, bukan error koordinat terverifikasi.
6. **Ko-lokasi dan objek pengikat — scene bukan entitas.** Objek pengikat dapat menunjukkan kesamaan scene/pass, tetapi tidak menyatukan listing yang berbeda dan tidak membuktikan satu kompleks atau satu koordinat.
7. **B87-type — signage pada objek Y bukan validasi pin pada objek X.** Catat identitas visual dan penempatan pin sebagai dua variabel terpisah; jangan gunakan satu untuk mengesahkan yang lain.
8. **B89–B91-type — screenshot/frame yang sama berulang bukan pass independen.** RPTRA Pintu Air Img1 dilaporkan identik dalam tiga batch berturut; itu satu frame yang disalin/ditampilkan ulang, bukan tiga observasi temporal.
9. **B90–B93-type — token lokasi yang dipakai banyak POI bukan satu entitas.** “Samanhudi” adalah string lokasi yang dapat melekat pada banyak usaha/lembaga. Jangan gabungkan listing hanya karena nama jalan sama.
10. **B92/B93-type — brand-core tanpa pembeda cabang/tier bukan match penuh.** Bila brand cocok tetapi suffix pembeda tidak cocok dua-arah atau tidak terlihat (mis. Scuto Platinum vs Signature; Indomaret Samanhudi vs logo Indomaret saja), tahan sebagai `UNRESOLVED-tipis-cabang`.
11. **B93-#16 — nama entitas penuh yang mirip lintas-batch adalah jebakan longitudinal tingkat lanjut.** “Indomaret Samanhudi” dan “Indomaret Samanhudi 27A TS1S” belum tentu cabang yang sama. Periksa kode cabang, lokasi rinci, identitas listing, dan koordinat pembanding sebelum menyebut re-appearance.
12. **B93-#17 — konflik tier/lokasi dua-arah.** Kecocokan brand-core tidak menghapus konflik pada nama pembeda cabang atau tier. Jangan menaikkan ke match penuh hanya karena fasad kaya signage.
13. **B93-type — ko-lokasi satu scene dua POI.** Img4/Img5 dilaporkan berbagi scene tetapi mewakili Indomaret dan hotel yang berbeda; objek pengikat menunjukkan konteks scene, bukan penyatuan entitas.
14. **Adjacent-NPC tetap kategori tersendiri.** Signage tenant lain pada frame pin POI (termasuk motor, minimarket, bank, atau nama kompleks) tidak otomatis menjadi mismatch listing; klasifikasikan sebagai signage sekitar sampai ada bukti pembanding yang memenuhi definisi mismatch.
15. **B139-type — label jalan lebih terbaca bukan resolusi spasial.** Perubahan parsial menjadi lengkap dapat disebabkan pose, sudut pandang, atau crop. Suffix ruas/angka Romawi yang tampil bukan koordinat dan tidak otomatis membuktikan designator blok.
16. **B140-type — exact recurrence lintas-batch bukan observasi independen.** Teks, rating, kategori, status, dan angka yang identik dapat berasal dari record/listing atau tampilan yang sama. Catat recurrence; jangan menyimpulkan cache, satu sesi, atau korroborasi independen tanpa bukti teknis/sumber independen.
17. **B140-type — kategori tersembunyi bukan mismatch.** Mismatch semantik internal mensyaratkan nama dan kategori sama-sama terbaca dan saling bertentangan. Jika salah satu field terpotong/tidak tampil, gunakan unresolved/unresolvable.
18. **Inkonsistensi listing ≠ salah koordinat.** Konflik nama-kategori yang tampak pada panel hanya mendukung catatan kualitas/semantik data yang dirender; penempatan pin memerlukan bukti spasial terpisah.

## 7. Prosedur melanjutkan audit

1. Terima batch baru dan catat apa yang benar-benar terlihat; jangan mengisi bagian screenshot yang terpotong dengan tebakan.
2. Cluster frame berdasarkan objek pengikat identik dan konteks pass sebelum menghitung observasi independen.
3. Untuk setiap frame, pisahkan: pin aktif, signage fisik live, background/NPC, metadata panel, photo strip, label jalan, dan watermark.
4. Beri tier per klaim, bukan per batch. Plafon SV saja adalah `OBSERVED-normal`, `SUSPECTED`, atau `UNRESOLVED-tipis`.
5. Uji seluruh jebakan pada §6 sebelum menyusun narasi.
6. Perbarui counter hanya jika definisi counter terpenuhi. Simpan kandidat yang belum jelas sebagai pending, bukan dipaksakan masuk hitungan.
7. Jangan menambah klaim `VERIFIED` tanpa bukti independen yang relevan. Jangan memakai watermark © sebagai tanggal capture. Jangan menghitung frame homogen sebagai sampel bebas.
8. Simpan laporan batch mentah sebagai jejak audit terpisah; handoff ini hanya memuat aturan stabil, state kumulatif, katalog eskalasi, dan log satu baris.
9. Saat record berulang lintas-batch, bandingkan seluruh teks/angka panel dan chrome, lalu catat tingkat kemiripannya. Jangan menyebut cache atau sesi yang sama tanpa bukti teknis; jangan menghitung recurrence sebagai sampel independen.
10. Bedakan field yang tidak terlihat karena truncation dari field yang terlihat dan bertentangan. Catat inkonsistensi semantik listing secara terpisah dari penilaian posisi pin.

## 8. Riwayat perubahan

- **2026-11-23 — v1.0:** Handoff pertama disusun dari state yang dilaporkan sampai B86. Kandidat match ke-10 B86 ditahan untuk review; counter mismatch 11× dipertahankan sebagai angka yang dilaporkan dan belum direkonsiliasi.
- **2026-11-23 — v1.1:** Diperluas sampai B93: log B87–B93, E41–E44, duplikasi frame B89–B91, token lokasi multi-POI, aturan brand-core vs pembeda cabang/tier, dan jebakan nama entitas penuh mirip lintas-batch. Counter 18× match dan 27× mismatch yang dilaporkan pengguna tidak diadopsi karena baseline dan definisi counter belum direkonsiliasi. Semua batch baru diringkas dari deskripsi pengguna; screenshot/koordinat tidak diperiksa ulang.
- **2026-11-23 — v1.2:** Menambahkan B139–B140 dan E45–E47; menegaskan label jalan yang lebih terbaca bukan resolusi koordinat, exact recurrence lintas-batch bukan observasi independen atau bukti cache, serta kategori tersembunyi bukan mismatch. Status breakthrough B137–B139 diturunkan dari klaim independen menjadi observasi/metadata yang belum diverifikasi. Rentang B94–B138 tetap belum dimasukkan ke handoff ini; counter kumulatif tidak direkonstruksi. Semua tambahan berbasis deskripsi pengguna; screenshot/koordinat tidak diperiksa ulang.

---

**State ringkas:** B140 (dengan log yang tersedia sampai B93 lalu tambahan B139–B140; B94–B138 belum dimasukkan); tidak ada lensa spasial baru pada B139–B140; VERIFIED baru=0; slot longitudinal terakhir yang tercatat n=0 sampai B93 dan tidak bertambah dari B139–B140; counter match/mismatch tetap belum direkonsiliasi; seluruh angka bersifat sementara dan berbasis laporan pengguna.
