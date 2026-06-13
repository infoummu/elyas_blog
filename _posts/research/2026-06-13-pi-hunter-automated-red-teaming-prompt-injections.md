---
title: "PI-Hunter: Kerangka Audit Proaktif untuk Mengekspos dan Melokalisasi Prompt Injection pada Agen LLM"
published: true
author: "Tim Riset Hacker Blog"
category: "research"
description: "PI-Hunter adalah framework auditing agentic otomatis untuk mengekspos kerentanan prompt injection pada LLM agents dengan membangun test case realistis yang berevolusi secara iteratif."
date: "2026-06-13"
source: "arXiv"
source_url: "https://arxiv.org/abs/2606.12737"
tags: [prompt-injection, llm-security, red-teaming, agentic-ai, cs.CR]
importance_score: "9"
technical_level: "Intermediate"
---

## Research Background

Prompt injection telah muncul sebagai salah satu ancaman paling kritis terhadap aplikasi berbasis LLM, sebagaimana diakui oleh OWASP Foundation pada tahun 2025. Seiring berkembangnya LLM menjadi sistem agentic yang berinteraksi dengan alat dan lingkungan eksternal (email, halaman web, API, database), risiko baru muncul: indirect prompt injection attack melalui sumber eksternal yang tidak tepercaya.

Pendekatan pertahanan yang ada saat ini — seperti Spotlighting, MELON, dan PIGuard — hanya fokus pada pemblokiran konten berbahaya pada saat inferensi. Sementara itu, metode red-teaming yang ada hanya mengoptimalkan keberhasilan serangan tanpa memberikan visibilitas kepada pengembang tentang bagaimana injeksi laten muncul dan menyebar melalui agen.

## Research Objective

Penelitian ini bertujuan untuk mengembangkan PI-Hunter, sebuah kerangka auditing agentic otomatis untuk eksposur kerentanan proaktif pada agen LLM yang mampu:
1. Membangun test case realistis yang sadar-sumber (source-aware).
2. Mengevolusi test case secara iteratif melalui eksplorasi berbasis feedback.
3. Menginduksi agen untuk mengambil dan mengungkapkan instruksi jahat laten yang tertanam di lingkungan eksternal.

## Methodology

PI-Hunter menggabungkan tiga komponen utama:

**Analisis Statis:** Memetakan tools, antarmuka retrieval, skema API, dan tipe file yang digunakan agen. Mengidentifikasi saluran berisiko tinggi (email, web search, database).

**Meta-Seeding Sadar-Sumber:** Menginisialisasi query yang menargetkan sumber/antarmuka spesifik (misalnya get_unread_email, search_web) dengan menyeimbangkan realisme, aktivasi sumber, dan eksposur.

**Mutasi Berbasis Feedback:** Menggunakan operator mutasi umum (volume_expansion, implicit_assumption, parameter_fuzzing, instruction_hierarchy_override, role_inversion, delimiter_hijacking, encoding_obfuscation) dan operator domain-spesifik (executive_review, fraud_investigation, flight_cancellation_panic). Meta-mutasi memperhalus operator berdasarkan efektivitas historis.

**Patch & Co-Evolution:** Patcher menerapkan mitigasi sementara (blacklisting instruksi, membatasi antarmuka) untuk memaksa eksplorasi permukaan serangan baru.

Framework diuji pada benchmark AgentDojo (4 domain) dan AgentDyn (7 domain) dengan 5 tipe serangan, 4 mekanisme pertahanan, dan 4 backbone LLM.

## Main Findings

1. **Eksposur Kerentanan Unggul:** PI-Hunter secara substansial meningkatkan eksposur kerentanan dan cakupan permukaan serangan dibandingkan baseline red-teaming otomatis yang kuat.

2. **Efektif Melawan Pertahanan:** PI-Hunter tetap efektif bahkan di bawah mekanisme pertahanan prompt injection yang ada (Spotlighting, MELON, PIGuard).

3. **Cakupan Multi-Skenario:** Berhasil mengekspos kerentanan dalam berbagai skenario injeksi: single_single, single_multi, multi_single, dan multi_multi.

4. **Diversitas Eksposur Tinggi:** Menghasilkan beragam vektor serangan dengan skor diversitas tinggi (berbasis entropi), mengungkap lebih banyak jalur eksploitasi potensial.

## Contributions

1. **Pergeseran paradigma** dari optimasi serangan ke eksposur injeksi — fokus pada menemukan jalur ingest tersembunyi, bukan sekadar mencapai attack success.
2. **Framework auditing agentik otomatis** yang menggabungkan analisis statis, generasi test case, dan mutasi berbasis feedback.
3. **Operator mutasi komprehensif** — 7 operator umum dan puluhan operator domain-spesifik.
4. **Mekanisme co-evolution** dengan patcher untuk memaksa eksplorasi permukaan serangan baru.

## Limitations

1. Bergantung pada kualitas analisis statis awal — jika antarmuka atau sumber tidak terdeteksi, kerentanan terkait mungkin terlewatkan.
2. Iterasi evolusioner membutuhkan biaya komputasi yang signifikan untuk agen dengan jumlah tools yang sangat besar.
3. Belum diuji pada arsitektur non-ReAct atau Planner-Executor yang lebih eksotis.

## Future Research Opportunities

1. **Integrasi dengan Defenses Adaptif:** Menggabungkan PI-Hunter dengan mekanisme pertahanan adaptif yang belajar dari pola serangan yang terdeteksi.
2. **Ekspansi ke Modalitas Lain:** Memperluas framework untuk mencakup multimodal agents (gambar, audio, video).
3. **Benchmark Standar:** Mendorong adopsi PI-Hunter sebagai benchmark industri untuk keamanan agen LLM.
4. **Runtime Monitoring:** Mengadaptasi teknik eksposur untuk monitoring runtime berkelanjutan pada agen yang sudah di-deploy.

## References

- He, P., Miculicich, L., Sharma, V., Fox, A., Lee, G., Tang, J., Pfister, T., & Le, L.T. (2026). "PI-Hunter: Automated Red-Teaming for Exposing and Localizing Prompt Injections." arXiv:2606.12737 [cs.CR].
- OWASP Foundation. (2025). "OWASP Top 10 for LLM & Generative AI Applications."
- Greshake, K., et al. (2023). "What's in a Prompt? Analyzing Indirect Prompt Injection Attacks."
