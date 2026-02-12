# Binning Numerik ke Kategorikal

Seperti yang sudah dipelajari pada materi Encoding Variabel ke Numerik, mungkin terasa bahwa semua permasalahan sudah dapat diselesaikan. Namun, masih ada metode lain yang dapat membantu meningkatkan performa model machine learning, yaitu **binning**.

**Binning** digunakan untuk mengubah data numerik kontinu menjadi kategori atau interval diskrit. Tujuannya adalah menyederhanakan data numerik dengan memisahkannya menjadi beberapa kelompok (bin) berdasarkan rentang atau distribusi nilai tertentu.

---

## Konsep Dasar Binning

Bayangkan Anda memiliki data usia dari 0 hingga 100 tahun. Jika langsung di-encoding, jumlah nilai unik akan sangat banyak. Dengan binning, data dapat dikelompokkan:

| Rentang Usia | Label |
|--------------|---------|
| 0–18 | Anak-Anak |
| 19–35 | Remaja |
| 36–55 | Dewasa |
| 56–100 | Lansia |

---

## Tujuan Binning

Binning digunakan saat:
- Menyederhanakan data numerik kontinu
- Mengurangi variasi kecil yang tidak signifikan
- Mengurangi pengaruh noise
- Menangani outlier
- Mempermudah interpretasi
- Membantu model fokus pada pola utama

---

## Perbedaan Encoding vs Binning

- **Encoding** → Mengubah data kategorikal menjadi numerik  
- **Binning** → Mengubah data numerik menjadi kategorikal

---

# Jenis Binning

Secara umum, binning dibagi menjadi dua:

## 1️⃣ Unsupervised Binning
- Tidak menggunakan target variabel
- Berdasarkan distribusi atau rentang data
- Netral terhadap label

Contoh:
- Equal-width binning
- Equal-frequency binning

## 2️⃣ Supervised Binning
- Menggunakan target variabel
- Bin dibentuk agar paling informatif terhadap target
- Cocok untuk model prediktif

Contoh:
- Entropy-based binning

---

# Equal-Width Binning

Membagi rentang nilai menjadi interval dengan **lebar yang sama**.

## Langkah

Data usia:

- Min = 5
- Max = 57
- Rentang = 52
- Jumlah bin = 3
- Lebar bin = 52 / 3 = 17.33

## Hasil Bin

- Bin 1: 5–22.33 → [5, 12, 17]
- Bin 2: 22.34–39.67 → [22, 27, 33, 38]
- Bin 3: 39.68–57 → [42, 50, 57]

## Kelebihan
- Sederhana
- Cepat
- Komputasi ringan

## Kekurangan
- Tidak mempertimbangkan distribusi data
- Bisa terjadi bin kosong atau terlalu padat

---

# Equal-Frequency Binning

Membagi data sehingga **jumlah data tiap bin sama atau hampir sama**.

## Langkah

Data diurutkan:

Jumlah data = 10  
Jumlah bin = 3  
≈ 3–4 data per bin

## Hasil Bin

- Bin 1 → [5, 12, 17]
- Bin 2 → [22, 27, 33, 38]
- Bin 3 → [42, 50, 57]

## Kelebihan
- Distribusi jumlah data merata
- Tidak ada bin kosong

## Kekurangan
- Lebar interval berbeda-beda
- Interpretasi rentang kurang intuitif

---

# Perbandingan Singkat

| Metode | Lebar Interval | Jumlah Data per Bin |
|---------|----------------|----------------------|
Equal Width | Sama | Bisa berbeda |
Equal Frequency | Berbeda | Sama |

---

# Entropy-Based Binning (Supervised)

Metode binning yang mempertimbangkan **target variabel**.  
Digunakan dalam supervised learning.

Tujuan: membentuk bin yang **memisahkan kelas target sebaik mungkin**.

---

## Konsep Entropy

Entropy = ukuran ketidakpastian data.

- Entropy rendah → data lebih homogen
- Entropy tinggi → data lebih acak

### Rumus Entropy

---

## Contoh Data


- Yes = 6 → p = 0.6
- No = 4 → p = 0.4
- Entropy total ≈ **0.971**

---

## Contoh Split di Usia 25

### Bin 1: Usia ≤ 25
- Yes = 1
- No = 2
- Entropy dihitung dari distribusi ini

### Bin 2: Usia > 25
- Yes = 5
- No = 2

---

## Information Gain

Information Gain = penurunan entropy setelah split.

### Rumus


Split terbaik = **information gain tertinggi**

---

# Kapan Pakai Entropy-Based Binning

Gunakan saat:
- Ada target variabel
- Fokus pada prediksi
- Ingin bin paling informatif
- Dipakai di decision tree & model klasifikasi

---

# Kesimpulan

Binning membantu:

- Menyederhanakan data numerik
- Mengurangi noise
- Mengatasi outlier
- Memperjelas pola
- Meningkatkan performa model

## Ringkasan Teknik

| Teknik | Tipe | Gunakan Saat |
|----------|----------|----------------|
Equal Width | Unsupervised | Butuh cepat & sederhana |
Equal Frequency | Unsupervised | Ingin distribusi merata |
Entropy-Based | Supervised | Ada target & ingin optimal |

---

Terus eksplorasi teknik preprocessing lainnya — fondasi data yang baik = model yang kuat 🚀

