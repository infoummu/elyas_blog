---
title: "Persaingan Panas dengan Peneliti, Microsoft Akhirnya Perbaiki Dua Celah Zero-Day"
published: true
author: "Dan Goodin"
category: "news"
description: "Microsoft memperbaiki dua celah zero-day yang diungkap peneliti Nightmare Eclipse di tengah perseteruan sengit, termasuk satu kerentanan LPE berbahaya."
date: "2026-06-09"
source: "Ars Technica"
source_url: "https://arstechnica.com/security/2026/06/locked-in-heated-rivalry-with-researcher-microsoft-fixes-0-day-they-disclosed/"
tags:
  - Microsoft
  - Zero-Day
  - Keamanan Siber
  - Patch Tuesday
  - Windows
  - CVE-2026-45586
  - LPE
importance_score: "9"
technical_level: "Intermediate"
---

## Summary

Microsoft akhirnya merilis tambalan untuk dua celah keamanan zero-day yang diungkapkan oleh peneliti keamanan independen yang dikenal dengan nama samaran Nightmare Eclipse. Perseteruan sengit antara Microsoft dan peneliti tersebut memanas setelah peneliti mengklaim bahwa Microsoft mengingkari perjanjian yang telah disepakati, yang berakibat pada kerugian pribadi yang serius hingga ia kehilangan tempat tinggal. Tambalan ini dirilis melalui Patch Tuesday Juni 2026, mencakup sekitar 200 kerentanan secara keseluruhan, termasuk CVE-2026-45586 (GreenPlasma), sebuah celah Local Privilege Escalation (LPE) di Windows Collaborative Translation Framework yang dinilai memiliki kompleksitas eksploitasi minimal dan tidak memerlukan interaksi pengguna sama sekali. Microsoft sendiri mengakui bahwa kemungkinan eksploitasi aktif di alam liar cukup tinggi untuk kerentanan ini. Satu celah lainnya, MiniPlasma, ternyata merupakan regresi dari CVE-2020-17103 yang seharusnya sudah diperbaiki enam tahun lalu — menunjukkan bahwa proses patch management Microsoft masih memiliki kelemahan serius. Meskipun telah merilis tambalan untuk kedua zero-day ini, beberapa kerentanan kritis lainnya seperti YellowKey yang mampu menembus enkripsi BitLocker secara fisik masih belum mendapatkan perbaikan resmi, hanya mitigasi manual yang tersedia.

## Key Points

* Microsoft merilis patch untuk dua zero-day (GreenPlasma/CVE-2026-45586 dan MiniPlasma/regresi CVE-2020-17103) pada Patch Tuesday Juni 2026
* GreenPlasma adalah kerentanan Local Privilege Escalation di Windows Collaborative Translation Framework dengan tingkat eksploitasi rendah dan tanpa perlu interaksi pengguna
* MiniPlasma merupakan kerentanan yang muncul kembali (regresi) dari CVE-2020-17103 yang seharusnya sudah ditambal enam tahun lalu
* Peneliti Nightmare Eclipse mengklaim Microsoft melanggar perjanjian yang menyebabkan dirinya kehilangan tempat tinggal
* Microsoft awalnya mengancam akan mengambil tindakan hukum terhadap peneliti, namun kemudian membatalkannya setelah mendapat kecaman publik
* Nightmare Eclipse terus mempublikasikan kode exploit baru, termasuk race condition yang menargetkan Windows Defender
* Kerentanan YellowKey yang menembus enkripsi BitLocker masih belum mendapatkan patch resmi

## Why It Matters

Kasus ini menyoroti dinamika kompleks dalam hubungan antara vendor perangkat lunak dan peneliti keamanan independen di era modern. Model responsible disclosure yang selama ini dianggap sebagai standar emas dalam industri keamanan siber sedang diuji. Ketika seorang peneliti merasa dikhianati oleh vendor dan kehilangan insentif untuk bekerja sama, konsekuensinya bisa berbahaya: publikasi kode exploit secara penuh yang memaparkan jutaan pengguna pada risiko.

Yang lebih mengkhawatirkan, kerentanan MiniPlasma yang merupakan regresi dari tambalan enam tahun lalu menunjukkan bahwa proses patch management Microsoft masih memiliki celah serius — kerentanan yang seharusnya sudah mati bisa kembali hidup. Sementara itu, YellowKey yang menembus BitLocker — fitur keamanan inti Windows — masih belum memiliki solusi selain mitigasi manual. Bagi organisasi yang mengandalkan BitLocker untuk melindungi data pada perangkat yang hilang atau dicuri, ini adalah risiko yang sangat serius.

## Future Impact

Perseteruan antara Microsoft dan Nightmare Eclipse berpotensi mengubah lanskap bug bounty dan responsible disclosure secara lebih luas. Jika semakin banyak peneliti keamanan yang kehilangan kepercayaan pada program vendor, kita mungkin akan melihat lebih banyak publikasi zero-day secara terbuka — tren yang merugikan keamanan siber secara keseluruhan.

Kerentanan regresi seperti MiniPlasma juga menimbulkan pertanyaan serius tentang kualitas proses patch Microsoft. Ke depannya, Microsoft perlu berinvestasi lebih besar dalam pengujian regresi dan verifikasi keamanan tambalan agar celah yang sudah diperbaiki tidak muncul kembali secara tidak sengaja.

YellowKey yang belum ditambal menjadi bom waktu bagi pengguna Windows yang mengandalkan BitLocker. Hingga patch resmi dirilis, perangkat fisik yang jatuh ke tangan yang salah tetap rentan, dan ini akan terus menjadi vektor serangan yang menarik bagi pelaku kejahatan siber.

## References

- Ars Technica - <a href="https://arstechnica.com/security/2026/06/locked-in-heated-rivalry-with-researcher-microsoft-fixes-0-day-they-disclosed/" target="_blank">https://arstechnica.com/security/2026/06/locked-in-heated-rivalry-with-researcher-microsoft-fixes-0-day-they-disclosed/</a>
