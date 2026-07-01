# Tugas Proyek Akhir Data Mining - Preprocessing & Clustering (UAS)

Repositori ini berisi pemenuhan Tugas Proyek Akhir untuk mata kuliah Data Mining yang mencakup tahap *Data Preprocessing* (Cleaning & Scaling) dan implementasi *Unsupervised Learning* menggunakan algoritma K-Means Clustering.

## Data Diri
* **Nama:** [Hasya Ferdiansyah Noer Rizqi]
* **NIM:** [241011401393]
* **Kelas:** [TPLM 008]

## Struktur Berkas
* `Tugas_UAS.ipynb`: File utama Jupyter Notebook yang berisi seluruh *source code* eksperimen, grafik evaluasi, serta visualisasi cluster.
* `water_potability.csv`: Dataset mentah kelayakan air yang diperoleh secara organik dari Kaggle.
* `UAS.md`: File dokumentasi (README) ini.

## Alur Eksperimen Ringkas
1. **Identifikasi & Pemilihan Dataset:** Menggunakan data kualitas air asli dengan kecacatan bawaan.
2. **Preprocessing:** * Imputasi nilai kosong (*missing values*) pada fitur `ph`, `Sulfate`, dan `Trihalomethanes` menggunakan nilai **Median**.
   * Pembersihan kolom target dan standarisasi fitur numerik menggunakan `StandardScaler`.
3. **Evaluasi Elbow:** Menentukan jumlah klaster optimal dan menemukan bahwa sudut siku melandai ideal pada **K=3**.
4. **Klasterisasi & Visualisasi:** Mengimplementasikan K-Means dengan 3 klaster dan memvisualisasikan sebaran data melalui hubungan fitur `ph` vs `Sulfate`.

---
*Seluruh detail analisis, pembahasan, dan grafik interaktif dapat langsung dilihat dengan membuka berkas notebook `Tugas_UAS.ipynb` di atas.*