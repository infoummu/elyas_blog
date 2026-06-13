---
title: "Zero-Trust Agentic Federated Learning for Secure IIoT Defense Systems — Keamanan Federated Learning untuk Pertahanan Industri IoT"
published: true
author: "Samaresh Kumar Singh, Joyjit Roy, Martin So"
category: "research"
description: "Framework Zero-Trust Agentic Federated Learning (ZTA-FL) yang menggabungkan attestasi TPM, agregasi SHAP-weighted, dan adversarial training on-device untuk deteksi intrusi IIoT."
date: "2026-06-13"
source: "arXiv"
source_url: "https://arxiv.org/abs/2512.23809"
tags:
  - cybersecurity
  - federated-learning
  - iiot
  - zero-trust
  - intrusion-detection
  - machine-learning
importance_score: "9"
technical_level: "Advanced"
---

## Research Background

Serangan baru-baru ini pada infrastruktur kritis — termasuk pelanggaran pengolahan air Oldsmar 2021 dan kompromi sektor energi Denmark 2023 — menyoroti kesenjangan keamanan mendesak dalam deployment Industrial Internet of Things (IIoT). Federated Learning (FL) memungkinkan deteksi intrusi kolaboratif yang menjaga privasi, namun kerangka FL yang ada tetap rentan terhadap serangan Byzantine poisoning dan tidak memiliki mekanisme autentikasi agen yang kuat. Ketergantungan pada arsitektur trust-based tradisional membuat sistem FL mudah dieksploitasi oleh node jahat.

## Research Objective

Penelitian ini bertujuan untuk mengusulkan **Zero-Trust Agentic Federated Learning (ZTA-FL)**, sebuah kerangka pertahanan berlapis yang menggabungkan: (1) attestasi kriptografi berbasis TPM (Trusted Platform Module), (2) algoritma agregasi SHAP-weighted untuk deteksi Byzantine yang dapat dijelaskan, dan (3) adversarial training on-device yang menjaga privasi. Tujuannya adalah menciptakan sistem FL yang aman terhadap serangan poisoning sambil mempertahankan akurasi deteksi yang tinggi.

## Methodology

ZTA-FL dibangun dengan tiga lapisan pertahanan:

1. **TPM-based Cryptographic Attestation**: Setiap agen FL harus membuktikan identitas dan integritas perangkat kerasnya melalui TPM, mencapai false acceptance rate (FAR) kurang dari 0.0000001 (10⁻⁷).
2. **SHAP-weighted Aggregation Algorithm**: Algoritma agregasi baru yang menggunakan nilai SHAP (SHapley Additive exPlanations) untuk mendeteksi dan menimbang kontribusi setiap klien secara explainable, dengan jaminan teoretis terhadap kondisi non-IID.
3. **Privacy-preserving On-Device Adversarial Training**: Pelatihan adversarial yang dilakukan langsung di perangkat untuk meningkatkan ketahanan model tanpa mengorbankan privasi data.

Evaluasi dilakukan pada tiga benchmark IDS: Edge-IIoTset, CIC-IDS2017, dan UNSW-NB15.

## Main Findings

Hasil eksperimen komprehensif menunjukkan:

| Metrik | Hasil |
|--------|-------|
| Detection Accuracy | **97.8%** |
| Accuracy di bawah 30% serangan Byzantine | **93.2%** (mengalahkan FLAME sebesar 3.1%, p < 0.01) |
| Adversarial Robustness | **89.3%** |
| Pengurangan Communication Overhead | **34%** |

ZTA-FL secara konsisten mengungguli metode baseline termasuk FLAME, Krum, dan Trimmed Mean dalam skenario serangan Byzantine dengan berbagai tingkat keparahan.

## Contributions

1. **Framework keamanan berlapis pertama** yang menggabungkan attestasi perangkat keras TPM, agregasi SHAP, dan adversarial training dalam konteks FL untuk IIoT.
2. **Algoritma SHAP-weighted aggregation** yang menyediakan deteksi Byzantine secara explainable dengan jaminan teoretis, berbeda dengan metode black-box sebelumnya.
3. **Analisis mode kegagalan** yang komprehensif dan karakterisasi teoretis dari berbagai jenis serangan terhadap FL.
4. **Pengurangan komunikasi 34%** melalui teknik agregasi yang efisien, menjadikannya praktis untuk deployment di lingkungan IIoT dengan bandwidth terbatas.
5. **Kode sumber terbuka** yang dirilis untuk reproduksibilitas.

## Limitations

1. Studi ini berfokus pada serangan Byzantine poisoning; vektor serangan lain seperti model inversion dan membership inference belum dieksplorasi secara mendalam.
2. Ketergantungan pada TPM sebagai root of trust memperkenalkan asumsi bahwa TPM itu sendiri tidak dikompromikan.
3. Overhead komputasi dari perhitungan SHAP pada perangkat IIoT dengan sumber daya terbatas belum dianalisis secara detail.
4. Dataset yang digunakan bersifat publik dan mungkin tidak sepenuhnya merepresentasikan lingkungan IIoT produksi nyata.

## Future Research Opportunities

1. **Integrasi dengan blockchain**: Menggabungkan ZTA-FL dengan ledger terdistribusi untuk immutability catatan attestasi dan agregasi.
2. **Heterogeneous FL**: Memperluas framework untuk menangani perangkat dengan kapabilitas komputasi yang sangat beragam.
3. **Adaptive threat detection**: Mengembangkan mekanisme deteksi ancaman adaptif yang dapat merespons pola serangan yang berubah secara real-time.
4. **Cross-domain transfer learning**: Mengeksplorasi transfer pengetahuan antar domain IIoT yang berbeda (misalnya, manufaktur ke energi).

## References

- **arXiv** - <a href="https://arxiv.org/abs/2512.23809" target="_blank">https://arxiv.org/abs/2512.23809</a>
- **DOI** - <a href="https://doi.org/10.48550/arXiv.2512.23809" target="_blank">10.48550/arXiv.2512.23809</a>
