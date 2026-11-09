# Resus

Telefonda ana ekrana eklenip internetsiz çalışan kişisel bir çalışma uygulaması (PWA).

- Çalışma içeriği `index.html` içinde **şifreli** durur: parola PBKDF2-SHA256 (1.000.000 tekrar) ile anahtara çevrilir, içerik AES-256-GCM ile şifrelenir. Parola olmadan okunamaz.
- Uygulama kodu açıktır; içerik açık değildir. Depoda şifresiz içerik bulunmaz.
- İlerleme yalnız kullanıcının cihazında (tarayıcı depolaması) tutulur; sunucu yoktur.
- Dış kütüphane ve sunucu kullanılmaz; kilit açıldıktan sonra internetsiz çalışır.

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

GitHub Pages sitesi depo gizli olsa bile herkese açıktır; içeriği koruyan şey yalnız parola ve şifrelemedir.

## Kullanım

- **İlk açılış:** parola sorulur. Doğruysa anahtar cihazda saklanır, parolanın kendisi saklanmaz; sonraki açılışlarda parola sorulmaz.
- **Kilitle:** Ayarlar → Kilitle. Anahtar cihazdan silinir; bir sonraki açılışta parola yeniden sorulur.
- **Yedek:** Ayarlar → Yedek. İlerleme bir metin ya da dosya olarak alınır ve aynı ekrandan geri yüklenir. Telefon değişmeden ya da tarayıcı verisi silinmeden önce yedek al.
- **Güncelleme:** yeni derlenen dosyaları aynı depoya yükle. Uygulama bir sonraki açılışta "Yeni sürüm hazır" der; yenileyince yeni sürüm açılır. İlerleme korunur.

## Parola

- Parola en az 4 rastgele kelimeden oluşmalı. Şifreli veri herkese açık olduğu için kısa ya da tahmin edilebilir parola kırılabilir.
- Parola hiçbir dosyada, kodda ya da bu belgede yazılı değildir.
- Parola unutulursa içerik bu dosyalardan geri açılamaz. Uygulama, içeriğin şifresiz kaynağından yeni bir parolayla yeniden derlenir ve dosyalar depoda değiştirilir; cihazda kilit yeniden açılır, yedekten ilerleme geri yüklenir.
