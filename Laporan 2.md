# Laporan Proyek Membuat Model Sistem Rekomendasi - Jannagata Tan Atmaja

## Project Overview
Minat baca merupakan salah satu aspek penting dalam pembangunan sumber daya manusia yang unggul dan berdaya saing. Di tengah era digital seperti saat ini, masyarakat dihadapkan pada lautan informasi dan pilihan bacaan yang sangat beragam. Hal ini justru menimbulkan tantangan baru, yaitu kesulitan dalam menemukan bacaan yang relevan, berkualitas, dan sesuai dengan preferensi masing-masing individu. Banyak pengguna, terutama pembaca pemula atau pengguna platform buku digital, merasa kewalahan dalam menentukan buku mana yang layak untuk dibaca. Oleh karena itu, dibutuhkan sistem yang dapat membantu pengguna menavigasi berbagai pilihan tersebut secara efisien dan personal.

Salah satu pendekatan teknologi yang dapat menjawab tantangan tersebut adalah pengembangan sistem rekomendasi. Sistem ini telah banyak digunakan oleh platform besar seperti Amazon, Goodreads, dan Google Books untuk memberikan rekomendasi bacaan berdasarkan perilaku pengguna. Sistem rekomendasi tidak hanya membantu pengguna menemukan buku yang sesuai dengan selera mereka, tetapi juga meningkatkan keterlibatan pengguna, memperpanjang waktu penggunaan aplikasi, dan secara tidak langsung mendorong peningkatan literasi. Dalam konteks institusi pendidikan, perpustakaan, dan toko buku daring, sistem rekomendasi juga dapat berperan sebagai alat bantu untuk mempromosikan buku-buku yang kurang dikenal namun relevan bagi pembaca tertentu.

Terdapat dua pendekatan utama dalam sistem rekomendasi, yaitu content-based filtering dan collaborative filtering. Content-based filtering memberikan rekomendasi berdasarkan kemiripan konten antar buku, seperti genre, penulis, atau kata-kata kunci pada deskripsi buku. Sementara itu, collaborative filtering menggunakan informasi interaksi antara pengguna dan buku, seperti rating, untuk menemukan pola dan preferensi yang tersembunyi. Kombinasi kedua pendekatan ini memungkinkan sistem rekomendasi untuk bekerja secara lebih akurat, terutama ketika data yang tersedia terbatas. Oleh karena itu, dalam proyek ini kedua metode tersebut digunakan untuk meningkatkan kualitas rekomendasi.

Menurut laporan Grand View Research (2022), pasar global sistem rekomendasi diperkirakan akan tumbuh secara signifikan dengan tingkat pertumbuhan tahunan (CAGR) sebesar 37,5% dari tahun 2022 hingga 2030. Angka ini menunjukkan bahwa sistem rekomendasi tidak hanya menjadi fitur tambahan, melainkan kebutuhan penting dalam berbagai sektor, termasuk edukasi dan literasi digital. Dengan semakin meluasnya digitalisasi layanan dan peningkatan jumlah pengguna platform daring, sistem rekomendasi akan menjadi alat vital untuk menyaring dan mempersonalisasi informasi secara efisien. Hal ini memperkuat urgensi untuk mengembangkan sistem rekomendasi buku yang efektif dan terjangkau, bahkan dalam skala kecil.

Melalui proyek ini, dikembangkan sistem rekomendasi buku berbasis content-based filtering dan collaborative filtering menggunakan dataset yang relatif kecil. Pendekatan ini relevan terutama bagi institusi atau platform yang belum memiliki data dalam jumlah besar namun tetap ingin memberikan pengalaman pengguna yang cerdas dan terpersonalisasi. Dengan membangun model rekomendasi yang ringan dan akurat, proyek ini diharapkan dapat menjadi prototipe sistem yang dapat diterapkan lebih luas, sekaligus mendukung inisiatif literasi di Indonesia secara digital dan berkelanjutan.
## Business Understanding
### Problem Statements
Di era digital dengan jutaan pilihan bacaan yang tersedia secara daring, pengguna sering kali mengalami kesulitan dalam menemukan buku yang sesuai dengan preferensi dan kebutuhan mereka. Permasalahan ini diperparah oleh kurangnya sistem rekomendasi yang dapat mempersonalisasi saran bacaan berdasarkan minat dan riwayat pengguna, terutama pada platform dengan skala data kecil atau menengah. Tanpa sistem yang cerdas dan adaptif, pengguna cenderung mengandalkan pencarian manual atau mengikuti tren umum, yang belum tentu mencerminkan kebutuhan atau minat mereka secara personal.

Selain itu, banyak platform edukasi atau perpustakaan digital di institusi pendidikan dan toko buku lokal belum menerapkan sistem rekomendasi karena keterbatasan sumber daya dan infrastruktur. Akibatnya, pengguna tidak mendapatkan pengalaman eksplorasi bacaan yang optimal, dan buku-buku yang relevan tetapi kurang populer menjadi sulit ditemukan. Permasalahan ini menghambat upaya untuk meningkatkan literasi, minat baca, dan keterlibatan pengguna dalam platform tersebut.

### Goals
Tujuan dari proyek ini adalah untuk mengembangkan sistem rekomendasi buku yang mampu memberikan saran bacaan yang relevan dan dipersonalisasi bagi setiap pengguna, dengan tetap mempertimbangkan keterbatasan ukuran dataset. Sistem yang dikembangkan diharapkan dapat:
- Memberikan rekomendasi buku berdasarkan preferensi pengguna secara otomatis dan efisien.
- Bekerja secara optimal meskipun data interaksi pengguna tidak terlalu besar.
- Diterapkan sebagai prototipe pada platform skala kecil atau institusi pendidikan.
- Mengintegrasikan dua pendekatan yang saling melengkapi untuk meningkatkan kualitas rekomendasi.
- Dengan tercapainya tujuan ini, sistem diharapkan mampu menjadi fondasi solusi literasi digital yang bersifat adaptif, personal, dan skalabel.

### Solution Approach
Untuk mencapai tujuan tersebut, proyek ini menggunakan dua pendekatan utama dalam sistem rekomendasi:

1. Content-Based Filtering
Pendekatan ini merekomendasikan buku kepada pengguna berdasarkan kemiripan konten dengan buku yang sebelumnya disukai. Informasi yang digunakan biasanya berupa fitur seperti judul, genre, atau deskripsi buku. Model menghitung kemiripan antar item dengan teknik seperti TF-IDF dan cosine similarity, lalu menyarankan buku yang paling mirip dengan preferensi pengguna. Pendekatan ini efektif dalam memberikan rekomendasi personal tanpa bergantung pada interaksi pengguna lain, sehingga cocok untuk mengatasi masalah cold start pada pengguna baru.

2. Collaborative Filtering (Matrix Factorization – SVD)
Collaborative filtering merekomendasikan buku berdasarkan pola interaksi antar pengguna. Teknik yang digunakan dalam proyek ini adalah Singular Value Decomposition (SVD) dari pustaka Surprise. Dengan menganalisis rating atau ulasan dari pengguna terhadap buku-buku tertentu, model dapat mengidentifikasi kesamaan preferensi antar pengguna dan memberikan saran berdasarkan perilaku pengguna serupa. Meskipun memerlukan cukup banyak data interaksi, pendekatan ini unggul dalam menemukan rekomendasi dari buku-buku yang sebelumnya belum pernah dilihat oleh pengguna.

Kedua pendekatan ini diuji dan dibandingkan untuk mengevaluasi keunggulan masing-masing, dengan harapan dapat menghasilkan sistem rekomendasi yang efektif dalam berbagai kondisi, baik pada data yang minim fitur maupun data yang minim interaksi pengguna.

## Data Understanding
Dataset yang digunakan dalam proyek sistem rekomendasi buku ini merupakan bagian dari Book Recommendation Dataset yang tersedia secara publik di platform Kaggle. Dataset ini terdiri dari beberapa file, namun proyek ini secara khusus memanfaatkan dua file utama, yaitu Books.csv dan Ratings.csv. Dataset ini dirancang untuk membangun sistem rekomendasi buku berbasis data eksplisit berupa rating yang diberikan oleh pengguna terhadap buku. Dataset tersebut dapat diakses melalui tautan berikut:

https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset 

Penjelasan mengenai data yang digunakan, yaitu:
1. File Books.csv memuat metadata deskriptif mengenai buku-buku yang tersedia dalam sistem. Total terdapat 271.360 baris data, di mana setiap baris mewakili satu entitas buku berdasarkan ISBN unik. Dataset ini      memiliki 8 fitur utama:

    | Fitur               | Tipe Data | Deskripsi                                           |
    | ------------------- | --------- | --------------------------------------------------- |
    | ISBN                | Object    | Nomor identifikasi buku yang unik secara global     |
    | Book-Title          | Object    | Judul buku                                          |
    | Book-Author         | Object    | Nama penulis buku                                   |
    | Year-Of-Publication | Object    | Tahun penerbitan, namun mengandung data tidak valid |
    | Publisher           | Object    | Nama penerbit buku                                  |
    | Image-URL-S         | Object    | URL gambar berukuran kecil                          |
    | Image-URL-M         | Object    | URL gambar berukuran sedang                         |
    | Image-URL-L         | Object    | URL gambar berukuran besar                          |

    Beberapa nilai pada kolom Year-Of-Publication ditemukan tidak valid, seperti berisi string 'DK Publishing Inc', 'Gallimard', atau nilai tahun yang ekstrem seperti 0 atau 9999. Hal ini menunjukkan perlunya        pembersihan data atau penghilangan kolom jika tidak relevan. Dalam proyek ini, fokus utama dari file ini adalah pada fitur Book-Title dan Book-Author, yang digunakan untuk membentuk representasi konten pada      pendekatan content-based filtering.

2. File Ratings.csv mencatat interaksi eksplisit antara pengguna dan buku dalam bentuk rating. Terdapat 1.149.780 baris data yang masing-masing mencerminkan satu aktivitas pemberian rating oleh pengguna             terhadap buku tertentu. Dataset ini memiliki 3 kolom:

    | Fitur       | Tipe Data | Deskripsi                                                  |
    | ----------- | --------- | ---------------------------------------------------------- |
    | User-ID     | Integer   | ID unik pengguna                                           |
    | ISBN        | Object    | ISBN buku yang diberi rating                               |
    | Book-Rating | Integer   | Nilai rating dari 0 hingga 10 yang diberikan oleh pengguna |

    Sebaran nilai rating menunjukkan bahwa sebagian besar rating bernilai 0, yang mengindikasikan tidak adanya rating eksplisit (kemungkinan besar merupakan interaksi implisit atau placeholder). Oleh karena itu,     dalam tahap data preparation, nilai rating bernilai 0 dihapus dan hanya rating eksplisit (1–10) yang dipertahankan untuk pendekatan collaborative filtering.

3. Exploratory Data Analysis (EDA)
   - Sebelum preprocessing:
     
     ![image](https://github.com/user-attachments/assets/1ed9bcd2-460c-42aa-8867-9a0ce120b0f7)

     Dari gambar di atas diketahui, jumlah rating dengan nilai 0 sangat tinggi, yaitu lebih dari 700.000. Ini menunjukkan bahwa mayoritas data rating diisi dengan angka 0, yang bukan penilaian sebenarnya,             melainkan kemungkinan pengguna tidak memberi rating sama sekali, sistem mencatat buku yang dibaca/tambah ke rak tanpa memberi nilai, atau placeholder untuk missing value. Jadi rating 0 harus dibuang              sebelum dipakai untuk pelatihan model rekomendasi, karena tidak memberi informasi preferensi pengguna.
   
     ![image](https://github.com/user-attachments/assets/a69831f1-1dbb-4ef1-bed9-bed9882aa3da)

     Dari gambar di atas diketahui buku-buku yang muncul di sini bukan hanya karena disukai atau dinilai tinggi, tapi mungkin hanya banyak dicatat tanpa ada penilaian nyata.

     ![image](https://github.com/user-attachments/assets/692b9f65-39a5-470c-b36e-b0c8d496443f)

     Dari gambar di atas diketahui bahwa:

     | Peringkat | Nama Penulis        | Jumlah Buku (estimasi visual) |
     | --------- | ------------------- | ----------------------------- |
     | 1         | Agatha Christie     | ±630 buku                     |
     | 2         | William Shakespeare | ±580 buku                     |
     | 3         | Stephen King        | ±530 buku                     |
     | 4         | Ann M. Martin       | ±430 buku                     |
     | 5         | Carolyn Keene       | ±370 buku                     |
     | 6         | Francine Pascal     | ±365 buku                     |
     | 7         | Isaac Asimov        | ±330 buku                     |
     | 8         | Nora Roberts        | ±315 buku                     |
     | 9         | Barbara Cartland    | ±310 buku                     |
     | 10        | Charles Dickens     | ±300 buku                     |

     Agatha Christie adalah penulis paling produktif dalam dataset ini, dengan lebih dari 600 buku terdaftar.

     Banyaknya jumlah buku dari penulis klasik seperti Shakespeare, Charles Dickens, dan Barbara Cartland bisa jadi karena:
        - Berbagai versi edisi/terjemahan masuk sebagai entri terpisah.
        - Buku-buku lama yang sudah menjadi domain publik dan banyak dicetak ulang.

    - Setelah preprocessing:
      
      ![image](https://github.com/user-attachments/assets/d2654617-473b-4be4-97f3-65ffdd9e9635)\
  
      Dari gambar di atas diketahui bahwa:

      | Rating | Jumlah Rating (Estimasi visual) | Catatan                                  |
      | ------ | ------------------------------- | ---------------------------------------- |
      | 1      | ±2.000                          | Sangat jarang digunakan                  |
      | 2      | ±3.000                          | Masih sangat sedikit                     |
      | 3      | ±6.000                          | Relatif jarang                           |
      | 4      | ±9.000                          | Mulai meningkat                          |
      | 5      | ±51.000                         | Cukup banyak, titik infleksi awal        |
      | 6      | ±37.000                         | Sedikit menurun                          |
      | 7      | ±76.000                         | Mulai tinggi                             |
      | 8      | **±104.000**                    | **Paling banyak diberikan**              |
      | 9      | ±68.000                         | Tinggi, tapi menurun                     |
      | 10     | ±78.000                         | Masih tinggi, pengguna cenderung positif |

      Hal-hal yang dapat dianalisis, yaitu:
      - Distribusi Positif: Terlihat jelas bahwa sebagian besar pengguna memberi rating yang cukup tinggi (7–10).
      - Puncaknya di 8: Nilai rating 8 adalah yang paling sering diberikan, menunjukkan banyak buku yang dianggap sangat bagus.
      - Distribusi Skewed (Condong ke Kanan): Artinya pengguna lebih suka memberikan rating tinggi dibandingkan rating rendah.
      - Rating rendah (1–4) sangat jarang: Bisa karena:
        - Buku yang dinilai buruk tidak dilanjutkan membaca, jadi tidak dirating.
        - Pengguna cenderung hanya menilai buku yang mereka sukai.
        - Bias umum: orang cenderung tidak memberikan kritik negatif.
        
      ![image](https://github.com/user-attachments/assets/9bd265de-f979-4148-9511-7285ec9fdee0)

      Dari gambar di atas diketahui bahwa:

      | Ranking | Judul Buku                                                       | Jumlah Rating (estimasi visual) |
      | ------- | ---------------------------------------------------------------- | ------------------------------- |
      | 1       | The Lovely Bones: A Novel                                        | ±700                            |
      | 2       | Wild Animus                                                      | ±600                            |
      | 3       | The Da Vinci Code                                                | ±500                            |
      | 4       | The Red Tent (Bestselling Backlist)                              | ±400                            |
      | 5       | Divine Secrets of the Ya-Ya Sisterhood: A Novel                  | ±350                            |
      | 6       | Harry Potter and the Sorcerer’s Stone (Harry Potter (Paperback)) | ±340                            |
      | 7       | The Secret Life of Bees                                          | ±320                            |
      | 8       | Where the Heart Is (Oprah’s Book Club (Paperback))               | ±310                            |
      | 9       | A Painted House                                                  | ±300                            |
      | 10      | Girl with a Pearl Earring                                        | ±300                            |
  
      Hal-hal yang dapat dianalisis, yaitu:
      - The Lovely Bones: A Novel menjadi buku dengan jumlah rating terbanyak, menggeser Wild Animus (yang sebelumnya di peringkat atas saat data masih mengandung rating 0).
      - Harry Potter mulai muncul dalam daftar setelah rating 0 dibuang, menunjukkan bahwa:
        - Banyak pembaca benar-benar memberi rating valid terhadap buku ini.
        - Namun mungkin banyak rating 0 sebelumnya yang menutupi posisi aslinya.
      - Buku-buku populer dan mainstream seperti The Da Vinci Code dan The Secret Life of Bees masih bertahan sebagai buku dengan rating tinggi.

## Data Preparation
Tahap data preparation merupakan langkah esensial sebelum membangun sistem rekomendasi, karena data mentah sering kali mengandung informasi yang tidak relevan, tidak konsisten, atau tidak dapat langsung digunakan oleh model. Dalam proyek ini, proses data preparation dilakukan secara sistematis melalui lima teknik utama yang diterapkan secara berurutan, dengan penjelasan dan alasan yang mendasarinya sebagai berikut:

1. Load dataset, langkah pertama yang dilakukan adalah membaca dua file utama dalam dataset, yaitu Books.csv dan Ratings.csv, menggunakan pustaka pandas dengan encoding 'latin-1'. Encoding ini dipilih untuk memastikan pembacaan karakter khusus pada metadata buku dapat dilakukan dengan benar tanpa error. Untuk membaca data ke dalam struktur dataframe merupakan dasar dari seluruh proses analisis dan modeling. Tanpa proses ini, data tidak dapat diakses atau dimanipulasi untuk keperluan sistem rekomendasi.
2. Rename kolom untuk konsistensi, setelah data berhasil dimuat, dilakukan perubahan nama kolom agar lebih ringkas dan konsisten dengan gaya penamaan Python. Kolom "ISBN" diubah menjadi "book_id", "Book-Title" menjadi "title", "Book-Author" menjadi "author", serta "User-ID" menjadi "user_id". Konsistensi penamaan sangat penting untuk mempermudah pengolahan data dan menghindari potensi kesalahan dalam tahap penggabungan dan pemanggilan kolom saat eksplorasi maupun modeling.
3. Filter data rating yang valid, pada file Ratings.csv, nilai rating yang bernilai 0 dihapus. Hal ini dikarenakan rating 0 menunjukkan bahwa pengguna tidak memberikan penilaian yang eksplisit terhadap suatu buku. Hanya rating dengan nilai 1 hingga 10 yang dipertahankan. Sistem rekomendasi berbasis collaborative filtering membutuhkan data preferensi eksplisit untuk dapat mengenali pola kesukaan pengguna. Rating nol tidak memberikan informasi yang berguna untuk proses ini dan dapat mengganggu akurasi model.
4. Menambahkan fitur ‘content’ untuk content-based filtering, untuk pendekatan content-based filtering, dilakukan penggabungan antara kolom title dan author ke dalam satu kolom baru bernama content. Kolom ini digunakan sebagai basis pembuatan vektor representasi teks menggunakan teknik TF-IDF (Term Frequency–Inverse Document Frequency). Kolom content memberikan informasi tekstual yang digunakan untuk menghitung kemiripan antar buku. Dengan membentuk representasi vektor dari data teks ini, sistem dapat merekomendasikan buku-buku yang serupa berdasarkan konten.
5. Menghapus entri dengan nilai kosong (missing values), sebelum data digunakan untuk membangun model content-based filtering, dilakukan pembersihan entri yang memiliki nilai kosong pada kolom title dan author. Hal ini dilakukan dengan perintah "books_small = books_small.dropna(subset=['title', 'author']).reset_index(drop=True)". Nilai kosong pada dua kolom ini dapat mengganggu proses pembentukan fitur content, karena fitur tersebut dibentuk dari gabungan nilai teks title dan author. Jika salah satu bernilai kosong (NaN), maka informasi konten menjadi tidak lengkap atau bahkan tidak valid. Penghapusan dilakukan secara selektif hanya pada entri yang tidak memiliki informasi penting ini, untuk menjaga kualitas data tanpa membuang informasi yang masih berguna. Proses ini juga diikuti dengan reset_index agar indeks DataFrame tetap rapi dan berurutan setelah entri dihapus.
6. Sampling data untuk efisiensi pemrosesan, untuk mempercepat proses pelatihan model dan eksplorasi awal, dilakukan penyamplingan terhadap data pengguna dan buku. Dataset asli memiliki jumlah interaksi dan entitas yang sangat besar, sehingga pemrosesan penuh akan membutuhkan sumber daya komputasi yang tinggi. Oleh karena itu, dilakukan pengambilan sampel sebanyak 500 pengguna unik secara acak menggunakan perintah "user_sample = ratings['user_id'].drop_duplicates().sample(500, random_state=42)", lalu difilter agar ratings_small hanya berisi interaksi dari pengguna yang disampling tersebut. Selanjutnya, diambil 1000 buku unik dari interaksi tersebut menggunakan "book_sample = ratings_small['book_id'].drop_duplicates().sample(1000, random_state=42)", lalu kembali disaring agar ratings_small hanya mencakup rating terhadap buku-buku tersebut. Terakhir, dataset metadata buku (books) juga difilter agar hanya mencakup buku-buku yang masih ada pada ratings_small, dengan perintah "books_small = books[books['book_id'].isin(ratings_small['book_id'].unique())]". Sampling ini bertujuan untuk menjaga efisiensi dan mempermudah eksperimen, tanpa mengorbankan representasi data yang relevan.
   
Dengan menerapkan keenam teknik di atas, data berhasil dibersihkan, diseleksi, disusun ulang, dan disiapkan untuk dua pendekatan sistem rekomendasi, yaitu content-based filtering dan collaborative filtering. Tahap ini berfungsi sebagai fondasi utama dalam memastikan bahwa model yang dibangun dapat bekerja dengan efisien dan menghasilkan rekomendasi yang relevan serta berkualitas.


# Modelling and Result
Sistem Rekomendasi untuk Menyelesaikan Permasalahan
Dalam era digital saat ini, pengguna sering kali kesulitan memilih buku yang sesuai dengan preferensi mereka karena banyaknya pilihan yang tersedia. Untuk mengatasi masalah ini, proyek ini membangun sistem rekomendasi buku yang dapat memberikan saran personal bagi pengguna. Dua pendekatan utama yang digunakan adalah:
- Content-Based Filtering, yang merekomendasikan buku serupa berdasarkan konten buku yang pernah disukai pengguna.
- Collaborative Filtering, khususnya menggunakan algoritma Singular Value Decomposition (SVD), yang merekomendasikan buku berdasarkan pola interaksi pengguna lain yang memiliki preferensi serupa.

Kedua pendekatan ini dirancang untuk saling melengkapi dan memberikan pengalaman rekomendasi yang relevan baik bagi pengguna baru maupun pengguna lama.

### Pendekatan 1: Content-Based Filtering
Pendekatan ini mengandalkan informasi konten dari buku, seperti judul dan penulis. Dalam implementasinya, digunakan metode TF-IDF (Term Frequency–Inverse Document Frequency) untuk merepresentasikan teks dari judul buku dan menghitung cosine similarity untuk menemukan kemiripan antar buku.

Buku Referensi (Acuan): Bare: On Women, Dancing, Sex, and Power

Penulis: Elisabeth Eaves

Top-5 Rekomendasi Content-Based Filtering:

| No | Judul Buku                    | Penulis                |
| -- | ----------------------------- | ---------------------- |
| 1  | Monoosook Valley              | Elisabeth Hyde         |
| 2  | Death Dancing Footman         | Ngaio Marsh            |
| 3  | Sex for Dummies               | Dr. Ruth K. Westheimer |
| 4  | Women with Men: Three Stories | Richard Ford           |
| 5  | The Gate to Women's Country   | Sheri S. Tepper        |

Pendekatan ini sangat efektif digunakan ketika sistem memiliki informasi tentang buku yang disukai pengguna, namun belum memiliki cukup data interaksi (cold-start user).

### Pendekatan 2: Collaborative Filtering (SVD)

Collaborative Filtering bekerja dengan menganalisis pola rating yang diberikan oleh pengguna terhadap berbagai buku. Dengan menggunakan algoritma Singular Value Decomposition (SVD), model mampu mengidentifikasi preferensi tersembunyi pengguna dan kesamaan antar pengguna atau item.

User ID Referensi: 253966
 
Top-5 Rekomendasi Collaborative Filtering (SVD):

| No | Judul Buku                     | Penulis             |
| -- | ------------------------------ | ------------------- |
| 1  | The Lovely Bones: A Novel      | Alice Sebold        |
| 2  | Into the Wild                  | Jon Krakauer        |
| 3  | The Bridges of Madison County  | Robert James Waller |
| 4  | The Great Gatsby               | F. Scott Fitzgerald |
| 5  | INVASION OF THE BODY SNATCHERS | Jack Finney         |

Model ini dapat memberikan rekomendasi personal meskipun tidak memperhatikan isi buku, melainkan berdasarkan pola rating dari pengguna dengan preferensi serupa.

### Perbandingan Pendekatan

| Aspek              | Content-Based Filtering                             | Collaborative Filtering (SVD)                              |
| ------------------ | --------------------------------------------------- | ---------------------------------------------------------- |
| Berdasarkan        | Fitur konten buku (judul, penulis)                  | Pola interaksi antar pengguna dan buku                     |
| Cocok untuk        | Pengguna baru dengan data buku yang disukai         | Pengguna aktif dengan banyak rating                        |
| Kelebihan          | Tidak perlu data dari pengguna lain                 | Sangat personal, memanfaatkan data historis pengguna lain  |
| Kelemahan          | Kurang variasi rekomendasi (buku serupa saja)       | Cold-start problem (tidak efektif untuk pengguna baru)     |
| Contoh Rekomendasi | Buku mirip dengan *Bare: On Women, Dancing, Sex...* | Buku populer di kalangan pengguna mirip dengan user 253966 |

Dengan menggabungkan Content-Based dan Collaborative Filtering, sistem rekomendasi buku menjadi lebih adaptif dalam menghadapi berbagai kondisi pengguna. Pendekatan hybrid ini memperkuat personalisasi rekomendasi sekaligus menangani keterbatasan masing-masing metode. Sistem seperti ini sangat bermanfaat untuk platform digital perpustakaan, toko buku online, atau aplikasi pembaca yang ingin meningkatkan keterlibatan pengguna.
## Evaluation
### Metrik Evaluasi yang Digunakan

Dalam proyek ini, dua jenis sistem rekomendasi dikembangkan, yaitu Content-Based Filtering dan Collaborative Filtering (SVD). Karena masing-masing pendekatan memiliki karakteristik yang berbeda, maka digunakan dua jenis metrik evaluasi yang sesuai dengan konteks masing-masing:

1. Precision@K dan Recall@K untuk Content-Based Filtering.

   Digunakan untuk mengevaluasi sejauh mana sistem mampu merekomendasikan item yang benar-benar relevan (yang disukai oleh pengguna).
   Precision@K mengukur proporsi item yang relevan di antara seluruh rekomendasi yang diberikan:
    - Precision@K = |Recommended ∩ Relevant| / |Recommended|
    
      atau
  
      Precision@K = (jumlah item relevan dalam top-K rekomendasi) / (jumlah total item yang direkomendasikan sampai K)
  
      Recall@K mengukur proporsi item yang relevan yang berhasil direkomendasikan dari seluruh item yang relevan:
    - Recall@K = |Recommended ∩ Relevant| / |Relevant|
  
      atau

      Recall@K = (jumlah item relevan dalam top-K rekomendasi) / (jumlah total item relevan)
  
      Metrik ini sesuai untuk skenario di mana kita ingin menilai kualitas rekomendasi Top-N, yaitu seberapa relevan hasil yang diberikan oleh sistem terhadap preferensi pengguna.

2. Root Mean Squared Error (RMSE) untuk Collaborative Filtering (SVD).
   
   RMSE digunakan untuk mengukur sejauh mana model dapat memprediksi rating pengguna terhadap item dengan akurasi tinggi. Formula RMSE:

   RMSE = √(∑(ri - r̂i)² / n)
   
   Keterangan:
   - ri adalah nilai rating aktual yang diberikan pengguna pada item ke-i,
   - r̂i adalah nilai rating prediksi yang diberikan sistem pada item ke-i,
   - n adalah jumlah total data (jumlah prediksi yang dihitung).

    Semakin rendah RMSE, semakin akurat prediksi model. Metrik ini sangat relevan pada model rating-based seperti SVD karena berfokus pada kesalahan prediksi kuantitatif.

### Hasil Evaluasi

1. Content-Based Filtering:
    - 📘 Buku acuan (random): In the Drink
    - ✍️ Penulis: Kate Christensen
    - 📚 Rekomendasi yang diberikan:
      - Human Croquet – Kate Atkinson
      - The Idea of Perfection – Kate Grenville
      - A Drink Before the War – Dennis Lehane
      - Isle of Dogs – Patricia Cornwell
      - Purity in Death – J.D. Robb
    - 📚 Buku yang disukai oleh user ID 125514: Kitchen, Bridget Jones: The Edge of Reason, In the Drink, Dying in the City of the Blues
    - 🔎 Evaluasi Top-N (N=5):
      - ✅ Precision@5: 0.00
      - ✅ Recall@5: 0.00
    - Interpretasinya adalah Sistem Content-Based Filtering belum berhasil merekomendasikan buku yang termasuk dalam daftar buku yang pernah disukai user ini. Hal ini bisa disebabkan oleh keterbatasan informasi        konten (judul dan penulis saja), atau minimnya kesamaan kosakata antar buku yang disukai dengan buku lainnya di dataset kecil ini.
2. Collaborative Filtering (SVD)
   - 👤 User ID acuan: 91886
   - 🤝 Rekomendasi:
     - The Lovely Bones: A Novel – Alice Sebold
     - The Bridges of Madison County – Robert James Waller
     - C Is for Corpse – Sue Grafton
     - The Toughest Indian in the World – Sherman Alexie
     - The Life and Death of King Richard the Second – William Shakespeare
    - 📏 RMSE model SVD: 1.7745
    - Interpretasinya adalah dengan RMSE sebesar 1.77, model memiliki tingkat kesalahan prediksi yang tergolong sedang. Artinya, meskipun rekomendasi yang diberikan cukup informatif, masih terdapat perbedaan           signifikan antara rating yang diprediksi dan rating aktual. Ini bisa disebabkan oleh data yang terbatas, sparsity tinggi, atau variasi preferensi pengguna yang sangat beragam.
### Kesimpulan Evaluasi
- Content-Based Filtering cocok untuk sistem dengan data pengguna terbatas dan fokus pada metadata buku (judul dan penulis), tetapi menunjukkan kelemahan dalam relevansi hasil rekomendasi (Precision dan Recall rendah).
- Collaborative Filtering (SVD) menunjukkan prediksi rating yang cukup baik secara kuantitatif (RMSE ~1.77), namun performa rekomendasi masih bisa ditingkatkan dengan data yang lebih lengkap dan representatif.

## Kesimpulan
Permasalahan utama yang diangkat dalam proyek ini adalah kesulitan pengguna dalam menemukan buku yang sesuai dengan preferensi mereka secara personal, terutama pada platform dengan data berskala kecil atau menengah yang tidak memiliki sistem rekomendasi adaptif. Melalui proyek ini, dua pendekatan sistem rekomendasi telah diimplementasikan dan dievaluasi: Content-Based Filtering dan Collaborative Filtering (SVD).

Hasil eksperimen menunjukkan bahwa:
- Content-Based Filtering, meskipun sederhana dan tidak bergantung pada riwayat pengguna lain, memiliki keterbatasan dalam kualitas rekomendasi ketika hanya mengandalkan informasi dasar seperti judul dan penulis. Evaluasi menggunakan metrik Precision@5 dan Recall@5 menghasilkan nilai 0, menandakan bahwa rekomendasi belum sepenuhnya sesuai dengan preferensi aktual pengguna.
- Collaborative Filtering menggunakan SVD mampu memprediksi rating pengguna terhadap buku yang belum pernah dibaca dengan cukup baik, ditunjukkan oleh nilai RMSE sebesar 1.77. Meskipun belum sempurna, model ini memberikan dasar yang kuat untuk personalisasi berdasarkan pola interaksi pengguna dalam dataset kecil.

Dengan demikian, proyek ini membuktikan bahwa bahkan dengan keterbatasan data dan sumber daya, sistem rekomendasi yang cerdas tetap dapat dikembangkan untuk meningkatkan pengalaman eksplorasi bacaan pengguna. Sistem ini dapat membantu:
- Pengguna menemukan buku-buku relevan yang tidak populer atau tidak sedang tren.
- Platform lokal seperti perpustakaan digital sekolah, universitas, atau toko buku kecil menyediakan saran bacaan yang dipersonalisasi tanpa infrastruktur yang kompleks.
- Mendorong minat baca dan meningkatkan keterlibatan pengguna terhadap platform literasi digital.

Proyek ini menunjukkan bahwa sistem rekomendasi bukan hanya milik platform besar, tetapi dapat diadaptasi untuk skala kecil dengan pendekatan yang tepat. Implementasi sistem ini diharapkan menjadi langkah awal menuju ekosistem literasi yang lebih inklusif, relevan, dan efisien bagi semua pengguna.
