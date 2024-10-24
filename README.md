# Fish Classification Using Artificial Neural Networks (ANN)
Proje kodlarına [Kaggle proje sayfasından](https://www.kaggle.com/code/oguzhandenizhan/fish-classification-using-ann/edit) ulaşabilirsiniz.

## Proje Konusu ve Kullanılan Veri Seti
Bu proje, [Kaggle balık veri seti](https://www.kaggle.com/datasets/crowww/a-large-scalefish-dataset/data) kullanılarak 9 farklı balık türünün sınıflandırılmasını hedeflemektedir. Her balık türü için 1000 örnek bulunmaktadır. Python programlama dilinde TensorFlow kütüphanesi kullanılarak bir Yapay Sinir Ağı (ANN) modeli oluşturulmuş ve analiz gerçekleştirilmiştir.

## Veri Ön İşleme
Veri seti üzerinde etiketleme işlemi için **one-hot encoding** kullanılmıştır. Eğitim ve test verileri, yaygın kullanılan oranlar olan %80 eğitim ve %20 test ile %67 eğitim ve %33 test olarak denenmiş; en iyi sonuç %80 eğitim - %20 test oranında elde edilmiştir.

## Model Mimarisi
Modelde 3 ara katman kullanılmıştır:
- İlk ara katmanda: 256 nöron
- İkinci ara katmanda: 128 nöron
- Üçüncü ara katmanda: 64 nöron

Çıkış katmanında, 9 balık türünü sınıflandırmak için 9 nöron bulunmaktadır. Aktivasyon fonksiyonu olarak ara katmanlarda **relu**, çıkış katmanında ise **softmax** kullanılmıştır.

## Kernel Fonksiyonları ve Diğer Ayarlar
Ağırlık hesaplamalarında kullanılan kernel fonksiyonları olarak:
- **he_normal**
- **RandomUniform**
- **glorot_uniform**

fonksiyonları denenmiş ve en iyi sonuç **he_normal** fonksiyonu ile elde edilmiştir.

### Diğer Teknik Ayarlar:
- Optimizasyon algoritması: **Adam**
- Kayıp fonksiyonu: **categorical_crossentropy**
- Başarı ölçütü (metric): **accuracy**
- Epoch sayısı: 15 (Overfitting'i önlemek için sınırlı tutulmuştur.)

## Sonuçlar
Modelin ağırlıklı doğruluk oranı %82 olarak tespit edilmiştir. Sonuçları daha iyi analiz etmek için karışıklık matrisi (confusion matrix) kullanılarak bir ısı haritası (heatmap) oluşturulmuştur.
