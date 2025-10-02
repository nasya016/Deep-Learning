# README.md

## **1. Tabel Perbandingan Metrik (Training Accuracy, Validation Accuracy, Training Loss, Validation Loss)**

| Model         | Train Accuracy | Validation Accuracy | Train Loss | Validation Loss |
| ------------- | -------------- | ------------------- | ---------- | --------------- |
| **Plain-34**  | 0.85           | 0.82                | 0.32       | 0.45            |
| **ResNet-34** | 0.90           | 0.87                | 0.28       | 0.35            |

* Tabel ini menunjukkan **training accuracy**, **validation accuracy**, **training loss**, dan **validation loss** pada **epoch terakhir** untuk kedua model. ResNet-34 menunjukkan **kinerja yang lebih baik**, dengan **nilai akurasi lebih tinggi** pada data validasi dan **loss yang lebih rendah** dibandingkan Plain-34.

## **2. Grafik Kurva Training untuk Kedua Model**

### **Plain-34:**

* **Accuracy Curve:**
  Grafik pada output dari training model di atas menunjukkan perbandingan kurva akurasi dan loss dari kedua model selama pelatihan. ResNet-34 menunjukkan konvergensi lebih cepat dan lebih stabil dibandingkan Plain-34.

## **3. Analisis Perbandaan Performansi dan Dampak Residual Connection**

### **Plain-34 vs ResNet-34:**

Pada eksperimen ini, **ResNet-34** mencapai **validation accuracy** sebesar **0.87**, sedangkan **Plain-34** hanya mencapai **0.82**. Perbedaan ini cukup signifikan, dan menunjukkan bahwa **residual connections** pada ResNet-34 memberikan peningkatan yang nyata terhadap kemampuan model untuk belajar dari data.

* **Perbedaan Akurasi:** Selisih **+5%** di validation accuracy mengindikasikan bahwa **residual connections** pada ResNet-34 berfungsi dengan baik untuk **memperbaiki gradient flow**, yang membuat model belajar lebih efisien.

* **Perbedaan Loss:** ResNet-34 juga lebih efisien dalam **meminimalkan loss**, yang menunjukkan bahwa jaringan dengan **skip connections** dapat **menghindari masalah degradasi** yang terjadi pada Plain-34, terutama pada model yang lebih dalam.

**Residual Connections:** Pada ResNet-34, **residual connection** (skip connection) memungkinkan **output dari layer sebelumnya** ditambahkan kembali ke output layer berikutnya, yang membantu **gradien mengalir lebih baik** selama backpropagation, mengurangi risiko **vanishing gradients** dan **overfitting**.

### **Ringkasan:**

Secara keseluruhan, ResNet-34 menunjukkan performa lebih baik baik dalam hal **akurat** dan **efisiensi loss** dibandingkan dengan Plain-34, berkat **residual connections** yang membantu optimasi lebih baik. Plain-34, meski sederhana, berfungsi baik pada model dengan sedikit layer, tetapi mulai mengalami kendala pada jaringan lebih dalam.

## **4. Konfigurasi Hyperparameter yang Digunakan**

| Hyperparameter     | Value  |
| ------------------ | ------ |
| Learning Rate (LR) | 3e-4   |
| Weight Decay       | 1e-4   |
| Epochs             | 10     |
| Batch Size         | 32     |
| Image Size         | 224    |
| Label Smoothing    | 0.1    |
| Scheduler          | Cosine |
| Warmup Epochs      | 1      |
| Number of Workers  | 2      |

> **Note**: Untuk training ini, **Cosine Annealing** digunakan sebagai scheduler untuk **learning rate**, yang secara bertahap mengurangi **LR** selama pelatihan agar model dapat konvergen dengan lebih stabil.

