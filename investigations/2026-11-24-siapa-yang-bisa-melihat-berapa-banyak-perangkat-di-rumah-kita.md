# SIAPA YANG BISA MELIHAT BERAPA BANYAK PERANGKAT DI RUMAH KITA?

**BLOON INVESTIGATION**

*ISP, Hacker, Modem Bawaan, Router Wi-Fi, IPFire, dan Misteri Perangkat yang Katanya Sedang Online*

**Tanggal publikasi:** 24 November 2026

**Mirror publikasi:**
- Blogger: https://solitudelabs.blogspot.com/2026/11/siapa-yang-bisa-melihat-berapa-banyak.html
- WordPress: https://solitudelabs.wordpress.com/2026/11/24/siapa-yang-bisa-melihat-berapa-banyak-perangkat-di-rumah-kita/

---

## Pendahuluan

Pernah kepikiran begini?

Di rumah ada:
- 1 HP Android.
- 1 laptop.
- 1 komputer.
- 1 Smart TV.
- 1 tablet.
- Beberapa perangkat IoT.
- Mungkin ada perangkat lain yang sudah lupa pernah dibeli.

Pertanyaannya sederhana:

Apakah ISP bisa mengetahui semuanya? Apakah hacker bisa melihat berapa banyak perangkat yang sedang aktif? Apakah seseorang dari luar rumah bisa mengetahui bahwa kita sedang menggunakan Samsung, laptop MSI, atau Smart TV?

Jawabannya: tergantung siapa yang mengakses, dari mana akses dilakukan, bagaimana konfigurasi jaringan, dan informasi apa yang tersedia.

Mari kita bongkar satu per satu.

---

## 1. Memahami dulu jaringan rumah kita

Bayangkan konfigurasi sederhana:

`INTERNET → MODEM/ROUTER ISP → PERANGKAT RUMAH`

Modem/router ISP biasanya mempunyai beberapa fungsi:

1. Menghubungkan rumah ke internet.
2. Menjadi router.
3. Menjalankan NAT.
4. Menyediakan DHCP.
5. Menyediakan Wi-Fi.
6. Mengelola koneksi perangkat lokal.
7. Dalam beberapa konfigurasi, menyediakan layanan administrasi jarak jauh untuk ISP.

Nah, di sinilah cerita dimulai.

Router bukan sekadar kotak yang mengeluarkan Wi-Fi. Router juga merupakan titik penghubung dan pengelola jaringan lokal.

## 2. Apa bedanya IP address, MAC address, dan hostname?

Sebelum membicarakan hacker, kita kenalan dengan tiga istilah.

### A. IP Address

Alamat jaringan yang digunakan perangkat untuk berkomunikasi.

Contoh:
- HP: `192.168.1.10`
- Laptop: `192.168.1.11`
- Smart TV: `192.168.1.12`

Alamat tersebut merupakan IP lokal. Bukan IP publik yang terlihat oleh seluruh internet.

### B. MAC Address

Alamat identifikasi antarmuka jaringan pada tingkat link layer.

Router biasanya dapat mempelajari MAC address perangkat yang berkomunikasi langsung dengannya. Namun, sekarang banyak perangkat menggunakan MAC randomization atau private MAC address. Jadi MAC yang terlihat belum tentu identitas permanen perangkat.

### C. Hostname

Nama perangkat yang dilaporkan atau dikonfigurasi oleh perangkat.

Contoh:
- `Galaxy-A23`
- `MSI-Laptop`
- `Android-TV`

Hostname dapat membantu mengenali perangkat, tetapi tidak selalu akurat. Nama perangkat juga bisa diubah.

**Penting:** IP address, MAC address, dan hostname bukan bukti mutlak identitas seseorang.

---

## 3. Skenario pertama: ISP melihat perangkat melalui modem/router bawaannya

Ini salah satu skenario paling penting.

Misalnya ISP memberikan modem/router yang sekaligus menjadi Wi-Fi rumah.

ISP mungkin memiliki sistem administrasi jaringan yang memungkinkan pengelolaan perangkat pelanggan dari jarak jauh.

Teknologi yang umum digunakan antara lain:
- TR-069 / CWMP.
- TR-369 / USP.
- ACS (Auto Configuration Server).
- Sistem manajemen perangkat CPE milik ISP.

Apa itu CPE?

CPE adalah Customer Premises Equipment, yaitu perangkat jaringan yang berada di lokasi pelanggan, misalnya modem atau router.

Apa itu ACS?

ACS merupakan server pengelolaan yang dapat digunakan operator untuk mengonfigurasi, memantau, dan memelihara perangkat pelanggan yang mendukung protokol terkait.

Tergantung implementasi dan izin yang diberikan, sistem tersebut dapat memperoleh informasi seperti:
- Status modem.
- Status koneksi internet.
- Statistik trafik.
- Konfigurasi Wi-Fi.
- Informasi antarmuka jaringan.
- Daftar perangkat yang terhubung.
- Informasi DHCP atau perangkat LAN, jika tersedia dan dilaporkan oleh perangkat.

Jadi, apakah ISP bisa mengetahui jumlah perangkat di rumah?

Bisa, jika modem/router dan sistem manajemen ISP menyediakan serta mengirimkan informasi tersebut.

Tetapi jangan menganggap semua ISP mempunyai kemampuan dan konfigurasi yang identik.

## 4. Skenario kedua: ISP hanya melihat koneksi internet dari sisi WAN

Sekarang bayangkan ISP tidak memiliki akses ke daftar perangkat lokal.

Di rumah ada lima perangkat yang menggunakan satu router. Router menjalankan NAT (Network Address Translation).

NAT memungkinkan beberapa perangkat menggunakan satu koneksi IP publik.

Gambaran sederhananya:

```
HP ─────┐
Laptop ─┤
TV ─────┼── ROUTER/NAT ─── INTERNET ─── ISP
Tablet ─┤
PC ─────┘
```

Dari sisi ISP, koneksi-koneksi tersebut dapat terlihat berasal dari satu IP publik pelanggan.

ISP masih dapat mengamati sejumlah informasi:
- IP publik pelanggan.
- Waktu koneksi.
- Volume upload dan download.
- IP tujuan koneksi.
- Protokol dan karakteristik trafik tertentu.
- Informasi DNS apabila tidak dilindungi oleh enkripsi dan konfigurasi jaringan yang sesuai.

Tetapi ISP tidak otomatis melihat:
- MAC address seluruh perangkat LAN.
- Seluruh IP lokal.
- Nama semua perangkat.
- Isi seluruh komunikasi.
- Daftar lengkap perangkat yang sedang menyala.

**PENTING:** Melihat satu IP publik tidak sama dengan melihat satu perangkat.

Sebaliknya, melihat banyak koneksi internet juga tidak otomatis berarti ada banyak perangkat. Satu perangkat dapat membuat banyak koneksi sekaligus.

## 5. Skenario ketiga: Hacker berhasil mengakses administrasi router

Sekarang masuk ke skenario keamanan.

Misalnya seseorang berhasil memperoleh akses administratif ke router.

Kemungkinan penyebabnya antara lain:

1. Password administrator terlalu lemah.
2. Password bawaan tidak diganti.
3. Firmware memiliki kerentanan keamanan.
4. Antarmuka administrasi jarak jauh terekspos ke internet.
5. Kredensial administrator bocor.
6. Router dikompromikan melalui jalur akses lain.

Jika berhasil mendapatkan hak akses yang cukup, penyerang mungkin bisa melihat informasi yang tersedia di router, seperti:
- DHCP lease.
- Daftar klien Wi-Fi.
- Perangkat yang terhubung.
- MAC address.
- IP lokal.
- Hostname.
- Statistik koneksi.
- Konfigurasi jaringan.

Namun, akses administratif tidak selalu berarti semua informasi tersedia. Kemampuan bergantung pada model router, firmware, hak akses, dan konfigurasi.

Apakah hacker bisa mengetahui berapa perangkat yang aktif? Bisa, jika informasi status perangkat tersedia.

Apakah hacker otomatis bisa membaca isi HP? Tidak.

Menguasai router dan menguasai seluruh perangkat yang terhubung adalah dua hal berbeda.

## 6. Skenario keempat: Hacker tidak menguasai router, tetapi sudah masuk ke Wi-Fi

Ini skenario yang berbeda.

Misalnya seseorang berhasil memperoleh akses ke jaringan Wi-Fi rumah.

Dia mungkin dapat melakukan pengamatan jaringan lokal sesuai segmentasi, konfigurasi, dan pembatasan yang berlaku. Dalam kondisi tertentu, dia dapat menemukan perangkat yang berkomunikasi di jaringan tersebut.

Informasi yang mungkin terlihat:
- IP lokal.
- MAC address pada segmen jaringan yang sama.
- Hostname yang tersedia.
- Port dan layanan jaringan yang merespons.
- Jenis perangkat yang dapat diperkirakan dari karakteristik layanan.

Tetapi ada batasan.

Guest Wi-Fi, client isolation, VLAN, firewall, dan segmentasi jaringan dapat membatasi komunikasi antarklien.

Jadi, masuk Wi-Fi tidak otomatis berarti dapat mengakses semua perangkat.

## 7. Skenario kelima: Salah satu perangkat di rumah terinfeksi malware

Ini sering terlupakan.

Misalnya laptop terinfeksi malware. Penyerang mungkin memperoleh kemampuan menjalankan aktivitas tertentu melalui laptop tersebut.

Jika malware memiliki akses dan jaringan mengizinkan, ia dapat mencoba mengamati atau memeriksa perangkat lain di jaringan lokal.

Misalnya:
- Router.
- NAS.
- Komputer lain.
- Printer jaringan.
- Perangkat IoT.

Dengan demikian, seseorang tidak harus terlebih dahulu meretas router dari internet. Kadang titik masuk justru berasal dari salah satu perangkat pengguna.

Namun, kemampuan malware tetap bergantung pada hak akses, jenis malware, konfigurasi firewall, dan segmentasi jaringan.

## 8. Skenario keenam: ISP menggunakan sistem fiber optik, ONT, OLT, atau perangkat lain

Pada jaringan fiber optik, perangkat pelanggan sering disebut ONT atau ONU. Di sisi operator terdapat perangkat jaringan seperti OLT.

ISP dapat mengelola koneksi pelanggan melalui infrastruktur tersebut.

Mereka dapat mengetahui berbagai informasi jaringan, misalnya:
- Status ONT.
- Status koneksi optik.
- Kualitas sinyal tertentu.
- Status layanan.
- Statistik trafik.
- Identitas perangkat jaringan pelanggan.

Tetapi perlu dibedakan:

Informasi ONT bukan otomatis daftar lengkap HP, laptop, dan perangkat Wi-Fi di rumah.

Untuk memperoleh daftar perangkat LAN, biasanya diperlukan informasi tambahan dari router atau sistem manajemen yang terhubung dengannya.

## 9. Skenario ketujuh: Router ISP + IPFire

Nah, ini menarik.

Misalkan konfigurasi rumah:

`MODEM ISP → IPFIRE → JARINGAN RUMAH`

IPFire menjadi router/firewall utama untuk perangkat di belakangnya.

Jika semua perangkat rumah benar-benar melewati IPFire, maka IPFire dapat mengelola:
- Routing.
- Firewall.
- NAT.
- DHCP, jika layanan tersebut diaktifkan.
- DNS forwarding atau resolusi lokal.
- Logging koneksi.
- Segmentasi jaringan, jika dikonfigurasi.

ISP umumnya melihat koneksi dari sisi WAN. ISP tidak otomatis memperoleh daftar lengkap MAC address perangkat yang berada di belakang IPFire.

Namun ada beberapa pengecualian penting.

### Kasus A: Modem ISP tetap menjalankan Wi-Fi

Jika HP terhubung langsung ke Wi-Fi modem ISP, perangkat tersebut tidak melewati IPFire.

Akibatnya, IPFire tidak mengawasi seluruh jaringan rumah.

### Kasus B: Modem ISP berada dalam mode router dan IPFire juga melakukan routing

Ini bisa menghasilkan double NAT.

ISP tetap mengelola modem/router di sisi depan, sedangkan IPFire mengelola jaringan di belakangnya.

### Kasus C: Modem ISP dalam mode bridge

IPFire menjadi router utama.

Modem atau ONT tetap berfungsi sebagai perangkat akses jaringan, tetapi fungsi routing utama dilakukan oleh IPFire.

Dalam skenario ini, ISP tetap mengetahui koneksi pelanggan dan statistik yang tersedia pada infrastrukturnya. Namun ISP tidak otomatis dapat melihat daftar lengkap perangkat LAN di belakang IPFire.

## 10. Skenario kedelapan: VPN, WireGuard, NetBird, dan DNS encryption

Apakah VPN membuat ISP tidak bisa melihat apa pun?

Tidak.

VPN mengubah visibilitas jaringan, bukan menghilangkannya.

ISP masih dapat melihat:
- IP publik pelanggan.
- IP endpoint VPN.
- Waktu koneksi.
- Volume trafik.
- Pola komunikasi tertentu.

Tetapi isi trafik di dalam tunnel VPN tidak dapat dibaca langsung oleh ISP apabila enkripsi dan autentikasi tunnel bekerja dengan benar.

DNS juga perlu diperhatikan.

Ada beberapa kemungkinan:
1. DNS biasa tanpa enkripsi.
2. DNS over TLS (DoT).
3. DNS over HTTPS (DoH).
4. DNS lokal yang meneruskan permintaan melalui resolver terenkripsi.
5. DNS yang berjalan melalui tunnel VPN.

Kalau menggunakan DNS biasa, ISP mungkin dapat mengamati permintaan DNS.

Kalau menggunakan DoH atau DoT, permintaan DNS dienkripsi dalam perjalanan menuju resolver. Tetapi resolver DNS yang menerima permintaan tetap dapat memprosesnya.

VPN bukan jaminan anonimitas total.

## 11. Skenario kesembilan: Perangkat mati, tidur, atau tidak aktif

Ini juga penting.

Router mungkin menampilkan:
- Online.
- Offline.
- Connected.
- Disconnected.
- DHCP lease.
- Last seen.

Namun status tersebut tidak selalu berarti perangkat benar-benar sedang digunakan manusia.

Contoh:

Laptop masuk sleep mode. Router mungkin masih menyimpan DHCP lease lama. Akibatnya, laptop dapat tetap muncul dalam daftar klien walaupun tidak sedang aktif menggunakan internet.

Sebaliknya, perangkat dapat menyala tetapi tidak mengirimkan trafik.

Jadi ada perbedaan:

1. Perangkat menyala.
2. Perangkat terhubung ke Wi-Fi.
3. Perangkat memperoleh IP address.
4. Perangkat sedang mengirim atau menerima trafik.
5. Perangkat sedang digunakan seseorang.

Lima kondisi tersebut tidak sama.

## 12. Skenario kesepuluh: MAC randomization dan private address

Perangkat modern dapat menggunakan MAC address acak atau private MAC address untuk jaringan Wi-Fi tertentu.

Akibatnya, router mungkin melihat alamat MAC yang berbeda dari alamat perangkat yang digunakan pada jaringan lain.

Ini membuat identifikasi perangkat tidak selalu sederhana.

Selain itu:
- Satu perangkat bisa memiliki beberapa antarmuka jaringan.
- Satu perangkat bisa memiliki MAC berbeda untuk Wi-Fi dan Ethernet.
- Perangkat dapat berpindah antara jaringan.
- Repeater dan mesh dapat membuat pengamatan jaringan lebih kompleks.

Jadi jumlah MAC address bukan selalu jumlah perangkat fisik.

## 13. Apa yang sebenarnya bisa diketahui ISP?

Mari kita rangkum.

| Informasi | Kemungkinan akses ISP |
|---|---|
| IP publik pelanggan | Umumnya ya |
| Waktu koneksi | Umumnya ya |
| Volume trafik | Umumnya ya |
| IP tujuan | Umumnya ya |
| Domain yang dikunjungi | Bisa dalam kondisi tertentu |
| MAC seluruh perangkat LAN | Tidak otomatis |
| IP lokal seluruh perangkat | Tidak otomatis |
| Daftar klien Wi-Fi | Bisa jika tersedia melalui sistem manajemen router |
| Jumlah perangkat terhubung | Bisa dalam kondisi tertentu |
| Isi chat terenkripsi | Tidak dapat dibaca begitu saja |
| Foto dan file pribadi | Tidak otomatis |
| Password perangkat | Tidak otomatis |

Perlu diingat, ISP dapat memiliki sistem monitoring yang berbeda-beda. Kebijakan, konfigurasi, dan kemampuan teknis masing-masing operator tidak bisa disamaratakan.

## 14. Bagaimana cara melindungi jaringan rumah?

Tidak perlu menjadi paranoid. Tetapi jangan juga membiarkan router menggunakan konfigurasi bawaan selamanya.

Checklist sederhana:

- [ ] Ganti password administrator router.
- [ ] Gunakan password Wi-Fi yang kuat.
- [ ] Gunakan WPA2-AES atau WPA3 jika tersedia.
- [ ] Matikan administrasi router dari WAN jika tidak diperlukan.
- [ ] Perbarui firmware.
- [ ] Periksa daftar perangkat yang terhubung.
- [ ] Nonaktifkan WPS jika tidak diperlukan.
- [ ] Gunakan guest network untuk tamu.
- [ ] Aktifkan client isolation jika sesuai kebutuhan.
- [ ] Periksa perangkat yang tidak dikenal.
- [ ] Gunakan segmentasi jaringan untuk perangkat IoT jika memungkinkan.
- [ ] Periksa konfigurasi DNS.
- [ ] Hindari membuka port administrasi router ke internet.

Untuk pengguna IPFire:

- Pastikan seluruh perangkat yang ingin dilindungi benar-benar berada di belakang IPFire.
- Pastikan modem ISP tidak menyediakan jalur Wi-Fi alternatif yang tidak melewati firewall.
- Periksa aturan firewall.
- Periksa DHCP dan DNS.
- Periksa logging.
- Jangan menganggap penggunaan IPFire otomatis membuat jaringan anonim atau tidak terlihat ISP.

## 15. Kesimpulan: Siapa yang bisa melihat apa?

Ada empat pihak yang perlu dibedakan.

### 1. Administrator router

Dapat melihat informasi jaringan lokal yang disediakan oleh router dan sesuai hak aksesnya.

### 2. ISP

Dapat mengamati koneksi pelanggan dari sisi jaringan operator. Jika modem/router dikelola melalui sistem manajemen jarak jauh, ISP mungkin memperoleh informasi tambahan tentang perangkat LAN.

### 3. Hacker yang berhasil menguasai router

Dapat memperoleh informasi yang tersedia melalui hak akses dan fungsi router yang berhasil dikuasainya.

### 4. Hacker yang hanya mengetahui IP publik

Tidak otomatis dapat mengetahui seluruh perangkat di rumah. Ia memerlukan informasi atau akses tambahan.

**Prinsip BLOON:**

- Mengetahui IP publik bukan berarti mengetahui seluruh perangkat rumah.
- Mengetahui jumlah koneksi bukan berarti mengetahui jumlah perangkat.
- Mengetahui perangkat terhubung bukan berarti dapat membaca isinya.
- Menguasai router bukan berarti otomatis menguasai seluruh HP dan komputer.

**Network Visibility ≠ Device Access ≠ Data Access.**

Tiga hal berbeda. Jangan dicampur.

---

## Catatan Metodologi BLOON

Tulisan ini merupakan penjelasan teknis berdasarkan mekanisme umum jaringan IP, NAT, DHCP, administrasi CPE, dan keamanan router.

Tidak ada klaim bahwa ISP tertentu sedang memantau perangkat tertentu.

Tidak ada bukti bahwa jaringan rumah tertentu telah diretas.

Tidak ada hasil pengujian router tertentu yang diklaim sebagai fakta.

Semua skenario harus diverifikasi melalui dokumentasi perangkat, konfigurasi jaringan, log, dan pengujian yang dapat diulang.

**GOBLOK BOLEH. NGARANG JANGAN.**
