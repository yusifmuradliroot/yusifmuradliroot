# Python Notlarım - Bölüm 1: Temeller (Uzun Anlatım)

> Bu dosya özgün olarak hazırlandı. Konu sırası W3Schools Python içeriğindeki başlık sırası örnek alınarak kuruldu. Başlıklar aynı olabilir, çünkü konu isimleri herkese aittir. Ama aşağıdaki anlatım, benzetmeler, örnekler ve alıştırmalar yeniden yazıldı. W3Schools metninin kopyası değildir. Telefonunda offline okuyabilirsin.

Nasıl çalışacaksın:
1. Her başlığı sırayla oku.
2. Kodu kafanda canlandır, sonra telefonda / bilgisayarda dene.
3. Her başlığın sonundaki "Kendin dene" mini görevini yapmadan geçme.

---

## 1. Python Intro

Python nedir, neden kolay?

Python'u mutfak tarifi gibi düşün. Adım adım, sade dille yazarsın. Bilgisayar da o tarifi harfi harfine uygular.

Neden yeni başlayanlar seviyor:
- Okuması neredeyse Türkçe-İngilizce karışımı cümle gibi: `if yas > 18:` demek "eğer yaş 18'den büyükse" demek.
- Girinti zorunluluğu var. Bu ilk başta gıcık eder ama kodun düzenli görünmesini sağlar.
- Çok iş yapar: web sitesi arka planı, otomasyon scripti, veri analizi, oyun, yapay zeka denemeleri.

Küçük bir tat:
```python
isim = "Aylin"
print("Merhaba", isim)
```

Burada iki şey oldu: bir kutu açıp içine "Aylin" koyduk (`isim` değişkeni), sonra ekrana yazdırdık.

Sık karıştırılan: Python derlenmez, yorumlanır. Yani `python3 dosyam.py` dediğinde Python satır satır okuyup çalıştırır. Hata varsa hatanın olduğu satırda durur.

Kendin dene:
- Kafandan bir cümle kur: "Benim adım X, Python öğreniyorum" ve bunu `print` ile nasıl yazardın düşün.

## 2. Python Get Started

Kurulum mantığı 3 adım:

1. Python 3 kur. Bilgisayarda python.org'dan, telefonda Termux / Pydroid / QPython gibi uygulamadan.
2. Sürümü kontrol et:
```
python3 --version
```
`Python 3.11.4` gibi bir şey görmen lazım. Eğer `python` komutu çalışmıyorsa `python3` dene.

3. İlk dosyanı çalıştır. `deneme.py` diye dosya aç, içine şunu yaz:
```python
print("ilk adim")
```
Sonra terminalde:
```
python3 deneme.py
```

Telefonda çalışıyorsan: Pydroid'de kodu yazıp Run üçgenine basman yeterli.

Sık hata:
- Dosyayı `deneme.txt` diye kaydetmek. Uzantı `.py` olmalı.
- Türkçe karakterli klasör yolunda çalışmak bazen eski Windows'ta sorun çıkarır. Klasör adını İngilizce yap: `python-calismalarim` gibi.

Kendin dene:
- `merhaba.py` oluştur, iki satır `print` yaz, çalıştır.

## 3. Python Syntax

Python'da süslü parantez yok, girinti var. Girinti = anlam.

Yanlış:
```python
if 10 > 5:
print("buyuk")
```
Bu çalışmaz. Python "bu print kime ait?" diye sorar.

Doğru:
```python
if 10 > 5:
    print("buyuk")
    print("hala if'in icindeyim")
print("artik if bitti")
```

Kurallarım:
- Aynı blokta hep aynı girinti: hep 4 boşluk kullan. Tab ile boşluğu karıştırma.
- `:` gördüysen sonraki satır girintili olacak. `if ...:`, `for ...:`, `def ...:`, `while ...:` hep böyle.
- Büyük-küçük harf farklıdır: `Ad` ile `ad` ayrı kutudur.

Bir de deyim (statement) kavramı: tek satırlık emir. Uzun satırı bölmek istersen parantez kullan:
```python
toplam = (10 + 20 +
          30 + 40)
```

Kendin dene:
- Bilerek girintisiz yazıp hatayı gör, sonra düzelt. Hata mesajını okumaya alış.

## 4. Python Output

`print()` ekrana yazmanın kapısıdır. İçine ne koyarsan onu gösterir.

```python
print("Elma")
print(25)
print(10 + 15)
```

Birden fazla şeyi virgülle verebilirsin, araya boşluk koyar:
```python
ad = "Mert"
yas = 22
print("Ad:", ad, "Yas:", yas)
# Ad: Mert Yas: 22
```

Tırnak işi:
- `"elma"` ile `'elma'` aynıdır.
- İçinde tırnak geçecekse tersini kullan: `"Ali'nin kedisi"` ya da `'O "merhaba" dedi'`.

`sep` ve `end` iki gizli ayar:
```python
print("a", "b", "c", sep="-")
# a-b-c
print("merhaba", end=" ")
print("dunya")
# merhaba dunya (alt satira gecmedi)
```

Sayı basmak:
```python
print(40 + 2)
print("40 + 2")  # bu toplama yapmaz, yazi olarak basar
```

Kendin dene:
- Adını, yaşını, sevdiğin yemeği üç ayrı `print` ile yazdır. Sonra tek `print` ile `sep=" | "` kullanarak yazdır.

## 5. Python Comments

Yorum = bilgisayara değil, insana not. Python `#` gördüğü yeri çalıştırmaz.

```python
# bu satir calismaz, sadece not
fiyat = 100  # buraya da not yazabilirsin
```

Neden yazıyoruz?
- 2 hafta sonra kendi kodunu unutuyorsun. Yorum hatırlatır.
- Başkasıyla çalışırken niyetini belli eder.

Çok satırlı not için üç tırnak kullanılır. Aslında bu teknik olarak string'dir ama değişkene atanmazsa yorum gibi durur:
```python
"""
Yapilacaklar:
- fiyati hesapla
- kdv ekle
"""
```

Benim alışkanlığım: "neden" yaz, "ne" değil. Kötü: `# x'i 1 artir`, x+=1 zaten belli. İyi: `# sepette en az 1 urun olmali, o yuzden 1'den basliyoruz`.

Kendin dene:
- Dünkü yazdığın koda 2 satır yorum ekle.

## 6. Python Variables

Değişken = etiketli kutu. `ad = "Elvin"` demek "üzerinde ad yazan kutuya Elvin koy" demek.

```python
ad = "Elvin"
yas = 19
boy = 1.78
ogrenci_mi = True
```

Python türü sen yazmadan anlar. Buna dinamik tipleme denir. Kutunun içindeki değişince tür de değişebilir:
```python
x = 10
print(type(x))  # int
x = "on"
print(type(x))  # str
```

İsim kuralları:
- Harf ya da _ ile başla: `ad`, `_gizli`, `not1` olur. `1not` olmaz.
- Boşluk olmaz: `ad soyad` yasak, `ad_soyad` serbest.
- Büyük-küçük duyarlı.

Toplu atama:
```python
a, b, c = 5, 10, 15
print(a, b, c)

x = y = z = 0
print(x, y, z)
```

Değişkeni ekrana basma:
```python
sehir = "Izmir"
print("Sehir:", sehir)
```

Global - local farkı çok önemli:
```python
sayac = 0  # global, her yerden gorunur

def artir():
    sayac = 5  # bu local, sadece fonksiyon icinde yasar
    print(sayac)

artir()  # 5
print(sayac)  # 0, disardaki degismedi
```

Dışardakini değiştirmek istersen:
```python
puan = 0

def puan_ekle():
    global puan
    puan += 10

puan_ekle()
print(puan)  # 10
```

`global` anahtarını gereksiz kullanma, kodu karıştırır. Fonksiyon genelde `return` ile değer döndürmeli.

Kendin dene:
- `urun`, `fiyat`, `adet` değişkenleri yap, toplam fiyatı hesaplayıp bas.

## 7. Python Data Types

Her veri bir türdür. Türü bilmek, ne yapabileceğini bilmektir. Sayı ile yazıyı toplayamazsın mesela.

Temel türler:
- `str`: yazı. `"merhaba"`
- `int`: tam sayı. `42`
- `float`: ondalıklı. `3.14`
- `bool`: `True / False`
- `list`: sıralı, değişir. `[1, 2, 3]`
- `tuple`: sıralı, değişmez. `(1, 2)`
- `set`: sırasız, tekrarsız. `{1, 2}`
- `dict`: anahtar-değer. `{"ad": "Ali"}`
- `NoneType`: boş / yok. `None`

Türü öğren:
```python
print(type("abc"))
print(type(100))
print(type(2.5))
print(type(True))
print(type([1, 2]))
print(type(None))
```

Bellek benzetmesi: `str` harf kutusu, `int` tam sayı kutusu. Kutuyu yanlış kullanırsan Python bağırır:
```python
# print("yas: " + 20)  # hata verir
print("yas: " + str(20))  # dogrusu
```

Kendin dene:
- 5 farklı türde değişken yapıp `type()` ile kontrol et.

## 8. Python Numbers

Üç sayı türü var:

```python
tam = 25        # int
ondalik = 2.5   # float
karmasik = 2 + 3j  # complex, genelde kullanmazsin
```

İşlemler:
```python
a = 10
b = 3
print(a + b)   # 13
print(a - b)   # 7
print(a * b)   # 30
print(a / b)   # 3.333...
print(a // b)  # 3, tam bolme
print(a % b)   # 1, kalan
print(a ** b)  # 1000, us
```

Klasik tuzak: `/` hep float verir. `10 / 2` sonucu `5.0` olur, `5` değil.

Yuvarlama:
```python
print(round(3.678, 2))  # 3.68
```

Rastgele sayı ileride lazım olur:
```python
import random
print(random.randint(1, 6))  # zar gibi
```

Kendin dene:
- Vize %40 final %60 etki eden not hesabı yap. `vize=70, final=80` için ortalama hesapla.

## 9. Python Casting

Casting = tür dönüştürme. Kullanıcıdan gelen her şey yazıdır, hesap için sayıya çevirmen lazım.

```python
print(int("42"))      # 42
print(float("3.5"))   # 3.5
print(str(100))       # "100"
```

Gerçek hayat:
```python
# input hep string verir
yas_yazi = "21"
yas = int(yas_yazi)
print(yas + 1)  # 22
```

Hata veren haller:
```python
# int("3.9") hata verir, once float yapman lazim
print(int(float("3.9")))  # 3
```

Bool'a çevirme mantığı:
- Boş olanlar `False`: `""`, `0`, `[]`, `{}`, `None`
- Dolu olanlar `True`

Kendin dene:
- `input()` ile yaşını alıp `int()` ile çevir, 10 yıl sonrasını bas.

## 10. Python Strings

String = tırnak içindeki her şey. Python'da yazı ile çalışmak çok rahattır.

Temel:
```python
mesaj = "  Merhaba Dunya  "
print(mesaj.strip())      # bas-son bosluklari at
print(mesaj.lower())      # kucuk harf
print(mesaj.upper())      # buyuk harf
print(mesaj.replace("Dunya", "Python"))
print(mesaj.split())      # kelimelere bol
```

Dilimleme (slicing) mantığı: `[baslangic:bitis]`, bitis dahil değil.
```python
kelime = "python"
print(kelime[0])    # p
print(kelime[1:4])  # yth
print(kelime[:3])   # pyt
print(kelime[3:])   # hon
print(kelime[-1])   # n, sondan
```

Birleştirme:
```python
ad = "Ayse"
soyad = "Demir"
tam = ad + " " + soyad
print(tam)
```

Modern yazım f-string, bunu alışkanlık yap:
```python
ad = "Ayse"
yas = 21
print(f"Ben {ad}, {yas} yasindayim")
print(f"Gelecek yil {yas + 1} olacagim")
```

Kaçış karakterleri:
- `\n` yeni satır, `\t` tab, `\"` tırnak içinde tırnak.

Uzunluk:
```python
print(len("merhaba"))  # 7
```

Kendin dene:
- Adını ters çevirmeden son 3 harfini dilimle. `len()` ile uzunluğunu bul.

## 11. Python Booleans

Bool sadece iki değer: `True` / `False`. Kararların temelidir.

```python
print(10 > 5)   # True
print(10 == 5)  # False
```

`bool()` ile test:
```python
print(bool("merhaba"))  # True
print(bool(""))         # False, bos yazi
print(bool(0))          # False
print(bool(100))        # True
print(bool([]))         # False, bos liste
print(bool([1]))        # True
```

`if` ile kullanımı:
```python
sifre_girildi_mi = True
if sifre_girildi_mi:
    print("giris yapabilirsin")
```

Sık hata: `True`, `False` büyük harfle başlar. `true` yazarsan hata verir.

Kendin dene:
- Yaşın 18'den büyük mü diye bool sonuç bas.

## 12. Python Operators

Operatörleri 6 grupta ezberle, tek tek değil:

1. Aritmetik: `+ - * / // % **`
2. Atama: `= += -= *= /=`
3. Karşılaştırma: `== != > < >= <=`
4. Mantıksal: `and or not`
5. Kimlik: `is / is not`
6. Üyelik: `in / not in`

Örnekler:
```python
sayi = 10
sayi += 5  # sayi = sayi + 5 demek, sonuc 15
print(sayi)

puan = 75
sart = puan >= 50 and puan <= 100
print(sart)  # True

print("a" in "ankara")  # True
print("z" not in "ankara")  # True
```

`==` ile `is` farkı:
- `==` değere bakar: `10 == 10.0` True'dur.
- `is` aynı kutu mu diye bakar. Küçük sayılarda şaşırtır, genelde `None` kontrolünde kullan:
```python
sonuc = None
if sonuc is None:
    print("henuz yok")
```

Öncelik sırası: parantez > üs > çarpma/bölme > toplama/çıkarma > karşılaştırma > not > and > or. Emin olamıyorsan parantez koy.

```python
print(2 + 3 * 4)      # 14
print((2 + 3) * 4)    # 20
```

Kendin dene:
- Kullanıcı adı "admin" VE şifre "1234" ise giriş başarılı diyen kod yaz.

## 13. Python Lists

Liste = sıralı, değiştirilebilir sepet. En çok kullanacağın yapı.

```python
meyveler = ["elma", "armut", "kiraz"]
print(meyveler[0])   # elma
print(meyveler[-1])  # kiraz, sondan
```

Ekleme / çıkarma:
```python
sepet = ["elma"]
sepet.append("muz")        # sona ekle
sepet.insert(0, "cilek")   # basa ekle
sepet.remove("elma")       # degerle sil
son = sepet.pop()          # sondakini al ve sil
print(sepet, son)
```

Döngü:
```python
for m in meyveler:
    print("seviyorum:", m)
```

Dilimleme listede de var:
```python
sayilar = [0, 1, 2, 3, 4, 5]
print(sayilar[1:4])  # [1, 2, 3]
```

Liste üretmenin kısa yolu:
```python
kareler = [x*x for x in range(5)]
print(kareler)  # [0, 1, 4, 9, 16]
```

Sıralama / ters çevirme:
```python
adlar = ["veli", "ali", "zara"]
print(sorted(adlar))  # yeni sirali liste verir
adlar.sort()          # yerinde siralar
print(adlar)
```

Kopya tuzağı: `yeni = eski` demek iki etiket aynı sepete yapışır. Birini değiştirince öteki de değişir.
```python
a = [1, 2]
b = a
b.append(3)
print(a)  # [1, 2, 3] oldu!
# dogrusu:
c = a.copy()
```

Kendin dene:
- 5 arkadaş ismi listesi yap, birini sil, birini ekle, alfabetik bas.

## 14. Python Tuples

Tuple = değişmeyen liste. Parantezle yazılır.

```python
renkler = ("kirmizi", "mavi", "yesil")
print(renkler[1])
```

Neden var? Bazı şeyler sabit olmalı: günler, koordinatlar, ayarlar. Yanlışlıkla değişmesin istiyorsun.

Paket açma çok kullanılır:
```python
a, b, c = renkler
print(a, b, c)
```

Tek elemanlı tuple'da virgül şart:
```python
t1 = ("elma")   # bu string!
t2 = ("elma",)  # bu tuple
print(type(t1), type(t2))
```

Değiştirmek istersen listeye çevir:
```python
t = (1, 2, 3)
liste = list(t)
liste.append(4)
t = tuple(liste)
print(t)
```

Kendin dene:
- Doğum tarihin (gün, ay, yıl) tuple yapıp açarak bas.

## 15. Python Sets

Set = tekrarsız torba. Sıra önemli değil, tekrar önemli.

```python
sayilar = {1, 2, 2, 3, 3, 3}
print(sayilar)  # {1, 2, 3}
```

Ekleme / silme:
```python
s = {1, 2}
s.add(3)
s.discard(2)  # yoksa hata vermez
# s.remove(99)  # bu hata verirdi
print(s)
```

Kesişim-birleşim çok pratik:
```python
a = {"ali", "veli", "zara"}
b = {"zara", "mert"}
print(a & b)  # kesisim: {'zara'}
print(a | b)  # birlesim
print(a - b)  # fark
```

Listede tekrarları temizleme hilesi:
```python
kirli = [1, 1, 2, 3, 3, 4]
temiz = list(set(kirli))
print(temiz)
```

Kendin dene:
- İki arkadaş grubun ortak arkadaşlarını `&` ile bul.

## 16. Python Dictionaries

Dict = etiketli dolap. Anahtar verirsin, değer alırsın.

```python
kisi = {"ad": "Veli", "yas": 25, "sehir": "Baku"}
print(kisi["ad"])
print(kisi.get("meslek", "yok"))  # hata vermez, varsayilan verir
```

Ekleme / güncelleme / silme:
```python
kisi["meslek"] = "ogrenci"
kisi["yas"] = 26
kisi.pop("sehir")
print(kisi)
```

Döngü:
```python
for anahtar, deger in kisi.items():
    print(anahtar, ":", deger)
```

İç içe dict gerçek hayattır:
```python
sinif = {
  "ogr1": {"ad": "Ali", "not": 90},
  "ogr2": {"ad": "Zara", "not": 85}
}
print(sinif["ogr1"]["not"])
```

Liste + dict karışımı:
```python
urunler = [
  {"ad": "ekmek", "fiyat": 10},
  {"ad": "sut", "fiyat": 30}
]
toplam = sum(u["fiyat"] for u in urunler)
print(toplam)
```

Kendin dene:
- Telefon rehberi dict yap: isim -> numara. Bir kişi ekle, birini sil, hepsini listele.

## 17. Python If...Else

Karar yapısı. "Eğer buysa şunu yap, değilse bunu yap."

```python
notum = 68
if notum >= 90:
    print("AA")
elif notum >= 70:
    print("BB")
elif notum >= 50:
    print("CC, gectin")
else:
    print("kaldin")
```

Kısa yazım:
```python
yas = 20
durum = "resit" if yas >= 18 else "resit degil"
print(durum)
```

Mantıksal bağlaçlarla:
```python
ad = "admin"
sifre = "1234"
if ad == "admin" and sifre == "1234":
    print("hosgeldin")
else:
    print("hatali")
```

İç içe if'i mümkünse düzleştir. Kötü:
```python
if yas >= 18:
    if para >= 100:
        print("alabilirsin")
```
Daha temiz:
```python
if yas >= 18 and para >= 100:
    print("alabilirsin")
```

`pass` boş blok için:
```python
if notum < 0:
    pass  # sonra dolduracagim
else:
    print(notum)
```

Kendin dene:
- Hava durumuna göre öneri veren kod: "yagmurlu" ise şemsiye, "güneşli" ise gözlük, diğer ise mont.

## 18. Python Match

`match` yeni nesil `if-elif` zinciri. Python 3.10+ gerekir. Menü gibi seçimlerde temiz durur.

```python
gun = "pazar"
match gun:
    case "pazartesi":
        print("hafta basi")
    case "cumartesi" | "pazar":
        print("hafta sonu")
    case _:
        print("hafta ici")
```

`_ ` demek "hiçbiri uymadıysa" demek.

Sayı ile:
```python
kod = 404
match kod:
    case 200:
        print("tamam")
    case 404:
        print("bulunamadi")
    case _:
        print("baska hata")
```

Eski sürümdeysen `if-elif` kullan, aynı işi yapar. `match` şart değil.

Kendin dene:
- 1-3 arası sayıya göre içecek öneren match yaz.

## 19. Python While Loops

`while` = şart doğru olduğu sürece tekrarla. Sayaçlı işlerde dikkat: artırmayı unutursan sonsuz döngü olur.

```python
i = 0
while i < 3:
    print(i)
    i += 1
```

Kullanıcıdan doğru girene kadar isteme:
```python
sifre = ""
while sifre != "1234":
    sifre = input("sifre: ")
print("giris ok")
```

`break` ve `continue`:
```python
n = 0
while True:
    n += 1
    if n == 3:
        continue  # 3'u atla
    if n > 5:
        break     # donguden cik
    print(n)
```

Sonsuz döngü tuzağı: telefonu kilitler gibi hissedersin. Pydroid'de stop düğmesi var. Bilgisayarda `Ctrl+C` ile durdurursun.

Kendin dene:
- 10'dan geriye sayan while yaz.

## 20. Python For Loops

`for` = koleksiyondaki her eleman için bir tur. En rahat döngü.

```python
for i in range(3):
    print(i)  # 0 1 2
```

`range` üç türlü:
```python
print(list(range(5)))        # 0-4
print(list(range(2, 6)))     # 2-5
print(list(range(0, 10, 2))) # 0 2 4 6 8
```

Liste, yazı, dict ile:
```python
for harf in "python":
    print(harf)

adlar = ["ali", "zara"]
for a in adlar:
    print("merhaba", a)
```

İndeks lazımsa:
```python
adlar = ["ali", "zara", "mert"]
for i, ad in enumerate(adlar):
    print(i, ad)
```

İç içe:
```python
for x in [1, 2]:
    for y in [10, 20]:
        print(x, y)
```

Kendin dene:
- 1-20 arası çift sayıları basan for yaz.

## 21. Python Functions

Fonksiyon = isimli tarif. Bir kez yaz, defalarca çağır.

```python
def selamla(ad):
    print(f"Merhaba {ad}")

selamla("Ali")
selamla("Zara")
```

Değer döndürme:
```python
def topla(a, b=10):
    return a + b

print(topla(5))     # 15, b varsayilan 10
print(topla(5, 20)) # 25
```

`*args` = istediğin kadar sayı:
```python
def liste_topla(*sayilar):
    return sum(sayilar)

print(liste_topla(1, 2, 3, 4))
```

Kapsam (scope) kuralı: fonksiyon içindeki değişken dışarı sızmaz.
```python
def hesap():
    sonuc = 100
    return sonuc

print(hesap())
# print(sonuc)  # hata, disaridan gorunmez
```

Lambda = tek satırlık mini fonksiyon:
```python
iki_kat = lambda x: x * 2
print(iki_kat(7))

# siralama anahtari olarak cok kullanilir
kisiler = [{"ad": "ali", "yas": 30}, {"ad": "zara", "yas": 20}]
kisiler.sort(key=lambda k: k["yas"])
print(kisiler)
```

Özyineleme (recursion) fikri:
```python
def faktoriyel(n):
    if n <= 1:
        return 1
    return n * faktoriyel(n-1)

print(faktoriyel(5))  # 120
```

Kendin dene:
- `ortalama(*notlar)` fonksiyonu yaz, 3 not verip sonucu bas.

## 22. Python Classes / Objects

Class = kalıp, object = kalıptan çıkan ürün. Kurabiye kalıbı gibi düşün.

```python
class Ogrenci:
    def __init__(self, ad, yas):
        self.ad = ad
        self.yas = yas

    def tanit(self):
        return f"Ben {self.ad}, {self.yas} yasindayim"

o1 = Ogrenci("Nigar", 20)
o2 = Ogrenci("Orhan", 23)
print(o1.tanit())
print(o2.tanit())
```

`__init__` ilk kurulum, `self` ise "bu ürünün kendisi" demek. `self.ad` = bu öğrencinin adı.

Miras (inheritance): hazır kalıbı genişletme.
```python
class MezunOgrenci(Ogrenci):
    def __init__(self, ad, yas, yil):
        super().__init__(ad, yas)
        self.yil = yil

m = MezunOgrenci("Orhan", 23, 2025)
print(m.tanit(), m.yil)
```

Çok biçimlilik (polymorphism): aynı isim, farklı iş.
```python
class Kedi:
    def ses(self):
        return "miyav"

class Kopek:
    def ses(self):
        return "hav"

for h in [Kedi(), Kopek()]:
    print(h.ses())
```

Kapsülleme (encapsulation): hassas bilgiyi saklama.
```python
class Kasa:
    def __init__(self):
        self.__bakiye = 0  # disaridan direk erisilmesin
    def ekle(self, miktar):
        if miktar > 0:
            self.__bakiye += miktar
    def goster(self):
        return self.__bakiye

k = Kasa()
k.ekle(100)
print(k.goster())
# print(k.__bakiye)  # hata verir, guzel
```

Kendin dene:
- `Kitap` class yap: ad, sayfa. `kalin_mi()` metodu sayfa > 300 ise True dönsün.

## 23. File Handling

Dosya ile çalışmanın güvenli yolu `with open(...)`. İş bitince dosyayı otomatik kapatır.

Yazma:
```python
with open("not.txt", "w", encoding="utf-8") as f:
    f.write("merhaba\n")
    f.write("ikinci satir\n")
```

Okuma:
```python
with open("not.txt", "r", encoding="utf-8") as f:
    icerik = f.read()
    print(icerik)
```

Satır satır:
```python
with open("not.txt", "r", encoding="utf-8") as f:
    for satir in f:
        print(satir.strip())
```

Modlar:
- `w`: sıfırdan yaz, eskisini siler. Dikkatli kullan.
- `a`: sona ekle, eskisini korur.
- `r`: sadece oku.

Ekleme örneği:
```python
with open("not.txt", "a", encoding="utf-8") as f:
    f.write("ucuncu satir\n")
```

Kendin dene:
- Alışveriş listeni dosyaya yazıp geri oku.

## 24. Python Try...Except

Hata olacak, önemli olan programın çökmemesi. `try` = dene, `except` = olursa bunu yap.

```python
try:
    print(int("abc"))
except ValueError:
    print("sayiya cevrilemedi")
finally:
    print("bitti, dosya kapatilir gibi isler buraya")
```

Birden fazla hata:
```python
try:
    a = int(input("sayi: "))
    print(10 / a)
except ValueError:
    print("sayi girmen lazim")
except ZeroDivisionError:
    print("sifira bolemezsin")
```

Kendi hatanı fırlatma:
```python
yas = -5
if yas < 0:
    raise ValueError("yas eksi olamaz")
```

Kendin dene:
- Kullanıcıdan iki sayı alıp bölen kod yaz, sıfıra bölmeyi ve yazı girmeyi yakala.

## 25. Python User Input

`input()` hep yazı döndürür. Bunu unutma, yoksa toplama yerine yanyana yazma yaparsın.

Hatalı:
```python
# a = input("sayi: ")  # "5" gelir
# print(a + 10)  # hata
```

Doğru:
```python
yas = int(input("Yasin: "))
print(f"10 yil sonra {yas + 10} olacaksin")
```

Güvenli alma kalıbı:
```python
while True:
    giris = input("0-100 arasi not: ")
    try:
        notum = int(giris)
        if 0 <= notum <= 100:
            break
        print("aralik disinda")
    except ValueError:
        print("sayi yaz")
print("notun:", notum)
```

Kendin dene:
- Adını ve sevdiğin rengi isteyip cümle kuran program yaz.

## 26. Python Modules / Dates / Math / JSON / PIP / VirtualEnv

Modül = başkasının yazdığı hazır alet kutusu. `import` ile alırsın.

```python
import math
print(math.sqrt(16))   # 4.0
print(math.pi)
```

Tarih:
```python
import datetime
bugun = datetime.date.today()
print(bugun)
print(bugun.year)
```

JSON = programların ortak dili. Sözlük gibi görünür.
```python
import json
veri = {"ad": "Ali", "yas": 30}
metin = json.dumps(veri)  # dict -> yazi
print(metin)
geri = json.loads(metin)  # yazi -> dict
print(geri["ad"])
```

Regex'e giriş:
```python
import re
metin = "telefonum 0555 123 45 67"
bul = re.search(r"\d+", metin)
print(bul.group())  # ilk sayi blogu
```

PIP = market. Hazır paket indirirsin:
```
pip install requests
```
```python
import requests
# r = requests.get("https://api.github.com")
# print(r.status_code)
```

VirtualEnv = her projeye ayrı oda. Paketler karışmasın diye:
```
python3 -m venv projem-env
source projem-env/bin/activate  # linux/mac
# projem-env\Scripts\activate  # windows
pip install requests
```

Benim önerim: her yeni proje için yeni venv aç. Global'e paket kurma.

Kendin dene:
- `math` ile dairenin alanını hesapla: `pi * r * r`. Yarıçapı input ile al.

---

Bu bölüm bitti. Sıradaki dosya önerim: `02-python-ileri.md` içinde dosya silme, `os` modülü, daha fazla oop, hata ayıklama alışkanlıkları.
