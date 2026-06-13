---
title: "Anka — Domain-Specific Language untuk Generasi Kode LLM yang Andal dengan Akurasi 95,8%"
published: true
author: "Saif Khalfan Saif Al Mazrouei"
category: "research"
description: "Anka adalah domain-specific language (DSL) untuk pipeline transformasi data yang dirancang khusus agar LLM dapat menghasilkan kode andal dengan akurasi 95,8% dan keunggulan 40 poin persen atas Python."
date: "2026-06-13"
source: "arXiv"
source_url: "https://arxiv.org/abs/2512.23214"
tags:
  - llm-code-generation
  - domain-specific-language
  - programming
  - ai-coding
  - software-engineering
importance_score: "8"
technical_level: "Intermediate"
---

## Research Background

Large Language Models (LLM) telah menunjukkan kemampuan luar biasa dalam generasi kode, namun mereka masih menunjukkan kesalahan sistematis pada tugas pemrograman kompleks yang memerlukan banyak langkah (multi-step). Kesalahan ini sering terjadi karena fleksibilitas bahasa pemrograman tujuan umum (seperti Python) yang memungkinkan banyak pendekatan valid dan memerlukan manajemen state implisit. Hipotesis penelitian ini adalah bahwa error tersebut berasal dari fleksibilitas bahasa general-purpose yang memberikan terlalu banyak kebebasan kepada LLM dalam memilih pendekatan.

## Research Objective

Penelitian ini bertujuan untuk menguji hipotesis bahwa **constrained syntax** dalam bentuk Domain-Specific Language (DSL) dapat secara signifikan mengurangi error generasi kode LLM pada tugas multi-step yang kompleks. Peneliti memperkenalkan **Anka**, sebuah DSL untuk pipeline transformasi data yang dirancang dengan sintaks eksplisit dan terbatas untuk mengurangi ambiguitas dalam generasi kode oleh LLM.

## Methodology

Peneliti merancang Anka sebagai DSL dengan karakteristik berikut:

1. **Sintaks eksplisit dan terbatas** yang hanya menyediakan konstruksi yang diperlukan untuk transformasi data pipeline.
2. **Manajemen state implisit dihilangkan** — setiap operasi dalam pipeline bersifat eksplisit dan berurutan.
3. **Validasi sintaks ketat** yang memastikan hanya kode yang valid secara grammar yang dapat dihasilkan.

Evaluasi dilakukan dengan:
- **Model LLM**: Claude 3.5 Haiku (utama) dan GPT-4o-mini (cross-validation)
- **Benchmark**: 100 masalah pipeline transformasi data
- **Metrik**: Parse success rate, overall task accuracy, dan perbandingan dengan Python
- **Kondisi**: LLM tidak memiliki pelatihan atau paparan sebelumnya terhadap Anka — hanya diberikan prompt in-context

## Main Findings

Hasil eksperimen menunjukkan temuan yang signifikan:

| Metrik | Anka | Python |
|--------|------|--------|
| Parse Success Rate | **99.9%** | — |
| Overall Task Accuracy | **95.8%** | — |
| Multi-step Task Accuracy | **100%** | **60%** |
| Keunggulan pada Multi-step | +40 poin persen | baseline |

Cross-model validation dengan GPT-4o-mini mengkonfirmasi keunggulan ini dengan **+26.7 poin persen** pada tugas multi-step.

**Temuan kunci:**
1. LLM dapat mempelajari DSL baru sepenuhnya dari prompt in-context, mencapai akurasi mendekati native.
2. Constrained syntax secara signifikan mengurangi error pada tugas kompleks.
3. DSL yang dirancang khusus untuk generasi LLM dapat mengungguli bahasa general-purpose di mana LLM memiliki pelatihan ekstensif.

## Contributions

1. **Anka DSL**: Bahasa domain-spesifik pertama yang dirancang khusus untuk generasi kode LLM yang andal pada pipeline transformasi data.
2. **Validasi empiris**: Bukti bahwa LLM dapat mengadopsi DSL baru dari in-context prompts dengan akurasi tinggi (95.8%).
3. **Benchmark suite**: 100 masalah pipeline transformasi data yang dirilis untuk komunitas riset.
4. **Prinsip desain bahasa**: Wawasan bahwa constrained syntax lebih efektif untuk generasi kode LLM daripada bahasa general-purpose yang fleksibel.
5. **Kode dan implementasi**: Seluruh bahasa, benchmark, dan framework evaluasi dirilis di GitHub.

## Limitations

1. Studi ini terbatas pada domain transformasi data pipeline; DSL untuk domain lain belum dieksplorasi.
2. Hanya dua model LLM (Claude 3.5 Haiku dan GPT-4o-mini) yang digunakan untuk validasi.
3. Skala masalah terbatas pada 100 benchmark; validasi pada skala yang lebih besar diperlukan.
4. Belum ada studi tentang bagaimana performa Anka pada LLM yang lebih baru atau lebih besar.
5. Tidak ada analisis tentang kemudahan pemeliharaan kode Anka oleh manusia dibandingkan Python.

## Future Research Opportunities

1. **DSL untuk domain lain**: Mengembangkan DSL serupa untuk domain seperti konfigurasi infrastruktur, pipeline CI/CD, atau query database.
2. **Multi-model validation**: Menguji Anka pada spektrum LLM yang lebih luas termasuk model open-source seperti Llama dan DeepSeek.
3. **Hybrid approach**: Menggabungkan DSL untuk bagian kritis dengan kode general-purpose untuk fleksibilitas.
4. **LLM-native language design**: Mengembangkan prinsip-prinsip desain bahasa pemrograman yang dioptimalkan untuk generasi oleh LLM.
5. **Integration with agentic coding**: Menggabungkan DSL seperti Anka ke dalam workflow AI coding agent untuk meningkatkan keandalan.

## References

- **arXiv** - <a href="https://arxiv.org/abs/2512.23214" target="_blank">https://arxiv.org/abs/2512.23214</a>
- **GitHub (Code & Benchmark)** - <a href="https://github.com/BleBlo/Anka" target="_blank">https://github.com/BleBlo/Anka</a>
