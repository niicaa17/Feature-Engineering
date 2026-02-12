# Encoding Variabel ke Numerik

Setelah dataset dibersihkan, masih ada beberapa tahap yang perlu dilakukan agar dataset benar-benar siap untuk diproses oleh model machine learning. Biasanya, dataset terdiri dari dua jenis data: **numerik** dan **kategorik**.

## Data Numerik
Contoh data numerik:
- Ukuran panjang
- Suhu
- Nilai uang
- Jumlah hitungan

Data numerik bisa berupa:
- Integer: -1, 0, 1, 2, 3
- Float: -1.0, 2.5, 39.99

Data numerik:
- Bisa dibandingkan
- Punya skala jelas
- Bisa diproses statistik
- Mudah dipahami komputer

## Data Kategorik

Data kategorik berupa label atau kategori (string), misalnya:
- Cuaca: cerah, hujan, berawan
- Buah: apel, pisang, jeruk

Data kategorik:
- Tidak punya makna matematis
- Tidak bisa dibandingkan secara numerik
- Tidak bisa langsung diproses model ML

---

# Mengapa Perlu Encoding?

Sebagian besar algoritma machine learning hanya menerima **input numerik**. Tanpa encoding:
- Model bisa gagal berjalan
- Hasil prediksi buruk
- Perhitungan jarak tidak valid

**Encoding** = proses mengubah data kategorikal menjadi numerik.

---

# Jenis Teknik Encoding

Materi ini membahas 7 teknik encoding paling umum:

1. One-Hot Encoding
2. Dummy Encoding
3. Effect Encoding
4. Label Encoding
5. Ordinal Encoding
6. Count Encoding
7. Binary Encoding

---

# One-Hot Encoding

Mengubah setiap kategori menjadi kolom biner (0/1).

## Contoh
Kategori: Merah, Kuning, Hijau

| Warna | Merah | Kuning | Hijau |
|--------|--------|---------|---------|
| Merah | 1 | 0 | 0 |

## Kelebihan
- Tidak mengasumsikan urutan
- Aman untuk data nominal
- Cocok untuk KNN, SVM, NN

## Kekurangan
- Dimensi membengkak (high cardinality)
- Boros memori

## Gunakan Saat
- Jumlah kategori kecil
- Tidak ada urutan kategori

---

# Dummy Encoding

Mirip One-Hot, tetapi **satu kategori dihapus** sebagai baseline.

## Tujuan
Menghindari **multikolinearitas** pada model linear.

## Cocok Untuk
- Regresi linear
- Regresi logistik

Baseline menjadi referensi perbandingan koefisien.

---

# Effect Encoding

Mirip Dummy Encoding tetapi:
- Kategori baseline diberi nilai **-1**
- Bukan dihapus

## Ciri
- Representasi: 1, 0, -1
- Koefisien dibandingkan terhadap **rata-rata**, bukan baseline

## Cocok Untuk
- Analisis statistik
- ANOVA
- Studi efek kategori terhadap rata-rata

---

# Label Encoding

Mengganti kategori dengan angka unik.

## Contoh

| Warna | Label |
|---------|--------|
| Merah | 0 |
| Kuning | 1 |
| Hijau | 2 |

## Kelebihan
- Sederhana
- Cepat
- Tidak menambah kolom

## Kekurangan
- Bisa dianggap punya urutan palsu
- Berbahaya untuk data nominal

## Cocok Untuk
- Data ordinal
- Target label klasifikasi

---

# Ordinal Encoding

Mirip label encoding tetapi **urutan ditentukan manual**.

## Contoh Urutan
Merah < Kuning < Hijau

| Warna | Ordinal |
|---------|-----------|
| Merah | 1 |
| Kuning | 2 |
| Hijau | 3 |

## Kelebihan
- Mempertahankan urutan logis
- Model bisa belajar hierarki

## Gunakan Saat
- Data benar-benar ordinal
- Ada ranking jelas

---

# Count Encoding (Frequency Encoding)

Kategori diganti dengan **jumlah kemunculan**.

## Contoh Data
Merah, Kuning, Hijau, Merah, Hijau, Kuning

Semua muncul 2 kali → semua jadi nilai 2.

## Kelebihan
- Tidak menambah dimensi
- Cocok high cardinality
- Hemat memori

## Kekurangan
- Bisa sebabkan overfitting
- Kurang cocok model berbasis jarak

---

# Binary Encoding

Gabungan Label Encoding + representasi biner.

## Langkah

1. Label encoding → angka
2. Angka → biner
3. Digit biner → kolom terpisah

## Contoh

| Kategori | Label | Biner |
|------------|---------|---------|
| Merah | 1 | 01 |
| Kuning | 2 | 10 |
| Hijau | 3 | 11 |

## Kelebihan
- Lebih hemat kolom dibanding One-Hot
- Cocok high cardinality

---

# Ringkasan Pemilihan Encoding

| Teknik | Cocok Untuk | Catatan |
|----------|--------------|------------|
One-Hot | Kategori sedikit | Dimensi besar |
Dummy | Regresi | Hindari multikolinearitas |
Effect | Statistik | Bandingkan ke rata-rata |
Label | Ordinal / target | Hati-hati nominal |
Ordinal | Data berurutan | Urutan manual |
Count | High cardinality | Risiko bias frekuensi |
Binary | High cardinality | Lebih efisien |

---

# Kesimpulan

Encoding bukan sekadar langkah teknis, tetapi fondasi penting dalam machine learning. Pemilihan teknik encoding yang tepat dapat:

- Meningkatkan performa model
- Mengurangi bias
- Menghemat komputasi
- Menjaga makna data

Selanjutnya: **Binning** 🚀
