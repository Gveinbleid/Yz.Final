# 🛩️ Uydu Görüntülerinden Otomatik Uçak Tespiti (PlanesNet)

## 📌 Projenin Amacı
Bu projenin amacı, uydu görüntülerindeki pikselleri analiz ederek bir bölgede uçak olup olmadığını makine öğrenmesi algoritmalarıyla otomatik olarak tespit etmektir. Proje, görüntü işleme alanında "İkili Sınıflandırma (Binary Classification)" problemi olarak ele alınmış ve model eğitimi "Learning with Complete Data" (Eksiksiz Veri) prensibine sadık kalınarak gerçekleştirilmiştir.

## 📂 Veri Seti ve Kaynak
Projeye ait orijinal veri seti Kaggle platformundan alınmıştır. Orijinal veri seti 32.000 adet (20x20 piksel) RGB uydu görüntüsünden oluşmaktadır. 
* **Veri Seti Linki:** [Kaggle - PlanesNet](https://www.kaggle.com/datasets/rhammell/planesnet)
* **Veri Hazırlama:** Eğitim süresini optimize etmek ve dengeli bir öğrenme sağlamak adına, projede orijinal veriden rastgele seçilmiş %50 uçak ve %50 uçak olmayan görsellerden oluşan 2000 örneklik bir alt set (Subset) oluşturulmuştur. Veri setinde eksik (NaN) değer bulunmamaktadır.

## ⚙️ Kullanılan Model
Görüntü verilerinin (1200 özellikli vektörler) sınıflandırılmasında, piksel tabanlı matrislerde yüksek başarı gösteren **Destek Vektör Makineleri (SVM - Support Vector Classifier)** algoritması kullanılmıştır. Model %80 Eğitim (Train) ve %20 Test (Test) seti olmak üzere ikiye ayrılarak eğitilmiştir.

## 📊 Elde Edilen Sonuçların Değerlendirilmesi
Modelin daha önce hiç görmediği %20'lik test verisi (400 adet görsel) üzerindeki performansı aşağıdaki metriklerle ölçülmüştür:

* **Accuracy (Doğruluk Oranı):** % [ 0.94]
* **Precision (Kesinlik):** % [0.95]
* **Recall (Duyarlılık):** % [ 0.94 ]
* **F1-Score:** % [0.94]

**Karmaşıklık Matrisi (Confusion Matrix) Yorumu:**
Model, uçağı tespit etme konusunda oldukça başarılıdır. Karmaşıklık matrisine göre, test setindeki uçakların büyük bir çoğunluğu "Uçak Var (True Positive)" olarak doğru sınıflandırılmıştır. Yanlış pozitif ve yanlış negatif (hata payı) oranlarının düşük olması, modelin veriyi ezberlemediğini (overfitting yapmadığını) ve örüntüyü doğru öğrendiğini kanıtlamaktadır.

---
🎓 **Not:** AI İçerikli Program Sertifikası bu repoda "Sertifika.pdf" olarak bulunmaktadır / Veya e-tablo linki üzerinden erişime açıktır.