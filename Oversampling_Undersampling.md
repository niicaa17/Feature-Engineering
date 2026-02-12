# Oversampling dan Undersampling

Hi calon engineer masa depan! 🚀  
Pada tahap ini kita membahas permasalahan umum dalam machine learning yaitu **imbalanced dataset** dan teknik penanganannya.

---

## 📌 Imbalanced Dataset

Imbalanced dataset adalah kondisi ketika jumlah data pada satu kelas jauh lebih banyak dibanding kelas lainnya.

Contoh:
- Kelas mayoritas: 95%
- Kelas minoritas: 5%

Masalah yang muncul:
- Model cenderung memprediksi kelas mayoritas
- Akurasi terlihat tinggi tetapi performa sebenarnya buruk
- Kelas minoritas sering salah diprediksi
- Akurasi bukan metrik yang tepat → gunakan precision, recall, F1-score

---

## ⚖️ Tingkat Ketidakseimbangan

Secara umum tingkat imbalance dapat dibagi menjadi:
- Ringan
- Sedang
- Parah

Disarankan tetap membuat **baseline model** terlebih dahulu sebelum melakukan teknik penyeimbangan data.

---

# 🔼 Oversampling

Oversampling adalah teknik **menambah jumlah data kelas minoritas** agar seimbang dengan kelas mayoritas.

## ✅ Tujuan
- Memberi model lebih banyak contoh kelas minoritas
- Mengurangi bias ke kelas mayoritas

---

## 🔹 Random Oversampling

Menyalin (duplicate) data minoritas secara acak hingga jumlahnya seimbang.

**Contoh:**
- Mayoritas = 100 data
- Minoritas = 10 data
- Minoritas diduplikasi menjadi 100

### Kelebihan
- Mudah diterapkan
- Cepat
- Komputasi ringan

### Kekurangan
- Risiko overfitting
- Model bisa “menghafal” data duplikat

---

## 🔹 SMOTE (Synthetic Minority Over-sampling Technique)

SMOTE membuat **data sintetis baru** dari kelas minoritas dengan interpolasi antar titik data.

### Cara kerja
- Memilih dua titik minoritas
- Membuat titik baru di antara keduanya
- Menambah variasi data minoritas

### Kelebihan
- Mengurangi overfitting
- Data tidak sekadar duplikat
- Variasi lebih baik

### Kekurangan
- Lebih kompleks
- Bisa menghasilkan data sintetis yang kurang realistis jika distribusi buruk

---

# 🔽 Undersampling

Undersampling adalah teknik **mengurangi jumlah data kelas mayoritas** agar seimbang dengan kelas minoritas.

---

## 🔹 Random Undersampling

Menghapus data mayoritas secara acak.

**Contoh:**
- Mayoritas = 100
- Minoritas = 10
- Mayoritas dipotong menjadi 10

### Kelebihan
- Sederhana
- Cepat
- Dataset lebih kecil → training lebih cepat

### Kekurangan
- Kehilangan informasi penting
- Risiko underfitting
- Pola mayoritas bisa hilang

---

## 🔹 Cluster Centroids

Menggunakan algoritma clustering (misal K-Means) untuk:
- Mengelompokkan data mayoritas
- Mengambil centroid sebagai wakil cluster
- Mengurangi data tanpa menghapus pola utama

### Kelebihan
- Representasi mayoritas lebih terjaga
- Lebih cerdas dari random undersampling

### Kekurangan
- Komputasi lebih berat
- Bisa kehilangan variasi pola
- Tidak selalu cocok untuk data sangat kompleks

---

# 🧠 Ringkasan Strategi

| Metode | Cara | Risiko |
|--------|--------|---------|
| Oversampling | Tambah data minoritas | Overfitting |
| SMOTE | Data sintetis minoritas | Data tidak realistis |
| Undersampling | Kurangi mayoritas | Kehilangan informasi |
| Cluster Centroids | Representasi cluster | Bias sampling |

---

# 🎯 Rekomendasi Praktis

- ✅ Bangun baseline model dulu
- ✅ Gunakan metrik selain akurasi
- ✅ Coba beberapa teknik sampling
- ✅ Validasi dengan cross-validation
- ✅ Jika memungkinkan → kumpulkan data asli tambahan
- ⚠️ Data sintetis bukan pengganti data nyata

---

> Imbalanced dataset adalah masalah umum — teknik sampling adalah alat bantu, bukan solusi utama. Data berkualitas tetap yang paling penting.
