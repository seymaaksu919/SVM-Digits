# 🔍 SVM ile Sayı Tanıma (0 ve 1) – Görselleştirmeli Sınıflandırma

Bu proje, sklearn kütüphanesinin içinde bulunan `digits` veri seti kullanılarak, **Destek Vektör Makineleri (SVM)** algoritması ile el yazısı rakamlarının sınıflandırılmasını amaçlamaktadır. Görselleştirme için PCA uygulanarak 2 boyutlu uzayda karar sınırları çizilmiştir.


## 📌 Kullanılan Yöntemler

- **Veri Seti**: `sklearn.datasets.load_digits()` → 8x8 el yazısı rakam görüntüleri.
- **Hedef Sınıflar**: Sadece `0` ve `1` rakamları kullanılmıştır (binary sınıflandırma).
- **Boyut İndirgeme**: PCA (Principal Component Analysis) ile 64 boyut → 2 boyut.
- **Model**: SVC (Support Vector Classifier)
  - Kernel türleri: `linear` kullanılmıştır.
  - `C`  hiperparametresi manuel belirlenmiştir.
- **Görselleştirme**: Karar sınırı, eğitim verileri ve destek vektörleri matplotlib ile çizilmiştir.

Bu proje aynı zamanda RBF kullanılarak da yapılabilir.

## Peki bu RBF nedir?

### 🔹 RBF (Radial Basis Function) Kernel
- **Doğrusal olmayan** (nonlinear) veriler için uygun olan
- Daha karmaşık, kıvrımlı karar sınırları oluşturan
- Veri uzayını yüksek boyutlara taşıyarak daha iyi ayrım sağlayan
- `gamma` parametresi ile esnekliği kontrol eden bir yapıdır.


## 🧪 Lineer Kernel ise

### 🔸 Lineer Kernel
- Veriyi **doğrusal bir düzlem** ile ayırmaya çalışır.
- Karar sınırı düz bir çizgi olur.
- Veri gerçekten doğrusal olarak ayrılabiliyorsa tercih edilir.
- Hızlı ve sadedir.


### 📊 RBF Kernel vs Lineer Kernel Karşılaştırma Tablosu

| Özellik                | 🔹 RBF (Radial Basis Function) Kernel   | 🔸 Lineer Kernel                             |
| ---------------------- | --------------------------------------- | -------------------------------------------- |
| **Veri Yapısı**        | Doğrusal olmayan (nonlinear) veriler    | Doğrusal (linear) olarak ayrılabilen veriler |
| **Karar Sınırı**       | Kıvrımlı ve karmaşık                    | Düz bir çizgi (doğrusal hiper düzlem)        |
| **Boyut Dönüşümü**     | Veriyi daha yüksek boyutlara taşır      | Boyut dönüşümüne ihtiyaç duymaz              |
| **Parametre**          | `gamma` parametresi hassasiyeti ayarlar | Parametre yok ya da çok azdır                |
| **Hesaplama Maliyeti** | Daha yüksektir                          | Daha düşüktür                                |
| **Esneklik**           | Yüksek – karmaşık desenleri öğrenebilir | Düşük – sadece doğrusal ayrımı yapabilir     |
| **Kullanım Durumu**    | Veri karmaşıksa, doğrusal değilse       | Veri açıkça doğrusal ayrılıyorsa             |
| **Overfitting Riski**  | `gamma` çok yüksekse olabilir           | Düşüktür                                     |






