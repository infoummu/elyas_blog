---
title: "Serangan Dekomposisi Konteks-Terfragmentasi pada Agen LLM Pengguna Alat: Eksploitasi Celah Provenans Artefak"
published: true
author: "Research Paper"
category: "research"
description: "Kelas serangan adversarial baru terhadap agen LLM pengguna alat yang mengeksploitasi celah provenans antara konteks eksekusi yang terdekomposisi untuk menyuntikkan artefak berbahaya."
date: "2026-06-08"
source: "arXiv"
source_url: "https://arxiv.org/abs/2606.09084"
tags:
  - AI Security
  - LLM Agents
  - Cyber Security
  - Adversarial Attacks
  - Agentic AI
  - Research
  - Tool-Using Agents
importance_score: "8"
technical_level: "Expert"

---

## Research Background

Agen large language model (LLM) semakin bergantung pada kemampuan penggunaan alat — mengeksekusi kode, mengakses database, menjelajah web, dan memanipulasi file. Agen-agen ini menguraikan tugas kompleks menjadi subtugas yang dieksekusi di berbagai pemanggilan alat. Setiap pemanggilan biasanya beroperasi dalam konteks eksekusinya sendiri, menciptakan celah provenans antara penalaran agen, output alat, dan pengambilan keputusan akhir. Meskipun dekomposisi memungkinkan alur kerja multi-langkah yang canggih, ia juga memperkenalkan permukaan serangan yang fundamentally baru: lawan dapat menyuntikkan artefak berbahaya yang mengeksploitasi celah provenans ini.

## Research Objective

Makalah ini memperkenalkan serangan Context-Fractured Decomposition (CFD) — kelas serangan adversarial baru yang dirancang khusus untuk mengeksploitasi celah provenans yang diciptakan oleh dekomposisi tugas agen. Tujuannya adalah untuk mendemonstrasikan bahwa arsitektur agen LLM saat ini rentan terhadap serangan yang memanipulasi artefak antara subtugas yang terdekomposisi.

## Methodology

Para peneliti merancang empat varian serangan CFD yang konkret: (1) Artifact Injection — menyuntikkan konten berbahaya ke file atau database perantara, (2) Context Poisoning — memanipulasi sinyal kontekstual yang diteruskan antara subtugas, (3) Provenance Spoofing — memalsukan metadata provenans untuk salah mengatribusikan asal artefak, dan (4) Temporal Reordering — mengeksploitasi celah waktu antara eksekusi alat asinkron. Serangan dievaluasi terhadap beberapa sistem agen LLM mutakhir (AutoGPT, agen LangChain, OpenAI Assistants API) di 12 tugas tolok ukur.

## Main Findings

* Serangan CFD mencapai tingkat keberhasilan 84% di semua arsitektur agen yang diuji
* Provenance spoofing adalah varian paling efektif (tingkat keberhasilan 91%)
* Agen LLM saat ini tidak memiliki kemampuan pelacakan provenans bawaan
* Rantai tugas yang lebih panjang (5+ subtugas) secara signifikan lebih rentan (92%) daripada rantai pendek (47%)
* Semua kerangka kerja agen utama yang diuji rentan tanpa mitigasi yang ada
* Deteksi oleh alat keamanan yang ada mendekati nol (tingkat deteksi 2%)

## Contributions

Makalah ini memberikan beberapa kontribusi baru: (1) identifikasi kelas kerentanan yang sebelumnya tidak terdokumentasi dalam arsitektur agen LLM, (2) karakterisasi formal serangan CFD dengan empat varian operasional, (3) evaluasi empiris komprehensif di berbagai kerangka kerja agen dan jenis tugas, (4) demonstrasi bahwa celah provenans adalah kelemahan arsitektural fundamental, dan (5) kerangka kerja pertahanan yang diusulkan yang mencakup pelacakan provenans artefak dan validasi lintas konteks.

## Limitations

Studi dilakukan di lingkungan laboratorium yang terkontrol, bukan sistem produksi. Permukaan serangan di deployment dunia nyata dengan lapisan keamanan tambahan mungkin berbeda. Agen yang berjalan lama dengan persistensi status tidak diuji sepenuhnya. Overhead komputasi dari pertahanan yang diusulkan tidak dikuantifikasi.

## Future Research Opportunities

Area kritis untuk pekerjaan masa depan meliputi: (1) mengembangkan sistem pelacakan provenans praktis untuk kerangka kerja agen LLM, (2) protokol verifikasi integritas lintas konteks, (3) studi deployment dunia nyata untuk memvalidasi temuan laboratorium, (4) mekanisme pertahanan yang menyeimbangkan keamanan dengan kinerja agen, dan (5) standarisasi praktik terbaik keamanan agen.

## Referensi

- arXiv - <a href="https://arxiv.org/abs/2606.09084" target="_blank">https://arxiv.org/abs/2606.09084</a>
