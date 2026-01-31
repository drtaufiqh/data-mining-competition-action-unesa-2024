# Prediksi Kualitas Udara Menggunakan Gradient Boosting Classifier

## 🌍 Deskripsi Proyek

Proyek ini bertujuan untuk **memprediksi kategori kualitas udara** (`Safety` atau `Dangerous`) pada tingkat **kota per tahun** menggunakan **Gradient Boosting Classifier**.

Fokus utama proyek ini adalah menangani **data tidak seimbang (imbalanced data)** yang umum terjadi pada kasus lingkungan, serta membangun model klasifikasi yang **andal, interpretatif, dan siap digunakan sebagai dasar pengambilan kebijakan**.

Proyek ini dikembangkan dalam konteks akademik oleh tim **Double Layer – Politeknik Statistika STIS**.

---

## 🎯 Tujuan

1. Membangun model klasifikasi kualitas udara berbasis machine learning.
2. Menangani permasalahan **class imbalance** secara tepat.
3. Mengidentifikasi **faktor utama** yang berkontribusi terhadap kualitas udara.
4. Menyediakan model yang berpotensi diintegrasikan dengan **sistem pemantauan real-time**.

---

## 🧠 Metode Utama

### Algoritma

* **Gradient Boosting Classifier**

  * Efektif untuk klasifikasi
  * Robust terhadap overfitting
  * Fleksibel dalam hyperparameter
  * Cocok untuk data imbalance

### Hyperparameter Optimization

* Menggunakan **Optuna**
* Pendekatan **Bayesian Optimization (Tree-structured Parzen Estimator / TPE)**
* Hyperparameter yang dituning:

  * `n_estimators`
  * `learning_rate`
  * `max_depth`
  * `subsample`
  * `max_features`
  * `min_samples_split`
  * `min_samples_leaf`

---

## 📊 Dataset

* **Unit observasi**: Kota per tahun
* **Data training**: 25.999 observasi
* **Data testing**: 14.005 observasi
* **Target variabel**: `Air_quality_category`

  * `Safety`
  * `Dangerous`

### Contoh Fitur Utama

* Konsentrasi polutan:

  * `pm10_concentration`
  * `pm25_concentration`
  * `no2_concentration`
* Karakteristik lingkungan:

  * `population`
  * `number_of_stations`
  * `type_of_stations`
* Informasi spasial:

  * `latitude`
  * `longitude`
* Informasi wilayah:

  * `WHO_region`
  * `country_name`

---

## ⚙️ Pra-pemrosesan Data

* Penyesuaian format dan konsistensi data
* Penghapusan fitur yang tidak relevan
* **Imputasi missing value** menggunakan **missForest**
* **Encoding variabel kategorikal** menggunakan **Target Encoding**
* Deteksi dan analisis outlier

---

## 🔀 Pembagian Data

* **Training set**: 70%
* **Testing set**: 30% (stratified)
* **Validation frame** khusus untuk evaluasi:

  * 10% dari kelas `Safety`
  * 50% dari kelas `Dangerous`

Pendekatan ini digunakan untuk memastikan performa model tetap baik pada kelas minoritas.

---

## 📈 Evaluasi Model

### Metrik yang Digunakan

* Confusion Matrix
* Precision
* Recall
* F1-Score

### Hasil Utama (Validation Data)

* **F1-Score**: 0.98
* **False Negative Rate**: 2.59%

Model menunjukkan kemampuan yang sangat baik dalam mendeteksi kondisi udara berbahaya.

---

## 🔍 Feature Importance

Fitur paling berpengaruh dalam model:

1. `pm10_concentration`
2. `pm25_concentration`
3. `iso3`
4. `longitude`
5. `WHO_region`

Hasil ini konsisten dengan literatur bahwa **particulate matter (PM10 dan PM25)** merupakan indikator utama kualitas udara.

---

## 🧩 Manfaat & Implementasi

* **Pemantauan kualitas udara real-time** (integrasi IoT)
* **Dasar kebijakan lingkungan** berbasis data
* **Pencegahan dampak kesehatan** akibat polusi udara
* Sistem peringatan dini kualitas udara

---

## 👥 Tim

**Double Layer – Politeknik Statistika STIS**

* Muh Farhan
* Dutatama Rosewika Taufiq Hadihardaya

---

## 📜 Lisensi

Proyek ini digunakan untuk keperluan **Data Mining Competition ACTION UNESA 2024**.

---

> _"Data lingkungan yang baik menghasilkan kebijakan yang lebih bai
