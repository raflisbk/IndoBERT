# Analisis Sentimen Review Aplikasi Korlantas POLRI dengan IndoBERT

## Deskripsi Proyek

Proyek ini bertujuan untuk melakukan analisis sentimen terhadap review aplikasi **Korlantas POLRI** yang diambil dari ulasan pengguna di Google Play Store. Model yang digunakan untuk analisis ini adalah model berbasis **IndoBERT** yang telah dilatih ulang (fine-tuned) menggunakan dataset yang dikumpulkan. Sentimen yang dianalisis terbagi menjadi dua kategori utama:

- **Positif**: Ulasan dengan rating di atas 3 bintang, mengindikasikan pengalaman baik atau kepuasan pengguna.
- **Negatif**: Ulasan dengan rating di bawah 3 bintang, mengindikasikan pengalaman buruk atau ketidakpuasan pengguna.

## Fitur Proyek

1. **Preprocessing Data**:
   - Membersihkan data dari entitas atau simbol yang tidak relevan.
   - Mapping sentimen berdasarkan label "positif" dan "negatif".
2. **Fine-tuning Model**:
   - Model **IndoBERT** digunakan sebagai model dasar dan dilatih ulang menggunakan dataset yang sudah diproses.
   - Optimasi hyperparameter dilakukan untuk meningkatkan akurasi model.
3. **Prediksi Sentimen**:
   - Input berupa teks ulasan aplikasi.
   - Prediksi dilakukan menggunakan model yang telah dilatih.

## Dataset

Dataset yang digunakan untuk melatih model diambil dari ulasan pengguna aplikasi Korlantas POLRI di Google Play Store. Dataset ini terdiri dari:

- **Total Ulasan**: 10,000 ulasan.
- **Kategori Sentimen**:
  - 4,500 ulasan positif
  - 5,500 ulasan negatif

Data telah dibersihkan dan dilabeli secara manual sebelum digunakan untuk pelatihan model.

## Model

Model yang digunakan dalam proyek ini adalah **IndoBERT-base**, sebuah model berbasis **Transformer** yang dirancang untuk pemrosesan bahasa alami (NLP) dalam Bahasa Indonesia. Model ini diambil dari **HuggingFace Transformers Library** dan telah dioptimasi untuk tugas klasifikasi teks (analisis sentimen).

### Fitur Model IndoBERT

1. **Pretrained Language Understanding**:
   - IndoBERT telah dilatih pada korpus besar dalam Bahasa Indonesia, sehingga memiliki pemahaman konteks yang baik.
2. **Fine-tuning untuk Tugas Spesifik**:
   - Model ini telah diadaptasi untuk tugas klasifikasi sentimen menggunakan dataset yang relevan.
3. **Efisiensi pada Input Beragam**:
   - Model mampu menangani teks dengan berbagai panjang dan kompleksitas dengan baik melalui teknik tokenisasi dan padding.

## Implementasi

### Langkah-langkah Utama:

1. **Persiapan Data**:
   - Unduh ulasan dari Google Play Store.
   - Lakukan pembersihan data menggunakan Python (pandas, regex).
2. **Fine-tuning Model**:
   - Gunakan dataset yang telah disiapkan untuk melatih model menggunakan library **Transformers**.
   - Hyperparameter seperti learning rate, batch size, dan jumlah epoch disesuaikan untuk mencapai hasil terbaik.
3. **Prediksi Sentimen**:
   - Model dapat digunakan untuk memprediksi sentimen ulasan baru melalui script Python.

## Hasil dan Evaluasi

Model telah diuji pada dataset validasi dengan hasil berikut:

| Kategori | Precision | Recall | F1-Score | Support |
| -------- | --------- | ------ | -------- | ------- |
| Negatif  | 0.93      | 0.97   | 0.95     | 1100    |
| Positif  | 0.97      | 0.90   | 0.93     | 900     |

- **Akurasi**: 94%
- **Macro Average**:
  - Precision: 0.95
  - Recall: 0.94
  - F1-Score: 0.94
- **Weighted Average**:
  - Precision: 0.94
  - Recall: 0.94
  - F1-Score: 0.94

### Kesimpulan

Hasil evaluasi menunjukkan bahwa model mampu mengklasifikasikan ulasan dengan akurasi tinggi. Model memiliki performa yang seimbang pada kategori positif dan negatif dengan nilai F1-Score di atas 0.93. Evaluasi ini mengindikasikan bahwa model cocok untuk menganalisis sentimen ulasan aplikasi secara akurat.

## Teknologi yang Digunakan

- **Python** (versi 3.8 atau lebih baru)
- **Transformers Library** (HuggingFace)
- **Pandas**
- **Torch** (PyTorch)

## Lisensi

Proyek ini dilisensikan di bawah **MIT License**. Silakan lihat file `LICENSE` untuk detail lebih lanjut.
