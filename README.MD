# 📚 Analisis Sentimen Aplikasi iPusnas

Proyek ini bertujuan untuk menganalisis sentimen pengguna terhadap aplikasi **iPusnas** (aplikasi perpustakaan digital Indonesia) berdasarkan ulasan yang diperoleh dari Google Play Store.  

Analisis dilakukan dengan dua pendekatan utama:
1. **Lexicon-based Sentiment Analysis** menggunakan kamus sentimen Bahasa Indonesia.  
2. **Machine Learning** dengan representasi teks **TF-IDF** dan **Word2Vec** untuk membangun model klasifikasi sentimen.  

---

## 📌 Deskripsi Proyek
- **Data**: Ulasan aplikasi iPusnas yang dikumpulkan dengan teknik *web scraping* dari Google Play Store.  
- **Preprocessing**: Pembersihan data teks (case folding, stopword removal, tokenisasi, stemming, dll.).  
- **Metode Analisis**:
  - **Lexicon-based**: Menghitung skor sentimen berdasarkan kamus lexicon.  
  - **Machine Learning**: Menggunakan algoritma klasifikasi dengan representasi fitur:
    - **TF-IDF (Term Frequency – Inverse Document Frequency)**
    - **Word2Vec Embedding**  
- **Evaluasi**: Membandingkan performa kedua pendekatan berdasarkan metrik akurasi, presisi, recall, dan F1-score.  

---

## 🔄 Tahapan Preprocessing

Proses preprocessing dilakukan untuk membersihkan teks ulasan iPusnas agar siap digunakan dalam analisis sentimen. Berikut adalah langkah-langkah yang diterapkan:

1. **Menghapus Emoji**  
   - Fungsi: `hapus_emoji`  
   - Tujuan: Menghapus karakter emoji dari teks ulasan.

2. **Cleaning Text**  
   - Fungsi: `cleaningText`  
   - Tujuan: Membersihkan teks dari karakter khusus, angka, dan tanda baca yang tidak diperlukan.

3. **Case Folding**  
   - Fungsi: `casefoldingText`  
   - Tujuan: Mengubah seluruh huruf menjadi huruf kecil agar konsisten.

4. **Normalisasi Kata (Slangword Fixing)**  
   - Fungsi: `fix_slangwords`  
   - Tujuan: Mengganti kata tidak baku/slang menjadi kata baku.

5. **Tokenisasi**  
   - Fungsi: `tokenizingText`  
   - Tujuan: Memecah kalimat menjadi token/kata.

6. **Stopword Removal**  
   - Fungsi: `filteringText`  
   - Tujuan: Menghapus kata umum (seperti *dan, yang, di*) yang tidak memberikan informasi penting.

7. **Stemming**  
   - Fungsi: `stemmingText`  
   - Tujuan: Mengubah kata berimbuhan menjadi kata dasar.  
     Contoh: *membaca → baca*

8. **Rekonstruksi Kalimat**  
   - Fungsi: `toSentence`  
   - Tujuan: Menggabungkan kembali token-token hasil stemming menjadi kalimat bersih.

---

### 📊 Hasil Preprocessing

Setelah preprocessing, DataFrame akan memiliki beberapa kolom tambahan:

| Review (Asli) | text_clean | text_casefoldingText | text_slangwords | text_tokenizing | text_stopword | text_stemming | text_akhir |
|---------------|------------|-----------------------|------------------|-----------------|---------------|---------------|------------|

👉 Kolom yang digunakan untuk analisis sentimen selanjutnya adalah **`text_akhir`** karena sudah melalui seluruh tahapan preprocessing.

---

## ⚙️ Alur Pengerjaan
1. **Pengambilan Data**  
   Scraping ulasan aplikasi iPusnas dari Google Play Store.  
   
2. **Pra-pemrosesan Data**  
   (lihat bagian [Preprocessing](#-tahapan-preprocessing))  

3. **Analisis Sentimen**  
   - **Lexicon-based**: Skor sentimen dihitung menggunakan kamus lexicon.  
   - **Machine Learning**:  
     - Representasi teks: **TF-IDF** dan **Word2Vec**  
     - Algoritma klasifikasi: (contoh: Logistic Regression, SVM, Random Forest)  

4. **Evaluasi Model**  
   Menggunakan metrik:
   - Accuracy  

