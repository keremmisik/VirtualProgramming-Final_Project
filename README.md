# 🌿 Yeşil Eksen (Green Axis)

**Tarımsal ve Endüstriyel Atık Yönetim Sistemi**

Yeşil Eksen, tarımsal ve endüstriyel atık yönetim sürecini denetleyen ve yöneten bir admin platformudur. Bu sistem, çiftlikler, firmalar ve odalar arasındaki atık ticaretini yönetir ve sürdürülebilirlik etkisini ölçer.

---

## 📋 İçindekiler

- [Özellikler](#-özellikler)
- [Sistem Gereksinimleri](#-sistem-gereksinimleri)
- [Kurulum](#-kurulum)
- [Kullanım](#-kullanım)
- [Proje Yapısı](#-proje-yapısı)
- [Veritabanı](#-veritabanı)
- [Kullanıcı Rolleri](#-kullanıcı-rolleri)
- [Teknolojiler](#-teknolojiler)
- [Geliştirme](#-geliştirme)
- [Katkıda Bulunma](#-katkıda-bulunma)
- [Lisans](#-lisans)

---

## ✨ Özellikler

### 🏢 Firma Yönetimi
- Firma kayıt ve onay süreçleri
- Firma bilgileri yönetimi
- Firma belgeleri yükleme ve görüntüleme
- Firma listesi ve detay görüntüleme

### 🌾 Çiftlik Yönetimi
- Çiftlik kayıt ve onay süreçleri
- Çiftlik bilgileri yönetimi
- Çiftlik ürünleri yönetimi
- Çiftlik belgeleri yükleme ve görüntüleme

### 📦 Ürün Yönetimi
- Tarımsal atık ürünleri kayıt
- Ürün kategorileri yönetimi
- Ürün miktarları takibi
- Ürün belgeleri yönetimi

### 📝 Alım Talepleri
- Firmaların çiftliklerden ürün talep etme
- Talep onay/red süreçleri
- Talep durumu takibi
- Talep geçmişi görüntüleme

### 📊 Raporlama
- **Genel Raporlar**: Sistem genelinde istatistikler
- **SDG Raporları**: Sürdürülebilir Kalkınma Hedefleri raporları
  - Geri kazanılan atık miktarı (ton)
  - Engellenen CO₂ salınımı (ton)
  - Ekonomiye kazandırılan değer (TL)
- **Excel Dışa Aktarma**: Raporları Excel formatında dışa aktarma

### 🔐 Kullanıcı Yönetimi
- Rol tabanlı erişim kontrolü
- Güvenli giriş sistemi
- Kullanıcı oturum yönetimi
- İşlem logları

### 📄 Belge Yönetimi
- PDF belge yükleme
- Belge görüntüleme
- Belge kategorileri
- QR kod oluşturma

---

## 💻 Sistem Gereksinimleri

### Minimum Gereksinimler
- **İşletim Sistemi**: Windows 7 veya üzeri
- **.NET Framework**: 4.7.2 veya üzeri
- **RAM**: 2 GB
- **Disk Alanı**: 500 MB
- **Ekran Çözünürlüğü**: 1024x768

### Önerilen Gereksinimler
- **İşletim Sistemi**: Windows 10/11
- **RAM**: 4 GB veya üzeri
- **Disk Alanı**: 1 GB
- **Ekran Çözünürlüğü**: 1920x1080

---

## 🚀 Kurulum

### 1. Projeyi İndirme
```bash
git clone https://github.com/kullaniciadi/VirtualProgramming-Final_Project.git
cd VirtualProgramming-Final_Project
```

### 2. Visual Studio ile Açma
1. `YesilEksen.sln` dosyasını Visual Studio ile açın
2. Visual Studio otomatik olarak NuGet paketlerini geri yükleyecektir
3. Eğer paketler yüklenmezse, Solution Explorer'da projeye sağ tıklayın ve "Restore NuGet Packages" seçeneğini seçin

### 3. Veritabanı Kurulumu
- Uygulama ilk çalıştırıldığında otomatik olarak `YesilEksen.db` veritabanı dosyası oluşturulur
- Veritabanı, uygulamanın çalıştığı klasörde (`bin\Debug` veya `bin\Release`) oluşturulur

### 4. Derleme ve Çalıştırma
1. Visual Studio'da `F5` tuşuna basın veya "Start Debugging" butonuna tıklayın
2. Uygulama derlenecek ve çalışacaktır

### 5. Test Kullanıcıları
Uygulama ilk çalıştırıldığında otomatik olarak aşağıdaki test kullanıcıları oluşturulur:

| Kullanıcı Adı | Şifre | Rol |
|--------------|-------|-----|
| `sanayi_admin` | `123456` | Sanayi Odası Admin |
| `ziraat_admin` | `123456` | Ziraat Odası Admin |

---

## 📖 Kullanım

### Giriş Yapma
1. Uygulamayı başlatın
2. Kullanıcı adı ve şifrenizi girin
3. "Giriş Yap" butonuna tıklayın
4. Rolünüze göre ilgili dashboard'a yönlendirileceksiniz

### Sanayi Odası Admin Paneli
- **Firma Onay**: Başvuruda bulunan firmaları görüntüleyin ve onaylayın/reddedin
- **Alım Talepleri**: Firmaların çiftliklerden yaptığı alım taleplerini yönetin
- **Raporlama**: Genel raporlar ve SDG raporları oluşturun
- **Firmalar**: Tüm firmaları listeleyin ve detaylarını görüntüleyin

### Ziraat Odası Admin Paneli
- **Çiftlik Onay**: Başvuruda bulunan çiftlikleri görüntüleyin ve onaylayın/reddedin
- **Ürün Onay**: Çiftliklerin eklediği ürünleri onaylayın/reddedin
- **Raporlama**: Genel raporlar ve SDG raporları oluşturun
- **Çiftlikler**: Tüm çiftlikleri listeleyin ve detaylarını görüntüleyin

### Firma Kullanıcısı
- Firma bilgilerinizi görüntüleyin ve güncelleyin
- Çiftliklerden ürün talep edin
- Talep durumlarınızı takip edin
- Belgelerinizi yükleyin

### Çiftlik Kullanıcısı
- Çiftlik bilgilerinizi görüntüleyin ve güncelleyin
- Ürünlerinizi ekleyin ve yönetin
- Gelen talepleri görüntüleyin
- Belgelerinizi yükleyin

---

## 📁 Proje Yapısı

```
VirtualProgramming-Final_Project/
│
├── YesilEksen/
│   ├── Sanayi/              # Sanayi Odası modülleri
│   │   ├── SanayiFirmaOnay.cs
│   │   ├── SanayiAlımTalebi.cs
│   │   └── SanayiGenelRapor.cs
│   │
│   ├── Tarım/               # Ziraat Odası modülleri
│   │   ├── ÇiftlikOnay.cs
│   │   ├── ÇitflikÜrünOnay.cs
│   │   ├── Çİftçi-Dasboard.cs
│   │   ├── GenelRapor.cs
│   │   └── SdkRapor.cs
│   │
│   ├── Belgeler/            # PDF belgeler klasörü
│   │
│   ├── Resources/           # Görseller ve kaynaklar
│   │
│   ├── DatabaseHelper.cs    # Veritabanı işlemleri
│   ├── ExcelHelper.cs       # Excel işlemleri
│   ├── Session.cs           # Oturum yönetimi
│   ├── Login.cs             # Giriş formu
│   ├── Form1.cs             # Ana dashboard (Sanayi)
│   ├── Firmalar.cs          # Firma listesi
│   ├── Ciftlikler.cs        # Çiftlik listesi
│   ├── Urunler.cs           # Ürün listesi
│   └── ...
│
├── packages/                # NuGet paketleri
│
└── YesilEksen.sln           # Visual Studio solution dosyası
```

---

## 🗄️ Veritabanı

### Veritabanı Yapısı

Uygulama SQLite veritabanı kullanır. Veritabanı dosyası (`YesilEksen.db`) uygulamanın çalıştığı klasörde otomatik olarak oluşturulur.

### Ana Tablolar

- **Tbl_Firmalar**: Firma bilgileri
- **Tbl_Ciftlikler**: Çiftlik bilgileri
- **Tbl_Kullanicilar**: Kullanıcı bilgileri
- **Tbl_CiftlikUrunleri**: Çiftlik ürünleri
- **Tbl_AlimTalepleri**: Alım talepleri
- **Tbl_CiftlikBelgeleri**: Çiftlik belgeleri
- **Tbl_FirmaBelgeleri**: Firma belgeleri
- **Tbl_UrunBelgeleri**: Ürün belgeleri
- **Tbl_IslemLoglari**: İşlem logları
- **Tbl_SdgRaporVerisi**: SDG rapor verileri

### Lookup Tabloları

- **Tbl_Sehirler**: Şehir listesi
- **Tbl_Sektorler**: Sektör listesi
- **Tbl_UrunKategorileri**: Ürün kategorileri
- **Tbl_OnayDurumlari**: Onay durumları (Onay Bekliyor, Onaylandı, Reddedildi)
- **Tbl_Roller**: Kullanıcı rolleri

### Veritabanı İşlemleri

Veritabanı işlemleri `DatabaseHelper` sınıfı üzerinden yapılır:

```csharp
// Sorgu çalıştırma
DataTable dt = DatabaseHelper.ExecuteQuery("SELECT * FROM Tbl_Firmalar");

// Veri ekleme/güncelleme/silme
int result = DatabaseHelper.ExecuteNonQuery("INSERT INTO ...");

// Tek değer alma
object count = DatabaseHelper.ExecuteScalar("SELECT COUNT(*) FROM ...");
```

---

## 👥 Kullanıcı Rolleri

### 1. Firma (RolID: 1)
- Firma bilgilerini görüntüleme ve güncelleme
- Çiftliklerden ürün talep etme
- Talep durumlarını takip etme
- Belge yükleme

### 2. Çiftlik (RolID: 2)
- Çiftlik bilgilerini görüntüleme ve güncelleme
- Ürün ekleme ve yönetme
- Gelen talepleri görüntüleme
- Belge yükleme

### 3. Sanayi Odası Admin (RolID: 3)
- Firma kayıtlarını onaylama/reddetme
- Alım taleplerini yönetme
- Genel raporlar oluşturma
- SDG raporları oluşturma
- Sistem istatistiklerini görüntüleme

### 4. Ziraat Odası Admin (RolID: 4)
- Çiftlik kayıtlarını onaylama/reddetme
- Ürün kayıtlarını onaylama/reddetme
- Genel raporlar oluşturma
- SDG raporları oluşturma
- Sistem istatistiklerini görüntüleme

---

## 🛠️ Teknolojiler

### Framework ve Platform
- **.NET Framework 4.7.2**
- **Windows Forms**
- **C# 7.3**

### Veritabanı
- **SQLite 1.0.119.0**
- **System.Data.SQLite**

### NuGet Paketleri
- **EPPlus 8.3.1**: Excel dosya işlemleri
- **QRCoder 1.7.0**: QR kod oluşturma
- **System.Buffers 4.5.1**: Buffer yönetimi
- **System.Memory 4.5.5**: Memory yönetimi
- **System.ComponentModel.Annotations 5.0.0**: Data annotations
- **System.Security.Cryptography.Xml 8.0.2**: XML şifreleme

### Geliştirme Ortamı
- **Visual Studio 2017 veya üzeri**
- **.NET Framework 4.7.2 SDK**

---

## 🔧 Geliştirme

### Projeyi Geliştirme Ortamına Alma

1. **Repository'yi klonlayın**
   ```bash
   git clone https://github.com/kullaniciadi/VirtualProgramming-Final_Project.git
   ```

2. **Visual Studio'da açın**
   - `YesilEksen.sln` dosyasını açın

3. **NuGet paketlerini geri yükleyin**
   - Solution Explorer'da projeye sağ tıklayın
   - "Restore NuGet Packages" seçeneğini seçin

4. **Projeyi derleyin**
   - `Ctrl+Shift+B` veya Build > Build Solution

### Veritabanı Test Verileri

Test verileri eklemek için `DatabaseHelper` sınıfında bulunan `InsertSyntheticData()` metodunu kullanabilirsiniz. Bu metod:
- 50+ şehir
- 50+ sektör
- 50+ ürün kategorisi
- 50+ firma
- 50+ çiftlik
- 50+ kullanıcı
- 50+ ürün
- 50+ alım talebi
- 50+ belge
- 50+ işlem logu
- 50+ SDG rapor verisi

ekler.

### Kod Standartları

- **İsimlendirme**: PascalCase (sınıflar, metodlar), camelCase (değişkenler)
- **XML Dokümantasyon**: Tüm public metodlar XML dokümantasyonu içermelidir
- **Hata Yönetimi**: Try-catch blokları kullanılmalı ve kullanıcıya anlamlı mesajlar gösterilmelidir
- **Veritabanı**: Tüm veritabanı işlemleri `DatabaseHelper` sınıfı üzerinden yapılmalıdır

---

## 🤝 Katkıda Bulunma

Katkıda bulunmak için:

1. Bu repository'yi fork edin
2. Yeni bir branch oluşturun (`git checkout -b feature/yeni-ozellik`)
3. Değişikliklerinizi commit edin (`git commit -am 'Yeni özellik eklendi'`)
4. Branch'inizi push edin (`git push origin feature/yeni-ozellik`)
5. Bir Pull Request oluşturun

### Katkı Kuralları

- Kod standartlarına uyun
- Yeni özellikler için test yazın
- README'yi güncelleyin
- Anlamlı commit mesajları kullanın

---

## 📝 Değişiklik Geçmişi

### Versiyon 1.0.0
- İlk sürüm
- Temel firma ve çiftlik yönetimi
- Onay süreçleri
- Raporlama modülleri
- Belge yönetimi
- Excel dışa aktarma

---

## 🐛 Bilinen Sorunlar

- Veritabanı dosyası büyüdükçe performans düşebilir (gelecek sürümlerde optimize edilecek)
- Çoklu kullanıcı desteği sınırlıdır (SQLite WAL modu kullanılıyor)

---

## 🔮 Gelecek Özellikler

- [ ] Web API entegrasyonu
- [ ] Mobil uygulama desteği
- [ ] Gelişmiş raporlama ve grafikler
- [ ] E-posta bildirimleri
- [ ] Çoklu dil desteği
- [ ] Bulut veritabanı desteği
- [ ] Otomatik yedekleme sistemi

---

## 📞 İletişim

Sorularınız veya önerileriniz için:
- **GitHub Issues**: [Issues sayfası](https://github.com/keremmisik/VirtualProgramming-Final_Project/issues)
- **E-posta**: [e-posta adresi](keremisik1010@gmail.com)

---

## 📄 Lisans

Bu proje [MIT Lisansı](LICENSE) altında lisanslanmıştır.

---

## 🙏 Teşekkürler

- EPPlus ekibine Excel işlemleri için
- QRCoder ekibine QR kod desteği için
- SQLite ekibine veritabanı desteği için
- Tüm katkıda bulunanlara

---

## 📚 Ek Kaynaklar

- [.NET Framework Dokümantasyonu](https://docs.microsoft.com/en-us/dotnet/framework/)
- [SQLite Dokümantasyonu](https://www.sqlite.org/docs.html)
- [EPPlus Dokümantasyonu](https://github.com/EPPlusSoftware/EPPlus)
- [QRCoder Dokümantasyonu](https://github.com/codebude/QRCoder)

---

**Yeşil Eksen** - Sürdürülebilir bir gelecek için 🌱

