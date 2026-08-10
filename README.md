# 🚀 Perancangan Sistem Information Retrieval pada Dokumen Berita Menggunakan Metode TF-IDF dan Okapi BM25

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![License](https://img.shields.io/badge/License-MIT-green)

Repositori ini berisi kode sumber dan dokumentasi untuk **Tugas Akhir Mata Kuliah Temu Kembali Informasi (Information Retrieval)**. Proyek ini bertujuan untuk membangun sistem pencarian berita Bahasa Indonesia dan membandingkan kinerja antara metode klasik (*Vector Space Model*) dan metode probabilistik modern (*Okapi BM25*).

---

## 📖 Tentang Proyek

Sistem ini dirancang untuk mengatasi masalah *information overload* pada artikel berita daring. Kami menggunakan dataset berisi **1.000 dokumen berita Indonesia** dan melakukan serangkaian proses mulai dari *text preprocessing* hingga evaluasi sistem.

### Fitur Utama:
* **Text Preprocessing Bahasa Indonesia:** Menggunakan library `Sastrawi` (Case folding, cleaning, tokenization, stopword removal, stemming).
* **Dual Model:** Implementasi dua algoritma sekaligus untuk perbandingan:
    1.  **TF-IDF (Term Frequency - Inverse Document Frequency)**
    2.  **Okapi BM25 (Best Matching 25)**
* **Search Engine:** Input query dan output berupa daftar dokumen relevan beserta skor kemiripan.
* **Evaluasi Otomatis:** Menghitung Precision, Recall, F-Measure, dan Mean Average Precision (MAP).

---

## 🛠️ Teknologi yang Digunakan

Proyek ini dibangun menggunakan bahasa pemrograman **Python** dengan pustaka-pustaka berikut:

* `pandas` & `numpy`: Manipulasi data.
* `Sastrawi`: Stemming & Stopword removal Bahasa Indonesia.
* `scikit-learn`: Implementasi TF-IDF & Cosine Similarity.
* `rank_bm25`: Implementasi algoritma Okapi BM25.
* `Google Colab`: Lingkungan pengembangan.

---

## 📊 Hasil Evaluasi

Berdasarkan pengujian terhadap 10 query uji dan *Ground Truth* manual, berikut adalah perbandingan kinerja kedua model:

| Metrik Evaluasi | Vector Space Model (TF-IDF) | Probabilistic Model (BM25) |
| :--- | :---: | :---: |
| **MAP (Mean Average Precision)** | 0.6976 | **0.7559** 🏆 |
| **Recall @ 10** | 83.33% | **100.00%** 🏆 |
| **Precision @ 10** | 48.00% | **57.00%** 🏆 |

**Kesimpulan:**
Model **Okapi BM25** terbukti lebih unggul dibandingkan TF-IDF, terutama dalam hal *Recall* (kelengkapan informasi) dan *Mean Average Precision*. Hal ini disebabkan oleh fitur *Length Normalization* pada BM25 yang mampu menangani variasi panjang dokumen berita dengan lebih baik.

---

## 🚀 Cara Menjalankan (Installation)

1.  **Clone repositori ini:**
    ```bash
    git clone [https://github.com/username-anda/nama-repo.git](https://github.com/username-anda/nama-repo.git)
    ```

2.  **Install library yang dibutuhkan:**
    ```bash
    pip install pandas numpy scikit-learn Sastrawi rank_bm25
    ```

3.  **Jalankan Notebook:**
    Buka file `modelling_news.ipynb` atau `Evaluasi_Kinerja.ipynb` menggunakan Jupyter Notebook atau Google Colab.

4.  **Siapkan Dataset:**
    Pastikan file dataset (`indonesia_news_1000.csv`) berada di direktori yang sesuai dengan path di dalam kode.
