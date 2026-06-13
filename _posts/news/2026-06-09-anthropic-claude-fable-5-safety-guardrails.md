---
title: "Anthropic Sebut Topik Ini Terlalu Berbahaya untuk Dibahas oleh Model Fable 5"
published: true
author: "Kyle Orland"
category: "news"
description: "Anthropic merilis Claude Fable 5, model Mythos-class pertama, dengan pengaman yang memblokir pertanyaan seputar keamanan siber, biologi, dan kimia untuk mencegah penyalahgunaan AI."
date: "2026-06-09"
source: "Ars Technica"
source_url: "https://arstechnica.com/ai/2026/06/anthropic-says-these-topics-are-too-dangerous-to-let-its-fable-5-model-talk-about/"
tags:
  - AI
  - LLM
  - AI Safety
  - Anthropic
  - Claude
  - Cyber Security
  - Frontier Models
importance_score: "9"
technical_level: "Intermediate"

---

## Ringkasan

Anthropic secara resmi merilis Claude Fable 5, model "Mythos-class" pertama mereka, dengan pengaman berbasis topik yang belum pernah ada sebelumnya — model ini menolak menjawab pertanyaan seputar keamanan siber, biologi, dan kimia. Alih-alih memblokir pertanyaan sepenuhnya, model ini mengalihkan pertanyaan sensitif ke Claude Opus 4.8 yang lebih lama. Keputusan ini diambil karena Anthropic menilai model Mythos 5 yang mendasarinya terlalu berbahaya untuk akses publik tanpa batasan, karena khawatir dapat "mengangkat" kemampuan aktor jahat dalam riset senjata biologis dan peretasan agen. Rilis ini menandai pergeseran paradigma dalam deployment AI frontier — merilis model canggih sambil melapisinya dengan pagar pembatas ketat, bukan menahannya sepenuhnya.

## Poin-Poin Penting

* Fable 5 adalah versi publik dengan pembatasan dari Mythos 5 (model yang sama dengan classifier keamanan)
* Pengaman memblokir pertanyaan keamanan siber, biologi, dan kimia dengan fallback otomatis ke Opus 4.8
* Tingkat false positive kurang dari 5%; 95% sesi berjalan sepenuhnya di Fable tanpa fallback
* Tidak ada jailbreak universal yang ditemukan dalam 1.000+ jam red-teaming eksternal
* Mythos 5 mencetak 78% di ExploitBench (tolok ukur keamanan siber ofensif), naik dari 40% milik Opus 4.8
* Harga: $10/juta token input, $50/juta token output — 67-100% lebih tinggi dari GPT-5.5
* Project Glasswing memperluas akses tepercaya untuk profesional keamanan siber dan organisasi sains hayati

## Mengapa Ini Penting

Ini adalah momen penting dalam cara perusahaan AI frontier mengelola ketegangan antara rilis kemampuan dan keamanan. Alih-alih pilihan biner "rilis atau tahan," Anthropic memelopori model akses berjenjang: publik dengan pagar pembatas ketat, akses diperluas untuk profesional terverifikasi, dan akses penuh untuk organisasi tepercaya. Pendekatan "lebih ketat dari ideal" ini mengakui bahwa blokir positif palsu pada pertanyaan aman dapat diterima untuk mencegah penyalahgunaan bencana. Kolaborasi dengan pemerintah AS dalam keputusan akses menetapkan preseden untuk ko-regulasi pemerintah-industri atas kemampuan AI tingkat lanjut.

## Dampak di Masa Depan

Model akses berjenjang ini bisa menjadi standar industri untuk mengatur AI yang kuat. Yang bisa kita harapkan: (1) laboratorium frontier lain akan mengadopsi sistem keamanan berbasis classifier, (2) perluasan program akses tepercaya sebagai segmen pasar baru, (3) perdebatan yang semakin intens tentang siapa yang menentukan kriteria akses, dan (4) ekosistem AI dua tingkat di mana perusahaan membayar harga premium untuk model tanpa batasan.

## Referensi

- Ars Technica - <a href="https://arstechnica.com/ai/2026/06/anthropic-says-these-topics-are-too-dangerous-to-let-its-fable-5-model-talk-about/" target="_blank">https://arstechnica.com/ai/2026/06/anthropic-says-these-topics-are-too-dangerous-to-let-its-fable-5-model-talk-about/</a>
- The Verge - <a href="https://www.theverge.com/news/946725/anthropic-releases-claude-fable-5-mythos" target="_blank">https://www.theverge.com/news/946725/anthropic-releases-claude-fable-5-mythos</a>
