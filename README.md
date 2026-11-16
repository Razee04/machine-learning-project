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

# Prediksi Gaji Menggunakan Support Vector Regression (SVR)

Proyek ini merupakan implementasi algoritma **Support Vector Regression (SVR)** untuk memprediksi besaran gaji (`Salary`) berdasarkan lama pengalaman kerja (`YearsExperience`).

## Dataset
Dataset yang digunakan adalah `Salary_Data.csv`, dengan total **30 baris data** dan **2 kolom**:
* **Atribut (Fitur):** `YearsExperience` (Lama pengalaman kerja dalam tahun.
* **Label (Target):** `Salary` (Besaran gaji).

## Alur Pengerjaan
1. **Import & Eksplorasi Data:** Membaca dataset menggunakan `pandas` serta memeriksa struktur dan tipe data dengan `.info()` dan `.head()` (seluruh data sudah lengkap dan bertipe numerik `float64`, sehingga tidak diperlukan proses *encoding*).
2. **Pemisahan & Penyesuaian Dimensi Data:** Memisahkan kolom atribut `YearsExperience` (`X`) dan label `Salary` (`y`), lalu mengubah bentuk array atribut menjadi 2 dimensi menggunakan `numpy` (`np.newaxis`) agar sesuai dengan format input model.
3. **Pelatihan Model (SVR):** Membangun dan melatih model `SVR` menggunakan `scikit-learn` dengan parameter `C=1000`, `gamma=0.05`, dan `kernel='rbf'`.
4. **Visualisasi Hasil:** Menampilkan grafik sebaran data asli menggunakan `.scatter()` dan garis kurva hasil prediksi model menggunakan `.plot()` dari library `matplotlib`.

## Teknologi & Library yang Digunakan
* **Python 3**
* **Pandas** (Manipulasi dan analisis data)
* **NumPy** (Pengolahan dimensi array)
* **Scikit-Learn** (`SVR`)
* **Matplotlib** (Visualisasi data dan garis prediksi)
