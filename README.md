# Product API Frontend

Bu proje, ürün yönetimi API'si ile etkileşim kuran basit bir frontend uygulamasıdır. Kullanıcılar ürünleri görüntüleyebilir, giriş yapabilir ve kimlik doğrulama gerektiren işlemleri gerçekleştirebilir.

## Özellikler

- **Ürün Listesi**: Tüm ürünleri görüntüleme
- **Tekil Ürün**: ID'ye göre belirli bir ürünü görüntüleme
- **Kullanıcı Girişi**: Email ve şifre ile giriş yapma
- **JWT Token Yönetimi**: Giriş sonrası token saklama ve kullanma

## API Endpoints

Uygulama aşağıdaki API endpoint'lerini kullanır:

- `GET /api/products` - Tüm ürünleri getir
- `GET /api/products/{id}` - Belirli bir ürünü getir (kimlik doğrulama gerekli)
- `POST /api/user/login` - Kullanıcı girişi

## Kurulum ve Çalıştırma

1. Bu HTML dosyasını yerel sunucuda çalıştırın
2. Backend API'nin `https://localhost:7015` adresinde çalıştığından emin olun
3. CORS ayarlarının frontend'den gelen isteklere izin verdiğinden emin olun

## Kullanım

### Ürünleri Görüntüleme
- **"Get Products"** butonuna tıklayarak tüm ürünleri görüntüleyebilirsiniz
- Bu işlem kimlik doğrulama gerektirmez

### Giriş Yapma
- **"Login"** butonuna tıklayarak giriş yapabilirsiniz
- Varsayılan kimlik bilgileri:
  - Email: `kackinilayda@gmail.com`
  - Şifre: `135790`
- Başarılı girişten sonra JWT token otomatik olarak localStorage'da saklanır

### Tekil Ürün Görüntüleme
- **"Get Product"** butonuna tıklayarak ID'si 4 olan ürünü görüntüleyebilirsiniz
- Bu işlem kimlik doğrulama gerektirir (önce giriş yapmanız gerekir)

## Teknik Detaylar

### Kullanılan Teknolojiler
- Vanilla JavaScript
- Fetch API
- LocalStorage
- HTML5/CSS3

### Kimlik Doğrulama
- JWT (JSON Web Token) tabanlı kimlik doğrulama
- Token'lar localStorage'da saklanır
- Bearer token formatında Authorization header'ında gönderilir

### Veri Görüntüleme
- Ürünler dinamik olarak DOM'a eklenir
- Her ürün için ürün adı ve fiyat gösterilir
- Fiyatlar mavi renkte (#00008B) vurgulanır

## Güvenlik Notları

⚠️ **Dikkat**: Bu uygulama demo amaçlıdır ve production ortamı için aşağıdaki güvenlik önlemleri alınmalıdır:

- Hassas bilgileri localStorage yerine güvenli yöntemlerle saklayın
- API endpoint'lerini environment variable'lardan okuyun
- HTTPS kullanın
- Input validation ekleyin
- Error handling'i geliştirin

## Geliştirme

Projeyi geliştirmek için:

1. HTML dosyasını bir kod editöründe açın
2. Değişikliklerinizi yapın
3. Tarayıcıda test edin
4. Backend API'nin çalıştığından emin olun

## API Bağımlılıkları

Bu frontend uygulaması aşağıdaki backend API yapısını bekler:

```json
// GET /api/products response
[
  {
    "productName": "Ürün Adı",
    "price": 100.00
  }
]

// GET /api/products/{id} response
{
  "productName": "Ürün Adı",
  "price": 100.00
}

// POST /api/user/login response
{
  "token": "jwt-token-string"
}
```

## Sorun Giderme

- **CORS hatası**: Backend'de CORS ayarlarını kontrol edin
- **Token hatası**: Önce login işlemini gerçekleştirdiğinizden emin olun
- **API bağlantı hatası**: Backend servisinin çalıştığını kontrol edin
