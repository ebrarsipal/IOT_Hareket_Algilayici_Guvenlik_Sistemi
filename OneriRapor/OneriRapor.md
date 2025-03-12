# Proje Konusu

Bu proje, Raspberry Pi Pico W mikrodenetleyicisi ve PIR (Passive Infrared) sensörü kullanarak bir hareket algılama sistemi geliştirmeyi amaçlamaktadır. Sistemde, PIR sensör hareket algıladığında, Raspberry Pi Pico W Telegram botu üzerinden bir mesaj gönderecektir. Bu mesaj, kullanıcının Telegram hesabına iletilecek olup, hareketin tespit edildiğini bildirecektir. Bu tür bir sistem, güvenlik uygulamaları, akıllı ev projeleri veya çevre izleme projelerinde kullanılabilir.

# Proje Hedefleri

## Proje Amaçları:

  - Raspberry Pi Pico W ve PIR sensörünü kullanarak hareket algılama sistemi kurmak.
  - Telegram API ile entegre edilen bir bot oluşturmak.
  - Telegram botu üzerinden hareketin algılanması sonucu mesaj göndermek.

## Başarı Kriterleri:

  - PIR sensörünün doğru şekilde hareket algılayabilmesi.
  - Telegram botunun, hareket algılandığında hızlı ve doğru bir şekilde mesaj gönderebilmesi.
  - Sistemin güvenilir çalışması (donanım ve yazılım).

# Tahmini Zaman Çizelgesi

Hafta | 1 | 2 - 3 | 4 - 5 | 6 - 9 | 10 - 11 | 12 | 13 | 14 
--- | --- | --- |--- |--- |--- |--- |--- |---
Gorev | Proje başlangıcı, görev dağılımı, proje planlaması | Donanım seçimi, Raspberry Pi Pico W ve PIR sensörü kurulumu ve test edilmesi | Telegram botu oluşturulması ve API entegrasyonu | Yazılım geliştirme, Raspberry Pi Pico W ile Telegram botunun entegrasyonu | Sistemin test edilmesi, yazılım hatalarının giderilmesi | Test ve final kontrolü | Belgelerin hazırlanması, raporlama | Son inceleme, teslimat ve kapanış 

# Kaynak Planlaması

Ekipmanlar:
  - 1 x Raspberry Pi Pico W
  - 1 x PIR sensörü
  - 1 x Telegram bot için bir Telegram hesabı
  - Gerekli kablolar ve bağlantı elemanları
  - Bilgisayar ve internet bağlantısı

Yazılımlar:
  - Arduino IDE
  - Telegram Bot API
  - Git

Proje Maliyeti:
  - Raspberry Pi Pico W: 200 TL
  - PIR Sensörü: 50 TL
  - Diğer malzemeler (kablolar, breadboard vs.): 50 TL

Toplam Maliyet (Yaklaşık): 300 TL


# Risk Analizi

Potansiyel Sorunlar ve Çözüm Önerileri:

  - PIR sensörünün hassasiyeti: PIR sensörleri bazen yanlış algılamalar yapabilir. Bu sorunun önüne geçmek için, sensör yerleşimini dikkatli yapmak ve yazılımda doğrulama algoritmaları kullanmak önerilir.
  - Telegram botunun çalışmaması: Telegram API bağlantısı zaman zaman kesilebilir. Bu durumda botun yeniden başlatılması ve hataların loglanması gerekecektir.
  - Donanım arızası: Raspberry Pi Pico W veya sensörde arıza yaşanabilir. Yedek donanım bulundurmak ve testler sırasında dikkatli olmak gerekir.
  - Kullanıcı dostu olmama: Kullanıcı geri bildirimlerine dayalı olarak Telegram botunun kullanımını daha kullanıcı dostu hale getirmek gerekecektir. Ayrıca, sistemde zaman zaman güncellemeler yapılmalıdır.

# Ticari Potansiyel

Bu proje, özellikle güvenlik sistemleri ve akıllı ev uygulamaları gibi alanlarda ticari olarak kullanılabilir. Ayrıca, ev ve işyeri güvenliğini artırmaya yönelik bu tür sistemler, geniş bir kullanıcı kitlesine hitap edebilir. Ticari kullanım alanları şunlar olabilir:

  - Ev güvenlik sistemleri: Hareket algılandığında ev sahiplerine anında bildirim gönderme.
  - İş yerleri ve ofisler: Güvenlik sağlama amacıyla kullanılan benzer uygulamalar.
  - Akıllı ev çözümleri: Farklı sensörlerle entegre edilebilen sistemler.
