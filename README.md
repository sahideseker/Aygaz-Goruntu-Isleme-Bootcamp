# Görüntü İşleme ve Sınıflandırma Projesi

Bu proje, **Animals with Attributes 2** veri seti kullanılarak, seçilen 10 hayvan sınıfının görüntülerinin sınıflandırılması ve manipüle edilmiş test setleriyle model performansının analiz edilmesi üzerine odaklanmıştır.

---

## Proje Adımları

### 1. Veri Setinin Hazırlanması
- **Veri Seti Kaynağı:**
  - [Animals with Attributes 2 - Kaggle](https://www.kaggle.com/datasets/rrebirrth/animals-with-attributes-2)
- 50 sınıftan 10 sınıf seçilmiştir: `collie, dolphin, elephant, fox, moose, rabbit, sheep, squirrel, giant panda, polar bear`.
- Her sınıftan 650 görüntü seçilmiş ve `FilteredDataset` klasörüne kopyalanmıştır.
- Görseller, `128x128` boyutuna getirilmiş ve normalize edilmiştir.

---

### 2. Modelin Tasarımı
- **Kullanılan Model:** CNN (Convolutional Neural Network)
- **Katmanlar:**
  - 2 adet konvolüsyon + max pooling + dropout katmanı
  - Flatten, fully connected (Dense) ve softmax çıkış katmanı
- **Optimizasyon:** Adam
- **Kayıp Fonksiyonu:** Sparse Categorical Crossentropy

---

### 3. Modelin Eğitimi
- Eğitim ve test seti %70 - %30 oranında ayrılmıştır.
- Eğitim sırasında veri artırma (augmentation) uygulanmıştır:
  - Döndürme, yakınlaştırma, kaydırma, yatay çevirme.
- Eğitim doğruluğu: **%54.51**.
- Model, manipüle edilmiş ve renk sabitliği uygulanmış test setleri üzerinde değerlendirilmiştir.

---

### 4. Manipüle Edilmiş ve Renk Sabitliği Uygulanmış Test Setleri
- **Manipüle edilmiş test seti:**
  - Rastgele parlaklık artırma uygulanmıştır.
  - Doğruluk: **%10.05**.
- **Renk sabitliği uygulanmış test seti:**
  - Gray World algoritması uygulanmıştır.
  - Doğruluk: **%10.05**.

---

### 5. Çıkarımlar ve Öneriler
- **Düşük başarı oranı:** Model, manipüle edilmiş ve renk sabitliği uygulanmış görüntülerde düşük performans göstermektedir.
- **Çözüm yolları:**
  - Daha çeşitli veri artırma teknikleri.
  - Daha karmaşık veya önceden eğitilmiş modellerin kullanımı.
  - Manipüle edilmiş görüntülerle eğitimin artırılması.

---

## Kullanılan Teknolojiler ve Kütüphaneler
- **Python**: 3.12
- **TensorFlow**: 2.x
- **OpenCV**: 4.x
- **Matplotlib** ve **NumPy**: Görselleştirme ve veri işlemleri için.

---

## Projeyi Çalıştırma
1. Veri setini indirin ve `Animals_with_Attributes2` klasörüne yerleştirin.
2. Gerekli kütüphaneleri yükleyin:
   ```bash
   pip install tensorflow opencv-python matplotlib numpy
