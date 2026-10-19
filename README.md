# Resus

Telefonda ana ekrana eklenip internetsiz çalışan kişisel bir çalışma uygulaması (PWA).

- Çalışma içeriği `index.html` içinde **şifreli** durur (PBKDF2-SHA256 ile anahtar türetme, AES-256-GCM). Parola olmadan okunamaz.
- Uygulama kodu açıktır; içerik açık değildir. Depoda şifresiz içerik bulunmaz.
- İlerleme yalnız kullanıcının cihazında (tarayıcı depolaması) tutulur; sunucu yoktur. Ayarlar ekranından yedek alınır ve geri yüklenir.
- Dış kütüphane kullanılmaz.

## Dosyalar

| Dosya | Görev |
|---|---|
| `index.html` | Uygulama kodu + şifreli içerik |
| `sw.js` | Çevrimdışı önbellek |
| `manifest.webmanifest` | Ana ekran uygulaması bilgileri |
| `icons/` | Simgeler |

## Yayınlama (GitHub Pages)

1. Bu dosyaları bir deponun köküne yükle.
2. Settings → Pages → "Deploy from a branch" → `main` / `(root)`.
3. Sayfa adresini iPhone'da Safari ile aç → Paylaş → "Ana Ekrana Ekle".
4. Uygulamayı ana ekrandan aç ve parolayı orada gir.

Güncelleme: yeni derlenen dosyaları aynı depoya yükle. Uygulama bir sonraki açılışta "Yeni sürüm hazır" der.
