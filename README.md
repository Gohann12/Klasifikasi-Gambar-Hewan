# Proyek Klasifikasi Gambar: 7-Class Animal Dataset (10,000 Images)

Proyek ini merupakan implementasi Convolutional Neural Network (CNN) untuk melakukan klasifikasi gambar hewan ke dalam 7 kelas berbeda. Dataset yang digunakan berisi **10.000 gambar hewan** dengan berbagai resolusi dan kondisi pencahayaan. Model dibangun menggunakan **Keras**, dilatih menggunakan arsitektur **ResNet50 + CNN custom layers**, dan diekspor ke format **SavedModel**, **TFLite**, dan **TensorFlow.js**.

---

## Dataset yang Digunakan
Dataset: **10000 Images of 7-Class Animal**  
Link: Kaggle (dhondoi/10000-images-of-7-class-animal)

Dataset terdiri dari 7 kelas:

- Spider 
- Cat  
- Fish 
- Dog  
- Butterfly
- Horse  
- Chicken

Dataset kemudian dibagi menjadi:

- **70% Train**
- **15% Validation**
- **15% Test**

---

## Model yang Digunakan

Model yang digunakan adalah kombinasi:

1. **Pretrained ResNet50** (tanpa top layer, bobot ImageNet)  
2. **CNN Custom Layers**:
   - Conv2D(32, 3×3)
   - MaxPooling2D
   - GlobalAveragePooling2D  
   - Dense(512, ReLU)  
   - Dropout(0.5)  
   - Dense(7, Softmax)

Optimizer: **Adam (lr = 1e-4)**  
Loss: **Categorical Crossentropy**  
Metrics: **Accuracy**

Callbacks:
- EarlyStopping  
- ReduceLROnPlateau  
- ModelCheckpoint  

Input size: **256 × 256 × 3**

---

## Hasil Training Model

| Metrik | Nilai |
|--------|--------|
| Training Accuracy | **0.9927** |
| Training Loss | **0.0276** |
| Validation Accuracy | **0.9860** |
| Validation Loss | ~0.05 |

Model mencapai akurasi **di atas 98%**,
