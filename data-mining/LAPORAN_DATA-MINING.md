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

# Laporan Proyek Akhir Data Mining: Preprocessing dan Unsupervised Learning

## 1. Identifikasi & Pemilihan Dataset
* **Dataset yang Digunakan:** Water Potability Dataset (Data Kualitas dan Kelayakan Air).
* **Karakteristik Data:** Memiliki total 3.276 baris data dan 10 kolom fitur numerik yang mengukur berbagai kandungan kimiawi di dalam air (seperti pH, Hardness, Sulfate, Conductivity, dll).

## 2. Tahap Preprocessing (Cleaning & Scaling)
* **Penanganan Missing Values:** Ditemukan indikasi data kosong (*missing values*) alami bawaan dari dataset asli pada tiga kolom utama, yaitu kolom `ph` sebanyak 491 data, `Sulfate` sebanyak 781 data, dan `Trihalomethanes` sebanyak 162 data. Penanganan kecacatan data ini diselesaikan secara organik dengan teknik **Imputasi menggunakan nilai Median** dari masing-masing kolom terkait agar nilai sebarannya tetap terjaga dari efek *outliers*.
* **Data Duplikat:** Hasil pengecekan menggunakan fungsi `.duplicated().sum()` menunjukkan angka **0**, yang berarti tidak terdapat redundansi baris data pada dataset ini.
* **Scaling Data:** Sebelum masuk ke pemodelan, fitur target (`Potability`) disingkirkan terlebih dahulu untuk menjaga esensi dari *Unsupervised Learning*. Sembilan fitur numerik yang tersisa kemudian diseragamkan skalanya menggunakan **StandardScaler** dari *library* Scikit-Learn. Proses ini wajib dilakukan agar algoritma klasterisasi tidak bias atau condong pada fitur yang memiliki rentang angka besar seperti `Sulfate` atau `Solids`.

## 3. Penentuan Cluster Optimal (Evaluasi Elbow)
* Eksplorasi jumlah klaster dilakukan menggunakan **Metode Elbow** dengan mengukur nilai WCSS (*Within-Cluster Sum of Squares*) atau *Inertia* dari rentang $K=1$ hingga $K=10$.
* Berdasarkan grafik visualisasi yang dihasilkan, penurunan nilai WCSS terlihat sangat tajam pada awal dan mulai melandai secara konsisten (membentuk sudut siku-siku/elbow yang ideal) tepat setelah titik **K=3**. Oleh karena itu, jumlah klaster optimal yang diputuskan untuk pemodelan akhir ini adalah **3 cluster**.

## 4. Implementasi K-Means & Analisis Hasil
* Algoritma **K-Means Clustering** berhasil diimplementasikan pada data yang telah di-*scaling* dengan parameter `n_clusters=3`.
* Hasil pembagian kelompok data menunjukkan bahwa data berhasil terbagi secara bervariasi ke dalam tiga klaster (Cluster 0, Cluster 1, dan Cluster 2).
* Visualisasi sebaran klaster telah ditampilkan melalui *scatter plot* 2D menggunakan kombinasi dua fitur dominan, yaitu `ph` terhadap `Sulfate`. Pola garis tegak dan mendatar yang terbentuk di tengah grafik merepresentasikan pemusatan data hasil dari proses imputasi nilai median pada tahap *preprocessing* sebelumnya.
---
*Seluruh detail analisis, pembahasan, dan grafik interaktif dapat langsung dilihat dengan membuka berkas notebook `Tugas_UAS.ipynb` di atas.*