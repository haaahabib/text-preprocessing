# Preprocessing Teks Bahasa Indonesia

Repositori ini menyediakan kumpulan fungsi Python yang dirancang khusus untuk melakukan *text preprocessing* pada teks berbahasa Indonesia. Proses ini merupakan langkah fundamental dalam banyak tugas *Natural Language Processing* (NLP) seperti analisis sentimen, klasifikasi teks, dan pemodelan topik.

---

## Daftar Isi

1.  [Latar Belakang](#latar-belakang)
2.  [Fitur (Fungsi Preprocessing)](#fitur-fungsi-preprocessing)
3.  [Tech Stack](#tech-stack)
4.  [Instalasi](#instalasi)
5.  [Cara Penggunaan](#cara-penggunaan)

---

## Latar Belakang

Data teks di dunia nyata sering kali "kotor" dan tidak terstruktur. Teks tersebut bisa mengandung huruf kapital yang tidak konsisten, tanda baca, angka, dan kata-kata umum (stopwords) yang tidak memiliki banyak makna. *Text preprocessing* adalah serangkaian langkah untuk membersihkan dan menstandarisasi teks, sehingga model *machine learning* dapat memprosesnya dengan lebih efektif dan akurat.

## Fitur (Fungsi Preprocessing)

Skrip ini menyediakan beberapa fungsi pembersihan teks yang esensial:

-   **Case Folding**: Mengubah seluruh teks menjadi huruf kecil (`lowercase`) untuk konsistensi.
-   **Menghapus Angka**: Membersihkan teks dari semua karakter numerik.
-   **Menghapus Tanda Baca**: Menghilangkan semua tanda baca (misalnya, `!`, `,`, `.`, `?`).
-   **Menghapus Spasi Berlebih**: Merapikan spasi putih yang tidak perlu di dalam teks.
-   **Tokenizing**: Memecah kalimat menjadi potongan-potongan kata atau token.
-   **Stopword Removal**: Menghapus kata-kata umum dalam Bahasa Indonesia yang tidak membawa banyak makna (misalnya, 'yang', 'di', 'dan', 'adalah') menggunakan library Sastrawi.
-   **Stemming**: Mengubah kata-kata ke bentuk dasarnya (misalnya, 'menjalankan' -> 'jalan') menggunakan library Sastrawi untuk mengurangi variasi kata.

---

## Tech Stack

-   **Bahasa Pemrograman**: Python
-   **Library Utama**:
    -   `Sastrawi`: Untuk proses *stopword removal* dan *stemming* khusus Bahasa Indonesia.
    -   `NLTK` (Natural Language Toolkit): Digunakan untuk proses *tokenizing*.
    -   `re` (Regular Expressions): Digunakan untuk membersihkan angka dan tanda baca.

---

## Instalasi

1.  **Clone Repositori Ini**
    ```bash
    git clone https://github.com/haaahabib/text-preprocessing.git
    ```

2.  **Masuk ke Direktori Proyek**
    ```bash
    cd text-preprocessing
    ```

3.  **Install Library yang Dibutuhkan**
    ```bash
    pip install sastrawi nltk
    ```
    Anda mungkin juga perlu mengunduh data pendukung untuk NLTK jika belum ada:
    ```python
    import nltk
    nltk.download('punkt')
    ```

---

## Cara Penggunaan

Anda dapat mengimpor fungsi-fungsi dari skrip utama dan menerapkannya pada data teks Anda. Berikut adalah contoh sederhana:

```python
# Import fungsi dari file preprocess_text.py
from preprocessing import preprocess_text

# Contoh teks kotor
teks_kotor = "  Saya sedang belajar Natural Language Processing (NLP) di tahun 2024!! Seru sekali. "

# Terapkan seluruh pipeline preprocessing
teks_bersih = preprocess_text(teks_kotor)

# Tampilkan hasilnya
print(f"Teks Asli: {teks_kotor}")
print(f"Teks Bersih: {teks_bersih}")

# Contoh output yang diharapkan:
# Teks Asli:   Saya sedang belajar Natural Language Processing (NLP) di tahun 2024!! Seru sekali. 
# Teks Bersih: saya ajar natural language processing nlp tahun seru sekali
