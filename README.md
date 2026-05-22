# TuneX Admin Panel

Modern ve kapsamlı Flutter web admin paneli. Ürün yönetimi, sipariş takibi, kullanıcı yönetimi ve detaylı raporlama özellikleri sunar.

## 🚀 Özellikler

### 📊 Dashboard
- Gerçek zamanlı istatistikler
- Satış grafikleri (günlük/haftalık/aylık)
- Kategori bazlı satış analizi
- En çok satılan ürünler listesi
- Modern ve responsive tasarım

### 📦 Ürün Yönetimi
- Ürün ekleme, düzenleme ve silme
- Toplu işlemler (çoklu seçim)
- Gelişmiş arama ve filtreleme
- Kategori yönetimi
- Stok takibi
- Fiyat yönetimi
- Profesyonel görsel yükleme (Cloudinary entegrasyonu)

### 🛒 Sipariş Yönetimi
- Sipariş listesi ve detayları
- Sipariş durumu timeline'ı
- Kargo takip numarası ekleme
- Sipariş notları
- Sipariş filtreleme

### 👥 Kullanıcı Yönetimi
- Kullanıcı listesi ve detayları
- Yetki yönetimi
- Kullanıcı profilleri
- En çok alışveriş yapan müşteriler

### 📈 Raporlama
- Finansal raporlar
- Satış raporları
- Kar/Zarar analizi
- PDF ve CSV export
- Gelişmiş grafikler

### 🎯 Kampanya Yönetimi
- Kampanya oluşturma ve düzenleme
- İndirim kuralları
- Aktif/pasif kampanya yönetimi

### 🔍 Global Arama
- Ürünlerde arama
- Siparişlerde arama
- Kullanıcılarda arama
- Hızlı sonuçlar

### 🔔 Bildirimler
- Push bildirimleri
- Email bildirimleri
- Bildirim geçmişi

## 🛠️ Teknolojiler

- **Flutter Web** - Modern UI framework
- **Firebase** - Backend servisleri
  - Firestore - Veritabanı
  - Storage - Dosya depolama
  - Functions - Cloud functions
  - Authentication - Kimlik doğrulama
- **Cloudinary** - Görsel yönetimi
- **fl_chart** - Grafikler
- **Material Design 3** - Modern UI

## 📋 Gereksinimler

- Flutter SDK (3.9.2 veya üzeri)
- Firebase projesi
- Node.js (Firebase Functions için)
- Git

## 🔧 Kurulum

### 1. Projeyi Klonlayın

```bash
git clone https://github.com/ibrahimbaspinardev/TuneX-Admin-Panel.git
cd TuneX-Admin-Panel
```

### 2. Bağımlılıkları Yükleyin

```bash
flutter pub get
```

### 3. Firebase Konfigürasyonu

1. Firebase Console'da yeni bir proje oluşturun
2. `firebase_options.dart` dosyasını Firebase CLI ile oluşturun:

```bash
flutterfire configure
```

3. `firebase_options.dart` dosyasının doğru şekilde oluşturulduğundan emin olun

### 4. Firebase Functions Kurulumu

```bash
cd functions
npm install
cd ..
```

### 5. Firebase Service Account Key

Firebase Console'dan service account key'i indirin ve `functions/` klasörüne ekleyin:
- `functions/tuning-app-789ce-firebase-adminsdk-*.json`

**⚠️ ÖNEMLİ:** Bu dosya `.gitignore`'da olduğu için GitHub'a yüklenmeyecektir.

## 🚀 Çalıştırma

### Development Modu

```bash
flutter run -d chrome
```

### Production Build

```bash
flutter build web --release
```

Build çıktısı `build/web/` klasöründe olacaktır.

## 📦 Deployment

### 🆓 GitHub Pages (Ücretsiz - Önerilen)

Proje GitHub Pages için hazırlanmıştır! Tamamen ücretsiz hosting.

**Kurulum:**
1. Repository → **Settings** → **Pages**
2. **Source** olarak **GitHub Actions** seçin
3. Her push'ta otomatik deploy olacak!

**Site URL:** `https://ibrahimbaspinardev.github.io/TuneX-Admin-Panel/`

Detaylı rehber için: [GITHUB_PAGES_SETUP.md](GITHUB_PAGES_SETUP.md)

### Firebase Hosting (Alternatif)

1. Firebase CLI'yi yükleyin:

```bash
npm install -g firebase-tools
```

2. Firebase'e giriş yapın:

```bash
firebase login
```

3. Build alın ve deploy edin:

```bash
flutter build web --release
firebase deploy --only hosting
```

### GitHub Actions ile Otomatik Deployment

Proje GitHub Actions ile otomatik deployment desteği içerir. `.github/workflows/deploy.yml` dosyası GitHub Pages için yapılandırılmıştır.

## 🔐 Güvenlik

- Firebase Service Account key'leri asla commit edilmemelidir
- Firestore ve Storage kuralları `firestore.rules` ve `storage.rules` dosyalarında tanımlıdır
- Production'da Firebase Security Rules'ları mutlaka kontrol edin

## 📁 Proje Yapısı

```
lib/
├── main.dart                 # Ana giriş noktası
├── web_admin_main.dart       # Admin uygulama ana dosyası
├── web_admin_dashboard.dart  # Dashboard sayfası
├── model/                    # Veri modelleri
├── services/                 # Servisler (Firebase, Cache, vb.)
├── widgets/                  # Özel widget'lar
└── utils/                    # Yardımcı fonksiyonlar
```

## 🎨 Tasarım

- Modern Material Design 3
- Responsive tasarım (mobil, tablet, desktop)
- Dark mode desteği
- Animasyonlar ve geçişler
- Gradient renkler ve modern UI bileşenleri

## 📝 Lisans

Bu proje özel bir projedir.

## 👥 Katkıda Bulunma

1. Fork edin
2. Feature branch oluşturun (`git checkout -b feature/amazing-feature`)
3. Commit edin (`git commit -m 'Add some amazing feature'`)
4. Push edin (`git push origin feature/amazing-feature`)
5. Pull Request açın

## 📞 İletişim

Sorularınız için issue açabilirsiniz.

---

**Not:** Bu admin paneli production kullanımı için hazırlanmıştır. Güvenlik ayarlarını ve Firebase kurallarını mutlaka kontrol edin.

