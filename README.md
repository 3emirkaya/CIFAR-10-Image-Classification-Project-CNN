# 🖼️ CIFAR-10 Görüntü Sınıflandırma Projesi (CNN)

Bu proje, popüler **CIFAR-10** veri setini (10 farklı nesne sınıfı) kullanarak gelişmiş bir **Evrişimsel Sinir Ağı (CNN)** modeli eğitir. Yüksek performans ve aşırı öğrenmeye (overfitting) karşı direnç sağlamak için modern derin öğrenme teknikleri uygulanmıştır.

---

## 🎯 Proje Hedefleri

* **Veri Seti:** CIFAR-10 (60.000 adet 32x32x3 renkli görüntü).
* **Model:** $\text{BatchNormalization}$ ve $\text{Dropout}$ içeren derin, katmanlı $\text{Sequential}$ CNN mimarisi.
* **Optimizasyon:** $\text{ImageDataGenerator}$ ile **Veri Artırma** ve $\text{EarlyStopping}$ ile eğitim yönetimi.

---

## 🛠️ Kullanılan Teknolojiler

| Kategori | Kütüphane / Modül | Amaç |
| :--- | :--- | :--- |
| **Derin Öğrenme** | `TensorFlow`, `Keras` | Model eğitimi ve GPU hızlandırma. |
| **Veri Artırma** | `ImageDataGenerator` | Aşırı öğrenmeyi önlemek için yapay veri üretimi. |
| **Metrikler** | `Scikit-learn` | Detaylı $\text{Classification Report}$ ve $\text{Confusion Matrix}$ analizi. |

---

## 🧠 Model Mimarisi Özeti

Model, $\text{BatchNormalization}$ ve $\text{Dropout}$ ile stabilize edilmiş üç Evrişim Bloğu içerir.

```python
model = Sequential()

# Blok 1: 32 Filtre (BN, Conv, MP, Dropout)
model.add(Conv2D(32, (3, 3), padding='same', activation='relu', input_shape=(32, 32, 3)))
# ...

# Blok 2: 64 Filtre
# ...

# Blok 3: 128 Filtre
# ...

# Çıktı Katmanı (10 Sınıf, Softmax)
model.add(Dense(10, activation='softmax'))
