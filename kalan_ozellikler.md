## Metin2 Sunucu Listesi Projesi - Kalan Özellikler ve Geliştirmeler

Bu belge, projenin mevcut durumunda tamamlanmamış veya iyileştirilebilecek özellikleri listelemektedir.

1.  **Gelişmiş Oylama Sistemi:**
    *   Kullanıcı veya IP adresi bazında günlük oy verme limitinin eklenmesi gerekmektedir. Mevcut sistemde bir kullanıcı veya aynı IP'den birden fazla oy kullanılabilir.
    *   Oylama işlemi sonrasında sunucu sıralamasının anlık olarak güncellenmesi ve oylamaya göre sıralamanın daha belirgin bir şekilde kullanıcıya sunulması iyileştirilebilir.
    *   Oy verdikten sonra belirli bir süre (örneğin, 12 veya 24 saat) tekrar oy vermeyi engelleyecek bir bekleme süresi (cooldown) mekanizması eklenmelidir.

2.  **VIP Sistemi Görselleştirmesi:**
    *   Yönetici panelinden VIP olarak işaretlenen sunucuların, web sitesinin kullanıcı arayüzünde (anasayfa, sunucu listeleri vb.) görsel olarak ayırt edilmesi gerekmektedir. Bu, özel bir etiket, farklı bir arkaplan rengi veya listenin en başında gösterme şeklinde olabilir.

3.  **Banner Gösterimi:**
    *   Yönetici panelinde oluşturulan ve pozisyonu belirlenen bannerların, web sitesinin ilgili alanlarında (örneğin, sayfa üstü, kenar çubuğu) dinamik olarak gösterilmesi işlevselliği eklenmelidir.

4.  **Metin2 Teması Detaylandırma:**
    *   Sitenin genel tasarımının Metin2 oyununun estetiğine daha uygun hale getirilmesi için ek CSS çalışmaları yapılabilir. Bu, özel fontların kullanılması, renk paletinin ayarlanması, arkaplan görselleri ve buton stillerinin özelleştirilmesini içerebilir.

5.  **Mobil Uyumluluk İyileştirmeleri:**
    *   Web sitesinin tüm sayfalarının farklı mobil cihazlarda (akıllı telefonlar, tabletler) sorunsuz bir şekilde görüntülenip kullanılabildiğinden emin olmak için kapsamlı testler yapılmalı ve gerekli CSS düzenlemeleri ile duyarlılık (responsiveness) artırılmalıdır.

6.  **Kullanıcı Yönetimi Geliştirmeleri (Admin):**
    *   Yönetici paneline, kullanıcıları yasaklama (ban) ve yasağı kaldırma işlevselliği eklenmelidir. Mevcut durumda sadece kullanıcı listeleme ve silme bulunmaktadır.
    *   Yöneticilerin kullanıcı profillerini daha detaylı görüntüleyebileceği veya düzenleyebileceği bir arayüz eklenebilir.

7.  **Sunucu Yönetimi Geliştirmeleri (Admin):**
    *   Yeni eklenen sunucuların yönetici tarafından onaylanması veya reddedilmesi sürecinin daha belirgin hale getirilmesi faydalı olacaktır. Örneğin, onay bekleyen sunucular için ayrı bir liste veya durum göstergesi eklenebilir.

8.  **Sunucu Detay Sayfası Geliştirmeleri:**
    *   Sunucu detay sayfasına, sunucunun anlık durumu (aktif/pasif - eğer mümkünse bir API ile kontrol edilerek), sunucuya ait detaylı özellikler (rate'ler, efsun oranları vb.), ekran görüntüleri galerisi gibi ek bilgiler eklenebilir.
    *   Kullanıcıların sunucular hakkında yorum yapabileceği bir bölüm eklenebilir.

9.  **SEO (Arama Motoru Optimizasyonu) İyileştirmeleri:**
    *   Sayfa başlıkları (title tags), meta açıklamaları (meta descriptions) ve anahtar kelimeler gibi temel SEO öğelerinin her sayfa için optimize edilmesi gerekmektedir.
    *   URL yapılarının daha okunabilir ve arama motoru dostu olacak şekilde düzenlenmesi (Laravel'in standart yapısı zaten büyük ölçüde uygundur, ancak özel ayarlamalar yapılabilir).

10. **Performans Optimizasyonu:**
    *   Özellikle sunucu ve kullanıcı sayısı arttığında veritabanı sorgularının verimliliğinin gözden geçirilmesi ve optimize edilmesi önemlidir (örneğin, indeksleme kullanımı).
    *   Sık erişilen veriler (örneğin, site ayarları, popüler sunucu listeleri) için önbellekleme (caching) mekanizmalarının (Redis, Memcached vb.) kullanılması sitenin hızını artıracaktır.
    *   Üretim ortamı için CSS ve JavaScript dosyalarının küçültülmesi (minification) ve birleştirilmesi (concatenation) performansı iyileştirecektir (Vite build komutu ile yapılabilir).

11. **Testler:**
    *   Uygulamanın temel işlevleri (kimlik doğrulama, sunucu ekleme/düzenleme, oylama, admin işlemleri vb.) için otomatik testler (Unit ve Feature testleri) yazılması, gelecekteki değişikliklerde hataların erken tespit edilmesini sağlar.
    *   Tüm kullanıcı akışlarının manuel olarak farklı senaryolarla test edilmesi gerekmektedir.

12. **Kurulum ve Yapılandırma Talimatları:**
    *   Projenin farklı bir geliştirme veya sunucu ortamında kolayca kurulabilmesi için detaylı bir `README.md` dosyası hazırlanmalıdır. Bu dosya, gerekli bağımlılıkların (PHP, Composer, Node.js) kurulumu, veritabanı oluşturma ve yapılandırma, `.env` dosyasının ayarlanması gibi adımları içermelidir.

13. **Toastr Bildirimlerinin Gözden Geçirilmesi:**
    *   Kullanıcı tarafından gerçekleştirilen tüm önemli işlemler (örneğin, sunucu ekleme, güncelleme, silme, oy verme, ayar kaydetme) sonrasında kullanıcıya işlemin başarılı veya başarısız olduğuna dair uygun Toastr bildirimlerinin gösterildiğinden emin olunmalıdır.

14. **Kod İçi Açıklamaların Tamamlanması ve Gözden Geçirilmesi:**
    *   Kodun okunabilirliğini ve anlaşılabilirliğini artırmak için tüm önemli fonksiyonlara, sınıflara ve karmaşık kod bloklarına Türkçe açıklamalar eklenmesi (mevcut açıklamalar gözden geçirilebilir ve eksikler tamamlanabilir).

