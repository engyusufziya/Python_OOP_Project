# Uzay Keşif Oyunu

Bu proje, Python kullanılarak geliştirilmiş metin tabanlı bir uzay keşif oyunudur. Oyun, nesne yönelimli programlama prensiplerine uygun olarak tasarlanmış olup, oyuncunun sınırlı yakıta sahip bir uzay aracı ile galaksideki gezegenleri keşfetmesini sağlar.

## İçindekiler

- [Genel Bakış](#genel-bakış)
- [Kullanılan Teknolojiler](#kullanılan-teknolojiler)
- [Oyun Bileşenleri Hakkında](#oyun-bileşenleri-hakkında)
- [Yapılan Adımlar](#yapılan-adımlar)
  - [1. Proje Yapısı Oluşturma](#1-proje-yapısı-oluşturma)
  - [2. Sınıf Tasarımı](#2-sınıf-tasarımı)
  - [3. Galaksi Oluşturma Sistemi](#3-galaksi-oluşturma-sistemi)
  - [4. Oyun Mekaniği Geliştirme](#4-oyun-mekaniği-geliştirme)
  - [5. Kullanıcı Arayüzü](#5-kullanıcı-arayüzü)
- [Sonuçlar ve Özellikler](#sonuçlar-ve-özellikler)

---

## Genel Bakış
Bu proje, **BLM19104/BLM22110 Bilgisayar Programlama II** dersi kapsamında geliştirilmiş bir **metin tabanlı uzay keşif simülasyonu**dur. Proje kapsamında, modüler programlama yaklaşımı benimsenmiş, her oyun bileşeni için ayrı sınıflar oluşturulmuş ve karmaşık oyun mekaniği sistemi kurulmuştur. Oyuncu, stratejik kararlar alarak yakıt ve kaynak yönetimi yaparak tüm gezegenleri keşfetmeye çalışır.

## Kullanılan Teknolojiler
- **Python 3.x**: Ana programlama dili
- **random modülü**: Rastgele galaksi ve oyun olayları oluşturma
- **Nesne Yönelimli Programlama**: Sınıf tabanlı tasarım yaklaşımı
- **Modüler Programlama**: Ayrı dosyalarda özelleşmiş fonksiyonlar

## Oyun Bileşenleri Hakkında
**Uzay Keşif Oyunu** 5 ana modülden oluşur ve her biri farklı sorumluluklara sahiptir:

- **main.py**: Ana oyun döngüsü ve menü sistemi
- **arac.py**: Uzay aracının özelliklerini ve davranışlarını yöneten sınıf
- **gezegen.py**: Gezegen özelliklerini ve etkileşimlerini yöneten sınıf
- **karadelik.py**: Karadelik mekaniği ve ışınlama sistemi
- **galaksi.py**: Galaksi haritası oluşturma ve görselleştirme fonksiyonları

## Yapılan Adımlar

### 1. Proje Yapısı Oluşturma
```python
# Modüler dosya yapısı oluşturuldu
from arac import Arac
from gezegen import Gezegen
from karadelik import Karadelik
from galaksi import galaksi_olustur, harita_goster, nesne_getir
```
Proje, her sınıf için ayrı modül dosyası oluşturularak düzenli bir yapıya kavuşturuldu. İmport sistemleri ile modüller arası bağlantı sağlandı.

### 2. Sınıf Tasarımı
- **Arac sınıfı** ile uzay aracının yakıt, kapasite, kaynak ve konum özellikleri tanımlandı
- **Gezegen sınıfı** ile her gezegenin isim, konum, kaynak, atmosfer ve yerçekimi özellikleri oluşturuldu
- **Karadelik sınıfı** ile rastgele ışınlama mekaniği geliştirildi
- Her sınıf için özelleşmiş metotlar (hareket_et, inis_yap, etkilesim) tanımlandı

### 3. Galaksi Oluşturma Sistemi
- `galaksi_olustur()` fonksiyonu ile rastgele galaksi üretimi sağlandı:
  ```python
  # 5 gezegen: Dünya, Mars, Venüs, Jüpiter, Satürn
  # 3 karadelik rastgele konumlarda
  # Her gezegen farklı atmosfer ve yerçekimi değerleriyle
  ```
- `harita_goster()` ile 11x11 ızgara üzerinde görsel harita sistemi oluşturuldu
- `nesne_getir()` ile belirli koordinatlardaki nesnelere erişim sağlandı

### 4. Oyun Mekaniği Geliştirme
- **Yakıt Sistemi**: Mesafe tabanlı yakıt tüketimi (Öklid mesafesi × 10)
- **İniş Mekaniği**: Atmosfer ve yerçekimine bağlı iniş maliyeti hesaplama
- **Kaynak Yönetimi**: Kaynak toplama, yakıt yenileme (1:2 oran) ve kapasite artırma (1:5 oran)
- **Karadelik Sistemi**: %50 şansla ücretsiz veya maliyetli rastgele ışınlama

### 5. Kullanıcı Arayüzü
- Menü tabanlı oyun kontrol sistemi oluşturuldu:
  - **Harita görüntüleme** ve konum takibi
  - **Hedef belirleme** ve seyahat sistemi
  - **Nesne etkileşimi** ve gezegen işlemleri
  - **Durum görüntüleme** ve bilgi paneli

## Sonuçlar ve Özellikler
- **Modüler Tasarım**: Her oyun bileşeni bağımsız sınıflarda tanımlanarak kodun okunabilirliği ve bakımı kolaylaştırıldı
- **Rastgele Oynanış**: Her oyun başlangıcında farklı galaksi konfigürasyonu ile yeniden oynanabilirlik sağlandı
- **Strateji Elementi**: Yakıt ve kaynak yönetimi ile oyuncunun stratejik düşünmesi gerektiren oynanış deneyimi
- **Hata Yönetimi**: Geçersiz girişler için try-except bloklarıyla güvenli kullanıcı etkileşimi
- **Görsel Harita**: ASCII tabanlı harita sistemi ile oyunun görsel takibi

**Oyun Başarı Koşulları**:
- **Zafer**: Tüm 5 gezegeni keşfetmek (aynı konuma ulaşmak)
- **Yenilgi**: Yakıt tükenmesi (≤0 yakıt)

**Öğrenci Bilgileri**: Yusuf Ziya Demirel - 2121241028

Keyifli keşifler!
