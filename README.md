# Fatura Kaşe/İmza

PDF ve HTML e-Arşiv/e-Fatura dosyalarına otomatik kaşe/imza basan basit masaüstü uygulaması.

Uygulama özellikle GİB/e-Arşiv ve pazaryeri faturalarında, kaşe/imza görselini faturanın belirlenen yerine otomatik yerleştirmek için hazırlanmıştır. (Şu anki konum uygundur dilerseniz arayüzden değiştirebilirsiniz.)

## Özellikler

- PDF faturaya doğrudan kaşe/imza ekler.
- HTML faturayı A4 PDF’e çevirir ve kaşe/imza ekler.
- HTML faturada `SAYIN` alanındaki müşteri adını okuyup çıktı dosya adı yapar.
- Kaşe/imza dosyasını bir kez seçtirir, sonra hatırlar.
- Çıktı klasörünü bir kez seçtirir, sonra hatırlar.
- Aynı isimli dosya varsa dosyanın üzerine yazmaz; sonuna `_2`, `_3` gibi ekler.
- macOS ve Windows için ayrı paketler içerir.

## İndirme

Sağ taraftaki **Releases** bölümünden işletim sisteminize uygun paketi indirin:

- `fatura_kase_imza_final_v4_paket.zip` → macOS
- `fatura_kase_imza_windows_v1_paket.zip` → Windows

> Not: Bu repoya kendi kaşe/imza görselinizi yüklemeyin. Uygulama ilk açılışta sizden kaşe/imza görselini seçmenizi ister.

## macOS Kurulum

1. `fatura_kase_imza_final_v4_paket.zip` dosyasını indirin.
2. ZIP dosyasını açın.
3. Klasör içinde Terminal açın.
4. Şunu çalıştırın:

```bash
chmod +x build_final_app_v4.sh
./build_final_app_v4.sh
```

5. Uygulama burada oluşur:

```text
dist/Fatura Kase Imza.app
```

6. `.app` dosyasını `Applications` klasörüne taşıyın.

İlk açılışta macOS güvenlik uyarısı verebilir. Bu durumda:

```text
Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç
```

## Windows Kurulum

1. `fatura_kase_imza_windows_v1_paket.zip` dosyasını indirin.
2. ZIP dosyasını açın.
3. `build_windows_exe.bat` dosyasına çift tıklayın.
4. İşlem bitince uygulama burada oluşur:

```text
dist\Fatura Kase Imza.exe
```

5. `.exe` dosyasını Masaüstü’ne veya istediğiniz klasöre kopyalayın.

Windows’ta HTML faturaları PDF’e çevirmek için Google Chrome veya Microsoft Edge kurulu olmalıdır. Microsoft Edge çoğu Windows bilgisayarda zaten yüklüdür.

## Kullanım

1. Uygulamayı açın.
2. İlk açılışta kaşe/imza görselinizi seçin.
3. Çıktı klasörünü seçin.
4. PDF veya HTML faturaları seçin.
5. **Kaşe/İmza Ekle** butonuna basın.

Uygulama kaşe/imza ve çıktı klasörü ayarlarını hatırlar. Sonraki açılışlarda tekrar seçmeniz gerekmez.

## Çıktı Dosya Adı

PDF dosyalarında çıktı adı şu formattadır:

```text
orijinal_dosya_adi_kaseli_imzali_07-08.pdf
```

HTML dosyalarında uygulama `SAYIN` alanından müşteri adını okur:

```text
Cahit_Arf_07-08.pdf
```

## Kaşe Konumu

Varsayılan konum A4 e-Arşiv/e-Fatura şablonuna göre ayarlanmıştır.

Uygulama içindeki değerler:

```text
Soldan
Üstten
Genişlik
Yükseklik
```

Bu değerlerle kaşe/imzanın yerini ve boyutunu değiştirebilirsiniz.

## Güvenlik ve Gizlilik

- Uygulama faturaları dışarı göndermez.
- İşlem bilgisayarınızda yerel olarak yapılır.
- Kaşe/imza görseliniz uygulama ayarlarında yerel olarak saklanır.
- Faturalar ve çıktılar sizin seçtiğiniz klasörde kalır.

## Bilinen Gereksinimler

macOS:

- Python 3
- PyMuPDF
- PyInstaller
- WeasyPrint opsiyonel
- HTML dönüştürme için Chrome kullanılabilir

Windows:

- Python 3
- PyMuPDF
- PyInstaller
- WeasyPrint opsiyonel
- HTML dönüştürme için Chrome veya Edge

Build scriptleri gerekli paketleri otomatik kurmaya çalışır.

## Sık Karşılaşılan Sorunlar

### macOS uygulamayı açmıyor

İlk açılışta güvenlik uyarısı normaldir.

```text
Sistem Ayarları → Gizlilik ve Güvenlik → Yine de Aç
```

### HTML çıktı kenarlardan kesiliyor

macOS v4 sürümünde HTML A4’e sığdırma düzeltmesi vardır. Eski sürüm kullanıyorsanız v4 paketini indirin.

### Kaşe/imza yanlış yere basılıyor

Uygulamadaki konum ayarlarını değiştirin:

- Soldan
- Üstten
- Genişlik
- Yükseklik

### HTML müşteri adını okuyamıyor

Uygulama `SAYIN` alanını arar. Fatura şablonunda bu alan farklıysa dosya adını orijinal dosya adından üretir.

## Lisans

Bu proje MIT lisansı ile paylaşılmıştır. Detay için `LICENSE` dosyasına bakın.

## Uyarı

Bu araç teknik kolaylık sağlamak için hazırlanmıştır. Kaşe/imza kullanımının hukuki ve ticari sorumluluğu kullanıcıya aittir.
