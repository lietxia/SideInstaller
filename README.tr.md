<div align="center">

<img src="app-icon.png" alt="SideInstaller" width="120" />

# SideInstaller

**SideStore ve LiveContainer'ı doğrudan iPhone'una yükle — bilgisayar gerekmez.**

[![Install](https://img.shields.io/badge/Install-SideInstaller-2ea44f?style=for-the-badge)](https://sideinstaller.net/)
[![Version](https://img.shields.io/badge/version-2.2.0-2669ed?style=for-the-badge)](CHANGELOG.md)
[![Platform](https://img.shields.io/badge/platform-iOS-lightgrey?style=for-the-badge&logo=apple)](#gereksinimler)
[![License](https://img.shields.io/badge/license-Custom-orange?style=for-the-badge)](LICENSE.md)

🌐 **Language / 语言:** [English](README.md) · [简体中文](README.zh-CN.md) · [Español](README.es.md) · [Italiano](README.it.md) · [Tiếng Việt](README.vi.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Português](README.pt-BR.md) · [Türkçe](README.tr.md)

</div>

---

> [!CAUTION]
> **SideInstaller'ı yalnızca resmi kaynaktan yükle.**
>
> Bu proje açık kaynaklıdır; yani herkes kodu çatallayabilir, Apple kimliğini ve parolanı kendi sunucusuna
> yükleyen bir kimlik bilgisi çalma aracı ekleyebilir, yeniden derleyebilir ve aynı ad ve simgeyle
> dağıtabilir. Kötü amaçlı bir çatal dışarıdan gerçek uygulamayla birebir aynı görünür.
>
> Yayınladığım **tek** derlemeler şunlardır:
> - **Web sitesi:** https://sideinstaller.net/
> - **Depo:** https://github.com/FrizzleM/SideInstaller
>
> SideInstaller'ı başka bir siteden, AltStore kaynağından, Telegram kanalından, Discord sunucusundan,
> uygulama deposundan veya aynadan yükleme, ne kadar resmi görünse de. Derlemelerimi açık izin olmadan
> yeniden dağıtmak da [lisans](LICENSE.md) ile yasaklanmıştır.
>
> "sideinstaller.com" adlı sahte bir site var. Bu site **resmi değil** ve büyük olasılıkla kötü amaçlı
> yazılım sunuyor. Lütfen yalnızca yukarıdaki **resmi kaynaklardan** indirdiğinden emin ol.

> [!NOTE]
> **Bu çatal hakkında — yalnızca belgeler.** Bu çatal yalnızca bu yönergeleri çevirmek ve netleştirmek
> için var. **Hiçbir uygulama ikilisi derlemiyor veya yayınlamıyor**; her indirme bağlantısı hâlâ yukarıdaki
> resmi kaynaklara işaret ediyor. Buradaki uygulamanın kaynak kodu değiştirilmemiştir. Gerçek uygulamayı
> her zaman https://sideinstaller.net/ adresinden al — asla bir çataldan, aynadan veya yeniden derlenmiş IPA'dan.

---

## Bu sayfada

- [Nedir](#nedir)
- [Gereksinimler](#gereksinimler)
- [Nasıl kullanılır](#nasıl-kullanılır)
  - [Yöntem A — siboot (iOS 27+, bilgisayarsız)](#yöntem-a--siboot-ios-27-bilgisayarsız)
  - [Yöntem B — kurumsal sertifika (eski iOS)](#yöntem-b--kurumsal-sertifika-eski-ios)
  - [Bağlantılar](#bağlantılar)
  - [Kestirmeler](#kestirmeler)
- [Uyumluluk](#uyumluluk)
  - [iOS 26.4'ten 26.x'e: uzaktan eşleme dosyası](#ios-264ten-26xe-uzaktan-eşleme-dosyası)
- [SideInstaller güvenli mi?](#sideinstaller-güvenli-mi)
- [Proje yapısı](#proje-yapısı)
- [Katkıda bulunma](#katkıda-bulunma)
- [Lisans](#lisans)

---

## Nedir

SideStore ve LiveContainer şu anda iOS'ta yan yüklemenin en iyi yolu. Ancak büyük bir sorun var:
bunları yüklemek bir PC gerektiriyor, ki birçok insanın PC'si yok. Bu yüzden SideInstaller'ı yaptım —
SideStore ve LiveContainer'ı doğrudan iPhone'una kuran, bilgisayar gerektirmeyen ücretsiz ve açık kaynaklı bir iOS uygulaması.

SideInstaller tüm kurulum sürecini cihaz üzerinde halleder. Eşleme, sağlama ve yükleme adımlarını —
normalde seni bilgisayara takılıp masaüstü araçları çalıştırmak zorunda bırakan adımları — telefonun
kendisinde çalışan tek bir uygulamadan yapar. İşlem bitince kendi uygulamalarını yan yüklemeye hazır,
tamamen çalışan bir SideStore ve LiveContainer kurulumu elde edersin.

Her şey basit olacak şekilde tasarlandı. Karmaşık yapılandırma yok, komut satırı yok, alttaki
mekanizmaların nasıl çalıştığını anlama ihtiyacı yok. Uygulamayı açıp birkaç adımı izlersin, gerisini
o yapar. Yan yükleme yapmak isteyip de Mac'i veya PC'si olmayan herkes için bu, başlamanın önündeki
en büyük engeli kaldırıyor.

Açık kaynaklı olduğu için hiçbir şeyi sadece benim sözüme güvenerek kabul etmen gerekmiyor. Tüm kod
herkesin okuyabilmesi, denetleyebilmesi veya katkıda bulunabilmesi için mevcut; cihazında tam olarak neyin çalıştığını görebilirsin.

## Gereksinimler

Başlamadan önce şunlara sahip olduğundan emin ol:

- **iOS 27+** üzerinde bir **iPhone veya iPad** — iOS 17.4+ için bilgisayarda oluşturulmuş bir eşleme
  dosyasıyla; iOS 26.4'ten itibaren bir [uzaktan eşleme dosyası](#ios-264ten-26xe-uzaktan-eşleme-dosyası)
  gerekir. [Uyumluluk tablosuna](#uyumluluk) bak.
- **Wi-Fi** (yalnızca ilk kez).
- **Geliştirici Modu** açık (siboot yöntemi için).
- **Apple hesap bilgilerin** — yalnızca cihaz üzerinde uygulamaları imzalamak için kullanılır; asla toplanmaz.

## Nasıl kullanılır

İki kurulum yöntemi var. iOS sürümüne uyanı seç:

| Durumun | Yöntem | PC gerekli mi? |
| --- | --- | --- |
| iOS 27 veya üzeri | [Yöntem A — siboot](#yöntem-a--siboot-ios-27-bilgisayarsız) (önerilen) | Hayır |
| iOS 17.4 – 26.7 veya siboot senin için çalışmıyor | [Yöntem B — kurumsal sertifika](#yöntem-b--kurumsal-sertifika-eski-ios) | Evet, bir kez |

### Yöntem A — siboot (iOS 27+, bilgisayarsız)

[siboot](https://github.com/FrizzleM/siboot), SideInstaller'ı iPhone'un kendisinden, kendi Apple hesabınla
imzalayarak kurar: ne bilgisayar ne sertifika gerekir. **iOS 27 veya üzeri**, **Wi-Fi** ve **Geliştirici
Modu açık** olması gerekir. [sideinstaller.net](https://sideinstaller.net/) web sitesi 1 ila 3. adımları
görsel olarak gösteriyor.

#### Adım 1 — Ücretsiz üç uygulamayı yükle

Üçünü de App Store'dan yükle:

- [rootshell](https://apps.apple.com/app/rootshell-local-terminal-ssh/id6755794662)
- [Open Minis](https://apps.apple.com/app/id6759188481)
- [LocalDevVPN](https://apps.apple.com/app/id6755608044)

#### Adım 2 — rootshell'de eşle

1. rootshell'de **Ayarlar › Konum Günlüğü Modu › Yalnızca Oturum** seçeneğini aç.
2. **Yerel Kabuk**a, sonra sağ üstteki **Aç**a dokun.
3. Şu komutları **satır satır, birer tane** çalıştır:

   ```sh
   curl -fsSLO https://raw.githubusercontent.com/FrizzleM/siboot/main/rootshell/bin/siboot-pair.wasm
   ```

   ```sh
   ifconfig en0 > ifconfig.txt
   ```

   ```sh
   ./siboot-pair.wasm
   ```

4. **Ayarlar › Gizlilik ve Güvenlik › Geliştirici Modu**nu aç, aşağıya kaydır,
   **siboot ile eşle**ye dokun, sonra iPhone parolanı ve rootshell'in gösterdiği kodu gir.
5. **rootshell'i çalışır durumda bırak** — kapatma.

#### Adım 3 — Open Minis'ten yükle

1. **LocalDevVPN**'e bağlan.
2. **Open Minis**te sağ üstteki konsol simgesine, ardından **Shell Terminal**e dokun.
3. Çalıştır:

   ```sh
   wget -qO- https://raw.githubusercontent.com/FrizzleM/siboot/main/minis/install.sh | sh
   ```

4. rootshell'in gösterdiği aktarım kodunu gir — **yalnızca ilk kez**;
   bundan sonra siboot kaydettiği eşleme dosyasını kullanır.
5. Apple hesabının **e-posta** adresini, **parolasını** ve **doğrulama kodunu** gir.
6. **Minis'i açık tut**, bitene kadar. İlk kez Apple hesabına **Ayarlar › Genel › VPN ve Aygıt
   Yönetimi** altında güven.

#### Adım 4 — SideInstaller'ı aç

**LocalDevVPN bağlıyken** Apple hesabınla oturum aç ve **SideInstaller'ı yükle** veya
**SideStore + LiveContainer yükle**ye dokun. Hepsi bu kadar.

> **Eşlemeden sonra:** Open Minis'te `siboot developer-mode` çalıştırmak iPhone'dan Ayarlar'da Geliştirici
> Modu anahtarını göstermesini ister; açmak için `--turn-on` ekle.
> [Ayrıntılar](https://github.com/FrizzleM/siboot/blob/main/minis/README.md#developer-mode) için bak.

### Yöntem B — kurumsal sertifika (eski iOS)

iOS 27'den önceki sürümlerde veya siboot senin için çalışmıyorsa, [sideinstaller.net/#legacy](https://sideinstaller.net/#legacy)
adresindeki kurumsal sertifikalardan biriyle SideInstaller'ı yükle, sonra yukarıdaki **4. adım**dan devam
et. (Eski sürümlerde ayrıca bir eşleme dosyası gerekir — bkz. [Uyumluluk](#uyumluluk).)

### Bağlantılar

SideInstaller üç tür `sideinstaller://` bağlantısı açar ve herhangi biri üzerinde işlem yapmadan önce sorar:

| Bağlantı | Ne yapar |
| --- | --- |
| `sideinstaller://install?url=<percent-encoded https link to an .ipa>` | IPA'yı özel .ipa olarak indirir ve yükler — bir web sitesinden tek dokunuşla yükleme içindir. |
| `sideinstaller://pairingFile?data=<base64 pairing file>` | Bir eşleme dosyasını içe aktarır. SideStore, `sidestore://pairing?urlname=sideinstaller` ile istendiğinde bir tane geri gönderir — Eşleme dosyası kartındaki **SideStore'dan al** tam olarak bunu yapar. |
| `sideinstaller://certificate?data=<base64 PKCS#12>&password=<password>` | Apple sertifikayı Apple kimliğinin sertifikaları arasında listelediğinde, SideInstaller'ın bundan sonra o sertifikayla imzalamasını sağlar. |

**SideStore'un sertifikasını kullan** ("Bir sertifika zaten var" açılır penceresinde ve Sertifikalar sayfasında),
SideStore'dan kendi sertifikasını şununla ister:
`sidestore://certificate?callback_template=sideinstaller://certificate?data=$(BASE64_CERT)&password=$(PASSWORD)`
(yüzde kodlanmış); böylece ücretsiz bir Apple kimliğinin tek sertifikası iki uygulamaya da hizmet eder. Bu yanıt,
tekrar sormayan tek bağlantıdır: SideStore az önce dışa aktarıp aktarmamayı sormuştur.

Discord ve çoğu sohbet uygulaması yalnızca `https://` bağlantılarını dokunulabilir yapar; oraya bir yükleme
bağlantısı göndermek için `https://sideinstaller.net/open.html?url=<percent-encoded https link to an .ipa>`
adresini kullan. Bu sayfa IPA'nın nereden indirildiğini gösterir ve bağlantıyı `sideinstaller://install`a
devreder; iOS uygulamayı kendiliğinden açmadığında kullanılacak bir düğmesi de vardır.

### Kestirmeler

SideInstaller'ın araçları Kestirmeler uygulamasındaki eylemlerdir; böylece bir kısayol, bir otomasyon,
Eylem düğmesi veya Siri bunları çalıştırabilir:

- **Konum taklidi:** Set Location (haritada seçilen bir yer, bir adres veya başka bir eylemden gelen bir konum),
  Set Location to Coordinates, Set Location to Saved Place, Reset Location, Get Spoofed Location, Is
  Location Spoofed, Play GPX Route, Travel to Place (OpenStreetMap üzerinde planlanmış, yürüyerek,
  bisikletle veya her yolun hız sınırında araçla gidilen bir rota), Stop Route, Save Place and
  Delete Saved Place.
- **Yan yüklenen uygulamalar:** Get Sideloaded Apps (her birinin sona erme günü ve kalan günleriyle),
  Refresh All Apps ve Refresh App.
- **Yükleme:** Install App (SideStore, LiveContainer + SideStore, Madeira veya AltStore; kararlı veya
  gecelik), Install IPA ve Install IPA from URL. Bunlar SideInstaller'ı açar, çünkü yükleme sırasında
  orada bir şey sormak için durabilir.
- **Eşleme ve diğerleri:** Get Pairing File, Import Pairing File, Install Pairing File into Apps,
  Show Developer Mode in Settings, Is LocalDevVPN Connected, Connect LocalDevVPN ve Get Activity
  Log.

Diğer eylemler, uygulamanın kendi sayfaları gibi LocalDevVPN üzerinden arka planda çalışır; tünelin
açık olması gerekir: eylemlerden önce bağlan (Kestirmeler'deki Set VPN eylemi bunu yapabilir) veya
**Gerektiğinde LocalDevVPN'i başlat**ı aç; eylem bağlanmak için SideInstaller'da devam etmeyi ister.
Kısayolla ayarlanan bir konum, Reset Location yapılana kadar kalır: SideInstaller, uygulamada bir konum
ayarladığında olduğu gibi onu korumak için arka planda çalışmaya devam eder. Siri, "Spoof my location
to *saved place* with SideInstaller", "Reset my location with SideInstaller" ve "Refresh my apps with
SideInstaller" ifadelerini bilir. Eylemlerin adları İngilizcedir; çalışırken söyledikleri SideInstaller'ın dilindedir.

## Uyumluluk

| iOS | Uyumlu mu? |
| --- | --- |
| 27+ | ✅ Evet — siboot ile bilgisayar gerekmez |
| 26.4 – 26.7 | ⚠️ Evet, ancak [uzaktan eşleme dosyası gerekir](#ios-264ten-26xe-uzaktan-eşleme-dosyası) ve bunun için PC gerekir |
| 17.4 – 26.3 | ⚠️ Evet, ancak [bir eşleme dosyası gerekir](https://docs.sidestore.io/docs/advanced/alternative#pairing) ve bunun için PC gerekir |
| <17.4 | ❌ Hayır |

### iOS 26.4'ten 26.x'e: uzaktan eşleme dosyası

iOS 26.4'ten itibaren iPhone, lockdown eşleme dosyalarını (jitterbugpair,
`pymobiledevice3 lockdown pair` veya idevice_pair'in **Lockdown** seçeneğiyle oluşturulanlar) LocalDevVPN üzerinden
bağlanır bağlanmaz reddeder; ne kadar yeni olursa olsun artık iPhone'da kullanılamazlar. Uzaktan eşleme (RPPairing)
dosyası hâlâ çalışır:

1. Mac, Windows PC veya Linux bilgisayarda [idevice_pair](https://github.com/jkcoxson/idevice_pair/releases/latest)
   uygulamasını aç ve iPhone'u tak. İsterse **Güven**e dokun.
2. iPhone'u seç, **Remote pairing** seçeneğini seç, **Create**e tıkla ve bitene kadar iPhone'un kilidini
   açık tut.
3. **Save to file…**e tıkla ve dosyayı AirDrop, iCloud Drive veya kabloyla iPhone'a gönder.
4. SideInstaller'da **Eşleme dosyasını içe aktar**a (veya **Değiştir**e) dokun ve dosyayı seç.

[iLoader](https://github.com/nab138/iloader) ile dışa aktarılmış bir eşleme dosyası (**Manage Pairing File** ›
**Export**) de iki türü birden içerir ve çalışır.

## SideInstaller güvenli mi?

SideInstaller güvenlik ve gizlilik gözetilerek oluşturuldu. Uygulama tamamen yerel ve açık kaynaklıdır,
yani herkes tam olarak ne yaptığını inceleyebilir.

**Apple kimlik bilgilerin cihazından asla çıkmaz.** Yalnızca yerel olarak, uygulamalarını imzalamak
ve yüklemek için kullanılır; hiçbir şekilde iletilmez, günlüğe kaydedilmez veya toplanmaz.

**Sunucu yok, analiz yok, hesap yok.** Hiçbir şey toplanmaz ve kayıt olacak bir şey de yoktur.

**Tamamen denetlenebilir.** Her satırı kaynak kodda doğrulanabilir.

> [!WARNING]
> Yukarıdakilerin tamamı **bu** depo ve buradan yayınlanan derlemeler için geçerlidir. Bu, çatallar,
> yeniden imzalanmış IPalar veya başka bir yerde bulduğun kopyalar için geçerli bir güvence **değildir**;
> bunlar içine yazdığın Apple kimliğini çalmak için değiştirilmiş olabilir. https://sideinstaller.net/
> adresinden almadıysan,
> kimlik bilgilerini ona emanet etme.

## Proje yapısı

| Yol | İçeriği |
| :-- | :-- |
| `ios-app/` | SwiftUI uygulaması — arayüz, yükleme motoru, sertifika işleme, çeviriler |
| `ios-live-activity/` | Eşleme kodunu Dynamic Island'da ve Kilit Ekranında çizen widget uzantısı |
| `ios-tests/` | Uygulamanın birim testleri (`SideInstallerTests`) |
| `rust-core/` | `SideInstallerFFI.xcframework` içine derlenen Rust çekirdek |
| `scripts/` | Derleme, kontrol ve yayın betikleri |
| `.github/` | Çekme isteklerini kontrol eden, imzasız IPA'yı derleyen, sürüm olarak yayınlayan ve imzalayana ileten iş akışları |

İmzalı derlemeler ve yükleme sayfası [FrizzleM/SideInstaller-Signed](https://github.com/FrizzleM/SideInstaller-Signed)
deposunda: her sürümün IPA'sını her sertifikayla imzalar, imzalı IPA'ları kendi sürümüne ekler ve
[sideinstaller.net](https://sideinstaller.net/)i dağıtır. Hiçbir IPA hiçbir depoya asla eklenmez.

SideInstaller'ı [iPhone'un kendisinden kuran](#nasıl-kullanılır) siboot,
[FrizzleM/siboot](https://github.com/FrizzleM/siboot) deposunda. Bu deponun satıcı crate'lerini ve
rust-core'ın `apple_session.rs` ve `error_text.rs` dosyalarını tek bir commit'e sabitlenmiş bir alt modül
üzerinden derler; bu yüzden buradaki bir değişiklik siboot'a yalnızca o sabitleme taşındığında ulaşır.

## Katkıda bulunma

Sorunlar ve çekme istekleri memnuniyetle karşılanır. Bir hata bildiriyorsan lütfen iOS sürümünü,
uygulama sürümünü ve hatanın hangi adımda oluştuğunu ekle.

Her çekme isteği `checks` iş akışıyla kontrol edilir: Rust testleri ve clippy, uygulamanın birim testleriyle
simülatör derlemesi ve çeviriler (uygulamaya eklenen bir dizenin her `ios-app/*Strings.swift` dosyasında
bir girdisi olması gerekir). Aynı kontroller Mac'te `scripts/test-rust.sh`, `scripts/check-ios.sh` ile
(Xcode projesini oluşturduğu için temiz bir klonda) ve `scripts/check_translations.py` ile
çalıştırılır.

## Lisans

Bkz. [LICENSE.md](LICENSE.md). Kısaca: **kaynak kodu** kaynak göstererek, ticari olmayan amaçlarla
okuyabilir, değiştirebilir ve paylaşabilirsin. Resmî derlemeleri (IPA'ları) yeniden dağıtmak veya projeyi
herhangi bir biçimde ticari olarak kullanmak yazılı izin gerektirir.

<div align="center">

**SideInstaller, [FrizzleM](https://github.com/FrizzleM) tarafından** · Bu çataldaki belge çevirileri topluluk katkılarıdır; uygulamanın telif hakkı © FrizzleM'de kalır.

</div>