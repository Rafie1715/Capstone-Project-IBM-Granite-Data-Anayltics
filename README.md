# Analisis Sentimen & Topik Ulasan Produk E-commerce Indonesia

**Capstone Project untuk menganalisis ulasan pelanggan Tokopedia menggunakan AI (IBM Granite) untuk mendapatkan wawasan bisnis yang dapat ditindaklanjuti.**

---

## 📂 Project Overview

Proyek ini bertujuan untuk menganalisis data ulasan produk dari platform e-commerce terkemuka di Indonesia, Tokopedia. Di tengah persaingan e-commerce yang ketat, memahami suara pelanggan adalah kunci untuk meningkatkan kualitas layanan dan memenangkan loyalitas.

Dengan memanfaatkan ribuan ulasan pelanggan, proyek ini melakukan beberapa hal:
1.  **Mengklasifikasikan Sentimen:** Mengubah rating bintang (1-5) menjadi label sentimen yang jelas (positif, netral, negatif) untuk mengukur tingkat kepuasan pelanggan secara kuantitatif.
2.  **Mengidentifikasi Akar Masalah:** Menggunakan model AI _Large Language Model_ (IBM Granite) untuk menganalisis dan merangkum keluhan-keluhan utama dari pelanggan yang memberikan ulasan negatif.
3.  **Menghasilkan Rekomendasi Bisnis:** Mengubah wawasan dari keluhan pelanggan menjadi rekomendasi yang konkret dan dapat ditindaklanjuti (_actionable_) bagi para penjual untuk meningkatkan layanan mereka.

## 📊 Dataset

Dataset yang digunakan dalam proyek ini adalah **"Tokopedia Product Reviews"** yang tersedia secara publik di Kaggle.

- **Sumber:** [Tokopedia Product Reviews on Kaggle](https://www.kaggle.com/datasets/farhan999/tokopedia-product-reviews/data)
- **Deskripsi:** Dataset ini berisi ribuan ulasan produk yang mencakup kolom-kolom seperti `rating` (peringkat bintang 1-5) dan `review_text` (teks ulasan), yang menjadi dasar utama analisis ini.

## ⚙️ Alur Kerja Proyek (Analysis Process)

Proyek ini dieksekusi dengan alur kerja yang sistematis sebagai berikut:

1.  **Pengambilan Data:** Dataset diunduh secara otomatis dari Kaggle menggunakan Kaggle API langsung di lingkungan Google Colab.
2.  **Persiapan & Pembersihan Data:** Data dibersihkan dari nilai yang kosong. Sebuah kolom baru `sentimen` dibuat berdasarkan kolom `rating` dengan aturan:
    - ⭐⭐⭐⭐ / ⭐⭐⭐⭐⭐ ➔ **Positif**
    - ⭐⭐⭐ ➔ **Netral**
    - ⭐ / ⭐⭐ ➔ **Negatif**
3.  **Analisis & Visualisasi:** Distribusi sentimen pelanggan divisualisasikan untuk mendapatkan gambaran umum tingkat kepuasan.
4.  **Analisis Mendalam dengan AI:** Kumpulan ulasan dengan sentimen `negatif` dianalisis oleh model IBM Granite untuk merangkum topik-topik keluhan utama.
5.  **Generasi Rekomendasi oleh AI:** Berdasarkan topik keluhan yang ditemukan, model AI yang sama diminta untuk menghasilkan rekomendasi bisnis yang praktis bagi penjual.

## 💡 Insight & Findings

Dari analisis yang dilakukan, ditemukan beberapa wawasan kunci:

- **Wawasan Kuantitatif:** Mayoritas ulasan pelanggan bersifat **positif**, yang mengindikasikan tingkat kepuasan dasar yang baik. Namun, terdapat segmen ulasan **negatif** yang signifikan dan vokal, yang jika tidak ditangani dapat merusak reputasi toko.

- **Wawasan Kualitatif (Hasil Analisis AI):** Analisis mendalam oleh AI pada ulasan-ulasan negatif menemukan tiga tema keluhan utama yang sering berulang:
    1.  **Kualitas Produk Tidak Sesuai:** Keluhan terkait produk yang diterima berbeda dari deskripsi atau foto, memiliki cacat, atau kualitas bahan yang buruk.
    2.  **Pengemasan (Packaging) Kurang Aman:** Banyak pelanggan mengeluh barang rusak atau pecah saat diterima karena pengemasan yang tipis atau tanpa pelindung yang memadai (seperti _bubble wrap_).
    3.  **Keterlambatan Pengiriman:** Keluhan mengenai proses pengemasan oleh penjual yang memakan waktu lama sebelum diserahkan ke pihak kurir.

## 🚀 Rekomendasi Bisnis (Conclusion & Recommendation)

Berdasarkan wawasan yang ditemukan, AI menghasilkan tiga rekomendasi utama yang dapat ditindaklanjuti oleh penjual untuk meningkatkan rating dan kepuasan pelanggan:

1.  **Tingkatkan Akurasi Deskripsi & Quality Control (QC):** Penjual disarankan untuk menggunakan foto produk asli (_real picture_) dan mendeskripsikan bahan serta potensi kekurangan secara transparan. Melakukan pemeriksaan kualitas terakhir sebelum pengiriman juga krusial.
2.  **Buat Standar Pengemasan Berlapis:** Terapkan standar pengemasan minimum, terutama untuk barang pecah belah. Gunakan pelindung seperti _bubble wrap_ dan kardus yang lebih tebal, serta pertimbangkan untuk menawarkan opsi asuransi atau packing kayu.
3.  **Optimalkan Proses Pemenuhan Pesanan:** Tetapkan batas waktu internal (misalnya, maksimal 1x24 jam) dari pesanan masuk hingga barang diserahkan ke kurir untuk meningkatkan kecepatan pengiriman dan mengelola ekspektasi pelanggan dengan lebih baik.

## 🤖 Penjelasan Dukungan AI (AI Support Explanation)

Pada proyek ini, model AI **IBM Granite (granite-3.3-8b-instruct)** digunakan sebagai alat bantu analisis kualitatif melalui API dari platform **Replicate**. Peran AI difokuskan pada dua tugas utama yang sulit dilakukan secara manual dalam skala besar:

1.  **Summarization:** AI menganalisis ratusan ulasan negatif dalam Bahasa Indonesia untuk mengekstrak dan merangkum tema-tema keluhan yang paling fundamental. Ini mengubah data teks tidak terstruktur menjadi wawasan yang terstruktur.
2.  **Recommendation Generation:** AI bertindak sebagai konsultan virtual dengan mengubah daftar masalah yang teridentifikasi menjadi serangkaian solusi bisnis yang logis, relevan, dan praktis untuk diimplementasikan oleh penjual.

## 🛠️ Teknologi yang Digunakan

- **Bahasa:** Python
- **Lingkungan:** Google Colab
- **Library Utama:** Pandas, Matplotlib, Seaborn, Kaggle API
- **Model AI:** IBM Granite (via Replicate API)
