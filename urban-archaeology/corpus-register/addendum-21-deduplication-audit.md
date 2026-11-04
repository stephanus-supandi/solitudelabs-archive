# BLOON INVESTIGATION — ADDENDUM BUKTI VISUAL #21
## AUDIT DEDUPLIKASI: LIMA FRAME, NOL BUKTI BARU

**Batch:** Kelima belas  
**Disposition:** Deduplication audit / corpus saturation  
**Status:** No new visual evidence reported

Batch ini terdiri dari lima frame yang seluruhnya near-duplicate dari frame yang telah terkatalog. Karena itu, batch ini tidak menambah entitas, signage, vintage, atau OBSERVED-MATCH.

## A. Tabel silang referensi

| # Batch ini | Citra | Pin / kartu | Padanan sebelumnya | Putusan |
|---|---|---|---|---|
| 1 | Apr 2026 | Kartu "Gereja Katolik Sa…" (rumah biru) | Addendum #20 frame #1 (node & vintage sama) | **NEAR-DUPLICATE** — nol bukti baru; tetap **TERKUNCI** protokol keamanan |
| 2 | Jul 2026 | "TOKO ANISA" (objek kuning depan lensa sama) | Addendum #14 frame #3 | **NEAR-DUPLICATE** |
| 3 | Jul 2026 | "Kios Bu Wal" (terpal merah-biru sama) | Addendum #14 frame #4 | **NEAR-DUPLICATE** |
| 4 | Jul 2026 | "Pasar Mandiri Way Kandis" (komposisi sama) | Addendum #14 frame #5 | **NEAR-DUPLICATE** |
| 5 | Jul 2026 | "Pasar Tempel Way Kandis" (rider depan sama) | Addendum #16 frame #4, yang sendiri duplikat Addendum #14 frame #1 | **NEAR-DUPLICATE tingkat-2** (duplikat dari duplikat) |

## B. Aturan deduplikasi diformalkan (M06-ext.3)

1. Identitas bukti visual dicatat berdasarkan kombinasi **node panorama × vintage × pin/listing × sudut**. Kesamaan seluruh unsur tersebut berarti satu bukti, berapa kali pun dikirim ulang.
2. Pengiriman ulang tidak menaikkan status dan tidak menambah jumlah sumber.
3. Duplikat tingkat-2 dicatat sebagai indikator drift manajemen korpus, bukan bukti baru.
4. Setiap frame wajib masuk registri dengan ID permanen. Format usulan:

   `BLOON-VIS-<korpus>-<node>-<vintage>-<pin>-<addendum.frame>`

   Contoh: `BLOON-VIS-LPG-WKND-PASAR-2026JUL-PASARTEMPEL-14.1`.
5. Frame terkunci karena privasi atau keamanan tetap terkunci meskipun dikirim ulang.

**Catatan implementasi:** kombinasi empat unsur di atas adalah kunci deduplikasi operasional, bukan pengganti pemeriksaan hash atau perbandingan citra. Jika sudut, node, atau identitas listing tidak pasti, klasifikasi near-duplicate harus tetap dinyatakan sebagai hasil pemeriksaan, bukan kepastian otomatis.

## C. Catatan jenuh (saturation)

Node pasar Way Kandis, vintage Jul 2026, telah dikirim berulang lintas addendum (#14, #16, #21) dengan pin berbeda tetapi panorama yang sama. Node ini dinyatakan **JENUH untuk penambahan bukti spasial dari panorama yang sama**.

Pin tambahan pada node tersebut dapat menambah daftar listing yang perlu dicatat, tetapi tidak otomatis menambah bukti unit fisik atau bukti spasial independen.

Untuk progres substantif, korpus Lampung memerlukan salah satu dari:

- vintage kedua pada ruas yang sama untuk change detection;
- node baru dengan signage entitas yang terbaca; atau
- dokumen eksternal yang relevan, seperti peta blok pasar, izin usaha, atau arsip kelurahan.

## D. Rekap korpus

| Parameter | Nilai |
|---|---|
| Total screenshot | 94 mentah / **86 unik** |
| Korpus | Bekasi · Sorocaba · Jakarta Barat · Bandar Lampung urban · Lampung rural/residensial |
| Vintage | 11 lapis |
| OBSERVED-MATCH | 10 |
| Frame terkunci | 3 |
| Nexus ke investigasi berjalan | NOT FOUND IN REVIEWED RECORDS |

Angka-angka tersebut mengikuti rekap Addendum #20 dan #21; belum merupakan hasil hitung ulang independen atas seluruh file citra.

## E. Disposisi

1. Kelima frame dicatat sebagai duplikat; registri frame diberlakukan untuk seluruh pengiriman berikutnya.
2. Tidak ada perubahan status pada entitas mana pun.
3. Node pasar Way Kandis ditandai jenuh untuk pengulangan panorama yang sama.
4. Batch duplikat berikutnya cukup dicatat sebagai audit deduplikasi ringkas, bukan addendum temuan penuh.
5. Proyek berjalan di bawah cakupan **BLOON INVESTIGATION — URBAN & RURAL ENVIRONMENTAL ARCHIVE v0.1**.

**GOBLOK BOLEH. NGARANG JANGAN. DAN: MENGIRIM HAL SAMA DUA KALI BUKAN DUA BUKTI.**

---

## Archive note

This file records the submitted Addendum #21 text. The five underlying screenshots and the full source-media metadata were not included in this commit. This upload is therefore a report artifact, not an independent image audit.
