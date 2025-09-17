# Analisis Sentimen Ulasan Produk E-Commerce Menggunakan Transformer
### Studi Kasus: Toko Pasar Stan Jogja di Tokopedia

![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)
![Libraries](https://img.shields.io/badge/Libraries-PyTorch%2C%20Transformers%2C%20Scikit--learn-orange.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

Ini adalah repositori untuk penelitian skripsi yang bertujuan membangun dan mengevaluasi model *deep learning* untuk analisis sentimen pada ulasan produk e-commerce berbahasa Indonesia.

---

## 📜 Abstrak

Di era ekonomi digital, ulasan pelanggan di platform e-commerce seperti Tokopedia telah menjadi aset krusial bagi evaluasi layanan bisnis. Namun, volume data yang besar dan bahasanya yang informal menjadi tantangan untuk dianalisis secara manual. Penelitian ini mengambil studi kasus pada Toko Pasar Stan Jogja untuk membangun sistem analisis sentimen otomatis menggunakan arsitektur Transformer. Sebanyak 15.278 ulasan digunakan untuk melatih model pra-terlatih IndoBERT, dengan menerapkan teknik *class weights* untuk menangani data tidak seimbang. Hasil pengujian menunjukkan performa yang sangat tinggi dengan pencapaian **akurasi keseluruhan sebesar 96.99%** dan **F1-Score rata-rata 0.97**. Analisis kualitatif juga berhasil mengidentifikasi bahwa kualitas produk dan efisiensi logistik menjadi pendorong utama kepuasan, sementara keluhan berpusat pada kondisi produk saat tiba. Penelitian ini membuktikan bahwa model Transformer efektif untuk klasifikasi sentimen pada ulasan lokal dan mampu berfungsi sebagai alat strategis untuk mengekstrak wawasan bisnis.

---

## 🎯 Latar Belakang Masalah

Tantangan utama yang dihadapi UMKM di ranah e-commerce, seperti pada studi kasus Toko Pasar Stan Jogja, adalah kesulitan dalam mengolah volume besar (lebih dari 15.000) data ulasan pelanggan yang tidak terstruktur. Masalah ini diperparah oleh ambiguitas sistem rating bintang yang seringkali tidak selaras dengan isi teks ulasan. Oleh karena itu, analisis mendalam pada isi teks ulasan menjadi satu-satunya cara untuk menangkap sentimen pelanggan yang sesungguhnya dan mengubahnya menjadi wawasan bisnis yang dapat ditindaklanjuti.

---

## ⚙️ Alur Penelitian

Penelitian ini dilaksanakan melalui alur kerja yang sistematis, mulai dari pengumpulan data mentah hingga penyajian hasil akhir.

![Alur Penelitian](alur%20penelitiannew.drawio.png) 
*(Catatan: Pastikan file gambar `alur penelitiannew.drawio.png` ada di root repositori Anda)*

1.  **Pengumpulan Data:** Mengakuisisi 15.278 ulasan pelanggan dari Toko Pasar Stan Jogja.
2.  **Pra-pemrosesan & Pelabelan:** Membersihkan teks (normalisasi, case folding) dan memberikan label sentimen ('positif', 'negatif', 'netral') menggunakan metode berbasis leksikon.
3.  **Pembagian & Penyeimbangan Data:** Membagi data dengan rasio 80:10:10 dan menerapkan teknik *Class Weights* untuk mengatasi data tidak seimbang.
4.  **Tokenisasi:** Mengubah teks menjadi format numerik yang dapat dipahami oleh model.
5.  **Pemodelan Data:** Melakukan *fine-tuning* pada model pra-terlatih IndoBERT.
6.  **Evaluasi & Visualisasi:** Mengukur performa model dengan metrik kuantitatif dan menganalisis hasilnya secara kualitatif.

---

## 🔧 Teknologi yang Digunakan

* **Bahasa:** Python 3.9+
* **Library Utama:**
    * `PyTorch`: Framework deep learning.
    * `Hugging Face Transformers`: Untuk memuat dan melatih model IndoBERT & GPT.
    * `Pandas`: Untuk manipulasi data.
    * `Scikit-learn`: Untuk pembagian data, metrik evaluasi, dan class weights.
    * `NLTK` & `Sastrawi`: Untuk pra-pemrosesan teks Bahasa Indonesia.
    * `Matplotlib` & `Seaborn`: Untuk visualisasi data.
    * `WordCloud`: Untuk membuat visualisasi awan kata.
* **Lingkungan:** Jupyter Notebook / Google Colab (disarankan dengan GPU).

---

## 🚀 Instalasi dan Cara Menjalankan

1.  **Clone Repositori**
    ```bash
    git clone [https://github.com/](https://github.com/)[username-anda]/[nama-repositori-anda].git
    cd [nama-repositori-anda]
    ```

2.  **Buat Virtual Environment (Disarankan)**
    ```bash
    python -m venv venv
    # Aktivasi di Windows
    .\venv\Scripts\activate
    # Aktivasi di macOS/Linux
    source venv/bin/activate
    ```

3.  **Instal Dependensi**
    Pastikan Anda memiliki file `requirements.txt` di repositori Anda, lalu jalankan:
    ```bash
    pip install -r requirements.txt
    ```

4.  **Menjalankan Kode**
    * Buka folder `notebooks/`.
    * Jalankan sel-sel pada `1_Preprocessing_dan_Labeling.ipynb` terlebih dahulu untuk menghasilkan dataset yang bersih dan berlabel.
    * Setelah itu, jalankan sel-sel pada `2_Pemodelan_IndoBERT.ipynb` atau `3_Pemodelan_GPT.ipynb` untuk melatih dan mengevaluasi model.

---

## 📊 Hasil Utama

Model IndoBERT yang dioptimalkan dengan *class weights* berhasil mencapai performa yang sangat tinggi pada 1.528 data uji.

* **Akurasi Keseluruhan:** **96.99%**
* **F1-Score Rata-rata:** **0.97**

#### Visualisasi Wawasan

**Kata Kunci Dominan pada Ulasan Positif:**
![Word Cloud Positif](results/wordcloud_positif.png)
*(Wawasan: Kepuasan didorong oleh kualitas produk (`segar`, `bagus`) dan efisiensi logistik (`cepat`, `sesuai`))*

**Kata Kunci Inti pada Ulasan Negatif:**
![Word Cloud Negatif](results/wordcloud_negatif.png)
*(Wawasan: Keluhan berpusat pada kondisi produk (`busuk`, `rusak`, `kurang`) dan pengemasan)*

---

## 📄 Lisensi
Proyek ini dilisensikan di bawah Lisensi MIT.

## ✍️ Penulis
* **[Abdan Syakura]** - *linkedin.com/in/abdansyakura23*
