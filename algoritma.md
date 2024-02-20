# Checkout Cart Application
# Alışveriş Sepeti Uygulaması Algoritması

Bu doküman, JavaScript ile geliştirilen basit bir alışveriş sepeti uygulamasının algoritmasını adım adım açıklamaktadır.

## 1. Hazırlık ve Başlangıç Ayarları

### 1.1 Değişkenleri Tanımla
- `taxRate`: Ürünler için uygulanan vergi oranı (%18 olarak ayarla).
- `shippingPrice`: Sabit bir kargo ücreti (15 birim olarak ayarla).
- `shippingFreePrice`: Ücretsiz kargo için minimum sepet tutarı (300 birim olarak ayarla).

### 1.2 Sayfa Yüklendiğinde Başlatma
- Sayfa yüklendiğinde (`window.addEventListener("load", ...)`) çalışacak fonksiyonu tanımla.
- `calculateCartPrice` fonksiyonunu çağırarak sepetin toplam fiyatını hesapla.
- Vergi oranı, kargo ücreti ve ücretsiz kargo limitini `localStorage`'a kaydet.

## 2. Ürünlerle Etkileşim Kurma

### 2.1 Ürünler Div'ine Olay Dinleyicisi Ekle
- `.products` sınıfına sahip div elemanına tıklama olay dinleyicisi ekle.

### 2.2 Artı ve Eksi Butonlarına Tepki Verme
- Tıklama olayı tetiklendiğinde, tıklanan elemanın sınıfını kontrol et.
- `fa-plus` veya `fa-minus` sınıfına sahipse, ürün miktarını güncelle.
- Ürün miktarı güncellendikten sonra, ürünün ve sepetin toplam fiyatını yeniden hesapla.

### 2.3 Ürünü Kaldırma İşlevi
- `remove-product` sınıfına sahip bir elemana tıklandığında, onay kutusu ile kullanıcıdan onay al.
- Onay alınırsa, ürünü DOM'dan kaldır ve sepet toplamını yeniden hesapla.

## 3. Fiyat Hesaplama Fonksiyonları

### 3.1 Ürün Fiyatını Hesapla
- Her bir ürün için, birim fiyatı ve miktarı alarak toplam fiyatı hesapla.
- Hesaplanan toplam fiyatı, ilgili HTML elemanına yaz.

### 3.2 Sepet Toplamını Hesapla
- Sepetteki tüm ürünlerin toplam fiyatını toplayarak sepetin alt toplamını bul.
- Alt toplam üzerinden vergi tutarını hesapla.
- Alt toplamı, vergi tutarını, kargo ücretini ve genel toplamı ilgili HTML elemanlarında güncelle.

## 4. Sonuçları Gösterme

### 4.1 HTML Elemanlarını Güncelle
- Alt toplam, vergi, kargo ücreti ve genel toplamı gösteren HTML elemanlarını güncel değerlerle doldur.

