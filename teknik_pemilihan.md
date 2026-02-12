# Teknik Pemilihan Fitur (Feature Selection)

Teknik Pemilihan Fitur (Feature Selection) adalah proses pemilihan subset fitur yang paling relevan atau penting untuk digunakan dalam model machine learning. Tujuannya adalah untuk meningkatkan performa model dengan menghilangkan fitur yang tidak relevan, redundan, atau kotor (noise). Dengan demikian, kita bisa mengurangi kompleksitas model, meningkatkan akurasi, dan mempercepat proses pelatihan.

Pemilihan fitur sangat penting karena model machine learning yang dilatih dengan fitur yang tidak relevan atau terlalu banyak fitur memungkinkan mengalami **overfitting**, yaitu kondisi ketika model terlalu cocok dengan data pelatihan sehingga tidak dapat melakukan generalisasi dengan baik untuk data baru. Dengan melakukan feature selection, kita dapat menghasilkan model yang lebih simpel, cepat, dan efektif.

> **Pertanyaan:** Apa bedanya dengan feature extraction?

## Feature Selection vs Feature Extraction

- **Feature Extraction**: Mengurangi jumlah variabel dengan menciptakan fitur baru melalui kombinasi fitur yang sudah ada.  
  Contoh: Principal Component Analysis (PCA).
- **Feature Selection**: Memilih fitur paling relevan dari dataset tanpa memodifikasi atau membuat fitur baru.

---

# Jenis Feature Selection

Feature selection terbagi menjadi dua kelompok besar:

## 1️⃣ Unsupervised Feature Selection

Pemilihan fitur tanpa menggunakan label target.

### Tujuan
- Mengurangi dimensionalitas
- Meningkatkan efisiensi algoritma
- Mempermudah visualisasi

### Teknik Umum

- Drop Incomplete Features (banyak missing value)
- Drop High Multicollinearity
- Drop (Near) Zero Variance
- Variance Thresholding
- PCA (transformasi dimensi)
- Clustering-based methods
- Correlation-based selection

---

## 2️⃣ Supervised Feature Selection

Pemilihan fitur menggunakan informasi label/target.

### Tujuan
- Menghilangkan fitur tidak relevan
- Mengurangi kompleksitas
- Meningkatkan performa model

### Tiga Metode Utama

- **Filter**
- **Wrapper**
- **Embedded**

---

# Persiapan Library

```python
import numpy as np
import pandas as pd
from sklearn.datasets import load_iris
from sklearn.feature_selection import SelectKBest, chi2
from sklearn.feature_selection import RFE
from sklearn.linear_model import LogisticRegression
from sklearn.ensemble import RandomForestClassifier
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.datasets import load_wine
