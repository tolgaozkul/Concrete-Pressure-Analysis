# 🏗️ Concrete Compressive Strength Prediction (Beton Basınç Dayanımı Tahmini)

Bu proje, betonun bileşen oranlarına ve kürlenme süresine (yaşına) dayanarak **beton basınç dayanımını (MPa)** tahmin etmeyi amaçlayan bir makine öğrenmesi (regresyon) çalışmasıdır.

## 📊 Veri Seti Hakkında

Bu çalışmada [UCI Machine Learning Repository - Concrete Compressive Strength](https://archive.ics.uci.edu/dataset/165/concrete+compressive+strength) veri seti kullanılmıştır. Betonun basınç dayanımı; çimento, cüruf, uçucu kül, su, süper akışkanlaştırıcı, kaba ve ince agrega gibi 8 farklı nicel girdiye bağlı olarak değişen karmaşık ve doğrusal olmayan bir fonksiyondur. Veri setinde hiç eksik değer (missing value) bulunmamaktadır.

## 🚀 Proje Kapsamı ve İş Akışı

Jupyter Notebook (`concrete-pressure-analysis.ipynb`) içerisinde sırasıyla şu adımlar izlenmiştir:

1. **Keşifsel Veri Analizi (EDA):** Değişkenlerin dağılımlarının incelenmesi ve beton bileşenleri arasındaki ilişkilerin korelasyon matrisi/ısı haritası ile görselleştirilmesi.
2. **Veri Ön İşleme (Preprocessing):** Farklı birimlerdeki bileşenlerin (örn. çok düşük oranlı akışkanlaştırıcılar ile çok yüksek oranlı agregalar) algoritmalar tarafından doğru yorumlanabilmesi için ölçeklendirme (Feature Scaling) yapılması.
3. **Modelleme:** Dayanım tahmini için farklı makine öğrenmesi algoritmalarının eğitilmesi:
   - Doğrusal Modeller: *Linear Regression, Ridge, Lasso*
   - Ağaç Tabanlı Modeller: *Random Forest, XGBoost, LightGBM*
4. **Değerlendirme:** Modellerin tahmin başarılarının **R²** (R-Kare) ve **RMSE** (Kök Ortalama Kare Hata) metrikleri kullanılarak karşılaştırılması.

## 🛠️ Kullanılan Teknolojiler

* **Dil:** Python
* **Kütüphaneler:** Pandas, NumPy, Scikit-Learn, XGBoost, LightGBM, Matplotlib, Seaborn

## 📈 Sonuçlar

Yapılan modelleme çalışmaları sonucunda, ağaç tabanlı algoritmalar (özellikle LightGBM, Random Forest ve XGBoost), veri setindeki doğrusal olmayan karmaşık ilişkileri yakalamada geleneksel regresyon modellerine göre çok daha üstün bir performans sergilemiştir. 

> **Not:** En başarılı modelimiz olan `LightGBM (Default)` ile **`0.9220`** R² ve **`4.0698`** RMSE skorları elde edilmiştir.

## 💻 Nasıl Çalıştırılır?

Projeyi kendi bilgisayarınızda incelemek isterseniz:

1. Repoyu klonlayın: 
   ```bash
   git clone https://github.com/tolgaozkul/concrete-pressure-analysis.git
   ```
2. Gerekli bağımlılıkları yükleyin:
   ```bash
   pip install pandas numpy scikit-learn xgboost lightgbm matplotlib seaborn
   ```
3. `concrete-pressure-analysis.ipynb` dosyasını Jupyter Notebook, JupyterLab veya VS Code üzerinden açarak hücreleri sırasıyla çalıştırın.
