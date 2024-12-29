# Python Temelleri ve Lineer Regresyon
# README: Veri Analizi ve Lineer Regresyon Modeli

## Giriş
Bu proje, Python programlama dilinde veri analizi ve lineer regresyon modeli kullanarak bir veri kümesi üzerinde çalışma yapılmasını kapsamaktadır. Aşağıdaki adımlar, kodun detaylı bir açıklamasını ve kullanımını içermektedir.

---

## Kullanılan Teknolojiler ve Kütüphaneler
- **Python**: Veri işleme ve analiz için temel programlama dili.
- **Pandas**: Veri çerçeveleri ile çalışmak ve CSV dosyalarını yüklemek için kullanıldı.
- **Matplotlib**: Veri görselleştirme için kullanıldı.
- **Scikit-learn**: Lineer regresyon modeli oluşturmak ve tahmin yapmak için kullanıldı.

---

## Veri
Bu projede bir aracın yıl ve km bilgilerini içeren bir CSV dosyası (**"reno_clio.csv"**) kullanılmıştır. Veri seti, aşağıdaki kolonlardan oluşmaktadır:
- **yıl**: Arabanın üretim yılı.
- **km**: Arabanın o yıldaki kilometresi.
- **yaş**: Arabanın yaşı (2024 - yıl).

---

## Adımlar

### 1. Değişken Tanımlama ve Veri Tipleri
Kodun ilk bölümü, farklı veri tiplerini (örneğin, string, integer, float, boolean) anlamak ve kullanmak için temel örnekler verilmiştir. Aşağıda anahtar noktalar yer almaktadır:
- **Listeler (List)**, **Kümeler (Set)** ve **Sözlükler (Dictionary)** gibi koleksiyon yapıları tanıtılmıştır.

### 2. Veri Yüklenmesi
```python
import pandas as pd
burcunun_verisi = pd.read_csv("reno_clio.csv")
```
Bu adımda, veri seti yüklenmiş ve temel özellikleri analiz edilmiştir. 

### 3. Veri Görselleştirme
Veri, Matplotlib kullanılarak grafik şeklinde görünür hale getirilmiştir. Şöyle bir görsel oluşturulmuştur:
- **Yaş-Km Grafiği**

```python
plt.scatter(burcunun_verisi["yaş"], burcunun_verisi["km"], color="red")
plt.xlabel("Yaş")
plt.ylabel("Km")
plt.title("Yaş-Km Grafiği")
plt.show()
```

### 4. Lineer Regresyon Modeli
Scikit-learn kullanılarak bir lineer regresyon modeli oluşturulmuştur:
- **Eğitim**: Yaş (özellik) ve km (etiket) kullanılarak model eğitilmiştir.
```python
from sklearn.linear_model import LinearRegression
model = LinearRegression()
model.fit(burcunun_verisi[["yaş"]], burcunun_verisi["km"])
```
- **Model Parametreleri**: Eğitim sonucunda modelin katsayıları ve kesme noktaları görülmüştür.
```python
model.coef_, model.intercept_
```

### 5. Tahminler ve Görselleştirme
Modelin tahmin değerleri kullanılarak yaş ve km arasındaki ilişki gösterilmiştir:
```python
plt.scatter(burcunun_verisi["yaş"], burcunun_verisi["km"], color="red")
plt.plot(burcunun_verisi["yaş"], model.predict(burcunun_verisi[["yaş"]]), color="blue")
plt.xlabel("Yaş")
plt.ylabel("Km")
plt.title("Yaş-Km Grafiği")
plt.show()
```

---

## Sonuçlar
Bu çalışma, basit bir lineer regresyon modelinin eğitilmesi ve kullanılması üzerine odaklanmaktadır. Şu detaylar öne çıkmıştır:
- Araç yaşı ve kilometre arasında pozitif bir ilişki vardır.
- Model, yeni yaş değerleri için tahmin yapabilir.

---

## Nasıl Çalıştırılır
1. Gerekli Python paketlerini yükleyin:
    ```bash
    pip install pandas matplotlib scikit-learn
    ```
2. **"reno_clio.csv"** dosyasını proje dizinine ekleyin.
3. Python betiğini çalıştırın:
    ```bash
    python script.py
    ```
4. Sonuç grafikleri ve tahminleri inceleyin.

---

## Gelecek Adımlar
- Daha karmaşık modelleri denemek (polinom regresyon vb.).
- Diğer veri setleri ile eğitim ve test yaparak model performansını artırmak.
- Modelin tahmin performansını değerlendirmek için metrikler eklemek (MSE, R^2 vb.).


