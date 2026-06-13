---
title: "Governing Cloud Data Pipelines with Agentic AI — Arsitektur Kontrol Berbasis Kebijakan untuk Pipeline Data Cloud"
published: true
author: "Aswathnarayan Muthukrishnan Kirubakaran, Adithya Parthasarathy, Nitin Saksena, Ram Sekhar Bodala, Akshay Deshpande, Suhas Malempati, Shiva Carimireddy, Abhirup Mazumder"
category: "research"
description: "Arsitektur Agentic Cloud Data Engineering yang mengintegrasikan AI agent terikat kebijakan ke dalam bidang kendali pipeline data cloud untuk mengurangi waktu pemulihan hingga 45%."
date: "2026-06-13"
source: "arXiv"
source_url: "https://arxiv.org/abs/2512.23737"
tags:
  - cloud-computing
  - ai-agents
  - data-pipelines
  - cloud-engineering
  - policy-aware
importance_score: "8"
technical_level: "Advanced"
---

## Research Background

Pipeline data cloud modern beroperasi di bawah beban kerja dinamis, skema yang terus berkembang, batasan biaya, dan persyaratan tata kelola yang ketat. Meskipun ada kemajuan dalam kerangka orkestrasi cloud-native, sebagian besar pipeline produksi masih mengandalkan konfigurasi statis dan praktik operasional reaktif. Hal ini mengakibatkan waktu pemulihan yang berkepanjangan, utilisasi sumber daya yang tidak efisien, dan overhead manual yang tinggi. Kesenjangan antara kebutuhan tata kelola yang kompleks dan kemampuan orkestrasi statis menjadi masalah kritis di lingkungan enterprise berskala besar.

## Research Objective

Penelitian ini bertujuan untuk mengusulkan dan mengevaluasi **Agentic Cloud Data Engineering** — sebuah arsitektur kontrol sadar-kebijakan yang mengintegrasikan AI agent terikat (bounded AI agents) ke dalam bidang kendali dan tata kelola pipeline data cloud. Tujuan utamanya adalah mengurangi intervensi manual, menurunkan biaya operasional, dan mempercepat pemulihan kegagalan pipeline sambil mempertahankan kepatuhan terhadap kebijakan tata kelola data.

## Methodology

Peneliti merancang platform Agentic Cloud Data Engineering dengan komponen-komponen berikut:

1. **Specialized AI Agents**: Agen khusus yang menganalisis telemetri dan metadata pipeline, melakukan penalaran atas kebijakan biaya dan kepatuhan deklaratif, serta mengusulkan tindakan operasional terbatas.
2. **Constrained Action Space**: Tindakan yang diusulkan dibatasi pada rekonfigurasi sumber daya adaptif, rekonsiliasi skema, dan pemulihan kegagalan otomatis.
3. **Policy Validation Layer**: Semua tindakan agen divalidasi terhadap kebijakan tata kelola untuk memastikan perilaku yang dapat diprediksi dan diaudit.

Evaluasi dilakukan menggunakan beban kerja batch dan streaming analitik representatif yang dibangun dari dataset publik bergaya enterprise.

## Main Findings

Hasil eksperimen menunjukkan peningkatan signifikan pada tiga metrik utama:

- **Mean pipeline recovery time**: Berkurang hingga **45%** dibandingkan orkestrasi statis.
- **Operational cost**: Turun sekitar **25%** melalui alokasi sumber daya yang lebih efisien.
- **Manual intervention events**: Menurun lebih dari **70%** karena agen AI menangani kegagalan secara otonom.

Seluruh peningkatan ini dicapai tanpa mengorbankan **data freshness** dan **policy compliance**, yang tetap terjaga pada tingkat yang sama dengan pendekatan tradisional.

## Contributions

1. **Arsitektur baru** untuk tata kelola pipeline data cloud yang memadukan AI agent dengan kebijakan deklaratif.
2. **Validasi empiris** pada beban kerja batch dan streaming yang menunjukkan pengurangan biaya dan waktu pemulihan yang signifikan.
3. **Pendekatan policy-bounded agentic control** yang memastikan tindakan agen dapat diaudit dan diprediksi, mengatasi masalah kepercayaan pada AI otonom di enterprise.
4. **Kerangka kerja** yang dapat direproduksi menggunakan dataset publik untuk memfasilitasi penelitian lanjutan.

## Limitations

1. Evaluasi dilakukan pada dataset sintetis bergaya enterprise, bukan pada pipeline produksi langsung dari perusahaan tertentu.
2. Studi ini tidak membahas aspek keamanan siber secara mendalam, seperti potensi serangan adversarial terhadap agen AI itu sendiri.
3. Skalabilitas arsitektur pada lingkungan dengan ribuan pipeline paralel belum diuji secara ekstensif.
4. Biaya komputasi tambahan dari menjalankan AI agent belum dianalisis secara detail.

## Future Research Opportunities

1. **Integrasi dengan MLOps**: Menggabungkan agentic control dengan pipeline machine learning untuk governance model端-to-end.
2. **Multi-cloud orchestration**: Memperluas arsitektur untuk menangani pipeline yang tersebar di beberapa penyedia cloud.
3. **Human-in-the-loop optimization**: Meneliti keseimbangan optimal antara otonomi agen dan pengawasan manusia.
4. **Real-time policy adaptation**: Mengembangkan mekanisme pembaruan kebijakan dinamis berdasarkan perubahan kondisi bisnis dan regulasi.

## References

- **arXiv** - <a href="https://arxiv.org/abs/2512.23737" target="_blank">https://arxiv.org/abs/2512.23737</a>
- **IJCST Volume 13 Issue 6** - <a href="https://www.ijcstjournal.org/volume-13/issue-6/IJCST-V13I6P44.pdf" target="_blank">https://www.ijcstjournal.org/volume-13/issue-6/IJCST-V13I6P44.pdf</a>
- **DOI** - <a href="https://doi.org/10.5281/zenodo.18048728" target="_blank">10.5281/zenodo.18048728</a>
