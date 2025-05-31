
# Persamaan Penting Algoritma Klasifikasi

## 1. Logistic Regression

**Kombinasi Linier:**  
z = β0 + β1 * x1 + β2 * x2 + ... + βn * xn

**Fungsi Aktivasi (Sigmoid):**  
P(y = 1 | x) = 1 / (1 + exp(-z))

**Fungsi Kerugian (Log Loss):**  
Loss = - [ y * log(p) + (1 - y) * log(1 - p) ]

---

## 2. Random Forest Classifier

**Prediksi Kelas (Voting Mayoritas):**  
ŷ = mode(h1(x), h2(x), ..., hT(x))

Keterangan:  
- hi(x) = prediksi dari pohon ke-i  
- T = jumlah pohon dalam hutan

---

## 3. XGBoost Classifier

**Prediksi Awal:**  
ŷ(0) = 0

**Update pada iterasi ke-t:**  
ŷ(t) = ŷ(t-1) + η * ft(x)

**Fungsi Objektif:**  
Obj = Σ Loss(yi, ŷi) + Σ Ω(ft)

Keterangan:  
- η = learning rate  
- ft(x) = prediksi pohon pada iterasi ke-t  
- Ω(ft) = penalti/regularisasi terhadap kompleksitas pohon ft

---

## 4. Support Vector Machine (SVM)

**Fungsi Keputusan:**  
f(x) = w · x + b

**Optimasi (Hard Margin):**  
Minimize: 0.5 * ||w||²  
Subject to: yi(w · xi + b) ≥ 1

**Fungsi Kernel (untuk Nonlinear SVM):**  
K(xi, xj) = φ(xi) · φ(xj)

---

## 5. K-Nearest Neighbors (KNN)

**Jarak Euclidean:**  
d = sqrt((x1 - x2)² + (y1 - y2)²)

**Prediksi Kelas (Mayoritas):**  
ŷ = mode(y1, y2, ..., yK)

Keterangan:  
- yi = label dari tetangga ke-i
