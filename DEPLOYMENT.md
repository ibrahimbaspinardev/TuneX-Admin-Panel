# 🚀 Deployment Rehberi

Bu rehber, TuneX Admin Panel'i GitHub'a yukleyip Firebase Hosting ile yayinlama adimlarini icerir.

## 📋 Ön Hazırlık

### 1. GitHub Repository Oluşturma

1. GitHub'da yeni bir repository oluşturun
2. Repository adını belirleyin (örn: `tuning-admin-panel`)
3. Public veya Private seçin

### 2. Firebase Projesi Hazırlama

1. [Firebase Console](https://console.firebase.google.com/)'a gidin
2. Yeni bir proje oluşturun veya mevcut projeyi kullanın
3. Hosting servisini etkinleştirin

## 🔧 Adım Adım Kurulum

### Adım 1: Git Repository'yi Başlatma

```bash
# Proje klasörüne gidin
cd TuneX-Admin-Panel

# Git'i başlatın (eğer başlatılmadıysa)
git init

# Tüm dosyaları ekleyin
git add .

# İlk commit'i yapın
git commit -m "Initial commit: Admin panel setup"
```

### Adım 2: GitHub Repository'ye Bağlama

```bash
# GitHub repository URL'inizi ekleyin
git remote add origin https://github.com/KULLANICI_ADI/REPO_ADI.git

# Branch'i main olarak ayarlayın
git branch -M main

# GitHub'a push edin
git push -u origin main
```

**Not:** `KULLANICI_ADI` ve `REPO_ADI` kısımlarını kendi bilgilerinizle değiştirin.

### Adım 3: Firebase CLI Kurulumu

```bash
# Firebase CLI'yi global olarak yükleyin
npm install -g firebase-tools

# Firebase'e giriş yapın
firebase login

# Firebase projenizi seçin
firebase use --add
```

### Adım 4: Firebase Hosting Konfigürasyonu

`firebase.json` dosyası zaten hosting konfigürasyonu içeriyor. Eğer manuel olarak yapmak isterseniz:

```bash
firebase init hosting
```

Seçenekler:
- **What do you want to use as your public directory?** → `build/web`
- **Configure as a single-page app?** → `Yes`
- **Set up automatic builds and deploys with GitHub?** → `No` (manuel yapacağız)

### Adım 5: Build ve Deploy

```bash
# Flutter web build alın
flutter build web --release

# Firebase Hosting'e deploy edin
firebase deploy --only hosting
```

### Adım 6: Deployment URL'ini Kontrol Etme

Deployment tamamlandıktan sonra terminal'de URL göreceksiniz:
```
✔  Deploy complete!

Project Console: https://console.firebase.google.com/project/PROJECT_ID/overview
Hosting URL: https://PROJECT_ID.web.app
```

## 🔄 Güncelleme Süreci

Kod değişikliklerinden sonra:

```bash
# Değişiklikleri commit edin
git add .
git commit -m "Update: Açıklama"
git push origin main

# Build alın
flutter build web --release

# Deploy edin
firebase deploy --only hosting
```

## 🤖 GitHub Actions ile Otomatik Deployment

Otomatik deployment için GitHub Actions kullanabilirsiniz:

### 1. GitHub Secrets Ayarlama

Repository Settings → Secrets and variables → Actions → New repository secret

Şu secret'ları ekleyin:
- `FIREBASE_SERVICE_ACCOUNT`: Firebase service account JSON içeriği
- `FIREBASE_PROJECT_ID`: Firebase proje ID'niz

### 2. GitHub Actions Workflow Dosyası

`.github/workflows/deploy.yml` dosyası oluşturun (aşağıdaki bölümde örnek var).

## 🔐 Güvenlik Kontrol Listesi

Deployment öncesi kontrol edin:

- [ ] `.gitignore` dosyası service account key'lerini içeriyor mu?
- [ ] `firebase_options.dart` doğru şekilde yapılandırılmış mı?
- [ ] Firestore Security Rules production için uygun mu?
- [ ] Storage Rules production için uygun mu?
- [ ] Environment variables doğru ayarlanmış mı?

## 📝 Özel Domain Kullanımı

Firebase Hosting'de özel domain kullanmak için:

1. Firebase Console → Hosting → Add custom domain
2. Domain'i ekleyin ve DNS ayarlarını yapın
3. SSL sertifikası otomatik olarak oluşturulacak

## 🐛 Sorun Giderme

### Build Hatası

```bash
# Flutter'ı güncelleyin
flutter upgrade

# Bağımlılıkları temizleyin
flutter clean
flutter pub get

# Tekrar build alın
flutter build web --release
```

### Firebase Deploy Hatası

```bash
# Firebase CLI'yi güncelleyin
npm update -g firebase-tools

# Firebase'e tekrar giriş yapın
firebase logout
firebase login

# Projeyi tekrar seçin
firebase use PROJECT_ID
```

### CORS Hatası

Eğer CORS hatası alıyorsanız, `cors.json` dosyasını kontrol edin ve Firebase Functions'da CORS ayarlarını yapın.

## 📊 Performance Optimizasyonu

Production deployment için:

1. **Code Splitting**: Flutter otomatik olarak yapar
2. **Asset Optimization**: Görselleri optimize edin
3. **Caching**: Firebase Hosting otomatik cache headers ekler
4. **CDN**: Firebase Hosting global CDN kullanır

## 🔍 Monitoring

Firebase Console'da:
- Hosting → Usage: Trafik ve bandwidth kullanımı
- Performance: Sayfa yükleme süreleri
- Analytics: Kullanıcı davranışları

## 📞 Destek

Sorun yaşarsanız:
1. GitHub Issues'da yeni issue açın
2. Firebase Support'a başvurun
3. Flutter documentation'ı kontrol edin

---

**Başarılar! 🎉**

