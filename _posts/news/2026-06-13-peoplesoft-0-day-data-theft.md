---
title: Zero-Day Oracle PeopleSoft Dieksploitasi, Ratusan Organisasi Kehilangan GigaByte Data
published: true
author: Tim Penerjemah
category: news
description: Kelompok ransomware ShinyHunters mengeksploitasi kerentanan critical SSRF (CVE-2026-35273, skor 9.8/10) di Oracle PeopleSoft yang menyerang ~100 organisasi, dengan 68% di antaranya adalah institusi pendidikan tinggi. Hingga 48 GB data berhasil dicuri dari satu korban.
---

## Summary

Kelompok ransomware ShinyHunters — salah satu geng kejahatan siber paling aktif di dunia — telah mengeksploitasi kerentanan zero-day kritis di Oracle PeopleSoft, sebuah suite perangkat lunak manajemen sumber daya perusahaan yang digunakan secara luas oleh perguruan tinggi, pemerintah, dan perusahaan besar. Kerentanan yang diidentifikasi sebagai CVE-2026-35273 ini adalah celah SSRF (*Server-Side Request Forgery*) dengan skor keparahan 9.8 dari 10, yang oleh para ahli digambarkan sebagai kerentanan yang "benar-benar kritis."

Serangan telah berlangsung setidaknya sejak 27 Mei 2026, dan Oracle baru memberikan tanda peringatan lebih dari dua minggu kemudian. Hingga 10 Juni, lebih dari 300 endpoint dari sekitar 100 organisasi telah menjadi sasaran. Sekitar 68% dari korban berada di sektor pendidikan tinggi, menjadikan universitas dan institusi akademik sebagai target utama. Salah satu korban — University of Nottingham — telah mengonfirmasi kebocoran data mahasiswa.

Kelompok ShinyHunters, yang aktif sejak setidaknya 2019 dan sebelumnya telah menyerang Ticketmaster, Santander, dan Salesforce, menggunakan celah SSRF ini untuk mengirimkan permintaan dari server PeopleSoft yang rentan ke sistem internal lainnya. Dari sana, mereka meluncurkan serangan rekognisi menggunakan skrip Bash, mengompres data curian dengan algoritma zstd, dan mengeksfiltrasinya melalui koneksi SSH keluar ke alamat IP 176.120.22.24 — situs kebocoran data milik ShinyHunters. Setidaknya satu korban kehilangan 48 GB data dalam satu serangan, dan data telah dipublikasikan di situs DLS (*Data Leak Site*) ShinyHunters setelah korban gagal membayar tebusan.

## Key Points

- **Kerentanan Kritis**: CVE-2026-35273 — SSRF (*Server-Side Request Forgery*) pada Oracle PeopleSoft dengan skor CVSS 9.8/10. Belum ada patch penuh dari Oracle; mitigasi sementara baru dirilis.
- **Aktor**: ShinyHunters, kelompok ransomware/shaktor yang aktif sejak 2019. Sebelumnya menyerang Ticketmaster, Santander, Salesforce, dan lainnya.
- **Korban**: ~100 organisasi, 68% di sektor pendidikan tinggi. ~300 endpoint telah menjadi sasaran.
- **Data Dicuri**: Hingga 48 GB per korban. University of Nottingham mengonfirmasi kompromi data mahasiswa.
- **Metode Eksfiltrasi**: Data dikompres dengan zstd, lalu dieksfiltrasi melalui koneksi SSH keluar ke IP 176.120.22.24 (milik ShinyHunters).
- **Alat Serangan**: Server *staging* ditemukan berisi alat-alat serangan; skrip Bash digunakan untuk memetakan konfigurasi PeopleSoft, melihat konfigurasi Process Scheduler dan WebLogic XML.
- **Timeline**: Eksploitasi sejak 27 Mei 2026. Oracle memberi peringatan setelah >2 minggu. Data dipublikasikan di DLS jika tebusan tidak dibayar.
- **Mitigasi**: Oracle merilis mitigasi sementara (stopgap). Mandiant dan Rapid7 menyediakan IoC (*Indicators of Compromise*) dan langkah remediasi mendesak.

## Why It Matters

Kerentanan Oracle PeopleSoft ini menjadi salah satu serangan siber paling signifikan di tahun 2026, terutama karena dampaknya yang sangat terfokus pada sektor pendidikan tinggi. Universitas dan institusi akademik menyimpan data sensitif dalam jumlah besar — mulai dari data pribadi mahasiswa, catatan keuangan, hingga riset akademik dan kekayaan intelektual — menjadikannya target yang sangat menarik bagi kelompok ransomware.

Fakta bahwa kerentanan ini memiliki skor 9.8 dari 10 menunjukkan betapa mudahnya celah ini dieksploitasi dari jarak jauh tanpa autentikasi. Lebih mengkhawatirkan lagi, Oracle membutuhkan waktu lebih dari dua minggu sejak eksploitasi aktif dimulai untuk memberikan peringatan, dan hingga saat ini patch penuh belum dirilis. Situasi ini menempatkan ratusan organisasi dalam posisi rentan dengan hanya mitigasi sementara sebagai perlindungan.

ShinyHunters sendiri bukan aktor sembarangan. Kelompok ini telah terbukti mampu menyerang perusahaan multinasional besar dan berhasil mengekstrak data dalam jumlah masif. Penggunaan server *staging* dan skrip Bash untuk rekognisi menunjukkan tingkat sofistikasi yang cukup tinggi dalam operasi mereka.

Dampak pada pendidikan tinggi juga menimbulkan kekhawatiran serius: data mahasiswa yang dicuri dapat digunakan untuk pencurian identitas, serangan phishing yang lebih terarah, dan bahkan pemerasan individu. Lebih dari 48 GB data dari satu institusi menandakan volume kerugian yang sangat besar.

## Future Impact

- **Patch Darurat**: Tekanan publik dan luasnya dampak akan memaksa Oracle untuk merilis patch penuh dalam waktu dekat. Namun, kerusakan telah terjadi pada ratusan organisasi.
- **Serangan Lanjutan**: Dengan detail teknis CVE-2026-35273 yang semakin banyak diketahui, aktor ancaman lain kemungkinan akan mengadopsi metode yang sama. Organisasi yang belum menerapkan mitigasi sementara menjadi sasaran empuk.
- **Peningkatan Target Pendidikan Tinggi**: Keberhasilan ShinyHunters menyerang sektor pendidikan akan mendorong kelompok ransomware lain untuk meniru pendekatan ini, menjadikan universitas sebagai target prioritas tinggi.
- **Perubahan Kebijakan Keamanan**: Institusi pendidikan tinggi akan dipaksa untuk meningkatkan postur keamanan siber mereka secara signifikan — termasuk segmentasi jaringan, pemantauan koneksi SSH keluar yang mencurigakan, dan pembatasan akses server PeopleSoft.
- **Kepatuhan Regulasi**: Kebocoran data mahasiswa dalam skala besar ini dapat memicu penyelidikan regulator di berbagai yurisdiksi, terutama terkait kepatuhan terhadap GDPR di Eropa dan undang-undang perlindungan data di negara lain.
- **Efek Domino**: Data yang dicuri dari universitas dapat digunakan untuk serangan lebih lanjut terhadap jaringan alumni, mitra riset, dan organisasi afiliasi lainnya.

## References

1. Ars Technica — "PeopleSoft 0-day affecting hundreds of organizations steals gigabytes of data" oleh Dan Goodin, 12 Juni 2026. https://arstechnica.com/security/2026/06/peoplesoft-0-day-affecting-hundreds-of-organizations-steals-gigabytes-of-data/
2. Mandiant (Google Cloud) — "ShinyHunters Targets Education Sector with Oracle PeopleSoft Exploit". https://cloud.google.com/blog/topics/threat-intelligence/shinyhunters-targets-education-sector-oracle-exploit
3. Rapid7 — "Active Exploitation of Oracle PeopleSoft Zero-Day CVE-2026-35273". https://www.rapid7.com/blog/post/etr-active-exploitation-of-oracle-peoplesoft-zero-day-cve-2026-35273/
4. Oracle Security Advisory — CVE-2026-35273 dan mitigasi sementara.

***

*Artikel ini diterjemahkan dan diringkas dari laporan asli Ars Technica oleh Dan Goodin. Dipublikasikan: 13 Juni 2026.*
