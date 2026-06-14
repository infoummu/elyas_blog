---
layout: post
title: "Alat Open Source Microsoft Diretas untuk Mencuri Kata Sandi Developer AI"
date: 2026-06-08 13:03:00 +0700
category:
  - keamanan-siber
  - open-source
  - ai
  - microsoft
source: TechCrunch
source_url: https://techcrunch.com/2026/06/08/microsofts-open-source-tools-were-hacked-to-steal-passwords-of-ai-developers/
author: Zack Whittaker
---

## Summary

Microsoft menonaktifkan akses ke puluhan proyek open source-nya di GitHub setelah ditemukan bahwa peretas berhasil menyuntikkan malware pencuri kata sandi ke dalam kode repositori tersebut. Serangan rantai pasokan (supply chain attack) ini menargetkan alat-alat yang terkait dengan **Microsoft Azure** dan aplikasi pengembangan AI seperti **Claude Code**, **Gemini CLI**, dan **VS Code**. Setidaknya **70 repositori Microsoft** dinonaktifkan, dan ini merupakan pelanggaran kedua yang menimpa proyek open source Microsoft dalam beberapa pekan terakhir.

## Key Points

- **Jenis serangan:** Serangan rantai pasokan — malware pencuri kredensial disuntikkan ke dalam proyek open source yang tersedia untuk publik.
- **Target utama:** Alat-alat pengembangan AI dan Azure, termasuk yang digunakan bersama Claude Code, Gemini CLI, dan VS Code.
- **Skala:** Setidaknya **70 proyek Microsoft** dinonaktifkan di GitHub. Microsoft menyebut "sejumlah kecil" pelanggan yang terdampak telah diberitahu.
- **Dampak:** Pengguna yang mengunduh dan membuka alat yang dikompromikan di aplikasi coding AI mereka berisiko kata sandi dan kredensial sensitifnya dicuri.
- **Insiden kedua:** Ini adalah **pelanggaran open-source kedua Microsoft dalam beberapa pekan**. Pada pertengahan Mei, proyek **Durable Task** juga diretas. OpenSourceMalware menyebut insiden ini sebagai "re-kompromi" dari proyek yang sama.
- **Respons:** Microsoft menarik repositori, memulihkan beberapa setelah ditinjau, dan menyisakan lainnya offline sementara penyelidikan berlanjut.

## Why It Matters

Serangan ini menyoroti **kerentanan serius dalam rantai pasokan perangkat lunak open source**, terutama yang digunakan oleh ekosistem pengembangan AI. Fakta bahwa Microsoft sendiri — perusahaan yang memiliki GitHub — menjadi korban serangan semacam ini menunjukkan bahwa **tidak ada yang kebal** terhadap ancaman rantai pasokan. Dengan semakin banyaknya developer AI yang mengandalkan alat open source dari GitHub, insiden ini menjadi peringatan keras tentang perlunya verifikasi integritas kode dan praktik keamanan yang lebih ketat dalam proses pengembangan perangkat lunak.

## Future Impact

- **Peningkatan keamanan GitHub:** Microsoft kemungkinan akan memperketat kebijakan keamanan di GitHub, termasuk verifikasi komitmen yang ditandatangani dan pemindaian malware otomatis yang lebih ketat.
- **Kesadaran developer AI:** Developer yang menggunakan alat AI open source perlu menerapkan praktik keamanan yang lebih ketat — verifikasi hash, tinjauan kode, dan rotasi kredensial secara berkala.
- **Kebijakan perusahaan:** Perusahaan yang mengadopsi AI kemungkinan akan menerapkan kebijakan rantai pasokan yang lebih ketat untuk semua dependensi open source.
- **Eskalasi ancaman:** Serangan terhadap rantai pasokan perangkat lunak AI diperkirakan akan meningkat karena para peretas mengejar akses ke sistem cloud dan data pelanggan melalui kredensial developer AI.

## References

- [TechCrunch: Microsoft's open source tools were hacked to steal passwords of AI developers](https://techcrunch.com/2026/06/08/microsofts-open-source-tools-were-hacked-to-steal-passwords-of-ai-developers/)
- Ars Technica: [For the 2nd time in weeks, Microsoft packages laced with credential stealer](https://arstechnica.com/security/2026/06/for-the-2nd-time-in-weeks-microsoft-packages-laced-with-credential-stealer/)
- 404 Media (laporan pertama)
- Cloudsmith & OpenSourceMalware (analisis malware)
