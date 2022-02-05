# Dil Spesifikasyonu

## Veri Tipleri

### Yazı

```py
"Bu bir yazı\n"
'Merhaba, Dünya!\n'
```

### Sayı

```py
10328
142.32
```

### Boolean

```py
doğru
yanlış
```

### Hiç

```py
hiç
```

### Blok
```py
blok blok-adı
  3 -> a
  5 -> b
son
```

## Anahtar Kelimeler

### yükle
bir modülü içe aktarır veya dahil eder; ya da bir modülün içindekileri kapsam içine alır.
#### Dahil etme
Dahil etmeyi modüldeki kodu kopyalayıp yapıştırmaya benzetebilirsiniz.
```py
yükle "benim-modülüm"* # yıldıza dikkat
```
#### İçe Aktarma
içe aktarma dahil etmeden farklı olarak adlı modüller dediğimiz parçaları oluşturur.
böyle kullanıldıklarında onları adları altında kullanabilirsiniz.
Özellikle üçüncü parti modüllerlerle ilgilenirken, bunu kullanmanızı tavsiye ederiz.
```py
yükle "benim-modulüm" -> benim-modulüm
# "benim-modülüm" modulünü benim-modulüm adlı değişkene koyar.
```

#### Kapsam İçine Alma
```py
yükle "mat.trl" -> mat # tests/ klasöründen mat.trl
yükle (mat:faktoriyel) # mat'taki faktoriyel'i kapsam içine getirir.
4 faktoriyel de
```
##### Stdout
```
24
```
> Not: kapsam içine alırken tanımlayıcı:`*` durumunda tanımlayıcı'nın içindeki herşey kapsama alınır.

### de
bir değişkeni ekrana yazdırmak için kullanılır
```py
"Merhaba, Dünya!\n" de
1232 de ' ' de
doğru de
```
#### Stdout
```stdout
Merhaba, Dünya!
1232 doğru
```

### kpy
bir değişkeni kopyalar
```py
10 kpy de de # 10 10 de de ile aynı
```

### ise
tr-lang'daki if ifadesi
koşulları kontrol etmek için kullanılır
```py
10 > 0 ise
  "Merhaba\n" de
son
```

### iken
tr-lang'da while ifadesi
bir koşula göre tekrarla
```py
10
:. kpy > 0 iken
  kpy de '\n' de --
son at
```
#### Stdout
```
10
9
8
7
6
5
4
3
2
1
```

### yoksa
tr-lang'da else ifadesi
kontrol edilen koşullar geçersizse birşeyler yap
```py
10 < 0 ise
  "Buraya nasıl geldik?\n" de
yoksa
  "Evren hala çalışıyor!\n" de
son
```

### işlev
tr-lang'da işlevler
işlevler çağırılabilen, yeniden kullanılabilir kod parçalarıdır.
Kendi küme ve ad alanlarına sahiplerdir.
stackteki son değişkeni `ver` anahtar kelimesi ile geri verebilirler.
```py
işlev kadar-topla -> a
  a > 0 ise
    a + (a --)kadar-topla ver
  yoksa
    0 ver
  son
son

5 kadar-topla de "\n" de
```

#### Stdout
```
15
```

### ver
kümedeki son değişkeni bir fonksiyondan geri verir
> Kod örneği için yukarıdaki işlev'e göz atın

### son
ise-yoksa, iken, blok<sup>(kafa karıştırıcı değil mi?)</sup> veya işlev bloğunu bitirir

### üst
sondan ikinci değişkeni kopyalar
```py
10 5 üst -* 10 5 10 la aynı *-
```

### tks
son değişkeni sondan ikinci değişkenle takas eder
```py
32 64 tks -* 64 32 yle aynı *-
```

### girdi
kullanıcıdan yazı olarak bir yanıt al
```py
"Adın ne? " de girdi -* Terminal: Adın ne? [kullanıcıdan alınan yanıt] *-
"Adın " de de ".\n" de -* Terminal: Adın [kullanıcıdan alınan yanıt]. *-
```

### dön
son üç değişkeni döndürür
```py
10 20 30 dön -* 30 20 10 la aynı *-
```

### at
kümedeki son değeri siler
```py
3 at de
```
#### Stderr
```

[HATA] <DOSYA>, Satır 1, Sütun 8
    KümedeYeterliDeğişkenYok: kümede yeterli değişken bulunmadığından dolayı `de` operatörü uygulanamamıştır
```

## Operatörler

### Matematik

#### Artı
sadece bir toplama operatörü. ama yazılarıda birleştirebilir.
```py
40 + 20 de "\n" de
"a" + "b" de
```

##### Stdout
```
60
ab
```

#### Tire
çıkarma operatörü
```py
40 - 20 de
```

##### Stdout
```
20
```

#### Yıldız
çarpma operatörü
```py
40 * 20 de
```

##### Stdout
```
800
```

#### Eğik Çizgi
bölme operatörü
```py
40 / 20 de
```

##### Stdout
```
2
```

#### Yüzdelik işareti
kalan operatörü
```py
40 % 20 de '\n' de
30 % 20 de
```

##### Stdout
```
0
10
```

### Karşılaştırma

#### Eşitlik
İki değerin eşitliğini kontrol eder
```py
10 = 10 de '\n' de
10 = 11 de
```
##### Stdout
```
doğru
yanlış
```

#### Eşit Değişldir
İki değerin eşit **olmadığını** kontrol eder
```py
10 != 10 de '\n' de
10 != 11 de
```
##### Stdout
```
yanlış
doğru
```

#### Büyüktür
a'nın b'den büyük olup olmadığını kontrol eder
```py
10 > 9 de '\n' de
10 > 11 de
```
##### Stdout
```
doğru
yanlış
```

#### Büyük veya Eşittir
a'nın b'den büyük veya b'ye eşit olup olmadığını kontrol eder
```py
10 >= 10 de '\n' de
10 >= 11 de
```
##### Stdout
```
doğru
yanlış
```

#### Küçüktür
a'nın b'den küçük olup olmadığını kontrol eder
```py
10 < 11 de '\n' de
10 < 9 de
```
##### Stdout
```
doğru
yanlış
```

#### Küçüktür veya Eşittir
a'nın b'den küçük veya b'ye eşit olup olmadığını kontrol eder
```py
10 <= 9 de '\n' de
10 <= 10 de
```
##### Stdout
```
yanlış
doğru
```

#### Değildir
olumsuzlaştırma operatörü
```py
!yanlış de '\n' de
!doğru de
```
##### Stdout
```
doğru
yanlış
```

#### Ve
ve operatörü
```py
doğru ve doğru de '\n' de
yanlış ve doğru de
```
##### Stdout
```
doğru
yanlış
```

#### veya
veya operator
```py
yanlış veya doğru de '\n' de
yanlış veya yanlış de
```
##### Stdout
```
doğru
yanlış
```

### Atama
atama operatörü kümedeki son değişkeni bir tanımlayıcıya atar
```py
10 -> a
5 -> b
a de '\n' de
b de '\n' de
a + b de
```
#### Stdout
```
10
5
15
```

### Tip Değiştirme
veri tipleri arasında değişim yapmak için bir operatör
```py
3@yazı = '3' de
0@bool de
```
#### Stdout
```
doğru
yanlış
```

### Erişim
bir blok ya da adlı modülün değerlerine erişmek için yapılmış bir operatör
```py
yükle "mat.trl" -> matematik # tests/ klasöründen mat.trl
blok benim-bloğum
  3 -> a
  5 -> b
son
benim-bloğum:a de '\n' de
benim-bloğum:b de '\n' de
4 matematik:faktoriyel
```
#### Stdout
```
3
5
24
```

## Yorumlar

### Blok Yorumları
bir blok yorumu `-*` ile başlar ve `*-` ile biter.
```
-* Bu tr-lang tarafından umursanmayacaktır *
 * "Bu bir şey yapmayacak" de              *-
```

### Satır Yorumları
bir satır yorumu `#` ile başlar. satır sonuna kadar devam eder.
```py
# evet, yine umursanmayacak
```

