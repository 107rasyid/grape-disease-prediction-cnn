# Deteksi Penyakit Daun Anggur dengan Deep Learning
Proyek ini mengimplementasikan model deep learning menggunakan TensorFlow dan Keras untuk mengklasifikasikan penyakit pada daun anggur. Model ini dilatih untuk membedakan antara daun anggur yang sehat dan daun yang terinfeksi oleh penyakit seperti Black Rot, ESCA, dan Leaf Blight. Model ini juga diekspor ke berbagai format untuk memudahkan deployment.

## Alur Kerja Proyek
Proyek ini mengikuti alur kerja tipikal pengembangan model deep learning:
1.  **Pengumpulan dan Persiapan Data:** Dataset gambar daun anggur dikumpulkan dan diproses. Ini melibatkan pemisahan data menjadi set pelatihan dan pengujian, serta augmentasi gambar untuk meningkatkan variasi data pelatihan.
2.  **Pembuatan dan Pelatihan Model:** Model Convolutional Neural Network (CNN) dibuat menggunakan Keras. Model ini dilatih menggunakan data pelatihan yang telah diproses. Proses pelatihan melibatkan optimasi bobot model untuk meminimalkan loss dan memaksimalkan akurasi pada data validasi.
3.  **Evaluasi Model:** Setelah pelatihan, model dievaluasi menggunakan data pengujian untuk mengukur performanya dalam mengklasifikasikan gambar yang belum pernah dilihat sebelumnya. Metrik seperti akurasi, precision, recall, dan f1-score digunakan untuk evaluasi.
4.  **Visualisasi Hasil:** Hasil pelatihan dan evaluasi divisualisasikan menggunakan plot akurasi dan loss selama pelatihan, serta confusion matrix untuk menganalisis kinerja klasifikasi per kelas.
5.  **Ekspor Model:** Model yang telah dilatih diekspor ke berbagai format untuk memudahkan deployment:
    * **SavedModel:** Format standar untuk deployment TensorFlow.
    * **TF-Lite:** Format yang dioptimalkan untuk perangkat mobile dan embedded.
    * **TFJS:** Format untuk deployment di aplikasi web menggunakan TensorFlow.js.
6.  **Inferensi Model:** Contoh kode disediakan untuk melakukan inferensi menggunakan model yang telah diekspor dalam format SavedModel dan TFJS.

## Hasil Pelatihan

Laporan klasifikasi pada data pelatihan adalah sebagai berikut:

|               | precision | recall | f1-score | support |
|---------------|-----------|--------|----------|---------|
| Healthy       | 1.0000    | 1.0000 | 1.0000   | 213     |
| Black Rot     | 0.9885    | 0.9961 | 0.9923   | 258     |
| ESCA          | 0.9957    | 0.9915 | 0.9936   | 236     |
| Leaf Blight   | 1.0000    | 0.9949 | 0.9975   | 197     |
| accuracy      |           |        | 0.9956   | 904     |
| macro avg     | 0.9961    | 0.9956 | 0.9958   | 904     |
| weighted avg  | 0.9956    | 0.9956 | 0.9956   | 904     |

Total waktu pelatihan adalah 963.14 detik.

## Visualisasi Hasil

### Plot Pelatihan

![Plot Pelatihan](https://github.com/107rasyid/grape-disease-prediction-cnn/blob/main/plot%20pelatihan%20model.png)\
_Plot ini menampilkan grafik akurasi dan loss pada set pelatihan dan validasi selama proses pelatihan._

### Confusion Matrix

![Confusion Matrix](https://raw.githubusercontent.com/107rasyid/grape-disease-prediction-cnn/main/confusion%20matrix.png)\
_Confusion matrix ini memvisualisasikan kinerja model dengan menunjukkan jumlah prediksi yang benar dan salah untuk setiap kelas penyakit daun anggur pada data pengujian._

## Ekspor Model
Model yang telah dilatih diekspor ke beberapa format di direktori:
* `saved_model/`: Berisi model dalam format SavedModel.
* `tflite/`: Berisi model yang dikonversi ke format TF-Lite.
* `tfjs_model/`: Berisi model yang dikonversi ke format TensorFlow.js untuk penggunaan di web.

## Struktur Proyek
[grape-disease-detection]/
├── README.md/
├── saved_model/
├── tflite/
│   ├── model.tflite/
│   └── labels.txt/
├── tflite/tfjs_model/
│   ├── model.json/
│   ├── group1-shard1of1.bin/
│   └── .../
├── notebook.ipynb/
├── requirements.txt/
├── plot_latihan.png/
└── confusion_matrix.png
