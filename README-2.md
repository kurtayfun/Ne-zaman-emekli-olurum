# Ne Zaman Emekli Olurum? — SGK Emeklilik Hesaplama

SGK'nın resmi ["Ne Zaman Emekli Olurum?"](https://uyg.sgk.gov.tr/nezaman/) sayfasındaki mantığı temel alan, tek dosyalık, bağımsız (dependency-free) bir emeklilik tarihi hesaplama uygulaması. Herhangi bir kurulum veya build adımı gerektirmez — `sgk-emeklilik-hesaplama.html` dosyasını açmanız yeterlidir.

**Canlı demo:** Bu depoyu GitHub Pages üzerinden yayınladıktan sonra buraya bağlantısını ekleyebilirsiniz.

---

## Özellikler

- Cinsiyet, doğum tarihi, hizmete başlama tarihi, SSK (4A) prim günü, diğer sandık günleri, askerlik borçlanması ve fiili hizmet zammı girişi
- Askerlik borçlanması işe başlamadan önce yapıldıysa efektif başlangıç tarihini SGK'nın 360 gün/30 gün esasına göre otomatik geriye çeker
- Üç emeklilik rejimini otomatik tespit eder ve buna göre hesaplar:
  - **EYT (08.09.1999 ve öncesi girişliler):** 506 sayılı Kanun Geçici 81. Madde'deki gerçek kademeli prim gün tablosu (5.000–5.975 gün, giriş tarihine göre), yaş şartı aranmaz
  - **09.09.1999–30.04.2008 arası girişliler:** Kadın 58 / Erkek 60 yaş + 7.000 gün + 25 yıl sigortalılık süresi
  - **01.05.2008 sonrası girişliler (5510 sayılı Kanun):** 7.200 gün + prim gününün tamamlandığı tarihe göre kademeli yaş (2036'dan 2048'e kadar 58/60'tan 65'e çıkan resmi tablo)
- Opsiyonel **Kademeli Emeklilik Simülasyonu**: 1999–2008 arası girişliler için kamuoyunda tartışılan (henüz yasalaşmamış) taslak tabloya göre alternatif bir sonuç gösterir, resmi sonuçla arasındaki farkı rozet olarak belirtir
- Sonuç panelinde üç şartın (yaş, prim günü, sigortalılık süresi) ayrı ayrı durumu ve tamamlanma tarihleri, ardından nihai emeklilik tarihi ve emekliliği geciktiren ana faktör

## Kullanılan Mevzuat

- 506 sayılı Sosyal Sigortalar Kanunu, Geçici 81. Madde (EYT kademeli prim tablosu)
- 5510 sayılı Sosyal Sigortalar ve Genel Sağlık Sigortası Kanunu, Madde 28 (7.200 gün ve kademeli yaş tablosu)
- 7438 sayılı Kanun (EYT'de yaş şartının kaldırılması, Mart 2023)

## Sorumluluk Reddi

Bu araç **bilgilendirme amaçlıdır** ve SGK'nın resmi bir hizmeti değildir. Kademeli emeklilik simülasyonu bölümü, kamuoyunda tartışılan ve henüz yasalaşmamış bir taslak modele dayanır — SGK'nın resmi bir kademeli emeklilik takvimi bulunmamaktadır. Kesin sonuç için SGK'nın ["Ne Zaman Emekli Olurum?"](https://uyg.sgk.gov.tr/nezaman/) hizmetini veya e-Devlet üzerinden hizmet dökümünüzü esas alınız.

## Kurulum / Yayınlama

Build adımı yoktur. Depoyu GitHub Pages'te yayınlamak için:

1. Depoyu GitHub'a yükleyin
2. **Settings → Pages** üzerinden `main` dalını (branch) kaynak olarak seçin
3. `sgk-emeklilik-hesaplama.html` dosyasını ana sayfa yapmak isterseniz `index.html` olarak yeniden adlandırın

## Teknik Notlar

- Saf HTML/CSS/JavaScript — React, Tailwind veya başka bir dış kütüphane/CDN kullanılmaz
- Tüm tarih hesaplamaları UTC üzerinden yapılır, zaman dilimi kaynaklı sapmaları önler
- Mobil öncelikli, tek sütun, dokunmatik uyumlu arayüz

---

Hazırlayan: [@kurtayfun — Bankacı Anlatıyor](https://x.com/kurtayfun)
