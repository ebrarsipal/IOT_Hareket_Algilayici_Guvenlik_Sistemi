# Proje Konusu

Bu proje, evdeki üç farklı odanın güvenliğini sağlamak amacıyla, her birine yerleştirilen hareket sensörleriyle çalışan akıllı bir güvenlik sistemi geliştirmeyi amaçlamaktadır. Sistem, hareket algılandığında kullanıcıya anında Telegram üzerinden bildirim gönderir. Geliştirilen ürün sonucunda kişi evde yokken evde hangi odada hareket tespit edildiği bilgisine sahip olur.

# Özet

Proje, Raspberry Pi Pico W ve üç adet PIR hareket sensörü kullanılarak geliştirilmiş bir IoT tabanlı güvenlik sistemidir. Her sensör farklı bir odayı temsil eder ve bu odalarda hareket algılandığında, sistem ilgili oda bilgisini de içeren bir uyarıyı Telegram botu aracılığıyla kullanıcıya iletir.

# Kullanılan Yöntemler

### Donanım

| Bileşen                  | Açıklama                                                                 |
|--------------------------|--------------------------------------------------------------------------|
| Raspberry Pi Pico W      | Wi-Fi destekli, RP2040 mikrodenetleyici tabanlı geliştirme kartı         |
| 3x PIR Sensör (HC-SR501) | Mutfak (GPIO 20), Garaj (GPIO 19), Koridor (GPIO 18) için hareket algılayıcı |
| Kill Switch (GPIO 21)    | Sistemin çalışmasını fiziksel olarak açma/kapama                         |
| Yerleşik LED             | Sistem durumunu kullanıcıya görsel olarak bildirir                       |

### Yazılım

| Bileşen                              | Açıklama                                                                  |
|--------------------------------------|---------------------------------------------------------------------------|
| Arduino C++ (Arduino-Pico Core)     | Pico W ile uyumlu C++ kodlama altyapısı                                   |
| UniversalTelegramBot                | Telegram API ile mesaj gönderimi                                          |
| ArduinoJson                         | JSON veri formatı için kullanılan kütüphane                               |
| WiFiClientSecure / X509 sertifika   | HTTPS üzerinden Telegram sunucusuyla güvenli bağlantı                     |
| NTP üzerinden zaman senkronizasyonu | Mesajlara zaman damgası eklemek için                                      |

### Metodoloji
 Her sensör, yapılandırılmış bir pir\_sensor dizisinde tanımlanır.
 loop() içinde sürekli izlenir, HIGH sinyali alınan sensör için bir defaya mahsus mesaj gönderilir (sent\_message kontrolü).
 Hareket yoksa sent\_message sıfırlanır ve tekrar tetiklenebilir hale gelir.
Kodda pin.value() ile sensör okuması yapılır, send\_message() fonksiyonu ile Telegram’a bildirim gönderilir.


# Yapılan Çalışmalar ve Görselleri

Raspberry Pi Pico W’ye 3 farklı PIR sensörü bağlandı.
Her sensör için ayrı GPIO pinleri kullanılarak odaların bağımsız takibi sağlandı.
C++ ile hareket kontrol ve Telegram mesaj gönderme kodları yazıldı.
Telegram botu oluşturularak entegre edildi.
Testler sonucunda her sensör için ayrı bildirimler başarıyla gönderildi.

# Elde Edilen Teknik Sonuçlar

Üç adet PIR (Passive Infrared) sensör, bağımsız GPIO pinleri (GPIO 18, 19, 20) üzerinden yapılandırılarak ayrı ayrı başarıyla konumlandırıldı.
Sensörlerden herhangi biri tarafından algılanan hareket, önceden yapılandırılmış struct dizisi aracılığıyla algılandığı odanın ismi ile ilişkilendirildi.
Telegram API aracılığıyla, olayın gerçekleştiği odaya özgü zaman damgalı mesaj, TLS sertifikalı HTTPS üzerinden başarılı şekilde iletildi.
Sistem yapısı, modüler sensör tanımı ile genişletilebilirlik prensibine uygun olarak tasarlandığından dolayı çok odalı (multi-zone) güvenlik izleme işlevselliği başarıyla sağlandı.

