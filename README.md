# Deteksi Pesan Spam dengan Machine Learning

Proyek pembelajaran machine learning untuk mengklasifikasikan pesan berbahasa Indonesia sebagai **spam** atau **bukan spam**. Model menggunakan `TfidfVectorizer` untuk mengubah teks menjadi fitur numerik dan `MultinomialNB` untuk melakukan klasifikasi.

> Dataset dalam notebook adalah contoh kecil buatan untuk belajar, bukan dataset produksi. Skor evaluasi dapat berubah jika data atau pembagian latih-uji diubah, dan prediksi tidak boleh dianggap sebagai kepastian.

## Isi proyek

Semua tahapan ada di [`app.ipynb`](./app.ipynb):

1. Memuat 46 contoh pesan dengan label spam/bukan spam.
2. Membagi data menjadi data latih (80%) dan data uji (20%) dengan pembagian berstrata agar proporsi kelas tetap seimbang.
3. Mengubah pesan menjadi fitur TF-IDF dan melatih model Naive Bayes.
4. Mengukur akurasi, precision, recall, F1-score, dan menampilkan matriks kebingungan.
5. Melihat kata-kata yang paling dipelajari model untuk tiap kelas.
6. Menguji pesan melalui fungsi `cek_spam(teks)` dan sekumpulan contoh tambahan.

## Persyaratan

- Python 3.11 atau lebih baru (versi notebook yang tercatat: 3.11.9)
- Jupyter Notebook, JupyterLab, atau VS Code dengan dukungan notebook
- scikit-learn

## Menjalankan notebook

1. Buka terminal di folder proyek.
2. (Opsional) Buat dan aktifkan virtual environment.
3. Instal dependensi:

   ```bash
   python -m pip install scikit-learn
   ```

4. Buka `app.ipynb`, lalu pilih **Run All**. Jalankan cell dari atas ke bawah karena cell analisis menggunakan variabel dan model yang dibuat di cell pelatihan.
5. Ubah daftar `contoh_tambahan` atau panggil fungsi `cek_spam("pesan yang ingin diuji")` di cell terakhir.

Notebook memasang `scikit-learn` melalui `%pip` pada cell pertama, jadi instalasi manual dapat dilewati jika notebook bisa mengakses internet dan izin instalasi tersedia.

## Membaca hasil

- Akurasi menunjukkan proporsi prediksi benar pada data uji yang kecil.
- Precision, recall, dan F1-score memberi gambaran lebih rinci untuk masing-masing kelas.
- Matriks kebingungan mencetak label asli sebagai baris dan hasil prediksi sebagai kolom, dengan urutan kelas `bukan`, `spam`.
- Persentase pada `cek_spam()` adalah probabilitas maksimum yang diberikan model, bukan jaminan bahwa prediksi benar.

## Batasan dan pengembangan berikutnya

- Contoh data masih sedikit dan dibuat khusus untuk demonstrasi. Model bisa salah pada slang, variasi ejaan, pesan ambigu, serta pola spam baru.
- Jangan memasukkan informasi pribadi ke contoh pesan. Sebelum penggunaan nyata, gunakan dataset yang representatif dan evaluasi model pada data terpisah yang memadai.
- Pengembangan berikutnya dapat mencakup penambahan data berlabel, preprocessing teks yang dievaluasi dengan hati-hati, validasi silang, serta antarmuka aplikasi sederhana.
