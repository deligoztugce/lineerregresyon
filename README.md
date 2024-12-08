# Python Temelleri ve Lineer Regresyon

Bu proje, Python dilinde temel programlama konuları olan değişkenler, koleksiyonlar, döngüler ve lineer regresyon ile ilgili örnekler ve açıklamalar içermektedir. Aşağıda bu konuların her birine dair örnekler bulabilirsiniz.

## İçerik

1. [Değişkenler](#değişkenler)
2. [Koleksiyonlar](#koleksiyonlar)
3. [Döngüler](#döngüler)
4. [Lineer Regresyon](#lineer-regresyon)

---

## Değişkenler

Python'da **değişkenler**, bir değeri saklamak için kullanılan isimlerdir. Değişkenler, her türlü veri tipini saklayabilir.

### Örnek:
```python
# Bir sayı değişkeni
x = 10

# Bir metin değişkeni
y = "Merhaba Python!"

# Bir ondalıklı sayı
z = 3.14

print(x, y, z)
# Bir liste oluşturma
my_list = [1, 2, 3, 4, 5]

# Listeye öğe ekleme
my_list.append(6)

# Listeyi yazdırma
print(my_list)
# Bir sözlük oluşturma
person = {"ad": "Ali", "yaş": 30, "şehir": "İstanbul"}

# Anahtar ile değer erişme
print(person["ad"])

# Yeni anahtar-değer çifti ekleme
person["meslek"] = "Mühendis"

print(person)

# Liste üzerinde döngü ile iterasyon
my_list = [1, 2, 3, 4, 5]
for item in my_list:
    print(item)
# 1'den 5'e kadar sayıları yazdırma
i = 1
while i <= 5:
    print(i)
    i += 1
import numpy as np

# Bağımsız değişken (x) ve bağımlı değişken (y)
X = np.array([1, 2, 3, 4, 5]).reshape(-1, 1)
y = np.array([1, 2, 3, 4, 5])

from sklearn.linear_model import LinearRegression

# Modeli oluşturma ve eğitme
model = LinearRegression()
model.fit(X, y)

# Yeni bir veri noktası için tahmin
prediction = model.predict([[6]])
print(prediction)  # Bu örnekte tahmin 6 olacaktır
print("Katsayı (a):", model.coef_)
print("Kesme noktası (b):", model.intercept_)
