# Python Notlarım - Bölüm 1: Temeller

> Bu dosya özgün olarak hazırlandı. Konu sırası W3Schools Python içeriğindeki başlık sırası örnek alınarak oluşturuldu, anlatım ve örnekler bana ait / yeniden yazıldı. W3Schools metninin kopyası değildir. Offline okumak için kullanılabilir.

## 1. Python Intro
Python, okunması kolay, girintiye dayalı bir dildir.
- Sunucu tarafında, otomasyonda, veri işlerinde kullanılır.
- Yorumlanan dildir, derleme gerekmez.

## 2. Python Get Started
Kurulum:
1. python.org adresinden Python 3 kur.
2. Kontrol et: `python3 --version`
3. Dosya çalıştır: `python3 deneme.py`

## 3. Python Syntax
- Bloklar girinti ile belli olur.
- 4 boşluk kullan.
- Yorum satırı `#` ile başlar.

```python
if 5 > 2:
    print("bes iki den buyuk")
```

## 4. Python Output
Ekrana yazmak için `print()` kullanılır.

```python
print("Merhaba")
print(40 + 2)
isim = "Yusif"
print("Ad:", isim)
```

## 5. Python Comments
```python
# tek satir yorum
"""
cok satirli
aciklama blogu
"""
```

## 6. Python Variables
- Tür yazmana gerek yok, değerden anlaşılır.
- İsimler harf / _ ile başlar, sayı ile başlamaz.

```python
ad = "Elvin"
yas = 19
boy = 1.78
aktif_mi = True

a, b, c = 1, 2, 3
x = y = 0
```

Global örneği:
```python
sayac = 0

def artir():
    global sayac
    sayac += 1
```

## 7. Python Data Types
Temel türler: `str, int, float, bool, list, tuple, set, dict, None`

```python
print(type("abc"))
print(type(10))
print(type(3.5))
print(type(True))
```

## 8. Python Numbers
- `int`: tam sayı
- `float`: ondalıklı
- `complex`: karmaşık

```python
t = 10
o = 2.5
print(t + o)
print(t // 3)
print(2 ** 4)
```

## 9. Python Casting
```python
print(int("42"))
print(float("3.5"))
print(str(100))
```

## 10. Python Strings
```python
m = "  merhaba dunya  "
print(m.strip())
print(m.upper())
print(m.replace("dunya", "python"))
print(m.split())

ad = "Ayse"
yas = 21
print(f"Ben {ad}, {yas} yasindayim")
print(m[2:7])
```

## 11. Python Booleans
```python
print(10 > 5)
print(bool(""))
print(bool([1]))
```

## 12. Python Operators
- Aritmetik: `+ - * / // % **`
- Karşılaştırma: `== != > < >= <=`
- Mantıksal: `and or not`
- Kimlik: `is, is not`
- Üyelik: `in, not in`

```python
puan = 75
gecti_mi = puan >= 50 and puan <= 100
print(gecti_mi)
print("a" in "ankara")
```

## 13. Python Lists
Sıralı, değiştirilebilir koleksiyon.

```python
meyveler = ["elma", "armut", "kiraz"]
meyveler.append("muz")
meyveler.remove("armut")
for m in meyveler:
    print(m)

kareler = [x*x for x in range(5)]
print(kareler)
print(sorted(meyveler))
```

## 14. Python Tuples
Sıralı ama değiştirilemez.

```python
renkler = ("kirmizi", "mavi", "yesil")
print(renkler[1])
a, b, c = renkler
print(a, b, c)
```

## 15. Python Sets
Tekrarsız koleksiyon.

```python
sayilar = {1, 2, 2, 3}
sayilar.add(4)
sayilar.discard(1)
print(sayilar)
```

## 16. Python Dictionaries
Anahtar-değer yapısı.

```python
kisi = {"ad": "Veli", "yas": 25}
kisi["sehir"] = "Baku"
for k, v in kisi.items():
    print(k, ":", v)
```

İç içe:
```python
sinif = {
  "ogr1": {"ad": "Ali", "not": 90},
  "ogr2": {"ad": "Zara", "not": 85}
}
print(sinif["ogr1"]["not"])
```

## 17. Python If...Else
```python
notum = 68
if notum >= 90:
    print("AA")
elif notum >= 70:
    print("BB")
else:
    print("kaldi ya da dusuk")

# kisa yazim
durum = "gecti" if notum >= 50 else "kaldi"
```

## 18. Python Match
Python 3.10+

```python
gun = "pazar"
match gun:
    case "pazartesi":
        print("hafta basi")
    case "pazar":
        print("tatil")
    case _:
        print("normal gun")
```

## 19. Python While Loops
```python
i = 0
while i < 3:
    print(i)
    i += 1
```

## 20. Python For Loops
```python
for i in range(3):
    print(i)

for harf in "python":
    print(harf)
```

## 21. Python Functions
```python
def topla(a, b=10):
    return a + b

print(topla(5))
print(topla(5, 20))

def liste_topla(*sayilar):
    return sum(sayilar)

print(liste_topla(1, 2, 3, 4))
```

Lambda:
```python
iki_kat = lambda x: x * 2
print(iki_kat(7))
```

## 22. Python Classes / Objects
```python
class Ogrenci:
    def __init__(self, ad, yas):
        self.ad = ad
        self.yas = yas

    def tanit(self):
        return f"Ben {self.ad}, {self.yas} yasindayim"

o = Ogrenci("Nigar", 20)
print(o.tanit())
```

Inheritance:
```python
class MezunOgrenci(Ogrenci):
    def __init__(self, ad, yas, yil):
        super().__init__(ad, yas)
        self.yil = yil

m = MezunOgrenci("Orhan", 23, 2025)
print(m.tanit(), m.yil)
```

Polymorphism / Encapsulation örneği:
```python
class Kedi:
    def ses(self):
        return "miyav"

class Kopek:
    def ses(self):
        return "hav"

for h in [Kedi(), Kopek()]:
    print(h.ses())

class Kasa:
    def __init__(self):
        self.__bakiye = 0
    def ekle(self, miktar):
        self.__bakiye += miktar
    def goster(self):
        return self.__bakiye
```

## 23. File Handling
```python
# yaz
with open("not.txt", "w", encoding="utf-8") as f:
    f.write("merhaba\n")

# oku
with open("not.txt", "r", encoding="utf-8") as f:
    print(f.read())
```

## 24. Python Try...Except
```python
try:
    print(int("abc"))
except ValueError:
    print("sayiya cevrilemedi")
finally:
    print("bitti")
```

## 25. Python User Input
```python
ad = input("Adin ne? ")
print(f"Merhaba {ad}")
```

## 26. Python Modules / Dates / Math / JSON
```python
import math, datetime, json

print(math.sqrt(16))
print(datetime.date.today())

veri = {"ad": "Ali", "yas": 30}
metin = json.dumps(veri)
print(metin)
print(json.loads(metin))
```

---
Sonraki dosya: `02-python-ileri.md` (dosya islemleri detay, virtualenv, pip, regex, oop detay) eklenecek.
