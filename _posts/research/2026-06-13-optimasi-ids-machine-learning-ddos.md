---
title: "Optimasi Intrusion Detection System dengan Machine Learning untuk Mendeteksi Distributed Attacks pada Server"
published: true
author: "Teddy Yuliswar, Ikhwana Elfitri, Onno W. Purbo"
category: "research"
description: "Paper ini mengembangkan IDS berbasis Decision Tree untuk deteksi DDoS menggunakan dataset CIC-DDoS2019, mencapai 100% akurasi dengan notifikasi real-time via Telegram."
date: "2026-06-13"
source: "INOVTEK Polbeng - Seri Informatika"
source_url: "https://doi.org/10.35314/vem9da98"
tags: [intrusion detection, machine learning, ddos, cybersecurity, decision tree]
importance_score: "8"
technical_level: "Advanced"
---

## Research Background

Serangan Distributed Denial-of-Service (DDoS) merupakan salah satu ancaman siber paling serius yang dihadapi oleh infrastruktur jaringan modern. Serangan ini membanjiri server target dengan lalu lintas data dalam jumlah besar sehingga layanan menjadi tidak responsif atau bahkan lumpuh total. Di Indonesia, Badan Siber dan Sandi Negara (BSSN) mencatat bahwa anomali lalu lintas internet mencapai ratusan juta serangan setiap tahunnya, dengan DDoS sebagai salah satu vektor serangan yang paling dominan.

Sistem Deteksi Intrusi (Intrusion Detection System/IDS) konvensional seringkali tidak mampu mendeteksi varian serangan DDoS yang terus berevolusi. Pendekatan berbasis *signature* memiliki keterbatasan dalam mengenali serangan baru yang belum memiliki pola yang dikenal. Oleh karena itu, diperlukan pendekatan yang lebih adaptif dan cerdas, yaitu dengan memanfaatkan teknik Machine Learning (ML) untuk mengoptimalkan kemampuan deteksi.

## Research Objective

Penelitian ini bertujuan untuk mengembangkan dan mengoptimalkan sistem deteksi intrusi dengan teknik machine learning menggunakan algoritma Decision Tree yang mampu mendeteksi serangan DDoS secara efisien dan akurat, serta memberikan notifikasi real-time kepada tim keamanan melalui Telegram Bot untuk mempercepat respons terhadap insiden.

## Methodology

Penelitian ini dilakukan melalui beberapa tahapan sistematis:

1. **Studi Literatur**: Kajian terhadap penelitian sebelumnya tentang IDS berbasis ML dan dataset serangan DDoS.
2. **Pemilihan Dataset**: Menggunakan **CIC-DDoS2019** dataset yang dikembangkan oleh Canadian Institute for Cybersecurity, yang mencakup berbagai skenario serangan DDoS yang komprehensif dan realistis.
3. **Preprocessing Data**: Meliputi pembersihan data, normalisasi, dan seleksi fitur untuk meningkatkan kualitas dataset.
4. **Implementasi Model**: Menerapkan algoritma **Decision Tree** untuk klasifikasi lalu lintas jaringan sebagai normal atau serangan.
5. **Pengujian dan Validasi**: Mengukur performa model menggunakan metrik akurasi, presisi, recall, dan F1-score.
6. **Integrasi Notifikasi**: Menghubungkan sistem dengan **Telegram Bot** untuk memberikan notifikasi real-time saat serangan terdeteksi, mencakup detail seperti sumber serangan, jenis serangan, waktu deteksi, dan protokol yang terlibat.

## Main Findings

Penelitian ini menghasilkan temuan yang signifikan:

1. **Deteksi 100%**: Sistem IDS yang dikembangkan berhasil mencapai **tingkat deteksi 100%** pada dataset CIC-DDoS2019, yang merupakan hasil luar biasa dalam lingkungan keamanan jaringan.
2. **Respons Real-time**: Setiap deteksi serangan langsung memicu notifikasi melalui Telegram Bot, memastikan tim keamanan dapat bereaksi dengan cepat untuk melakukan isolasi dan penanganan serangan.
3. **Informasi Detail**: Notifikasi mencakup informasi lengkap seperti sumber serangan, jenis serangan, waktu deteksi, dan informasi protokol yang terlibat, memungkinkan respons yang lebih terinformasi dan strategis.
4. **Kinerja Algoritma Decision Tree**: Algoritma Decision Tree terbukti sangat efektif untuk klasifikasi lalu lintas DDoS dengan kompleksitas komputasi yang rendah dan interpretasi model yang mudah.
5. **Skalabilitas**: Sistem dirancang untuk dapat diintegrasikan ke dalam infrastruktur jaringan yang sudah ada dan mendukung penyesuaian di berbagai skenario operasional.

## Contributions

Kontribusi utama dari penelitian ini adalah:

1. **IDS Optimal dengan Akurasi Sempurna**: Menunjukkan bahwa algoritma Decision Tree, meskipun sederhana, mampu mencapai akurasi deteksi DDoS 100% pada dataset standar.
2. **Integrasi Notifikasi Real-time**: Menggabungkan kemampuan deteksi ML dengan sistem notifikasi Telegram Bot untuk respons insiden yang lebih cepat.
3. **Validasi dengan Dataset Standar**: Menggunakan CIC-DDoS2019 sebagai tolok ukur yang diakui secara internasional, memungkinkan perbandingan yang adil dengan penelitian lain.
4. **Solusi Open Source**: Penelitian dipublikasikan secara terbuka dan dapat direproduksi, mendukung pengembangan keamanan siber di Indonesia.

## Limitations

1. **Pengujian Dataset Spesifik**: Akurasi 100% dicapai pada dataset CIC-DDoS2019 dan mungkin berbeda pada dataset lain atau lingkungan produksi nyata.
2. **Serangan Terbatas pada DDoS**: Sistem saat ini difokuskan pada deteksi serangan DDoS dan belum mencakup jenis serangan siber lainnya.
3. **Overfitting Potensial**: Meskipun akurasi tinggi, terdapat risiko overfitting pada dataset tertentu yang perlu divalidasi dengan data dunia nyata.
4. **Ketergantungan pada Dataset Historis**: Model ML sangat bergantung pada data pelatihan, sehingga serangan dengan pola yang benar-benar baru mungkin tidak terdeteksi (*zero-day attacks*).

## Future Research Opportunities

1. **Pengujian di Lingkungan Produksi**: Menerapkan dan menguji sistem pada infrastruktur jaringan nyata untuk memvalidasi efektivitas di dunia nyata.
2. **Eksplorasi Algoritma Lain**: Membandingkan kinerja Decision Tree dengan algoritma lain seperti Random Forest, XGBoost, atau Deep Learning untuk deteksi DDoS.
3. **Deteksi Multi-Vektor**: Memperluas cakupan deteksi untuk mencakup berbagai jenis serangan siber selain DDoS.
4. **Sistem Hibrid**: Menggabungkan pendekatan signature-based dan anomaly-based detection untuk meningkatkan ketahanan terhadap serangan baru.
5. **Deteksi Real-time Skala Besar**: Mengoptimalkan sistem untuk menangani lalu lintas jaringan berskala besar di lingkungan enterprise.

## References

1. Yuliswar, T., Elfitri, I., & Purbo, O. W. (2025). Optimization of Intrusion Detection System with Machine Learning for Detecting Distributed Attacks on Server. *INOVTEK Polbeng - Seri Informatika*, 10(1), 367-376. DOI: [10.35314/vem9da98](https://doi.org/10.35314/vem9da98)
2. Sharafaldin, I., Lashkari, A. H., Hakak, S., & Ghorbani, A. A. (2019). Developing Realistic Distributed Denial of Service (DDoS) Attack Dataset and Taxonomy. *2019 International Carnahan Conference on Security Technology (ICCST)*.
3. Canadian Institute for Cybersecurity. (2019). CIC-DDoS2019 Dataset. University of New Brunswick.
4. BSSN. (2024). Laporan Tahunan Monitoring Keamanan Siber. Badan Siber dan Sandi Negara Indonesia.
5. Sommer, R. & Paxson, V. (2010). Outside the Closed World: On Using Machine Learning for Network Intrusion Detection. *IEEE Symposium on Security and Privacy*.
