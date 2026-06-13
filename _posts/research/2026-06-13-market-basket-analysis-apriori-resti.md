---
title: "Market Basket Analysis pada Mini Market dengan Algoritma Apriori — Studi Kasus Data Mining Ritel"
published: true
author: "Erlin Elisa (Jurnal RESTI)"
category: "research"
description: "Paper ini membahas penerapan algoritma Apriori untuk Market Basket Analysis guna menemukan pola asosiasi pembelian konsumen di ritel mini market."
date: "2026-06-13"
source: "Jurnal Rekayasa Sistem dan Teknologi Informasi (RESTI)"
source_url: "https://www.neliti.com/publications/240153/market-basket-analysis-pada-mini-market-ayu-dengan-algoritma-apriori"
tags:
  - data-mining
  - apriori-algorithm
  - market-basket-analysis
  - sistem-informasi
  - artificial-intelligence
  - association-rules
importance_score: "8"
technical_level: "Intermediate"
---

## Research Background

Data mining telah menjadi teknik penting untuk menggali informasi berharga dari data warehouse. Dalam bisnis ritel seperti mini market, data transaksi harian terus bertambah namun seringkali hanya disimpan sebagai arsip tanpa dianalisis lebih lanjut. Mini Market Ayu yang berlokasi di Kota Batam — dekat dengan kawasan pemukiman penduduk — memiliki volume penjualan yang signifikan namun belum memanfaatkan data transaksinya untuk pengambilan keputusan strategis. Padahal, data transaksi tersebut menyimpan pola tersembunyi tentang kebiasaan belanja konsumen yang dapat digunakan untuk optimalisasi tata letak produk, promosi silang, dan manajemen inventaris.

## Research Objective

Penelitian ini bertujuan untuk menerapkan algoritma Apriori dalam menganalisis keranjang belanja (Market Basket Analysis) pada Mini Market Ayu di Kota Batam. Tujuan spesifiknya adalah mengidentifikasi pola asosiasi antar produk yang sering dibeli secara bersamaan oleh konsumen, serta menghitung nilai support dan confidence dari setiap aturan asosiasi yang terbentuk.

## Methodology

Penelitian menggunakan pendekatan kuantitatif dengan metode Market Basket Analysis yang diimplementasikan melalui algoritma Apriori. Algoritma Apriori bekerja dengan mencari frequent itemset — kumpulan item yang sering muncul bersama dalam transaksi — kemudian menghasilkan aturan asosiasi yang memenuhi ambang batas minimum support dan confidence. Proses analisis meliputi:
- Pengumpulan data transaksi penjualan
- Transformasi data ke format transaksional
- Penentuan nilai minimum support dan confidence
- Eksekusi algoritma Apriori untuk menemukan frequent itemset
- Pembentukan aturan asosiasi dari itemset yang memenuhi syarat

## Main Findings

Hasil penelitian menunjukkan bahwa aturan asosiasi dengan nilai tertinggi adalah hubungan antara pembelian **Minyak dan Susu**, dengan nilai *support* sebesar **42.85%** dan *confidence* sebesar **85.71%**. Nilai support 42.85% mengindikasikan bahwa kombinasi Minyak dan Susu muncul bersama dalam 42.85% dari seluruh transaksi. Sementara itu, nilai confidence 85.71% menunjukkan bahwa probabilitas konsumen yang membeli Minyak juga membeli Susu sangat tinggi — mencapai 85.71%. Temuan ini memberikan bukti kuat adanya pola pembelian simultan antara kedua produk tersebut.

## Contributions

Penelitian ini memberikan kontribusi praktis bagi pengelola Mini Market Ayu berupa rekomendasi berbasis data untuk:
- Optimalisasi penempatan produk secara berdampingan (Minyak dan Susu diletakkan berdekatan)
- Strategi promosi silang dan bundling produk
- Manajemen stok yang lebih efisien berdasarkan pola pembelian
- Peningkatan penjualan melalui cross-selling yang terarah
Di samping itu, penelitian ini turut memperkaya literatur penerapan data mining pada sektor ritel skala kecil-menengah di Indonesia.

## Limitations

Penelitian memiliki beberapa keterbatasan. Pertama, hanya menggunakan satu dataset dari satu mini market sehingga generalisasi temuan terbatas. Kedua, analisis hanya fokus pada dua item (Minyak dan Susu) tanpa mengeksplorasi kombinasi itemset yang lebih luas. Ketiga, belum mempertimbangkan faktor temporal seperti musim, hari libur, atau tren musiman yang dapat memengaruhi pola pembelian.

## Future Research Opportunities

Penelitian selanjutnya dapat memperluas cakupan dengan:
- Menggunakan dataset dari multiple store atau periode waktu yang lebih panjang
- Menerapkan algoritma data mining lain seperti FP-Growth untuk perbandingan performa
- Mengintegrasikan analisis sentimen atau data demografis konsumen
- Mengembangkan sistem rekomendasi real-time berbasis pola asosiasi untuk e-commerce

## References

- Elisa, E. (2018). Market Basket Analysis pada Mini Market Ayu dengan Algoritma Apriori. *Jurnal Rekayasa Sistem dan Teknologi Informasi (RESTI)*, 2(2). DOI: 10.29207/resti.v2i2.280
- https://www.neliti.com/publications/240153/market-basket-analysis-pada-mini-market-ayu-dengan-algoritma-apriori
