# METODE DAN HASIL

## Tabel Penelitian Terdahulu tentang Estimasi Kedalaman Monocular

| JUDUL | METODE YG DIGUNAKAN | HASILNYA |
|-------|---------------------|----------|
| Mancini et al. (2019) | Deep learning untuk estimasi kedalaman | ARE: 0.312, RMSE: 0.565, Akurasi (δ<1.25): 80.9% |
| Xu et al. (2018) | Multi-scale deep network | ARE: 0.125, RMSE: 0.593, Akurasi (δ<1.25): 80.6% |
| Alhashim et al. (2018) | DenseDepth - Fully convolutional architecture | ARE: 0.123, RMSE: 0.465, Akurasi (δ<1.25): 84.6% |
| Li et al. (2018) - VGG16 | Deep convolutional neural network dengan VGG16 backbone | ARE: 0.152, RMSE: 0.611, Akurasi (δ<1.25): 78.9% |
| Li et al. (2018) - VGG19 | Deep convolutional neural network dengan VGG19 backbone | ARE: 0.146, RMSE: 0.617, Akurasi (δ<1.25): 79.5% |
| Li et al. (2018) - ResNet50 | Deep convolutional neural network dengan ResNet50 backbone | ARE: 0.143, RMSE: 0.635, Akurasi (δ<1.25): 78.8% |
| Rudolph et al. (2018) | Structured attention guided network | ARE: 0.138, RMSE: 0.501, Akurasi (δ<1.25): 82.3% |
| Lee et al. (2019) | From Big to Small: Multi-scale local planar guidance | ARE: 0.131, RMSE: 0.538, Akurasi (δ<1.25): 83.7% |
| Guizilini et al. (2020) | 3D packing for self-supervised monocular depth | ARE: 0.072, RMSE: 2.727, Akurasi (δ<1.25): 93.2% |
| Basak et al. (2022) | Encoder-decoder architecture untuk indoor scenes | ARE: 0.103, RMSE: 0.388, Akurasi (δ<1.25): 89.2% |
| Das et al. (2022) | Encoder-Decoder dengan InceptionResNetV2 | ARE: 0.064, RMSE: 0.228, Akurasi (δ<1.25): 89.3% |
| Ignatov et al. (2023) | Fast and accurate depth estimation | ARE: 0.090, RMSE: 0.322, Akurasi (δ<1.25): 92.9% |
| **Hybrid Ensemble UNet (2025)** | **Transformer-based Hybrid UNet dengan ResNet18 encoder dan BADCL loss function** | **ARE: 0.063, RMSE: 0.237, Akurasi (δ<1.25): 98.2%, SSIM: 99.8%** |

---

## Keterangan Metrik

- **ARE (Absolute Relative Error)**: Kesalahan relatif absolut - semakin rendah semakin baik
- **RMSE (Root Mean Square Error)**: Akar kuadrat rata-rata kesalahan - semakin rendah semakin baik
- **Akurasi (δ<1.25)**: Persentase prediksi dengan kesalahan kurang dari ambang batas 1.25 - semakin tinggi semakin baik
- **SSIM (Structural Similarity Index)**: Indeks kemiripan struktural - semakin tinggi semakin baik (maksimal 100%)

---

## Ringkasan Hasil Terbaik

**Metode yang diusulkan (Hybrid Ensemble UNet, 2025)** mencapai hasil terbaik dengan:

1. **SSIM tertinggi**: 99.8% - menunjukkan kualitas peta kedalaman yang sangat baik
2. **ARE terendah**: 0.063 - kesalahan relatif paling kecil dibandingkan semua metode lain
3. **Akurasi tertinggi**: 98.2% pada ambang batas δ<1.25
4. **RMSE kompetitif**: 0.237 - kesalahan kuadrat rata-rata yang rendah

### Keunggulan Metode Hybrid Ensemble UNet:
- Menggunakan arsitektur encoder-decoder dengan ResNet18
- Memanfaatkan Transformer attention blocks untuk konteks global
- BADCL (Boundary-Aware Depth Consistency Loss) untuk tepi yang lebih tajam
- Parameter yang lebih sedikit namun performa lebih baik
- Cocok untuk aplikasi real-time pada sistem otonom

### Aplikasi Praktis:
- **Kendaraan Otonom**: Persepsi lingkungan dan deteksi rintangan
- **Navigasi Robot**: Perencanaan jalur dan penghindaran objek
- **Augmented Reality**: Pemahaman scene dan pemetaan kedalaman
- **Pemahaman Scene Indoor**: Estimasi tata letak ruangan dan lokalisasi objek
