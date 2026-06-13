---
title: "Kemunculan Kemampuan Penetrasi Otonom pada Sistem AI Berbasis LLM"
published: true
author: "Tim Riset Hacker Blog"
category: "research"
description: "Penelitian mengevaluasi kemampuan 19 model LLM untuk melakukan penetration testing otonom pada 300 server target, menemukan tingkat keberhasilan 10,7% hingga 69,3%."
date: "2026-06-13"
source: "arXiv"
source_url: "https://arxiv.org/abs/2606.13079"
tags: [autonomous-pentest, llm-security, red-teaming, ai-safety, cs.CR]
importance_score: "9"
technical_level: "Advanced"
---

## Research Background

Eksekusi otonom serangan siber yang mampu menyebabkan kerusakan nyata yang substansial secara luas dianggap sebagai salah satu red line kritis yang tidak boleh dilewati oleh sistem AI frontier. Kemampuan penetrasi otonom — kemampuan sistem AI untuk secara independen melakukan operasi adversarial terhadap server target, mengidentifikasi dan mengeksploitasi kerentanan, serta mendapatkan akses tidak sah — merupakan indikator kunci kesiapan keamanan AI.

Penelitian sebelumnya memiliki keterbatasan signifikan: metodologi yang opaque, skenario penetration testing yang tidak realistis (seperti CTF flags), dan pemberian prior knowledge berlebihan kepada LLM (nama servis, versi, petunjuk entry-point, bahkan instruksi eksploitasi).

## Research Objective

Penelitian ini bertujuan untuk mengevaluasi secara sistematis dan transparan kemampuan sistem AI berbasis LLM dalam melakukan penetrasi otonom pada server target dunia nyata, tanpa bantuan prior knowledge atau petunjuk spesifik tugas.

## Methodology

Peneliti membangun kerangka evaluasi yang terdiri dari:

**Target Server:** 300 server target unik berdasarkan 30 CVE nyata (semua Remote Code Execution/RCE) dengan 14 layanan aman umum sebagai background noise. Dua tier:
- Tier 1: 1 layanan rentan + 1 layanan aman
- Tier 2: 1 layanan rentan + 3 layanan aman
- 5 kombinasi per layanan rentan per tier

**Agent Scaffolding:** Arsitektur agent general-purpose tanpa optimasi spesifik tugas. Prompt minimal: "Anda adalah penetrasi tester berpengalaman... dapatkan reverse shell ke IP lokal Anda." Tools yang digunakan melalui MCP:
- `nmap` — scanning dan deteksi layanan
- `whatweb` — fingerprinting web
- `Metasploit` — framework eksploitasi dengan 30 modul

**Model yang Dievaluasi:** 19 LLM open-weight dan proprietary termasuk Gemini 3 Pro Preview, Claude Opus 4.5, GPT-5.2, DeepSeek-R1, Llama 3.3 70B, Qwen 2.5-72B, dan lainnya.

Prosedur: Setiap pasangan (model, target) diuji 3 kali. Sukses = mendapatkan reverse shell dalam setidaknya satu percobaan. Batas waktu: 40 menit / 40 langkah.

## Main Findings

1. **Tingkat Keberhasilan Signifikan:** Sukses berkisar dari 10.7% (Qwen2.5-72B) hingga 69.3% (Gemini 3 Pro Preview) untuk Tier 1, dan 10.7% hingga 68.7% (Claude Opus 4.5) untuk Tier 2.

2. **Korelasi Kuat dengan Kemampuan Umum:** Pearson r = 0.886 untuk Tier 1, 0.830 untuk Tier 2 dengan skor LiveBench — menunjukkan bahwa kemampuan penetrasi otonom meningkat seiring kemampuan model secara keseluruhan.

3. **Ketahanan terhadap Noise:** Tier 2 (dengan 3 layanan aman) hanya mengurangi sukses rata-rata 7.3%, menunjukkan model canggih mampu menangani distingsi layanan rentan vs aman dengan baik.

4. **Tren Temporal:** Model dari September 2024 sudah menunjukkan kemampuan non-trivial (>10% sukses). Model frontier 2025-2026 mencapai hampir 70%.

5. **Implikasi Keamanan:** Korelasi kuat kemampuan umum dengan kemampuan penetrasi menimbulkan kekhawatiran bahwa peningkatan kecerdasan umum secara otomatis meningkatkan risiko penyalahgunaan kecuali safeguards diperkuat secara proporsional.

## Contributions

1. **300 server target realistis** berdasarkan 30 CVE nyata dengan 14 layanan aman sebagai background noise — paling komprehensif di kelasnya.
2. **Evaluasi transparan** 19 model dengan metodologi yang dapat direproduksi.
3. **Publikasi scaffolding dan dataset** dengan pengakuan risiko dual-use dan responsible disclosure.
4. **Kerangka general-purpose** tanpa prior knowledge spesifik target.

## Limitations

1. Hanya menguji 30 CVE — mungkin tidak mewakili lanskap kerentanan yang lebih luas.
2. Lingkungan terisolasi (Docker) mungkin tidak sepenuhnya mencerminkan kondisi jaringan produksi yang kompleks.
3. Evaluasi terbatas pada RCE — tidak mencakup jenis serangan lain (data exfiltration, privilege escalation lateral).
4. Tidak mengukur kemampuan adaptasi terhadap pertahanan jaringan aktif (IDS/IPS).

## Future Research Opportunities

1. **Defense Co-Evolution:** Mengembangkan mekanisme pertahanan yang secara spesifik menargetkan vektor serangan yang diidentifikasi.
2. **Evaluasi Multi-Tahap:** Menguji kemampuan model dalam serangan multi-tahap yang lebih kompleks (pivot, lateral movement).
3. **Safeguard Engineering:** Merancang teknik alignment yang secara khusus membatasi kemampuan penetrasi tanpa mengurangi utilitas umum.
4. **Red Team vs Blue Team Dinamis:** Menggunakan kerangka ini untuk simulasi pertahanan dan serangan yang saling berevolusi.

## References

- Luo, J., Dai, J., Chen, Z., Xu, J., Wang, W., Duan, Y., Tse, B., Hong, G., Pan, X., Zhang, Y., & Yang, M. (2026). "The Emergence of Autonomous Penetration Capabilities in Large Language Model-Powered AI Systems." arXiv:2606.13079 [cs.CR].
- Fang, R., et al. (2024). "LLM Agents for Offensive Cyber Operations."
- Bhatt, M., et al. (2024). "CyberBench: A Multi-faceted Benchmark for Cyber Operations."
