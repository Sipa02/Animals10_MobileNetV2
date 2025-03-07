# Klasifikasi Gambar Hewan dengan MobileNetV2 dan Transfer Learning

## Deskripsi

*Notebook* ini mendemonstrasikan proses klasifikasi 10 jenis hewan menggunakan model MobileNetV2 yang sudah terlatih sebelumnya (*pre-trained*) dan teknik *transfer learning*. Dataset yang digunakan adalah Animals-10 yang diunduh dari Kaggle.

## Langkah-langkah

1. **Persiapan**:
   - Mengunduh dan menginstal Kaggle API.
   - Mengunduh dataset Animals-10 menggunakan Kaggle API.
   - Mengekstrak dataset dan memverifikasi isinya.
   - Menerjemahkan nama label kelas ke dalam Bahasa Inggris.
   - Membagi dataset menjadi set pelatihan, validasi, dan pengujian dengan rasio 80:10:10.
2. **Augmentasi Data**:
   - Menggunakan `ImageDataGenerator` untuk *rescaling* gambar.
3. **Transfer Learning**:
   - Memuat model MobileNetV2 yang sudah terlatih sebelumnya dengan bobot ImageNet.
   - Membekukan lapisan-lapisan model dasar agar tidak diperbarui selama pelatihan.
   - Menambahkan lapisan-lapisan klasifikasi baru di atas model dasar.
4. **Pelatihan**:
   - Mengompilasi model dengan *optimizer* Adam, *loss function* categorical cross-entropy, dan metrik akurasi.
   - Melatih model menggunakan data pelatihan dan validasi.
   - Menggunakan *callback* untuk menghentikan pelatihan jika akurasi mencapai 95%.
5. **Evaluasi**:
   - Mengevaluasi performa model pada data pengujian.
   - Menampilkan laporan klasifikasi yang berisi presisi, *recall*, F1-score, dan akurasi.
6. **Penyimpanan dan Konversi**:
   - Menyimpan model dalam format SavedModel dan TensorFlow Lite.
   - Menyimpan label kelas ke dalam file `labels.txt`.
   - Mengonversi model ke format TensorFlow.js.

## Dependensi

- TensorFlow 2.18.0
- TensorFlow Datasets
- Keras
- Matplotlib
- NumPy
- Pillow
- Scikit-learn
- Kaggle

## Cara Menjalankan

1. Unggah *notebook* ini ke Google Colab.
2. Pastikan Anda telah mengunggah file `kaggle.json` yang berisi kredensial Kaggle Anda.
3. Jalankan semua sel kode secara berurutan.

## Hasil

Model yang dilatih mencapai akurasi yang tinggi pada data pengujian. Anda dapat melihat hasil evaluasi dan laporan klasifikasi pada *output* sel kode yang bersangkutan.

## Catatan

- *Notebook* ini menggunakan MobileNetV2 sebagai model dasar. Anda dapat mencoba model lain yang sudah terlatih sebelumnya jika diinginkan.
- Anda dapat menyesuaikan parameter pelatihan seperti *learning rate*, *batch size*, dan jumlah *epochs* untuk meningkatkan performa model.
- Pastikan untuk mengganti path dataset dengan path yang sesuai pada kode.
