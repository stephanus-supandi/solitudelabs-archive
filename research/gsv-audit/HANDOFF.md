---
title: "GSV Audit — Handoff Spec & State"
project: "SolitudeLabs"
document_type: "audit-handoff"
version: "1.1"
status: "working"
last_batch: "B93"
last_updated: "2026-11-23"
language: "id"
canonical_source: true
---

# GSV Audit — Handoff Spec & State (SolitudeLabs)

> Dokumen handoff ringkas untuk model penerus dan peneliti. Isinya satu definisi aturan, tier pembuktian, state, katalog eskalasi, log batch, dan jebakan yang sudah dilewati. Laporan batch lengkap tetap menjadi jejak kerja terpisah. Prinsip utamanya: jangan menghakimi benar/salahnya koordinat hanya dari tampilan Street View.

**Status sumber:** Dokumen ini merangkum deskripsi dan hasil audit yang disampaikan pengguna sampai B93. Screenshot asli, koordinat, data listing mentah, dan catatan lapangan tidak diperiksa ulang dalam proses pengarsipan ini. Angka kumulatif di bawah adalah state yang dilaporkan, bukan hasil hitung ulang independen dari seluruh arsip mentah.

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

## 3. State terkini — per B93 (sementara; counter belum direkonsiliasi)

- **Slot longitudinal (entitas/listing sama dengan koordinat yang dapat dibandingkan pada pass berbeda): n = 0**, dilaporkan kosong **38 batch/uji**. Ini adalah hitungan laporan pengguna, bukan hitung ulang independen. B90↔B93 “Indomaret Samanhudi” tidak memenuhi identitas cabang/koordinat yang sama; kemiripan nama bukan re-appearance.
- **Slot uji proyeksi terverifikasi:** kosong. Tidak ada kasus `VERIFIED` yang dilaporkan (TASK 116A).
- **Counter match-fisik-eksternal-kebaca-penuh:** **belum direkonsiliasi setelah B86**. Baseline terakhir yang dapat dipertahankan dari handoff lama adalah 9 sampai B84; B86-Img4 tetap pending karena deskripsi “match penuh” bertentangan dengan “fasad-live parsial”. B87–B93 menambah kandidat yang perlu dihitung dengan definisi seragam; angka 18× yang dilaporkan pengguna **tidak diadopsi sebagai total terverifikasi** dalam handoff ini.
- **Counter mismatch:** baseline 11× sampai B86 adalah angka yang dilaporkan dan belum direkonsiliasi per kasus. Angka 27× yang dilaporkan untuk B93 **belum diadopsi**: adjacent-NPC (mis. signage tenant lain) dan status UNRESOLVED-tipis-cabang tidak otomatis dihitung sebagai mismatch dalam counter kumulatif. Catat sebagai observasi/kategori terpisah sampai definisi counter dipastikan.
- **Counter anomali name-vs-kategori:** 3× menurut laporan pengguna; B93 tidak menambah kasus. Angka tetap berstatus reported, belum dihitung ulang dari seluruh batch.
- **Re-appearance listing-aktif intra-batch:** 2× menurut laporan pengguna (B83 Mie Ayam A3; B89 BNI KLN Krekot); B93 tidak menambah. Ini bukan uji longitudinal.
- **Duplikat-frame lintas-batch:** pola 3 batch berturut (B89/B90/B91 Img1 = RPTRA Pintu Air) berhenti pada B92; B93 juga tidak mengulang frame tersebut.
- **Kontras bulan dalam satu batch:** 3× menurut laporan pengguna (B86–B88); B89–B93 dilaporkan homogen Apr-25.
- **Zona/era yang dilaporkan:** B87 industrial corridor (Aug 2024 + May 2025); B88 May/Apr 2025; B89–B93 koridor Samanhudi/Pasar Baru/Krekot, mayoritas/homogen Apr 2025 sesuai laporan batch.
- **Batas sumber:** seluruh rincian B87–B93 berasal dari deskripsi pengguna. Screenshot asli, koordinat, data listing mentah, dan catatan lapangan tidak diperiksa ulang dalam proses pembaruan ini. Counter yang belum direkonsiliasi sengaja tidak dipromosikan menjadi state terverifikasi.
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

## 7. Prosedur melanjutkan audit

1. Terima batch baru dan catat apa yang benar-benar terlihat; jangan mengisi bagian screenshot yang terpotong dengan tebakan.
2. Cluster frame berdasarkan objek pengikat identik dan konteks pass sebelum menghitung observasi independen.
3. Untuk setiap frame, pisahkan: pin aktif, signage fisik live, background/NPC, metadata panel, photo strip, label jalan, dan watermark.
4. Beri tier per klaim, bukan per batch. Plafon SV saja adalah `OBSERVED-normal`, `SUSPECTED`, atau `UNRESOLVED-tipis`.
5. Uji seluruh jebakan pada §6 sebelum menyusun narasi.
6. Perbarui counter hanya jika definisi counter terpenuhi. Simpan kandidat yang belum jelas sebagai pending, bukan dipaksakan masuk hitungan.
7. Jangan menambah klaim `VERIFIED` tanpa bukti independen yang relevan. Jangan memakai watermark © sebagai tanggal capture. Jangan menghitung frame homogen sebagai sampel bebas.
8. Simpan laporan batch mentah sebagai jejak audit terpisah; handoff ini hanya memuat aturan stabil, state kumulatif, katalog eskalasi, dan log satu baris.

## 8. Riwayat perubahan

- **2026-11-23 — v1.0:** Handoff pertama disusun dari state yang dilaporkan sampai B86. Kandidat match ke-10 B86 ditahan untuk review; counter mismatch 11× dipertahankan sebagai angka yang dilaporkan dan belum direkonsiliasi.
- **2026-11-23 — v1.1:** Diperluas sampai B93: log B87–B93, E41–E44, duplikasi frame B89–B91, token lokasi multi-POI, aturan brand-core vs pembeda cabang/tier, dan jebakan nama entitas penuh mirip lintas-batch. Counter 18× match dan 27× mismatch yang dilaporkan pengguna tidak diadopsi karena baseline dan definisi counter belum direkonsiliasi. Semua batch baru diringkas dari deskripsi pengguna; screenshot/koordinat tidak diperiksa ulang.

---

**State ringkas:** B93; longitudinal n=0 (38× dilaporkan); VERIFIED=0; baseline match terkonfirmasi terakhir=9 sampai B84, B86 pending, B87–B93 belum direkonsiliasi; mismatch baseline 11× sampai B86, angka 27× yang dilaporkan belum diadopsi; seluruh angka bersifat sementara dan berbasis laporan pengguna.
