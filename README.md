<div align="center">

<img src="[AbonelikTakibi/Assets.xcassets/AppIcon.appiconset/A.png](https://github.com/mugione/abonelik/blob/main/icon.png)" width="128" alt="Abonelik Takip ikonu" style="border-radius: 28px;">

# Abonelik Takip

**Netflix, Spotify, iCloud+ ve diğer tüm dijital aboneliklerin tek bir yerde.**<br>
Ne kadar ödediğini gör, zamlanmadan önce haberin olsun, verin cihazında kalsın.

![iOS 17+](https://img.shields.io/badge/iOS-17.0%2B-000000?style=flat-square&logo=apple&logoColor=white)
![Swift 5](https://img.shields.io/badge/Swift-5-F05138?style=flat-square&logo=swift&logoColor=white)
![SwiftUI](https://img.shields.io/badge/SwiftUI-0A84FF?style=flat-square&logo=swift&logoColor=white)
![Xcode 16+](https://img.shields.io/badge/Xcode-16%2B-147EFB?style=flat-square&logo=xcode&logoColor=white)
![Çevrimdışı](https://img.shields.io/badge/%C3%A7evrimd%C4%B1%C5%9F%C4%B1-%25100-22C55E?style=flat-square)
![Reklamsız](https://img.shields.io/badge/reklam-yok-8B5CF6?style=flat-square)

[Özellikler](#-özellikler) · [Hızlı başlangıç](#-hızlı-başlangıç) · [Mimari](#-mimari) · [Veri](#-veri-modeli) · [Yedekleme](#-yedekleme) · [Yol haritası](#-yol-haritası)

</div>

---

## ✨ Neden Abonelik Takip?

| | |
|---|---|
| 🔒 **Gizlilik önce** | Hesap yok, sunucu yok, analitik yok. Veriler yalnızca cihazındaki tek bir JSON dosyasında. |
| ⚡ **Saniyeler içinde ekle** | 41 hazır servis şablonu. "Netflix" seç, fiyatı yaz, bitti. |
| 📊 **Tek bakışta özet** | Aylık ve yıllık toplam, bu ay ödenecek tutar, kategori dağılımı, yaklaşan ödemeler. |
| 🔔 **Zamanında haber** | Ödeme gününden 1, 3 veya 7 gün önce yerel bildirim. |
| 💾 **Senin verin, senin dosyan** | JSON yedek al, CSV'ye aktar, istediğin zaman geri yükle. |
| 🎨 **Modern arayüz** | Gradyan kartlar, marka logoları, açık ve koyu mod, iPhone. |

---

## 🚀 Hızlı başlangıç

```sh
git clone https://github.com/mugione/abonelik.git abonelik && cd abonelik
open AbonelikTakibi.xcodeproj
```

1. **Signing & Capabilities** sekmesinden Team seç.
2. Bir iPhone simülatörü seç, **⌘R**.

<details>
<summary>Komut satırından derleme</summary>

```sh
# Simülatör · Debug
xcodebuild -project AbonelikTakibi.xcodeproj -scheme AbonelikTakibi \
  -destination 'generic/platform=iOS Simulator' build

# Cihaz · Release (imzasız kontrol)
xcodebuild -project AbonelikTakibi.xcodeproj -scheme AbonelikTakibi \
  -destination 'generic/platform=iOS' -configuration Release \
  CODE_SIGNING_ALLOWED=NO build
```

Proje Xcode 16'nın *dosya sistemi senkronize grup* yapısını kullanır: `AbonelikTakibi/` altına eklenen her dosya otomatik olarak hedefe girer, `project.pbxproj` içinde dosya listesi tutulmaz.

</details>

<details>
<summary>Yardımcı betikler</summary>

| Betik | Ne yapar |
|---|---|
| `bash Scripts/fetch_logos.sh` | Simple Icons'tan 17 marka logosunu indirip asset kataloğuna ekler |
| `swift Scripts/make_app_icon.swift` | Uygulama ikonunu CoreGraphics ile çizer, 1024×1024 PNG üretir |
| `swift Tests/ModelLogicTests.swift` | Tarih ve maliyet hesaplarını 13 senaryoyla doğrular |
| `swift Scripts/make_screenshots.swift` | App Store pazarlama görsellerini üretir (5 adet, 1290×2796) → `Marketing/AppStore/` |

</details>

---

## 📱 Özellikler

<table>
<tr>
<td width="33%" valign="top">

### 📋 Takip
- Ekle, düzenle, sil, **duraklat**
- Haftalık · Aylık · 3 Aylık · Yıllık
- TRY · USD · EUR · GBP
- Sonraki ödeme tarihi otomatik
- Toplam ödenen tutar tahmini
- Not alanı

</td>
<td width="33%" valign="top">

### 📊 Özet
- Aylık / yıllık toplam
- Bu ay ödenecek
- Yaklaşan ödemeler (7–60 gün)
- Kategori halka grafiği
- En yüksek 3 harcama
- Çoklu para birimi toplamları

</td>
<td width="33%" valign="top">

### 🔍 Liste
- Anında arama
- Kategori çipleri
- 4 sıralama seçeneği
- Kaydır → duraklat / sil
- Duraklatılanları gizle
- Boş durum yönlendirmesi

</td>
</tr>
<tr>
<td valign="top">

### ⚡ Hızlı ekleme
- 41 hazır servis
- Türkiye'ye özel: Exxen, BluTV, Gain, tabii, TOD, S Sport Plus, Fizy
- 50 simge · 17 renk
- Canlı önizleme kartı

</td>
<td valign="top">

### 🔔 Hatırlatma
- 0 · 1 · 2 · 3 · 5 · 7 gün önce
- Saat 09:00
- Abonelik başına açılır
- Genel anahtar Ayarlar'da

</td>
<td valign="top">

### 💾 Yedekleme
- JSON yedek al
- CSV dışa aktar
- Birleştir **veya** değiştir
- Dosyalar uygulamasında görünür

</td>
</tr>
</table>

---

## 🖼 Ekranlar

| Özet | Abonelikler | Yeni abonelik |
|:---:|:---:|:---:|
| Gradyan özet kartı, yaklaşan ödeme kartları, kategori grafiği | Arama, kategori çipleri, logo'lu satırlar, kaydırma eylemleri | Hazır servis seçici, canlı önizleme, renk ve simge paleti |

> `Preview/onizleme.html` dosyası üç ekranın statik HTML temsilidir. Gerçek ekran görüntüleri için Xcode Canvas veya simülatör kullanın.

---

## 🏗 Mimari

```
          ┌──────────────────────┐
          │  SubscriptionStore   │  @Observable · @MainActor
          │  tek veri kaynağı    │  CRUD · toplamlar · JSON · içe/dışa aktarma
          └──────────┬───────────┘
                     │ .environment(store)
     ┌───────────────┼───────────────┐
     ▼               ▼               ▼
 Dashboard      Subscriptions     Settings
 (Özet)         (Liste → Detay    (Yedek · Bildirim
                 → Form)           · Para birimi)
                     │
                     ▼
          ┌──────────────────────┐
          │ NotificationService  │  her persist() sonrası yeniden planlar
          └──────────────────────┘
```

**İlkeler**

- **Tek veri kaynağı.** Görünümler store'u `@Environment` ile alır, kendi kopyasını tutmaz.
- **Değer tipli model.** `Subscription` bir struct. Form bir *draft* üzerinde çalışır, kaydedince store'a yazılır. Detay sayfası kimlikle gezinir ve her çizimde güncel kaydı okur.
- **Hesaplar modelde.** Sonraki ödeme, aylık maliyet, ödeme sayısı `Subscription` üzerinde; store yalnızca koleksiyon toplamlarını üretir.
- **Yan etkiler tek yerde.** Dosyaya yazma ve bildirim planlama yalnızca `persist()` içinde.
- **Ayarlar `@AppStorage`.** Anahtar adları `SettingsKeys` altında.

<details>
<summary>📁 Proje yapısı</summary>

```
abonelik/
├── AbonelikTakibi.xcodeproj/
├── AbonelikTakibi/
│   ├── AbonelikTakibiApp.swift        giriş noktası
│   ├── Models/
│   │   ├── Subscription.swift         model · BillingCycle · SubscriptionCategory · BackupPayload
│   │   └── ServicePreset.swift        hazır servisler · logo eşlemesi · simge/renk kütüphanesi
│   ├── Store/SubscriptionStore.swift  tek veri kaynağı
│   ├── Services/
│   │   ├── NotificationService.swift  yerel bildirimler
│   │   └── BackupDocument.swift       fileExporter belgesi
│   ├── Utilities/
│   │   ├── Formatters.swift           para ve tarih biçimleri (tr_TR)
│   │   └── AppTheme.swift             renkler · kart · ServiceIcon · boş durum
│   ├── Views/
│   │   ├── ContentView.swift          sekmeler
│   │   ├── Dashboard/DashboardView.swift
│   │   ├── Subscriptions/{List,Detail,Form}View.swift
│   │   └── Settings/SettingsView.swift
│   └── Assets.xcassets/
│       ├── AppIcon.appiconset/        AppIcon.png (betikle üretilir)
│       └── Logos/                     logo-<servis>.imageset (SVG, template)
├── Config/Info.plist                  ek plist anahtarları
├── Scripts/                           fetch_logos.sh · make_app_icon.swift
├── Tests/ModelLogicTests.swift
└── Preview/onizleme.html
```

</details>

---

## 🗃 Veri modeli

<details open>
<summary><b>Subscription</b></summary>

| Alan | Tip | Açıklama |
|---|---|---|
| `id` | `UUID` | Benzersiz kimlik; yedek birleştirmede eşleşme anahtarı |
| `name` | `String` | Görünen ad |
| `price` | `Double` | Döngü başına ücret |
| `currencyCode` | `String` | `TRY` · `USD` · `EUR` · `GBP` |
| `cycle` | `BillingCycle` | `weekly` · `monthly` · `quarterly` · `yearly` |
| `startDate` | `Date` | İlk ödeme tarihi |
| `category` | `SubscriptionCategory` | 9 kategoriden biri |
| `iconName` | `String` | SF Symbols adı |
| `colorHex` | `String` | 6 haneli hex, `#` olmadan |
| `logoName` | `String?` | Asset kataloğundaki logo, ör. `logo-netflix` |
| `notes` | `String` | Serbest metin |
| `isActive` | `Bool` | `false` ise toplamlara ve bildirimlere girmez |
| `reminderDaysBefore` | `Int?` | `nil` ise hatırlatma yok |
| `createdAt` | `Date` | Birleştirmede sıralama için |

Çözümleme her alanı `decodeIfPresent` ile okur; eksik alanlar varsayılan alır. Eski yedekler ve elle düzenlenmiş dosyalar sorunsuz yüklenir.

</details>

<details>
<summary><b>BillingCycle</b> · aylık çarpanlar</summary>

| Değer | Başlık | Aylık çarpan |
|---|---|---|
| `weekly` | Haftalık | 52 ÷ 12 |
| `monthly` | Aylık | 1 |
| `quarterly` | 3 Aylık | 1 ÷ 3 |
| `yearly` | Yıllık | 1 ÷ 12 |

</details>

<details>
<summary><b>SubscriptionCategory</b> · sabit renkler</summary>

Grafikte renk kategoriye bağlıdır, sıraya göre değişmez.

| Değer | Başlık | Renk |
|---|---|---|
| `streaming` | Dizi & Film | `#D9262E` |
| `music` | Müzik | `#1E9E5A` |
| `software` | Yazılım | `#2F62E8` |
| `cloud` | Bulut | `#0C8FBF` |
| `gaming` | Oyun | `#8A3FD9` |
| `news` | Haber & Dergi | `#D98A0B` |
| `fitness` | Spor & Sağlık | `#DB3E8E` |
| `education` | Eğitim | `#14A08A` |
| `other` | Diğer | `#6B7280` |

</details>

<details>
<summary><b>Hesaplama kuralları</b></summary>

- **Sonraki ödeme.** Başlangıca döngü *n* kez eklenir (`DateComponents(month: n)`, birikimli değil); bugünden büyük veya eşit ilk tarih seçilir. Ayın 31'inde başlayan abonelik şubatta 28'e kayar, martta 31'e döner.
- **Aylık maliyet.** `price × monthlyMultiplier`; yıllık bunun 12 katı.
- **Toplamlar.** Yalnızca aktif abonelikler, para birimine göre ayrı. Birimler arası dönüşüm yok.
- **Ana para birimi.** En çok aboneliği olan birim; eşitlikte Ayarlar'daki varsayılan.
- **Bu ay ödenecek.** Sonraki ödemesi bu takvim ayına düşen aboneliklerin ücret toplamı.
- **Ödeme sayısı.** Başlangıçtan bugüne geçen döngü sayısı + 1. Toplam ödenen = sayı × ücret (fiyat geçmişi bilinmez, tahmindir).

</details>

---

## 💾 Yedekleme

**Yerel depolama:** `Documents/subscriptions.json`, atomik yazma, tam dosya koruması, ISO 8601 tarihler, sıralı ve girintili anahtarlar. Dosyalar uygulamasında "Abonelik Takip" klasöründe görünür.

<details>
<summary>JSON yedek biçimi</summary>

```json
{
  "app" : "Abonelik Takip",
  "version" : 1,
  "exportedAt" : "2026-11-05T09:00:00Z",
  "subscriptions" : [
    {
      "id" : "2F1C6C7A-0D5E-4C0B-9B1E-6B8E2B0E1A11",
      "name" : "Netflix",
      "price" : 229.99,
      "currencyCode" : "TRY",
      "cycle" : "monthly",
      "startDate" : "2026-01-15T00:00:00Z",
      "category" : "streaming",
      "iconName" : "play.rectangle.fill",
      "colorHex" : "E50914",
      "logoName" : "logo-netflix",
      "notes" : "",
      "isActive" : true,
      "reminderDaysBefore" : 1,
      "createdAt" : "2026-01-15T10:00:00Z"
    }
  ]
}
```

Geri yükleme hem bu sarmalayıcıyı hem de düz `[Subscription]` dizisini kabul eder.

</details>

| Mod | Davranış |
|---|---|
| 🔀 **Birleştir** | Aynı `id` → güncelle · yeni → ekle · yedekte olmayan → koru |
| ♻️ **Tümünü değiştir** | Mevcut her şeyi sil, yedeği olduğu gibi yükle |

**CSV:** noktalı virgül ayraçlı, tüm alanlar tırnaklı. Sütunlar: Ad · Fiyat · Para Birimi · Döngü · Aylık Maliyet · Kategori · Başlangıç · Sonraki Ödeme · Aktif · Notlar. Yalnızca dışa aktarım içindir.

**Dosya adları:** `abonelik-yedek-YYYY-AA-GG.json` / `.csv`

---

## 🔔 Bildirimler

- Ayarlar'daki anahtar açılınca sistem izni istenir; reddedilirse anahtar kapanır ve iOS Ayarlar yönlendirmesi görünür.
- Her kaydetmede bekleyen bildirimler silinir ve **yalnızca aktif + hatırlatması açık** abonelikler için yeniden planlanır.
- Kimlik = abonelik UUID'si; silinen aboneliğin bildirimi de gider.
- Tetikleme: sonraki ödeme − `reminderDaysBefore` gün, 09:00. Geçmiş tarihler atlanır.
- Abonelik başına tek bildirim planlanır; iOS'un 64 bekleyen bildirim sınırı aşılmaz.

---

## 🏷 Marka logoları

`Scripts/fetch_logos.sh`, [Simple Icons](https://simpleicons.org) (CC0) kaynağından tek renk SVG indirir ve `Assets.xcassets/Logos/logo-<ad>.imageset` olarak template + vektör korumalı ekler. Uygulama logoyu marka renkli kutu üzerinde beyaz gösterir.

| | Servisler |
|---|---|
| ✅ **Logo var (17)** | Netflix · Spotify · YouTube · YouTube Music · HBO Max · MUBI · Dropbox · Google One · Claude Pro · Notion · 1Password · PlayStation Plus · Twitch · Duolingo · Udemy · Strava · Medium |
| 🔤 **Simge ile** | Apple Music · Apple TV+ · iCloud+ · Apple One / Arcade / Fitness+ (5.2.5) · Amazon Prime · OneDrive · ChatGPT Plus · Adobe · Canva · LinkedIn · Xbox · Nintendo · Storytel · Exxen · BluTV · Gain · tabii · TOD · S Sport Plus · Fizy |

`ServiceIcon` önce `UIImage(named:)` ile logoyu arar; yoksa SF Symbol'a döner. Logolar indirilmemiş olsa bile uygulama hatasız çalışır.

<details>
<summary>Kendi logonu ekle</summary>

1. `Assets.xcassets/Logos/logo-<ad>.imageset` oluştur, beyaz tek renk SVG veya PNG koy.
2. `ServicePreset.swift` → `logoSlugs` sözlüğüne `"Servis Adı": "<ad>"` ekle.

</details>

> ⚠️ Marka logoları tescillidir. Uygulama logoları yalnızca kullanıcının kendi eklediği aboneliği tanımlamak için gösterir. App Store incelemesinde kural 5.2.1 kapsamında sorumluluk yayıncıya aittir.

---

## 🎨 Tasarım

| | |
|---|---|
| **Vurgu** | `#5B5CE6` |
| **Özet kartı** | `#5B5CE6 → #8B5CF6 → #EC4899` çapraz gradyan |
| **Kartlar** | 20 pt sürekli köşe, sistem gruplu arka plan (açık / koyu otomatik) |
| **Rakamlar** | Sabit genişlikli rakamlar; değişimde yalnızca 0,25 s solma, başka animasyon yok |
| **Servis simgesi** | Marka renkli gradyan kutu, içinde beyaz logo veya SF Symbol |
| **Uyarı** | Ödeme ≤ 3 gün ise turuncu vurgu |

**Uygulama ikonu** elle çizilmez; `Scripts/make_app_icon.swift` CoreGraphics ile üretir. İndigo-mor-pembe gradyan zemin, sol üstte ışık, ortada abonelik döngüsünü temsil eden 270° açık halka ve onay işareti. Betiği düzenleyip yeniden çalıştırınca `AppIcon.png` güncellenir.

---

## 🧪 Test

```sh
swift Tests/ModelLogicTests.swift
```

Bağımsız betik, `Subscription.swift` içindeki algoritmanın kopyasını 13 senaryoda doğrular: dört döngü için sonraki ödeme, ayın 31'i / şubat / mart davranışı, bugün ödeme günü, gelecek tarihli başlangıç, ödeme sayısı, aylık maliyet dönüşümleri. **Son çalıştırma: 13 / 13 geçti.**

> `nextBillingDate` veya `paymentsMade` değişirse betikteki kopyayı da güncelleyin.

**Derleme durumu (Xcode 27.2):** iOS Simulator Debug ✅ · iOS cihaz Release ✅ · uyarı yok

---

## 🚢 App Store'a hazırlık

Mağaza metinleri ve form değerleri: [`Marketing/AppStoreMetadata.md`](Marketing/AppStoreMetadata.md)

- [x] Bundle identifier: `io.github.mugione.abonelik`, Team `H86X88P8FK`, otomatik imzalama
- [x] `MARKETING_VERSION` 1.0 / `CURRENT_PROJECT_VERSION` 1
- [x] Yalnızca iPhone (`TARGETED_DEVICE_FAMILY = 1`)
- [x] 1024×1024 ikon, alfa kanalı yok
- [x] `ITSAppUsesNonExemptEncryption = false`
- [x] `PrivacyInfo.xcprivacy` (UserDefaults · CA92.1, veri toplanmıyor)
- [x] Ekran görüntüleri 6,7" iPhone, 1290×2796, alfa yok
- [x] Apple marka logoları kaldırıldı (5.2.5); diğer logolar için inceleme notu hazır (5.2.1)
- [x] Gizlilik ve destek sayfası: `docs/` → https://mugione.github.io/abonelik/
- [x] App Store Connect: "Abonelik Takip – Hatırlatıcı" (Apple ID 6831321319), 1.0 (1) 5 Kasım 2026 incelemeye gönderildi

```sh
# Arşiv (imzasız) + App Store dağıtım imzalı IPA
xcodebuild -project AbonelikTakibi.xcodeproj -scheme AbonelikTakibi -configuration Release \
  -destination 'generic/platform=iOS' -archivePath build/AbonelikTakibi.xcarchive CODE_SIGNING_ALLOWED=NO archive
xcodebuild -exportArchive -archivePath build/AbonelikTakibi.xcarchive -exportPath build/export \
  -exportOptionsPlist Config/ExportOptions.plist -allowProvisioningUpdates
```

> Hesapta kayıtlı test cihazı yokken imzalı `archive` geliştirme profili bulamaz; bu yüzden imza dışa aktarmada atılır.

---

## ⚠️ Bilinen sınırlamalar

- Para birimleri arasında dönüşüm yok; toplamlar birim bazında ayrı.
- Toplam ödenen tutar fiyat geçmişini bilmez, tahmindir.
- Bildirimler yalnızca uygulama açılıp kaydetme yapıldığında yenilenir.
- iCloud eşitleme yok; cihazlar arası taşıma JSON yedekle.
- Arayüz metinleri kodda Türkçe sabit; çoklu dil için String Catalog gerekir.

---

## 🗺 Yol haritası

- [ ] 🆓 Ücretsiz deneme takibi ve bitiş hatırlatması
- [ ] 🧾 Gerçek ödeme geçmişi ve fiyat değişikliği kaydı
- [ ] 📱 Ana ekran ve kilit ekranı widget'ları
- [ ] 🎯 Aylık bütçe limiti
- [ ] 📈 Son 12 ay harcama grafiği
- [ ] 🔐 Face ID ile uygulama kilidi
- [ ] ☁️ İsteğe bağlı iCloud eşitleme
- [ ] 🌍 İngilizce yerelleştirme
- [ ] 💻 iPad için yan yana liste-detay düzeni

---

<div align="center">

**Lisans:** Kaynak kod projeyi oluşturan kişiye aittir. Marka logoları ilgili şirketlerin tescilli markasıdır; Simple Icons SVG dosyaları CC0.

<sub>SwiftUI ile, reklamsız ve çevrimdışı. 💜</sub>

</div>
