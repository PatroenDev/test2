# Metin2 Sunucu Listesi Projesi

Bu proje, Laravel, Tailwind CSS ve Alpine.js kullanılarak geliştirilmiş bir Metin2 özel sunucu (PVP) listeleme platformudur.

## Özellikler (Mevcut Durum)

*   Kullanıcı Kayıt ve Giriş (Modal pencereler ile)
*   Sunucu Ekleme/Düzenleme/Silme (Kullanıcılar için, admin onayı gerekli)
*   Sunucu Listeleme (VIP sunucular üstte ve vurgulu)
*   Sunucu Detay Sayfası (Temel bilgiler, galeri/yorum için placeholder)
*   Oylama Sistemi (Kullanıcı ve IP bazlı günlük limit)
*   Admin Paneli:
    *   Dashboard (Basit istatistikler - geliştirilebilir)
    *   Site Ayarları (Site adı, açıklama vb.)
    *   Banner Yönetimi (Ekleme, düzenleme, silme, pozisyon atama)
    *   Sunucu Yönetimi (Onaylama, düzenleme, silme, VIP işaretleme)
    *   Kullanıcı Yönetimi (Listeleme, düzenleme, banlama/ban kaldırma)
*   Metin2 Temasına Yönelik Arayüz (Font, renkler)
*   Toastr Bildirimleri
*   Temel SEO (Dinamik başlık/açıklama)

## Kurulum Talimatları

1.  **Projeyi Klonlayın:**
    ```bash
    git clone <repository_url> metin2-server-list
    cd metin2-server-list
    ```

2.  **Bağımlılıkları Yükleyin:**
    *   **Composer (PHP):**
        ```bash
        composer install
        ```
    *   **NPM (Node.js):**
        ```bash
        npm install
        ```

3.  **Ortam Dosyasını Ayarlayın:**
    *   `.env.example` dosyasını kopyalayarak `.env` adında yeni bir dosya oluşturun:
        ```bash
        cp .env.example .env
        ```
    *   `.env` dosyasını açın ve özellikle aşağıdaki veritabanı ayarlarını kendi ortamınıza göre düzenleyin:
        ```dotenv
        DB_CONNECTION=mysql
        DB_HOST=127.0.0.1
        DB_PORT=3306
        DB_DATABASE=laravel
        DB_USERNAME=root
        DB_PASSWORD=
        ```
        *Not: Proje geliştirme sırasında SQLite kullanılmıştır. Eğer SQLite ile devam etmek isterseniz `DB_CONNECTION=sqlite` yapın ve `DB_DATABASE` kısmını boş bırakın (veya veritabanı dosyasının tam yolunu belirtin, örn: `/path/to/your/project/database/database.sqlite`). Eğer SQLite kullanacaksanız, `database/database.sqlite` adında boş bir dosya oluşturmanız gerekebilir.* 

4.  **Uygulama Anahtarını Oluşturun:**
    ```bash
    php artisan key:generate
    ```

5.  **Veritabanı Migrasyonlarını Çalıştırın:**
    *   Eğer SQLite kullanıyorsanız, önce `database/database.sqlite` dosyasını oluşturun.
    ```bash
    php artisan migrate
    ```

6.  **Sembolik Link Oluşturun (Storage):**
    Dosya yüklemelerinin (banner, sunucu kapak görselleri) public olarak erişilebilir olması için:
    ```bash
    php artisan storage:link
    ```

7.  **Frontend Assetlerini Derleyin:**
    *   Geliştirme sırasında:
        ```bash
        npm run dev
        ```
    *   Üretim ortamı için:
        ```bash
        npm run build
        ```

8.  **Uygulamayı Çalıştırın:**
    Laravel'in dahili geliştirme sunucusunu kullanabilirsiniz:
    ```bash
    php artisan serve
    ```
    Uygulama varsayılan olarak `http://127.0.0.1:8000` adresinde çalışacaktır.

## Yönetici (Admin) Kullanıcısı

Varsayılan olarak ilk kayıt olan kullanıcı (ID: 1) admin yetkisine sahip **değildir**. Bir kullanıcıyı admin yapmak için:

1.  Normal şekilde bir kullanıcı kaydı oluşturun.
2.  Veritabanı yönetim aracınızla (phpMyAdmin, Sequel Ace, DB Browser for SQLite vb.) `users` tablosunu açın.
3.  Admin yapmak istediğiniz kullanıcının satırını bulun ve `is_admin` sütunundaki değeri `1` (veya `true`) olarak değiştirin.

Artık bu kullanıcı ile giriş yaparak `/admin` yolundan yönetici paneline erişebilirsiniz.

## Testler

Projede henüz kapsamlı otomatik testler (Unit ve Feature testleri) yazılmamıştır. Geliştirme sürecinde manuel testler yapılmıştır. İlerleyen aşamalarda testlerin eklenmesi önerilir.

Laravel ile test yazmak için:
```bash
php artisan make:test OrnekFeatureTest --feature
php artisan make:test OrnekUnitTest --unit
```
Testleri çalıştırmak için:
```bash
php artisan test
```

## Kalan Özellikler ve Geliştirmeler

Detaylı liste için `kalan_ozellikler.md` dosyasına bakınız.


