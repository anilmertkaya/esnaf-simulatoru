# Esnaf Simülatörü – Telefondan Play Store'a yayın rehberi

Bu rehberi sırayla takip et. Her aşamanın sonunda ne göreceğin yazıyor. Bir yerde takılırsan ekran görüntüsünü Claude'a gönder.

---

## AŞAMA A – Oyunu telefonuna kur (yaklaşık 20 dakika)

1. **Zip'i aç.** `esnaf-simulatoru.zip` dosyasına sağ tıklayıp "Tümünü ayıkla" de. İçinden `esnaf-simulatoru` klasörü çıkar.
2. **Gizli dosyaları göster.** Windows: Dosya Gezgini › Görünüm › Göster › Gizli öğeler. Mac: klasörde Cmd + Shift + . tuşları. Klasörde `.github` klasörünü görmelisin.
3. **GitHub hesabı aç.** github.com › Sign up. E-postanı doğrula.
4. **Depo oluştur.** Sağ üstte **+** › **New repository**. Ad: `esnaf-simulatoru`. **Public** seçili kalsın. **Create repository**.
5. **Dosyaları yükle.** "uploading an existing file" bağlantısına tıkla. `esnaf-simulatoru` klasörünü aç, **içindeki her şeyi** (`.github` dahil) seçip tarayıcıya sürükle. Yükleme bitince **Commit changes**.
6. **Derlemeyi bekle.** Üstte **Actions** sekmesi. "Uygulamayı derle" işi sarı döner, 5–10 dakikada yeşil tik olur.
7. **APK'yı indir.** İşe tıkla, alttaki **Artifacts** bölümünden `1-telefona-kur-APK`'ya tıkla. İnen zip'in içinde `esnaf-simulatoru.apk` var.
8. **Telefona kur.** APK'yı telefona gönder (WhatsApp'ta kendine, Drive, kablo). Dokun › bilinmeyen kaynaklara izin ver › Yükle. Play Koruma uyarısında "Yine de yükle".

✅ Ana ekranda çay bardağı ikonlu **Esnaf Simülatörü** var ve oyun açılıyor.

---

## AŞAMA B – E-posta adresini yaz (5 dakika)

Gizlilik politikasında iletişim adresi olmalı. GitHub'da iki dosyada `[E-POSTA ADRESİNİZ]` yazan yeri kendi e-postanla değiştir:

1. Depoda `docs/gizlilik-politikasi.html` dosyasına tıkla › sağ üstte kalem ikonu › `[E-POSTA ADRESİNİZ]` yazısını bul, e-postanı yaz › **Commit changes**.
2. Aynısını `www/index.html` dosyasında yap (dosyanın alt kısmında, `CONTACT:` yazan satırda).
3. Aynısını `docs/index.html` dosyasında da yap (web sürümü için).

---

## AŞAMA C – Gizlilik sayfasını internete aç (5 dakika)

1. Depoda **Settings** › soldan **Pages**.
2. "Branch" altında **main** ve klasör olarak **/docs** seç › **Save**.
3. 1–2 dakika sonra sayfanın üstünde adres çıkar: `https://KULLANICI-ADIN.github.io/esnaf-simulatoru/`

✅ Şu iki adres çalışıyor:
- Oyunun web sürümü: `https://KULLANICI-ADIN.github.io/esnaf-simulatoru/`
- Gizlilik politikası: `https://KULLANICI-ADIN.github.io/esnaf-simulatoru/gizlilik-politikasi.html`

Web sürümünün linkini, telefonu Android olmayan arkadaşlarına da gönderebilirsin.

---

## AŞAMA D – Play Store paketini (AAB) üret (10 dakika)

`imza-anahtari.zip` dosyasında uygulamanın imza anahtarı var. **Bu dosyayı GitHub'a yükleme, kimseyle paylaşma, güvenli bir yere yedekle.**

1. Depoda **Settings** › soldan **Secrets and variables** › **Actions** › **New repository secret**.
2. Ad: `KEYSTORE_BASE64`. Değer: `KEYSTORE_BASE64.txt` dosyasının **tüm** içeriğini kopyala-yapıştır › **Add secret**.
3. Tekrar **New repository secret**. Ad: `KEYSTORE_PASSWORD`. Değer: `KEYSTORE_PASSWORD.txt` içeriği › **Add secret**.
4. **Actions** › soldan "Uygulamayı derle" › sağda **Run workflow** › yeşil **Run workflow**.

✅ İş bitince Artifacts bölümünde `2-play-store-AAB` da var. İçindeki `esnaf-simulatoru-play.aab`, Play Store'a yükleyeceğin dosya.

---

## AŞAMA E – Google Play geliştirici hesabı (1–3 gün)

1. play.google.com/console adresine git, Google hesabınla giriş yap.
2. Hesap türü: **Kişisel** (şirketin yoksa).
3. Tek seferlik kayıt ücretini öde, kimlik doğrulamasını tamamla (kimlik fotoğrafı istenir). Onay birkaç gün sürebilir.

---

## AŞAMA F – Uygulamayı oluştur ve mağaza sayfasını doldur (1 saat)

1. Play Console › **Uygulama oluştur**. Ad: Esnaf Simülatörü, dil: Türkçe, Oyun, Ücretsiz. Beyanları onayla.
2. **Ana mağaza girişi**: `magaza-gorselleri` klasöründeki `MAGAZA-METINLERI.md` dosyasından metinleri kopyala, görselleri yükle.
3. **Uygulama içeriği** bölümündeki her formu, aynı dosyadaki cevaplarla doldur.

---

## AŞAMA G – Kapalı test (14 gün, zorunlu)

Yeni kişisel hesaplarda, en az 12 test kullanıcısının 14 gün boyunca kesintisiz testte kalması gerekiyor.

1. **Test ve yayınla › Test › Kapalı test** › yeni kanal oluştur.
2. **Test kullanıcıları**: bir e-posta listesi oluştur, en az **15–20 kişinin** Gmail adresini ekle (biri ayrılırsa süre bozulmasın diye 12'den fazla).
3. **Yeni sürüm oluştur** › Play uygulama imzalama sorulursa Google'ın önerdiği seçeneği kabul et › `esnaf-simulatoru-play.aab` dosyasını yükle › sürüm notu yaz › incelemeye gönder.
4. Onaylanınca "Katılma bağlantısı"nı test kullanıcılarına gönder. Her biri bağlantıyı açıp **"Test kullanıcısı ol"** demeli ve oyunu Play Store'dan indirmeli.
5. 14 gün boyunca kimse testten çıkmasın. Arada oyunu açıp oynamalarını rica et.

---

## AŞAMA H – Yayına çık

1. 14 gün dolunca Play Console panelinde **Üretim erişimi için başvur** düğmesi açılır.
2. Soruları cevapla (test sürecini, aldığın geri bildirimleri anlat).
3. Onay gelince **Üretim** kanalında yeni sürüm oluştur, aynı veya daha yeni AAB'yi yükle, yayınla.

🎉 Oyun Play Store'da!

---

## Oyunu güncellemek

`www/index.html` dosyasını değiştirip GitHub'a yükle. Aynı dosyayı `docs/index.html` olarak da yükle (web sürümü için). GitHub yeni APK ve AAB'yi otomatik üretir; sürüm numarası kendiliğinden artar. Yeni AAB'yi Play Console'da yeni sürüm olarak yükle.
