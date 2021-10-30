---
hide:
  - toc
---

# tr-lang
#### <center>Hızlı ve Kolay</center>
<hr style="width: 50%; margin: 0 auto; border-top: 1px solid;">

### ❤️ ile 🇹🇷 de yapılmıştır


tr-lang programlama dili sözdizimini Türkçeye yaklaştırmayı amaçlayan bir programlama dilidir.
tr-lang küme(stack) orantılı bir dil ve matematik için ters leh notasyonu kullanıyor.

# :triangular_flag_on_post: İçindekiler
- [:trophy: Dilin Hangi Parçaları Tamamlandı?](#dilin-hangi-parçaları-tamamlandı)
- [:memo: Komutlar](#komutlar)
- [:rocket: İndirme](#i̇ndirme)
- [:handshake: Katkıda Bulunma](#katkıda-bulunma)
- [:scroll: Teşekkürler](#teşekkürler)

# :trophy: Dilin Hangi Parçaları Tamamlandı?

## ✔️ Dilin tüm parçaları tamamlanmış gözüküyor!

#### ✔️ tr-lang lexer'ı bitmiş gibi gözüküyor [İssue #1](https://github.com/kaiserthe13th/tr-lang/issues/1#issue-1027652152)<br>
#### ✔️ tr-lang parser'ı bitmiş gibi gözüküyor [İssue #2](https://github.com/kaiserthe13th/tr-lang/issues/2#issue-1027660436)<br>
#### ✔️ tr-lang bytecode bitmiş gibi gözüküyor [İssue #3](https://github.com/kaiserthe13th/tr-lang/issues/3#issue-1027661753)<br>
#### ✔️ tr-lang bytecode okuyucu bitmiş gibi gözüküyor [İssue #4](https://github.com/kaiserthe13th/tr-lang/issues/4#issue-1027663331)<br>
#### ✔️ tr-lang çalışma zamanı bitmiş gibi gözüküyor [İssue #5](https://github.com/kaiserthe13th/tr-lang/issues/5#issue-1027665033)<br>

## :memo: Komutlar

* `tr-lang y <dosya>` - Dosyayı direkt çalıştır.
* `tr-lang b <dosya> [-o <çıktı-dosyası>]` - dosya için bytecode oluştur ve eğer belirtildiyse `çıktı-dosyası`na yoksa `dosya.byt`ye koy.
* `tr-lang yb <bytecode>` - bytecode'dan çalıştır.
* `tr-lang -h` - Yardım mesajı yaz ve çık.

# :rocket: İndirme

## :beer: Homebrew
Homebrew kullanarak indirebilirsiniz
```console
$ brew tap kaiserthe13th/tr-lang
$ brew install tr-lang
```

## :package: Cargo
```console
$ cargo install tr-lang
```

## :gear: Kaynaktan Derleme
gereksinimler: `rust, cargo`
```console
$ git clone https://github.com/kaiserthe13th/tr-lang
$ cd tr-lang
$ cargo build --release
```
dosyanız `target/release/tr-lang`'da bulunacaktır

# :handshake: Katkıda Bulunma
bug raporlamak, yeni özellik tavsiye etmek veya dokümantasyonu güncellemek için [issue takipçisini](https://github.com/kaiserthe13th/tr-lang/issues) kullanın.

özellikler için <span class="tag">`(enhancement | yükseltme)`</span> etiketini, buglar için <span class="tag">`(bug)`</span> etiketini ve dokümantasyon güncellemeleri için <span class="tag">`(documentation | dökümantasyon)`</span> etiketini kullanın

:+1: Bugfix PR'lerine açığız!

# :scroll: Teşekkürler

stackoverflow.com'dan [Netwave](https://stackoverflow.com/users/1695172/netwave) adlı kullanıcıya parser yapım sürecinde yaşanan bir [bug'ın](https://stackoverflow.com/questions/69635458/pattern-matching-does-not-allow-me-to-change-values/69636181#69636181) çözümündeki yardımından dolayı teşekkürlerimi sunarım.

