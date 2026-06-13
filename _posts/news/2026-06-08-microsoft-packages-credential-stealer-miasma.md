---
title: "Untuk Kedua Kalinya dalam Beberapa Minggu, Paket Microsoft Dibubuhi Pencuri Kredensial"
published: true
author: "Dan Goodin"
category: "news"
description: "73 paket npm Microsoft yang terverifikasi secara kriptografis dibackdoor dengan worm Miasma yang mencuri kredensial dan aktif saat dibuka di agen coding AI."
date: "2026-06-08"
source: "Ars Technica"
source_url: "https://arstechnica.com/security/2026/06/for-the-2nd-time-in-weeks-microsoft-packages-laced-with-credential-stealer/"
tags:
  - Cyber Security
  - Supply Chain Attack
  - Malware
  - Microsoft
  - AI Agents
  - DevOps
  - Open Source
importance_score: "9"
technical_level: "Advanced"

---

## Ringkasan

Untuk kedua kalinya dalam dua bulan, repositori GitHub resmi Microsoft dibobol. Sebanyak 73 paket npm yang terverifikasi secara kriptografis dibackdoor dengan worm Miasma, malware pencuri kredensial yang menjalankan payload sebesar 28 KB untuk mengambil kredensial dari AWS, Azure, GCP, Kubernetes, manajer kata sandi, dan 90+ alat pengembang. Yang paling kritis: malware ini aktif secara otomatis saat pengembang membuka paket di agen coding AI (Claude Code, Gemini CLI, Cursor, VS Code), tanpa perlu menjalankan kode apa pun. Serangan ini menggunakan token OIDC Microsoft yang dicuri untuk menerbitkan build berbahaya dengan bukti asal SLSA yang valid, melewati langkah-langkah keamanan rantai pasok konvensional.

## Poin-Poin Penting

* 73 paket npm resmi Microsoft diracuni dengan worm pencuri kredensial Miasma
* Payload aktif otomatis saat dibuka di agen coding AI (Claude Code, Gemini CLI, Cursor, VS Code)
* Mencuri kredensial dari AWS, Azure, GCP, Kubernetes, 90+ alat pengembang, dan manajer kata sandi
* Token OIDC Microsoft yang dicuri digunakan untuk menandatangani build berbahaya dengan bukti asal SLSA valid
* Setiap infeksi memiliki payload yang dienkripsi secara unik — deteksi berbasis hash sama sekali tidak berguna
* Akun Microsoft yang sama dibobol pada Mei 2026 (insiden durabletask di PyPI, 400k unduhan/bulan)
* GitHub awalnya memberi label paket sebagai "pelanggaran Syarat Layanan" bukan malware
* Worm Miasma (toolkit Mini Shai-Hulud oleh TeamPCP) bersifat open source dan tersedia luas

## Mengapa Ini Penting

Serangan ini mewakili evolusi berbahaya dalam serangan rantai pasok perangkat lunak di berbagai dimensi. Dengan menargetkan agen coding AI sebagai mekanisme pemicu, permukaan serangan meluas secara dramatis — pengembang tidak perlu lagi menjalankan kode, cukup membuka file di IDE mereka. Senjataisasi bukti asal SLSA melawan dirinya sendiri sangat meresahkan: verifikasi kriptografis dirancang untuk meningkatkan kepercayaan, tetapi penyerang mengubahnya menjadi senjata. Bobolnya akun Microsoft yang sama dua kali menimbulkan pertanyaan serius tentang kebersihan kredensial di salah satu perusahaan teknologi terbesar dunia.

## Dampak di Masa Depan

Harapkan beberapa perubahan di tingkat industri: (1) alat coding AI akan menambahkan sandboxing wajib untuk paket yang dibuka, (2) revisi kerangka kerja SLSA untuk mengatasi serangan token OIDC curian, (3) pengawasan ketat di semua registry paket utama (npm, PyPI, GitHub Packages), (4) serangan tiruan yang menargetkan penerbit terkenal lainnya, dan (5) desain ulang fundamental tentang cara kerja penandatanganan paket dan verifikasi identitas dalam rantai pasok perangkat lunak.

## Referensi

- Ars Technica - <a href="https://arstechnica.com/security/2026/06/for-the-2nd-time-in-weeks-microsoft-packages-laced-with-credential-stealer/" target="_blank">https://arstechnica.com/security/2026/06/for-the-2nd-time-in-weeks-microsoft-packages-laced-with-credential-stealer/</a>
