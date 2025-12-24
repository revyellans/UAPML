# 👤 Klasifikasi Gender Berdasarkan Nama  
**Perbandingan Machine Learning, Deep Learning, dan Pretrained Language Model**

---

## 📌 Deskripsi Proyek

Proyek ini bertujuan untuk membangun sistem **klasifikasi gender berdasarkan nama** menggunakan pendekatan **Natural Language Processing (NLP)**. Sistem diimplementasikan dalam bentuk **website interaktif berbasis Streamlit**, sehingga pengguna dapat memasukkan nama dan memperoleh hasil prediksi gender secara real-time.

Penelitian ini membandingkan beberapa pendekatan model, yaitu:
1. **Machine Learning klasik**
2. **Deep Learning non-pretrained (RNN)**
3. **Pretrained Language Model (BERT dan DistilBERT)**

Tujuan utama proyek ini adalah menganalisis performa, efisiensi, dan karakteristik masing-masing model dalam menangani data teks pendek berupa nama.

---

## 📂 Penjelasan Dataset dan Preprocessing

### 📊 Dataset
Dataset yang digunakan merupakan dataset supervised yang berisi:
- **Nama** (teks)
- **Label gender** (Laki-laki / Perempuan)

Dataset digunakan dalam proses pelatihan, validasi, dan evaluasi model.

### 🧹 Tahapan Preprocessing
Tahapan preprocessing yang dilakukan meliputi:
1. **Case folding**  
   Mengubah seluruh teks menjadi huruf kecil.
2. **Pembersihan teks**  
   Menghapus karakter non-alfabet dan simbol yang tidak relevan.
3. **Tokenisasi**
   - Machine Learning & RNN: tokenisasi menggunakan tokenizer Keras.
   - BERT & DistilBERT: tokenisasi menggunakan tokenizer bawaan HuggingFace.
4. **Padding dan Truncation**  
   Menyamakan panjang input agar sesuai dengan kebutuhan model.

---

## 🤖 Model yang Digunakan

### 1️⃣ Model Deep Learning Non-Pretrained (RNN)

Model ini dibangun menggunakan **Recurrent Neural Network (RNN)** dan dilatih dari awal tanpa bobot pretrained.

**Arsitektur:**
- Embedding Layer  
- Simple RNN Layer  
- Dense Layer  

**Kelebihan:**
- Mampu mempelajari pola urutan karakter dalam nama

**Kekurangan:**
- Membutuhkan data yang cukup
- Sensitif terhadap hyperparameter

---

### 2️⃣ Model Pretrained Language Model (BERT)

**BERT (Bidirectional Encoder Representations from Transformers)** merupakan model berbasis Transformer yang dilatih secara bidirectional sehingga mampu memahami konteks teks dari dua arah.

**Karakteristik:**
- Menggunakan tokenizer WordPiece
- Menghasilkan embedding kontekstual
- Dilakukan fine-tuning untuk klasifikasi dua kelas

**Kelebihan:**
- Akurasi sangat tinggi
- Generalisasi kuat

**Kekurangan:**
- Ukuran model besar
- Waktu inferensi lebih lambat

---

### 3️⃣ Model Pretrained Language Model (DistilBERT)

DistilBERT merupakan versi ringan dari BERT yang dikembangkan melalui teknik knowledge distillation.

**Karakteristik:**
- Model lebih kecil dan cepat
- Akurasi mendekati BERT
- Lebih efisien untuk deployment

---

## 📊 Perbandingan BERT dan DistilBERT

| Aspek | BERT | DistilBERT |
|------|------|------------|
| Ukuran Model | Besar | Lebih kecil |
| Kecepatan Inferensi | Lambat | Lebih cepat |
| Akurasi | Sangat tinggi | Tinggi |
| Efisiensi | Rendah | Tinggi |
| Deployment | Kurang optimal | Sangat optimal |

---

## 📈 Hasil Evaluasi dan Analisis Perbandingan

| Model | Akurasi | Analisis |
|------|--------|---------|
| Machine Learning | Rendah–Sedang | Cocok sebagai baseline |
| RNN | Sedang | Mampu menangkap pola urutan |
| BERT | Sangat Tinggi | Representasi teks terbaik |
| DistilBERT | Tinggi | Akurasi dan efisiensi seimbang |

**Kesimpulan:**  
DistilBERT dipilih untuk implementasi dashboard karena memberikan keseimbangan terbaik antara performa dan efisiensi komputasi.

---

## 🌐 Panduan Menjalankan Sistem Website Secara Lokal

### 🔧 1. Persiapan
Pastikan Python ≥ 3.10 telah terpasang.

Masuk ke direktori proyek:
```bash
cd uapml-DistillBert
