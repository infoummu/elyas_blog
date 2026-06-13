---
title: "ForenSeeker: Platform Pemeriksaan Forensik Digital Otomatis dengan Pemanfaatan Tools Open Source"
published: true
author: "Stefanus Santori Zen, Jeckson Sidabutar, Setiyo Cahyono, Tiyas Yulita, Rheva Anindya Wijayanti"
category: "research"
description: "Paper ini merancang platform forensik digital otomatis ForenSeeker berbasis CLI Linux dengan integrasi Telegram Bot menggunakan bash scripting dan Agile SDLC Kanban."
date: "2026-06-13"
source: "IEEE Conference on Electrical Engineering, Computer Science and Informatics (EECSI) 2025"
source_url: "https://doi.org/10.1109/EECSI67060.2025.11290359"
tags: [digital forensics, linux, open-source, automation, cybersecurity]
importance_score: "8"
technical_level: "Intermediate"
---

## Research Background

Pertumbuhan penetrasi internet yang pesat di Indonesia berbanding lurus dengan peningkatan serangan siber. Contoh nyata adalah serangan ransomware Brain Cipher (varian Lockbit 3.0) yang melumpuhkan PDNS 2 Surabaya dan menghentikan layanan imigrasi selama tiga hari. Audit forensik digital yang dilakukan BSSN menunjukkan bahwa kemampuan mengidentifikasi akar penyebab insiden secara cepat melalui bukti digital sangat penting untuk memperpendek waktu pemulihan layanan. Namun, proses pemeriksaan bukti digital secara konvensional seringkali rumit dan tidak efisien, sehingga menghambat upaya pemulihan pasca-serangan.

Framework forensik yang banyak diadopsi seperti DFRWS (7 tahap) dan NIST SP 800-86 (4 tahap) menempatkan proses *examination* (pemeriksaan) sebagai inti dari forensik digital. Tahap ini membutuhkan alat-alat khusus untuk mengekstrak dan memeriksa data. Di sinilah diperlukan sebuah platform yang mampu melakukan proses pemeriksaan bukti digital secara praktis, efisien, dan terotomatisasi.

## Research Objective

Penelitian ini bertujuan untuk merancang dan membangun sebuah platform pemeriksaan forensik digital otomatis bernama ForenSeeker yang memanfaatkan berbagai tools open source dengan integrasi Telegram Bot, sehingga proses instalasi tools, pemeriksaan bukti digital, dan pelaporan hasil dapat dilakukan secara otomatis dan efisien melalui Command Line Interface (CLI) Linux.

## Methodology

Penelitian ini menggunakan metodologi **Agile Software Development Life Cycle (SDLC)** dengan visualisasi **Kanban Model**. Tahapan pengembangan meliputi:

1. **Analysis** — Identifikasi kebutuhan sistem dan tools forensik open source yang relevan.
2. **Design** — Perancangan arsitektur platform berbasis CLI dengan skrip bash dan integrasi Telegram Bot.
3. **Develop** — Implementasi platform menggunakan bash scripting untuk mengotomatiskan proses instalasi, pemeriksaan, dan pelaporan.
4. **Testing** — Pengujian meliputi:
   - **Alpha Testing**: Seluruh test case dijalankan untuk memvalidasi fungsionalitas platform.
   - **Beta Testing (User Acceptance Test / UAT)**: Pengujian oleh pengguna akhir untuk mengukur tingkat penerimaan.
   - **Performance Testing**: Pengujian beban sistem dan alokasi memori.
5. **Deploy** — Penerapan platform di lingkungan nyata dengan prinsip *pull system* dan pembatasan Work-in-Progress (WIP).

## Main Findings

Platform ForenSeeker berhasil melewati seluruh rangkaian pengujian dengan hasil sebagai berikut:

- **Alpha Testing**: Seluruh test case terpenuhi tanpa kegagalan.
- **Beta Testing (UAT)**: Tingkat penerimaan pengguna mencapai **100%**, menunjukkan bahwa platform sangat mudah digunakan dan memenuhi kebutuhan pengguna.
- **Performance Testing**: Pengujian beban sistem menunjukkan *load average* tertinggi **2.61**, dengan alokasi memori *used* berkisar **500–600 MB**. Hasil ini membuktikan bahwa platform mampu bekerja secara stabil dan optimal bahkan di bawah beban tinggi.

ForenSeeker mengintegrasikan berbagai tools forensik open source dalam satu ekosistem yang terotomatisasi. Telegram Bot berfungsi sebagai antarmuka untuk memicu proses pemeriksaan dan menerima laporan hasil secara real-time, memungkinkan tim keamanan untuk merespons insiden dengan lebih cepat.

## Contributions

Kontribusi utama dari penelitian ini adalah:

1. **Platform Forensik Otomatis Open Source**: ForenSeeker menyediakan solusi forensik digital yang sepenuhnya otomatis berbasis tools open source, mengurangi ketergantungan pada perangkat lunak komersial yang mahal.
2. **Integrasi Telegram Bot**: Inovasi dalam menghubungkan platform forensik CLI dengan notifikasi real-time melalui Telegram Bot, mempercepat alur kerja respons insiden.
3. **Metodologi Agile pada Forensik Digital**: Penerapan Agile SDLC dengan Kanban Model dalam pengembangan alat forensik, yang jarang dilakukan di domain ini.
4. **Efisiensi Operasional**: Otomatisasi proses instalasi, pemeriksaan, dan pelaporan mengurangi waktu dan kompleksitas yang dibutuhkan dalam investigasi forensik digital.

## Limitations

1. **Ketergantungan pada CLI**: Platform hanya beroperasi pada Command Line Interface, sehingga membutuhkan pengguna yang memiliki kompetensi teknis dalam lingkungan Linux terminal.
2. **Lingkungan Terbatas**: Pengujian dilakukan dalam lingkungan laboratorium dan belum diuji pada berbagai skenario insiden dunia nyata yang lebih kompleks.
3. **Ketersediaan Tools**: Keberhasilan platform sangat bergantung pada ketersediaan dan kompatibilitas tools open source yang digunakan.
4. **Cakupan Platform**: Platform saat ini masih terbatas pada sistem operasi Linux dan belum mendukung platform lain seperti Windows atau macOS.

## Future Research Opportunities

1. **Pengembangan Antarmuka Grafis (GUI)**: Menambahkan antarmuka pengguna grafis untuk memperluas aksesibilitas bagi pemeriksa forensik yang kurang terbiasa dengan CLI.
2. **Dukungan Multi-Platform**: Memperluas kompatibilitas ke sistem operasi Windows dan macOS.
3. **Integrasi dengan SIEM**: Menghubungkan ForenSeeker dengan sistem Security Information and Event Management (SIEM) untuk alur kerja respons insiden yang lebih terpadu.
4. **Pembelajaran Mesin**: Mengintegrasikan algoritma machine learning untuk deteksi anomali dan klasifikasi bukti digital secara cerdas.
5. **Validasi di Lingkungan Nyata**: Pengujian lebih lanjut pada berbagai studi kasus insiden siber di Indonesia untuk memvalidasi efektivitas platform.

## References

1. Zen, S. S., Sidabutar, J., Cahyono, S., Yulita, T., & Wijayanti, R. A. (2025). ForenSeeker: An Automated Digital Forensic Examination Platform with Open-source Tools Utilization. *2025 12th International Conference on Electrical Engineering, Computer Science and Informatics (EECSI)*. IEEE. DOI: [10.1109/EECSI67060.2025.11290359](https://doi.org/10.1109/EECSI67060.2025.11290359)
2. BSSN. (2024). Laporan Tahunan Monitoring Keamanan Siber Indonesia. Badan Siber dan Sandi Negara.
3. Digital Forensic Research Workshop (DFRWS). (2001). A Road Map for Digital Forensic Research. Report from the First Digital Forensic Research Workshop.
4. National Institute of Standards and Technology (NIST). (2006). NIST SP 800-86: Guide to Integrating Forensic Techniques into Incident Response.
5. Carrier, B. (2005). File System Forensic Analysis. Addison-Wesley Professional.
