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
## Anahtar Kelimeler

### de
verş tiplerini ekrana yazmak için kullanılır
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
10 kpy de de
```

### ise
tr-lang'da if ifadesi
koşulları kontrol etmek için kullanılır
```py
10 0 > ise
  "Merhaba\n" de
son
```

### iken
tr-lang'da while ifadesi
bir koşula göre tekrarla
```py
10
:. kpy 0 > iken
  kpy de --
son
```

### yoksa
tr-lang'da else ifadesi
kontrol edilen koşullar geçersizse birşeyler yap
```py
10 0 < ise
  "Buraya nasıl geldik?\n" de
yoksa
  "Evren hala çalışıyor!\n" de
son
```

### işlev
tr-lang'da işlevler
işlevler çağırılabilen, yeniden kullanılabilir kod parçalarıdır.
Ancak çoğu diğer programlama dilinin aksine tr-lang fonksiyonları argüman almaz.
Özel argümanlar almak yerine, programın herhangi diğer yanı gibi stackle etkileşime girebilirler.
```py
işlev kadar-topla
  kpy 0 > ise
    kpy -- recursive-sum-up-to +
  son
son

5 kadar-topla de "\n" de
```

#### Stdout
```
15
```

### son
ise-yoksa, iken veya işlev bloğunu bitirir

## Commentler
kodunuzu nasıl commentlersiniz? sadece `-*` ile bir blok comment başlatın ve `*-` ile sonlandırın
```
-* Bu tr-lang tarafından görmezden gelinecek *-
-* "Bu hiç bir şey yapmayacak" de *-
```
