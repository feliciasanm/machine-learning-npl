# Prediksi Kredit Macet Dengan ML - Classification

Hi, _repository_ ini memuat _**capstone project**_ yang kukerjakan untuk kelas **_Certified Junior Data Scientist_ Narasio Data** (Agustus 2021), yakni **membuat sistem penilaian kelayakan kredit secara otomatis** menggunakan _machine learning_ (ML). Eksplorasi data (EDA) dilakukan terlebih dahulu pada data yang diberikan, sebelum dibangun **model _imbalanced classifier_** untuk kredit macet **menggunakan _logistic regression_** dengan optimisasi pada metrik _recall_. 

**Berikut ini link untuk [PPT cantik hasil presentasi _capstone_](https://drive.google.com/file/d/1CEycnSlAkVkkShm51Tc06gymAR5kxxhN/view?usp=sharing) (sama dengan PDF _slide_ yang ada di _repository_!)** ❤️

## Problem
**Secara Bisnis**
- Bank A ingin melakukan **analisa pengajuan kredit pada data nasabahnya**, sehingga diberikan **data penggunaan kartu kredit nasabah serta indikator kredit macet (`flag_kredit_macet`)** untuk tujuan tersebut
- Diharapkan agar Bank A dapat **membangun sistem otomatis yang bisa memberikan rekomendasi** menerima atau menolak pengajuan kredit nasabah melalui **prediksi kredit macet (NPL)**
- Karena sifat kasusnya, maka Bank A akan **mengalami kerugian substantif** apabila model memprediksi nasabah tidak kredit macet, namun ternyata nasabah tersebut kredit macet di kemudian hari **(dengan kata lain, _false negative_)**

**Secara Teknis**
- Kita memiliki **masalah _classification_** (memprediksi label/kategori pada data baru berdasarkan hasil dari data _training_ yang telah diberikan)
- **Variabel yang perlu diprediksi** dalam masalah _classification_ ini adalah **variabel `flag_kredit_macet`**
- Dalam pembangunan model, **metrik _recall_ akan diberikan perhatian khusus** untuk mendapatkan prediksi yang meminimalisasi jumlah _false negative_

## Metode & Alat
**Ringkasan Metode:**
1. Dilakukan **EDA (_Exploratory Data Analysis_)** untuk mengulik faktor-faktor apa saja yang dapat memprediksi nasabah kredit macet (banyak kejutan menarik di sini!)
2. Setelah EDA, **_feature engineering_** dilakukan untuk memilih dan membuat variabel-variabel yang akan dipakai saat pembangunan model ML
3. Model **_logistic regression_** pertama dibangun sebagai _baseline_, dan ditemukan bahwa model memiliki akurasi tinggi namun _recall_ yang rendah karena **_imbalanced data_** (lebih banyak nasabah yang tidak kredit macet dibandingkan yang kredit macet, 91.2% vs 8.8%)
4. Teknik **_borderline_ SMOTE dan _undersampling_** dicampur untuk mengatasi tantangan _imbalanced class_ sebelum model kedua dibangun
5. Model kedua memiliki **nilai _recall_ yang jauh lebih baik**, dan dilakukan **_grid-search cross-validation_** untuk optimisasi model lebih lanjut
6. Setelah optimisasi tersebut, maka dilakukan **evaluasi** terhadap model _final_ yang dibuat diikuti dengan **prediksi pada data _test_**

**Alat dan Teknologi**: Eksplorasi data dan pembangunan model dilakukan dalam _Jupyter Notebook_ (tersedia dalam _repository_ ini) menggunakan bahasa Python, serta:
- **_Library_ standar analisis data**: `pandas`, `matplotlib`, `seaborn`
- **_Library_ seputar _machine learning_**: `sklearn` maupun `imblearn`
 
## Ruang Pengembangan
Model _logistic regression_ dipilih saat itu karena _interpretability_ jika diperlukan dan karena itu model yang dibahas saat kelas untuk _classification_, namun sebenarnya pada saat itu pun aku sudah _aware_ tentang **_tree-based models_** seperti **_random forest_ dan XGBoost**. Jadi, jika proyek ini dikerjakan ulang atau ditingkatkan masa depan, kemungkinan besar aku akan **mencoba _tree-based models_** sekalian barangkali hasilnya akan lebih bagus lagi 😁

## Kata Penutup
- **_Slide_ dan _notebook_ dalam _repository_ ini** telah dibuat dengan cantik, rapi, dan penuh catatan **sehingga mudah diikuti**, _go check it out!_
- **Mau proyek ML yang _feature engineering_ dan _modelling_ lebih _hardcore_ lagi dari ini? [_Check out_ proyek NLPku](https://github.com/feliciasanm/nlp-book-summary).**
