# Deteksi Pesan Spam (Machine Learning)

Proyek sederhana berbasis Machine Learning untuk mendeteksi apakah sebuah pesan teks atau pesan *chat* berbahasa Indonesia termasuk ke dalam kategori **Spam** atau **Bukan Spam (Ham)**.

Proyek ini menggunakan algoritma **Multinomial Naive Bayes** yang dikombinasikan dengan metode ekstraksi fitur teks **TF-IDF (Term Frequency - Inverse Document Frequency)**.

---

## Alur Kerja Program

1. **Pengumpulan Data:** Menggunakan contoh pesan teks berbahasa Indonesia (penawaran pinjol, undian palsu, pesan harian, tugas, dsb.).
2. **Pembagian Data (*Split Dataset*):** Data dibagi menjadi 80% data latih (*training*) dan 20% data uji (*testing*).
3. **Ekstraksi Fitur (TF-IDF):** Mengubah kata-kata dalam teks menjadi representasi angka berbobot agar dapat diproses oleh algoritma.
4. **Pelatihan Model (*Model Training*):** Melatih model menggunakan algoritma `MultinomialNB`.
5. **Evaluasi & Pengujian:** Mengukur akurasi model serta menguji prediksi teks baru beserta tingkat keyakinan (*confidence score*).

---

## Teknologi & *Library*

- **Python** (versi 3.8+)
- **Jupyter Notebook**
- **Scikit-Learn**
  - `TfidfVectorizer` (pengubah teks ke angka)
  - `MultinomialNB` (algoritma klasifikasi)
  - `train_test_split` (pemisah data)
  - `accuracy_score` (pengukur akurasi)

---

## Struktur File

```text
├── app.ipynb      # Notebook utama: data, pelatihan, evaluasi, dan fungsi prediksi
└── README.md      # Dokumentasi proyek
```

---

## Cara Menjalankan

### 1. Prasyarat
Pastikan Python sudah terinstal di komputer Anda. Disarankan menggunakan environment Python atau editor seperti VS Code / Jupyter Lab.

### 2. Instalasi Dependensi
Jalankan perintah berikut di terminal:

```bash
pip install scikit-learn
```

### 3. Menjalankan Proyek
Buka file `app.ipynb` di VS Code atau Jupyter Notebook, lalu jalankan semua sel secara berurutan (*Run All*).

---

## Contoh Penggunaan

Di dalam notebook, Anda dapat menguji pesan baru menggunakan fungsi `cek_spam()`:

```python
cek_spam("SELAMAT ANDA MENANG HADIAH GRATIS KLIK LINK")
# Output:
# Chat: SELAMAT ANDA MENANG HADIAH GRATIS KLIK LINK
# Hasil: SPAM - yakin 87%

cek_spam("bro besok jadi futsal ga jam 4")
# Output:
# Chat: bro besok jadi futsal ga jam 4
# Hasil: BUKAN - yakin 78%
```

---

## Pengembangan Lebih Lanjut

Untuk meningkatkan performa dan cakupan model di masa mendatang:
- [ ] Menambahkan lebih banyak variasi data latih (dataset publik SMS spam Indonesia).
- [ ] Menerapkan *text preprocessing* (pembersihan teks, *lowercasing*, penghapusan tanda baca, *stopword removal*).
- [ ] Mengekspor model (`pickle` / `joblib`) dan membuat antarmuka web sederhana menggunakan **Streamlit** atau **Gradio**.
