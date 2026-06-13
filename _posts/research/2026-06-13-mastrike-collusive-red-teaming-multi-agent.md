---
title: "MAStrike: Red-Teaming Kolusif pada Sistem Multi-Agent Berbasis Shapley"
published: true
author: "Tim Riset Hacker Blog"
category: "research"
description: "MAStrike adalah framework closed-loop untuk red-teaming kolusif pada hierarchical multi-agent systems, menggunakan analisis Shapley value untuk mengidentifikasi koalisi agen rentan dan menghasilkan serangan terkoordinasi."
date: "2026-06-13"
source: "arXiv"
source_url: "https://arxiv.org/abs/2606.12918"
tags: [multi-agent, red-teaming, shapley, keamanan-ai, cs.CR]
importance_score: "8"
technical_level: "Advanced"
---

## Research Background

Sistem multi-agent hierarkis (MAS) semakin banyak diadopsi dalam workflow berisiko tinggi di bidang keuangan, rekayasa perangkat lunak, dan CRM. Dalam sistem ini, keamanan dan keselamatan terdistribusi di seluruh agen yang memiliki peran khusus, yang secara signifikan memperluas permukaan serangan — khususnya terhadap perilaku adversarial terkoordinasi seperti privilege escalation dan collusion antar agen.

Pendekatan red-teaming yang ada masih sangat terbatas: metode sebelumnya hanya mengandalkan pemilihan agen target secara heuristik dan mengganggu alur pesan secara terisolasi. Pertanyaan kritis seperti agen mana yang paling bertanggung jawab terhadap keamanan sistem, dan bagaimana agen yang dikompromikan dapat berkoordinasi untuk melewati pertahanan, masih belum terjawab.

## Research Objective

Penelitian ini bertujuan untuk mengembangkan MAStrike, sebuah framework closed-loop untuk red-teaming kolusif pada MAS hierarkis yang mampu:
1. Mengukur kontribusi marjinal setiap agen terhadap ketahanan sistem menggunakan analisis Shapley value tingkat agen pertama di MAS.
2. Mengidentifikasi koalisi agen yang rentan dan menghasilkan manipulasi adversarial terkoordinasi yang sadar-peran.
3. Menyempurnakan serangan secara iteratif melalui diagnosis kausal terstruktur.

## Methodology

Peneliti memperkenalkan beberapa kontribusi metodologis utama:

**Analisis Shapley Value Tingkat Agen:** Untuk setiap tugas q, nilai koalisi didefinisikan sebagai v_q(C) = ASR_q(C) (Attack Success Rate). Shapley value individu dihitung sebagai:

φ_i(q) = Σ_{C ⊆ A \ {a_i}} (|C|!(|A|-|C|-1)!/|A|!) × [v_q(C ∪ {a_i}) - v_q(C)]

Interaksi Shapley berpasangan mengukur sinergi antara dua agen. Estimasi efisien dilakukan melalui stratified coalition sampling.

**Optimasi Red-Teaming Berbasis Shapley:** Koalisi optimal dipilih dengan objective fungsi yang mempertimbangkan Shapley value individu dan interaksi berpasangan. Similarity-weighted aggregation mentransfer pengetahuan dari tugas sampel ke tugas target.

**Closed-Loop Iterative Optimization:** Red-teaming agent menghasilkan injeksi terkoordinasi untuk koalisi terpilih, menjalankannya pada MAS, mengevaluasi dengan judge, dan jika gagal, mendiagnosis kondisi blocking untuk menyempurnakan injeksi.

**MABENCH Benchmark:** Dibangun lingkungan MAS yang dapat dikontrol di tiga domain (finansial, rekayasa perangkat lunak, CRM) dengan topologi hierarkis yang beragam.

## Main Findings

1. **Kinerja Unggul:** MAStrike mencapai 61.8% Attack Success Rate (ASR) terhadap Claude Opus 4.7 dan 55.6% terhadap GPT-5.5, secara signifikan mengungguli baseline heuristik.

2. **Distribusi Shapley Non-Trivial:** Analisis mengungkapkan bahwa kontribusi agen terhadap keamanan sistem tidak merata — beberapa agen memiliki pengaruh yang jauh lebih besar terhadap ketahanan sistem secara keseluruhan.

3. **Pola Interaksi Tingkat Tinggi:** Ditemukan struktur interaksi orde-tinggi antar agen yang tidak terdeteksi oleh metode single-agent atau template-based sebelumnya.

4. **Kerentanan Koordinasi:** MAStrike berhasil mengeksploitasi celah keamanan yang muncul dari koordinasi antar agen, menunjukkan bagaimana agen yang dikompromikan dapat bekerja sama untuk melewati pertahanan.

## Contributions

1. **Analisis Shapley value tingkat agen pertama di MAS** — mengukur kepentingan individu dan efek interaksi dengan estimasi efisien.
2. **Framework red-teaming closed-loop berbasis Shapley** — integrasi pemilihan berbasis Shapley, pembangkitan injeksi terkoordinasi, dan diagnosis kegagalan terstruktur.
3. **MABENCH** — lingkungan MAS yang dapat dikontrol dan benchmark red-teaming komprehensif di tiga domain.
4. **Validasi ekstensif** di berbagai model frontier (Claude Opus 4.7, GPT-5.5, dll.) yang mengungkap pola kerentanan baru.

## Limitations

1. Framework saat ini berfokus pada arsitektur MAS hierarkis — belum diuji pada topologi non-hierarkis seperti MAS yang terdesentralisasi sepenuhnya atau berbasis graph.
2. Asumsi bahwa penyerang memiliki pengetahuan tentang struktur MAS (peran agen, topologi komunikasi) mungkin tidak selalu realistis dalam semua skenario.
3. Komputasi Shapley value membutuhkan sumber daya yang signifikan untuk sistem dengan jumlah agen yang sangat besar.

## Future Research Opportunities

1. **Ekstensi ke Arsitektur Non-Hierarkis:** Mengadaptasi MAStrike untuk topologi MAS yang lebih kompleks seperti graph-based atau fully decentralized.
2. **Partial-Knowledge Attacks:** Mengembangkan varian yang bekerja dengan pengetahuan terbatas tentang struktur MAS.
3. **Defense Mechanisms:** Merancang mekanisme pertahanan berdasarkan wawasan Shapley value untuk melindungi agen-agen kritis.
4. **Real-time Shapley Estimation:** Mengoptimalkan estimasi Shapley value untuk penggunaan real-time dalam sistem produksi.

## References

- Xu, C., Chen, Z., Zhang, J., Lecue, F., Kothari, A., Tan, S., Guo, W., & Li, B. (2026). "MAStrike: Shapley-Guided Collusive Red-Teaming on Multi-Agent Systems." arXiv:2606.12918 [cs.CR].
- OWASP Foundation. (2025). "OWASP Top 10 for LLM Applications."
- Shapley, L.S. (1953). "A Value for n-Person Games." Contributions to the Theory of Games.
