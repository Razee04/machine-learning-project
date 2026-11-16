# Klasifikasi Diabetes Menggunakan Support Vector Machine (SVM)

Proyek ini merupakan implementasi algoritma **Support Vector Classifier (SVC)** untuk memprediksi risiko diabetes berdasarkan data medis pasien.

## Dataset
Dataset yang digunakan adalah `diabetes.csv` yang diunduh dari Kaggle, dengan total **768 baris data** dan **9 kolom**:
* **Atribut (Fitur):** `Pregnancies`, `Glucose`, `BloodPressure`, `SkinThickness`, `Insulin`, `BMI`, `DiabetesPedigreeFunction`, dan `Age'.
* **Label (Target):** `Outcome` (`0` = Tidak Diabetes, `1` = Diabetes).

## Alur Pengerjaan
1. **Import & Eksplorasi Data:** Membaca dataset menggunakan `pandas` serta memeriksa struktur dan tipe data dengan `.head()` dan `.info()` (seluruh data sudah bertipe numerik `int64` dan `float64` tanpa nilai kosong, sehingga tidak diperlukan proses *encoding*).
2. **Pemisahan Fitur & Target:** Memisahkan 8 kolom atribut (`X`) dan kolom label `Outcome` (`y`).
3. **Standarisasi Data:** Menyeragamkan skala nilai pada seluruh atribut menggunakan `StandardScaler` agar jarak antar data terukur secara proporsional.
4. **Split Data:** Membagi dataset menjadi data latih (*training*) dan data uji (*testing*) menggunakan `train_test_split` dengan rasio **67% data latih** dan **33% data uji** (`test_size=0.33`, `random_state=42`).
5. **Pelatihan Model (SVC):** Membangun dan melatih model `SVC()` dengan `scikit-learn`. Selama proses `.fit()`, model secara otomatis menentukan garis pembatas (*hyperplane*) beserta ruang toleransi (*margin*) yang paling optimal untuk memisahkan kedua kelas.
6. **Evaluasi Model:** Menguji performa model terhadap data uji menggunakan fungsi `.score()`.

## Hasil Evaluasi
Model Support Vector Classifier (SVC) menghasilkan tingkat akurasi sebesar **75,59%** (`0.7559`) pada data uji.

## Teknologi & Library yang Digunakan
* **Python 3**
* **Pandas** (Manipulasi dan analisis data)
* **Scikit-Learn** (`StandardScaler`, `train_test_split`, `SVC`)
