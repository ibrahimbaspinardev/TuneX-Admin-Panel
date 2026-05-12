# 🔄 GitHub Actions'ı Manuel Tetikleme

## Yöntem 1: GitHub UI'dan Manuel Tetikleme

1. Repository'nize gidin: `https://github.com/ibrahimbaspinar00/TuneX-Admin-Panel`
2. **Actions** sekmesine tıklayın
3. Sol menüden **"Build and Deploy to GitHub Pages"** workflow'unu seçin
4. Sağ üstte **"Run workflow"** butonuna tıklayın
5. Branch olarak **"main"** seçin
6. **"Run workflow"** butonuna tıklayın

Workflow otomatik olarak başlayacak!

## Yöntem 2: Boş Commit ile Tetikleme

Terminal'de:

```bash
git commit --allow-empty -m "chore: Trigger GitHub Actions"
git push origin main
```

## Yöntem 3: Workflow Dosyasını Güncelleme

Workflow dosyasında küçük bir değişiklik yapıp push edin:

```bash
# .github/workflows/deploy.yml dosyasında küçük bir değişiklik yapın
git add .github/workflows/deploy.yml
git commit -m "chore: Update workflow"
git push origin main
```

## ✅ Kontrol Etme

1. **Actions** sekmesine gidin
2. En üstte yeni bir workflow run göreceksiniz
3. Durumu takip edebilirsiniz:
   - 🟡 Sarı = Çalışıyor
   - 🟢 Yeşil = Başarılı
   - 🔴 Kırmızı = Hata

## 🎯 En Hızlı Yöntem

**GitHub UI'dan manuel tetikleme** en hızlı yöntemdir:
1. Actions → Build and Deploy to GitHub Pages → Run workflow

---

**Not:** Workflow zaten push edildi ve otomatik çalışacak! 🚀

