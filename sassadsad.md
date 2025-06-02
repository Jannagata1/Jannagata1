# Laporan Proyek Machine Learning - Jannagata Tan Atmaja

## Project Overview
Diabetes mellitus merupakan salah satu penyakit tidak menular paling mematikan dan menjadi tantangan serius dalam sistem kesehatan global. Menurut laporan dari World Health Organization (WHO), pada tahun 2021 terdapat lebih dari 537 juta orang dewasa yang hidup dengan diabetes di seluruh dunia. Jumlah ini diprediksi akan meningkat secara drastis menjadi 643 juta pada tahun 2030, dan bahkan mencapai 783 juta pada tahun 2045 jika tidak ada intervensi yang signifikan. Penyakit ini tidak hanya menyebabkan berbagai komplikasi kronis seperti nefropati (kerusakan ginjal), retinopati (kebutaan), neuropati, dan penyakit jantung koroner, tetapi juga berdampak besar terhadap produktivitas kerja dan pembiayaan kesehatan nasional.

Di Indonesia sendiri, prevalensi diabetes mengalami peningkatan yang signifikan. Berdasarkan data Riset Kesehatan Dasar (Riskesdas) tahun 2018 dari Kementerian Kesehatan RI, prevalensi diabetes meningkat dari 6,9% (2013) menjadi 8,5% (2018) dari total populasi. Sayangnya, sekitar 2 dari 3 penderita diabetes tidak menyadari bahwa mereka mengidap penyakit ini, sehingga diagnosis sering kali baru dilakukan setelah komplikasi parah muncul. Masalah utama dalam pengendalian diabetes adalah rendahnya tingkat deteksi dini. Pemeriksaan laboratorium konvensional seperti tes HbA1c, Gula Darah Puasa (GDP), dan Glukosa Toleransi Oral (GTT) memiliki keterbatasan dari sisi aksesibilitas, biaya, dan waktu. Oleh karena itu, diperlukan pendekatan alternatif yang efisien, terjangkau, dan mudah digunakan, terutama di daerah dengan fasilitas kesehatan terbatas.

Di sinilah peran teknologi kecerdasan buatan (Artificial Intelligence/AI), khususnya machine learning (ML), menjadi sangat relevan. ML memungkinkan pengembangan sistem deteksi awal berdasarkan data klinis sederhana yang mudah diperoleh, seperti: kadar glukosa, tekanan darah, indeks massa tubuh (BMI), usia, jumlah kehamilan, dan ketebalan kulit. Dengan melatih algoritma klasifikasi pada data ini, kita dapat membangun sistem prediktif yang dapat digunakan sebagai alat bantu untuk menilai risiko diabetes secara non-invasif dan hemat biaya. 

Dalam proyek ini, digunakan dataset Pima Indian Diabetes yang berisi catatan medis dari wanita keturunan Indian Pima di Amerika Serikat. Dataset ini telah banyak digunakan sebagai benchmark dalam penelitian klasifikasi diabetes karena karakteristiknya yang representatif dan kualitas data yang terstruktur. Proyek bertujuan untuk membangun sistem klasifikasi diabetes yang akurat dan dapat diinterpretasikan dengan baik melalui pembandingan lima algoritma klasifikasi machine learning, yaitu logistic regression, random forest, XGBoost, support vector machine, dan k-nearest model. Dengan mengevaluasi kelima model ini, proyek ini diharapkan dapat menghasilkan model terbaik yang akurat, stabil, dan dapat dijelaskan (interpretable) sehingga dapat berkontribusi pada peningkatan deteksi dini diabetes secara digital dan berkelanjutan.
## Business Understanding
### Problem Statements

Menjelaskan pernyataan masalah:
- Bagaimana cara mengidentifikasi individu yang berisiko terkena diabetes menggunakan data klinis sederhana tanpa prosedur medis invasif?
Banyak masyarakat yang tidak memiliki akses mudah ke pemeriksaan laboratorium atau belum menyadari pentingnya skrining dini terhadap diabetes.
- Model machine learning mana yang paling akurat dan andal untuk melakukan klasifikasi diabetes pada dataset Pima Indian Diabetes?
Diperlukan pembandingan antar model untuk mengetahui mana yang paling optimal dan generalisabel dalam klasifikasi risiko diabetes.
- Fitur klinis apa yang paling berkontribusi dalam klasifikasi risiko diabetes?
Pemahaman terhadap fitur penting dapat membantu penyuluhan dan pencegahan dini yang lebih terarah.

### Goals

Menjelaskan tujuan proyek yang menjawab pernyataan masalah:
- Mengembangkan sistem klasifikasi berbasis machine learning untuk mendeteksi risiko diabetes hanya berdasarkan parameter klinis seperti glukosa darah, BMI, tekanan darah, dan lainnya.
- Membandingkan lima algoritma klasifikasi yaitu Logistic Regression, Random Forest, XGBoost, SVM, dan KNN untuk menentukan model dengan performa terbaik berdasarkan metrik evaluasi (akurasi, precision, recall, F1-score).
- Mengidentifikasi fitur-fitur klinis yang paling berpengaruh dalam diagnosis diabetes melalui teknik interpretasi model (seperti feature importance dari Random Forest/XGBoost atau koefisien pada Logistic Regression).

### Solution Approach
1. Penerapan dan pembandingan lima algoritma klasifikasi. Solusi pertama adalah menerapkan lima algoritma machine learning populer dan membandingkan performanya berdasarkan metrik evaluasi yang relevan. Algoritma yang digunakan meliputi:
    - Logistic Regression
    - Random Forest
    - XGBoost
    - Support Vector Machine (SVM)
    - K-Nearest Neighbors (KNN)
      
    Tujuan dari pendekatan ini adalah mengevaluasi keandalan masing-masing model dalam mengklasifikasikan individu sebagai positif atau negatif diabetes. Model yang             menghasilkan performa terbaik berdasarkan metrik:
    - Akurasi adalah persentase klasifikasi yang benar dari seluruh prediksi.
    - Precision adalah seberapa akurat prediksi positif model.
    - Recall adalah kemampuan model dalam menemukan seluruh kasus positif.
    - F1-score adalah harmonik dari precision dan recall, cocok saat data tidak seimbang.
      
    Dengan membandingkan hasil dari kelima model, kita dapat mengidentifikasi pendekatan yang paling efektif dan dapat dipercaya untuk diterapkan secara nyata.
2. Peningkatan model melalui hyperparameter tuning dan cross-validation. Solusi kedua adalah melakukan penyetelan hyperparameter (hyperparameter tuning) dan cross-validation pada model-model terbaik dari solusi pertama untuk meningkatkan performa dan menghindari overfitting. Langkah-langkah utama dalam solusi ini meliputi:
    - Menggunakan teknik Grid Search atau Randomized Search untuk menemukan kombinasi hyperparameter optimal.
    - Menerapkan k-Fold Cross-Validation (misal 5-Fold) untuk menguji stabilitas model pada data yang berbeda dan memperkirakan generalisasi model.
    - Mengukur dan membandingkan ulang hasil dengan metrik yang sama: accuracy, precision, recall, dan F1-score.
      
    Tujuannya adalah memastikan model tidak hanya unggul pada data pelatihan, namun juga memiliki generalizability yang tinggi saat digunakan pada data nyata yang belum pernah dilihat sebelumnya.
## Data Understanding
Dataset yang digunakan dalam proyek ini adalah Pima Indians Diabetes Database, yang merupakan dataset medis populer untuk klasifikasi kondisi diabetes. Dataset ini diperoleh dari Kaggle dan dapat diakses melalui tautan berikut: 

https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database 

Dataset ini berisi 768 data observasi yang merepresentasikan pasien perempuan keturunan Pima Indian berusia di atas 21 tahun. Tujuan dari dataset ini adalah untuk memprediksi apakah seorang pasien mengidap diabetes atau tidak berdasarkan sejumlah fitur medis yang diperoleh dari pemeriksaan klinis. Dataset memiliki sebanyak 768 baris dengan 8 fitur prediktor dan 1 fitur target. file dalam format csv. Pada dataset, terdapat beberapa fitur yang memiliki nilai 0 yang tidak realistis dan dianggap sebagai missing value (contoh: Glucose, BMI, Insulin). Untuk variabel target, berisi angka nol dan satu, di mana nol adalah orang yang tidak terkena diabetes dan satu adalah orang yang terkena diabetes. Berikut adalah penjelasan mengenai masing masing variabelnya:
| **Fitur**                  | **Tipe Data**  | **Deskripsi**                                                                 |
| -------------------------- | -------------- | ----------------------------------------------------------------------------- |
| `Pregnancies`              | Numerik        | Jumlah kehamilan yang pernah dialami pasien                                   |
| `Glucose`                  | Numerik        | Kadar glukosa plasma dalam tes 2 jam oral glucose tolerance (mg/dL)           |
| `BloodPressure`            | Numerik        | Tekanan darah diastolik (mm Hg)                                               |
| `SkinThickness`            | Numerik        | Ketebalan lipatan kulit trisep (mm)                                           |
| `Insulin`                  | Numerik        | Kadar insulin serum 2 jam (mu U/ml)                                           |
| `BMI`                      | Numerik        | Indeks massa tubuh (kg/m²), menghitung rasio berat badan dan tinggi badan     |
| `DiabetesPedigreeFunction` | Numerik        | Fungsi silsilah diabetes, menunjukkan kemungkinan genetik berdasarkan riwayat |
| `Age`                      | Numerik        | Usia pasien (dalam tahun)                                                     |
| `Outcome`                  | Kategori (0/1) | Label target: 1 jika menderita diabetes, 0 jika tidak                         |

Berikut adalah distribusi untuk variabel target:

![image](https://github.com/user-attachments/assets/740066bb-2c6c-46b1-a26e-fcb2156b3d0e)

Dapat dilihat dari grafik bahwa dataset tidak seimbang (imbalanced), karena jumlah data pada kelas nol jauh lebih banyak dibanding kelas satu. Artinya, ada ketimpangan kelas (imbalanced dataset), meskipun belum ekstrem. Sehingga tidak perlu diberlakukan oversampling. Selanjutnya berikut hubungan antar variabel dalam bentuk heatmap:

![image](https://github.com/user-attachments/assets/40314dc0-5da0-487c-af0d-16f5903b8e91)

Berikut adalah penjelasannya:

| Fitur                        | Korelasi terhadap `Outcome` | Interpretasi                                     |
| ---------------------------- | --------------------------- | ------------------------------------------------ |
| **Glucose**                  | **0.47**                    | Paling berkorelasi; kadar gula tinggi → diabetes |
| **BMI**                      | 0.29                        | Korelasi sedang; berat badan tinggi → berisiko   |
| **Age**                      | 0.24                        | Orang lebih tua lebih berisiko                   |
| **Pregnancies**              | 0.22                        | Semakin banyak kehamilan, risiko meningkat       |
| **Insulin**                  | 0.13                        | Korelasi lemah                                   |
| **BloodPressure**            | 0.065                       | Sangat lemah                                     |
| **SkinThickness**            | 0.075                       | Lemah                                            |
| **DiabetesPedigreeFunction** | 0.17                        | Keturunan juga berpengaruh sedikit               |

Sehingga fitur yang paling penting untuk prediksi diabetes secara linier adalah:
- Glucose
- BMI
- Age
- Pregnancies
  
Untuk keseluruhan:
- Fitur Glucose adalah indikator paling kuat untuk memprediksi diabetes.
- BMI, Age, dan Jumlah Kehamilan juga relevan.
- Korelasi antar fitur cukup rendah, artinya semua fitur bisa tetap dipertahankan.
- Korelasi ini membantu saat ingin memilih fitur penting untuk feature selection atau model interpretability.

Dataset memiliki nilai nol atau dapat disebut data yang tidak valid, yaitu:
- Glucose memiliki 5 nilai nol.
- BloodPressure memiliki 35 nilai nol.
- SkinThickness memiliki 227 nilai nol.
- Insulin memiliki 374 nilai nol.
- BMI memiliki 11 nilai nol.

Yang terakhir adalah distribusi setiap fitur, dapat dilihat dari gambar berikut:

![image](https://github.com/user-attachments/assets/384feb0b-b141-4e68-b2b0-c5d245424cf4)

Berikut adalah penjelasannya:

| Fitur                        | Distribusi                     | Interpretasi                                                             |
| ---------------------------- | ------------------------------ | ------------------------------------------------------------------------ |
| **Pregnancies**              | Positively skewed              | Mayoritas pasien memiliki sedikit kehamilan; nilai tinggi jarang.        |
| **Glucose**                  | Hampir normal, sedikit skew    | Sebagian besar pasien memiliki kadar gula 80–150, outlier >180 ada.      |
| **BloodPressure**            | Mendekati normal               | Terdistribusi simetris, dengan rata-rata sekitar 70–80.                  |
| **SkinThickness**            | Positively skewed, zero peak   | Banyak nilai nol atau rendah → kemungkinan ada missing value disamarkan. |
| **Insulin**                  | Sangat skewed ke kanan (right) | Banyak nol → indikasi data kosong atau tidak diukur. Outlier tinggi.     |
| **BMI**                      | Hampir normal                  | Rata-rata BMI sekitar 30–35. Distribusi cukup sehat.                     |
| **DiabetesPedigreeFunction** | Skewed kanan                   | Mayoritas bernilai kecil; beberapa kasus dengan risiko keturunan tinggi. |
| **Age**                      | Skewed kanan                   | Mayoritas pasien muda hingga usia pertengahan; sedikit pasien lansia.    |
| **Outcome**                  | Kategori biner (0 atau 1)      | Tidak seimbang → kelas 0 (tidak diabetes) lebih banyak dari kelas 1.     |

Sehingga dapat disimpulkan:
- Distribusi bervariasi: tidak semua normal, beberapa sangat miring.
- Beberapa fitur mengandung nilai nol tidak wajar, indikasi data tidak lengkap.
- Skewness signifikan pada Insulin, Age, Pregnancies, Pedigree.
- Normalisasi dan imputasi sangat penting untuk persiapan data.
- Perlu penanganan outlier sebelum pemodelan.
## Data Preparation
Pada tahap ini dilakukan serangkaian proses pembersihan dan penyesuaian data sebelum digunakan dalam pelatihan model machine learning. Tujuannya adalah untuk memastikan bahwa data bersih, bebas dari inkonsistensi, dan berada dalam format yang sesuai untuk digunakan oleh berbagai algoritma klasifikasi. Teknik-teknik yang diterapkan dijelaskan secara terurut di bawah ini:
- Penanganan nilai tidak logis. Berdasarkan pemahaman domain medis, terdapat beberapa fitur dalam dataset yang tidak mungkin memiliki nilai nol secara biologis. Nilai nol pada fitur-fitur seperti Glucose, BloodPressure, SkinThickness, Insulin, dan BMI diindikasikan sebagai data hilang atau tidak tercatat. Oleh karena itu, nilai nol pada fitur-fitur tersebut digantikan dengan nilai NaN (Not a Number) untuk selanjutnya diproses.
- Imputasi data yang hilang. Setelah nilai nol dikonversi menjadi NaN, data yang hilang diimputasi menggunakan nilai median dari masing-masing kolom. Penggunaan median bertujuan untuk mengurangi pengaruh nilai pencilan (outlier) yang umum ditemukan pada data medis.
- Pemisahan fitur dan target. Seluruh fitur prediktor (X) dipisahkan dari target label (y), di mana kolom Outcome sebagai target menunjukkan apakah seorang pasien positif atau negatif diabetes.
- Pembagian data training dan testing. Dataset dibagi menjadi dua subset, yaitu data training sebesar 80% dan data testing sebesar 20%. Tujuannya adalah untuk membangun model menggunakan data training dan mengevaluasi performanya menggunakan data testing yang belum pernah dilihat sebelumnya oleh model.
- Normalisasi data, normalisasi dilakukan menggunakan teknik StandardScaler dari pustaka sklearn. Proses ini bertujuan untuk menstandardisasi skala fitur sehingga setiap fitur memiliki rata-rata nol dan deviasi standar satu. Ini sangat penting untuk algoritma seperti K-Nearest Neighbors, Support Vector Machine, dan Logistic Regression yang sensitif terhadap skala data.

Alasan dan manfaat dari tahapan preparation. Setiap tahapan yang diterapkan memiliki alasan yang kuat berdasarkan praktik terbaik machine learning:
- Penanganan nilai tidak logis untuk menghindari bias akibat nilai yang tidak mungkin secara biologis.
- Imputasi data hilang untuk menjaga konsistensi ukuran dataset dan mengurangi kehilangan informasi.
- Pemisahan fitur dan target untuk menyiapkan data sesuai dengan struktur supervised learning.
- Pembagian data untuk mencegah overfitting dan memungkinkan evaluasi yang objektif.
- Normalisasi untuk meningkatkan kinerja dan stabilitas algoritma, terutama yang berbasis jarak.
## Modeling
Dalam proyek ini, dilakukan pemodelan machine learning untuk menyelesaikan permasalahan klasifikasi risiko diabetes menggunakan lima algoritma yang berbeda. Tujuannya adalah membandingkan performa masing-masing model setelah proses pelatihan dan tuning. Setiap algoritma diinisialisasi dan dilatih menggunakan data latih. Berikut adalah lima algoritma yang digunakan dalam proses pemodelan beserta penjelasan cara kerjanya:
- Logistic Regression:
    1. **Linear Combination**:
       Model menghitung kombinasi linear dari fitur:
       z = β₀ + β₁x₁ + β₂x₂ + ... + βₙxₙ
       di mana:
       - xᵢ adalah fitur (fitur ke-i).
       - βᵢ adalah bobot atau koefisien yang dikalikan dengan fitur xᵢ.
    2. **Fungsi Aktivasi (Sigmoid)**:
       Output linear z dimasukkan ke fungsi sigmoid untuk mengubahnya menjadi probabilitas:
       P(y=1|x) = 1 / (1 + e⁻ᶻ)
    3. **Fungsi Kerugian (Log Loss)**:
       Model menggunakan fungsi log loss:
       Loss = −[y log(p) + (1−y) log(1−p)]
    4. **Optimasi Koefisien**:
       Menggunakan gradient descent atau solvers lain (misalnya, liblinear). Tujuannya untuk meminimalkan log loss.
    5. **Prediksi**:
       - Probabilitas > 0.5 → kelas 1
       - Probabilitas ≤ 0.5 → kelas 0
- Random Forest Classifier
    1. Bootstrap Sampling:
       Buat banyak subset data acak (dengan pengembalian) dari data training.
    2. Pembangunan Decision Trees:
       - Setiap subset digunakan untuk melatih 1 pohon keputusan.
       - Saat pemilihan fitur di tiap node, hanya sebagian kecil fitur yang dipertimbangkan (feature bagging).
    3. Split Node:
       Setiap node memutuskan split terbaik berdasarkan metrik seperti Gini impurity atau entropy.
    4. Voting:
       Untuk klasifikasi: setiap pohon memberikan satu suara → kelas dengan mayoritas suara dipilih.
    5. Output Final:
       Gabungan hasil dari seluruh pohon → klasifikasi akhir.
- XGBoost Classifier
    1. Model Awal:
       Prediksi awal biasanya konstan (misalnya rata-rata label).
    2. Hitung Residual/Error:
       Error dihitung antara label aktual dan prediksi.
    3. Bangun Pohon Baru:
       - Pohon baru dilatih untuk memprediksi error (gradien loss).
       - Gunakan pendekatan gradient descent untuk memperbaiki kesalahan sebelumnya.
    4. Update Model:
       - Model diperbarui dengan menambahkan prediksi pohon baru dengan bobot tertentu.
       - Prediksi akhir:
         ŷᵗ = ŷᵗ⁻¹ + η·fₜ(x)
         di mana η adalah learning rate, dan fₜ(x) adalah pohon ke-t.
    5. Regularisasi:
       Diterapkan untuk menghindari overfitting, termasuk penalti terhadap jumlah leaf dan besarnya output leaf.
    6. Berhenti Jika Konvergen:
       Bisa menggunakan early stopping berdasarkan validasi.
- Support Vector Machine (SVM)
    1. Mencari Hyperplane:
       Model mencari garis (2D), bidang (3D), atau hyperplane (n-D) yang memisahkan kelas secara maksimal.
    2. Maximize Margin:
       - Margin = jarak antara hyperplane ke titik data terdekat dari masing-masing kelas.
       - Titik terdekat ini disebut support vectors.
    3. Optimization Problem:
       min₍w, b₎ ½‖w‖² dengan syarat yᵢ(w ⋅ xᵢ + b) ≥ 1
    4. Jika Data Tidak Linear:
       Gunakan kernel trick untuk memetakan data ke ruang berdimensi lebih tinggi:
       - Linear
       - RBF (Gaussian)
       - Polynomial
       - Sigmoid
    5. Regularisasi (C):
       Parameter C mengontrol trade-off antara margin maksimum dan kesalahan klasifikasi.
- K-Nearest Neighbors (KNN)
    1. Membaca Nilai K:
       Misalnya K = 3 berarti 3 tetangga terdekat akan dipertimbangkan.
    2. Hitung Jarak:
       Gunakan metrik seperti:
       - Euclidean distance:
         d = √(∑ᵢ (xᵢ − xᵢ′)²)
       - Manhattan distance
       - Minkowski distance
    3. Ambil K Terdekat:
       Urutkan semua data berdasarkan jarak ke titik uji → ambil K data terdekat.
    4. Voting:
       Mayoritas label dari tetangga digunakan sebagai prediksi.
    5. Untuk Regresi:
       Prediksi = rata-rata nilai dari K tetangga.
       
Untuk meningkatkan performa masing-masing model, dilakukan GridSearchCV untuk mencari kombinasi parameter terbaik pada setiap model:
- Parameter Logistic Regression adalah "C=1, solver='liblinear'". "C=1" artinya inverse dari regularisasi (C = 1/λ). Nilai kecil artinya regularisasi kuat (menghindari overfitting). C=1 artinya regularisasi moderat. "solver='liblinear'" artinya optimizer yang digunakan untuk mencari parameter terbaik. "liblinear" cocok untuk dataset kecil dan binary classification.
- Parameter Random Forest adalah "n_estimators=100, max_depth=None, min_samples_split=2, random_state=42". "n_estimators=100" artinya jumlah pohon dalam hutan (semakin banyak maka akurasi naik, tapi waktu komputasi naik). "max_depth=None" artinya kedalaman pohon tidak dibatasi maka pohon bisa tumbuh sampai overfit. "min_samples_split=2" artinya minimum sampel untuk membagi node. Nilai kecil maka pohon bisa tumbuh lebih dalam. "random_state=42" artinya untuk hasil acak yang bisa direproduksi (reproducibility).
- Parameter XGBoost adalah "learning_rate=0.1, max_depth=3, n_estimators=50, subsample=1.0, use_label_encoder=False, eval_metric='logloss', random_state=42". "learning_rate=0.1" artinya ukuran langkah dalam boosting. Nilai kecil maka pelatihan lebih lambat tapi bisa lebih akurat. "max_depth=3" artinya maksimal kedalaman setiap pohon. Semakin besar maka model lebih kompleks. "n_estimators=50" artinya jumlah boosting rounds (jumlah pohon). "subsample=1.0" artinya persentase sampel data yang digunakan tiap pohon. 1.0 berarti semua data. "use_label_encoder=False" artinya tidak menggunakan encoder label bawaan (rekomendasi baru). "eval_metric='logloss'" artinya metrik evaluasi yang digunakan selama training. "random_state=42" agar hasilnya bisa diulang.
- Parameter SVM adalah "C=1, gamma='scale', kernel='linear', probability=True, random_state=42". "C=1" artinya regularisasi. Nilai kecil maka margin lebih lebar (lebih general), nilai besar maka mencoba mengklasifikasikan semua data dengan benar. "gamma='scale'" artinya parameter untuk kernel RBF/polinomial. "scale" otomatis menyesuaikan berdasarkan jumlah fitur. "kernel='linear'" artinya menggunakan kernel linier (cocok untuk data linear separable). "probability=True" artinya menghitung probabilitas prediksi (menambah beban komputasi). "random_state=42" untuk hasil acak yang konsisten.
- Parameter KNN adalah "n_neighbors=7, weights='uniform', metric='manhattan'". "n_neighbors=7" artinya jumlah tetangga terdekat yang digunakan untuk menentukan kelas. "weights='uniform'" artinya semua tetangga diberi bobot yang sama. "metric='manhattan'" menggunakan jarak Manhattan (L1), cocok jika fitur punya skala yang mirip atau sudah dinormalisasi.

Proses ini dilakukan menggunakan 5-fold cross-validation untuk menjamin stabilitas hasil tuning. Model-model dilatih ulang menggunakan parameter hasil tuning dan digunakan untuk membuat prediksi pada data uji.

Kelebihan dan kekurangan dari masing-masing algoritma, yaitu:
| Algoritma               | Kelebihan                                                         | Kekurangan                                                         |
| ----------------------- | ----------------------------------------------------------------- | ------------------------------------------------------------------ |
| **Logistic Regression** | Sederhana, interpretatif, cepat                                   | Kurang akurat untuk hubungan non-linear                            |
| **Random Forest**       | Tahan terhadap overfitting, fleksibel                             | Relatif lambat dalam prediksi, kurang interpretatif                |
| **XGBoost**             | Performa tinggi, efisien, menangani missing value secara internal | Kompleksitas tinggi, tuning memerlukan waktu dan sumber daya       |
| **SVM**                 | Efektif pada dimensi tinggi dan margin yang jelas                 | Tidak efisien untuk data besar, sensitif terhadap pemilihan kernel |
| **KNN**                 | Konsep sederhana dan mudah diimplementasikan                      | Waktu prediksi lambat, dipengaruhi jumlah fitur dan skala data     |

## Evaluation
Dalam proyek klasifikasi ini, metrik evaluasi yang digunakan untuk mengukur performa model adalah sebagai berikut:
- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

Metrik-metrik ini dipilih karena sesuai dengan konteks data dan permasalahan klasifikasi kesehatan yang berpotensi berdampak serius jika salah klasifikasi. Dalam kasus ini, kesalahan dalam mengklasifikasikan pasien diabetes (false negative) lebih berisiko daripada false positive. Oleh karena itu, Recall dan F1-Score menjadi metrik yang sangat penting.

Penjelasan metrik evaluasi:

a. Accuracy

Mengukur proporsi prediksi yang benar terhadap keseluruhan prediksi.

Accuracy = (TP + TN)/(TP + TN + FP + FN)

- Kelebihannya adalah mudah dipahami, cocok digunakan jika distribusi kelas seimbang.
- Kekurangannya adalahTidak cukup informatif jika data tidak seimbang (seperti pada kasus ini).

b. Precision

Mengukur seberapa tepat model dalam memprediksi kelas positif (yaitu penderita diabetes).

Precision = TP/(TP + FP)

Precision untuk menghindari false positive, misalnya untuk mengurangi diagnosis palsu.

c. Recall (Sensitivity)

Mengukur seberapa banyak data kelas positif yang berhasil ditangkap oleh model.

Recall = TP/(TP + FN)

Sangat penting dalam konteks medis, karena kita ingin meminimalkan false negative (tidak salah mengklasifikasikan penderita sebagai sehat).

d. F1-Score

Merupakan rata-rata harmonis dari Precision dan Recall.

F1-Score = 2 ( (Precision) (Recall)/(Precision) + (Recall) )

Cocok untuk data tidak seimbang, karena F1-score memberikan keseimbangan antara Precision dan Recall. F1-Score menggabungkan dua aspek penting, yaitu ketepatan dan kelengkapan.

e. Confusion Matrix

Menampilkan jumlah prediksi benar dan salah berdasarkan kelas aktual dan prediksi. Matriks ini membantu melihat distribusi kesalahan model.


Model: Logistic Regression
Classification Report:

                   precision    recall  f1-score   support

               0       0.80      0.83      0.81        99
               1       0.67      0.62      0.64        55

        accuracy                           0.75       154
       macro avg       0.73      0.72      0.73       154
    weighted avg       0.75      0.75      0.75       154

Model: Random Forest
Classification Report:

                  precision    recall  f1-score   support

               0       0.80      0.79      0.79        99
               1       0.62      0.64      0.63        55
    
        accuracy                           0.73       154
       macro avg       0.71      0.71      0.71       154
    weighted avg       0.73      0.73      0.73       154

Model: XGBoost
Classification Report:

                  precision    recall  f1-score   support

               0       0.80      0.81      0.80        99
               1       0.65      0.64      0.64        55

        accuracy                           0.75       154
       macro avg       0.72      0.72      0.72       154
    weighted avg       0.75      0.75      0.75       154

Model: SVM
Classification Report:

                  precision    recall  f1-score   support

               0       0.80      0.83      0.81        99
               1       0.67      0.62      0.64        55

        accuracy                           0.75       154
       macro avg       0.73      0.72      0.73       154
    weighted avg       0.75      0.75      0.75       154

Model: KNN
Classification Report:

                  precision    recall  f1-score   support
    
               0       0.80      0.77      0.78        99
               1       0.61      0.65      0.63        55

        accuracy                           0.73       154
       macro avg       0.71      0.71      0.71       154
    weighted avg       0.73      0.73      0.73       154

Evaluasi dilakukan pada semua model setelah proses pelatihan dan tuning parameter. Berdasarkan hasil evaluasi menggunakan metrik di atas, didapatkan bahwa:
- Model XGBoost memberikan performa yang paling seimbang antara Precision dan Recall.
- Model SVM dan KNN memiliki keunggulan pada precision, tetapi cenderung lebih rendah recall-nya.
- Model Logistic Regression cukup stabil tetapi kurang baik menangkap kasus positif.
- Random Forest memiliki hasil yang kompetitif tetapi sedikit kalah dalam recall dibanding XGBoost.

Kesimpulan:
1. Penelitian ini menunjukkan bahwa individu yang berisiko terkena diabetes dapat diidentifikasi secara cukup akurat hanya dengan data klinis sederhana seperti jumlah kehamilan, kadar glukosa, tekanan darah,        ketebalan kulit, kadar insulin, indeks massa tubuh (BMI), fungsi silsilah diabetes, dan usia—semuanya tanpa perlu prosedur medis invasif. Model machine learning mampu mengenali pola yang signifikan dari          fitur-fitur ini, sehingga skrining dini terhadap diabetes bisa dilakukan secara cepat dan murah, bahkan di komunitas yang aksesnya terbatas terhadap fasilitas laboratorium.
2. Berdasarkan hasil evaluasi pada dataset Pima Indian Diabetes, berikut adalah akurasi dan f1-score dari masing-masing model:
   
    | Model               | Accuracy | F1-score (class 1) |
    | ------------------- | -------- | ------------------ |
    | Logistic Regression | 0.75     | 0.64               |
    | Random Forest       | 0.73     | 0.63               |
    | XGBoost             | 0.75     | 0.64               |
    | SVM                 | 0.75     | 0.64               |
    | KNN                 | 0.73     | 0.63               |

   Logistic Regression, SVM, dan XGBoost tampil sebagai model dengan performa paling tinggi secara konsisten, dengan akurasi 75% dan f1-score untuk kelas positif (penderita diabetes) sebesar 0.64.
   Di antara ketiganya, Logistic Regression dan SVM juga memiliki nilai macro average dan weighted average f1-score tertinggi (0.73 dan 0.75), yang mengindikasikan kinerja yang lebih seimbang antar kelas.
   Maka, SVM bisa dianggap sebagai model yang paling optimal dan andal, karena:
    - Akurasi dan f1-score kompetitif
    - Lebih sederhana dan mudah diinterpretasikan
    - Lebih sedikit overfitting dibanding model kompleks seperti Random Forest atau XGBoost
3. Berdasarkan interpretasi model menggunakan koefisien Logistic Regression dan/atau feature importance dari Random Forest/XGBoost, fitur yang paling berkontribusi dalam klasifikasi risiko diabetes adalah:
    - Glukosa – kontribusi paling signifikan terhadap prediksi; makin tinggi, makin besar risiko.
    - BMI (Indeks Massa Tubuh) – faktor risiko utama karena berkaitan langsung dengan obesitas.
    - Age (Usia) – semakin tua, semakin tinggi risikonya.
    - Diabetes Pedigree Function – menunjukkan kemungkinan genetik terhadap diabetes.
    - Insulin – meski sulit diukur tanpa lab, secara model tetap berperan penting.

Temuan ini dapat digunakan untuk program penyuluhan dan pencegahan dini yang lebih terarah, terutama dengan menekankan gaya hidup sehat pada individu dengan glukosa dan BMI tinggi.
Berdasarkan kebutuhan konteks medis, Recall dan F1-Score menjadi prioritas utama untuk memastikan pasien yang memiliki diabetes tidak terlewat oleh model.
