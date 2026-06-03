# Çok Kanallı ve Dinamik Zaman Ayarlı Süpermarket Kuyruk Yönetimi ve Reyon Darboğaz Simülasyonu

**Benzetim Programları | Dönem Sonu Final Projesi** 
**Hazırlayan:** Merve Sarı — 24430070068

---

## 📋 Proje Hakkında
Bu proje, bir süpermarketin günlük operasyonunu **Ayrık Olay Benzetimi** yöntemiyle modelleyen kapsamlı ve interaktif bir Karar Destek Sistemi 'dir. 

Sistem, müşteri akışını ve mağaza içi dinamikleri en gerçekçi şekilde simüle edebilmek için aşağıdaki gelişmiş özelliklerle donatılmıştır:
* 📊 **Çok Kanallı Kasa Mimarisi:** Müşterileri sepet büyüklüğüne göre otomatik yönlendiren Normal, Hızlı (Express) ve Dijital (Self-Servis) kasa hatları.
* 🕐 **Dinamik Saat Dilimleri:** Günün farklı saatlerindeki (Sabah, Öğle, İş çıkışı) yoğunluk dalgalanmaları.
* 📅 **Özel Takvim Etkileri:** Standart günlerin yanı sıra Hafta Sonu ve Bayram Yoğunluğu stres testi senaryoları.
* 🧑‍🤝‍🧑 **Stokastik Müşteri Profilleri:** Alışveriş hacmine ve mağaza içi davranışına göre ayrılmış 3 farklı kitle (Hızlı Alıcı, Keyfi Alıcı, Aylık Alışverişçi).
* 🐟 **Mağaza İçi Reyon Darboğazları:** Yalnızca kasaları değil; Kasap, Balık ve Süt/Peynir/Şarküteri reyonlarındaki iç kuyruk şebekelerini de kapsayan bütüncül analiz.

---

## 🚀 Projeyi  Çalıştırma


### Yerel Ortamda (VS Code / Jupyter) Çalıştırma
Simülasyonun interaktif panellerini ve dinamik loglarını canlı olarak test etmek isterseniz:
1. Sağ üstteki yeşil **`Code`** butonuna tıklayıp **`Download ZIP`** seçeneği ile bu depoyu bilgisayarınıza indirin.
2. Klasöre çıkarttığınız `market_simulasyonu.ipynb` dosyasını **VS Code** veya **Jupyter Notebook** ortamında açın.
3. Gerekli kütüphaneleri (`pip install simpy ipywidgets matplotlib seaborn pandas`) yükledikten sonra "Run All" (Tümünü Çalıştır) diyerek kontrol panelini aktifleştirebilirsiniz.

---

## 🎛️ Kullanıcı Arayüzü (Kontrol Paneli)

| Kontrol | Açıklama | Aralık |
| :--- | :--- | :--- |
| **Normal Kasa** | Standart kasiyer sayısı | 0 – 5 |
| **Hızlı Kasa (Express)** | 10 ürün altı müşteriler için | 0 – 3 |
| **Dijital Kasa** | Self-servis ödeme noktası | 0 – 3 |
| **Et / Kasap Per.** | Kasap reyonu personeli | 0 – 3 |
| **Balık Per.** | Balık reyonu personeli | 0 – 3 |
| **Süt / Peynir Per.** | Şarküteri personeli | 0 – 3 |
| **Saat Dilimi** | Sabah / Öğle / İş çıkışı | Açılır Menü |
| **Özel Dönem** | Standart / Hafta sonu / Bayram | Açılır Menü |

> ⚠️ **Not:** Herhangi bir kaynağı `0` yapmak o kasayı/reyonu tamamen kapatır. Sistem, müşteri yükünü otomatik olarak açık olan diğer birimlere dağıtır.

---

## 📊 Simülasyon Çıktıları
Butona her basıldığında sistem yöneticisine 3 temel çıktı sunulur:

1. **Bölüm 1 — Görsel Analiz (Grafikler):** Kasa türlerine göre bekleme süreleri  ve reyon bazlı iç darboğaz analizleri . Bekleme süreleri dinamik formatlıdır (sn/dk).
2. **Bölüm 2 — Kapasite Performans Tablosu:** Seçilen senaryo altında, kasiyer sayısı 1'den 5'e kadar test edilerek sistemin optimum performans noktası otomatik olarak bulunur.
3. **Bölüm 3 — Olay Akış Logları:** Gerçek hayatı yansıtacak şekilde her müşterinin markete giriş saati, ziyaret ettiği reyonlar ve kasadan çıkış anları kronolojik olarak listelenir.

---

## 👥 Müşteri Profilleri

| Profil | Sepet Hacmi | Market İçi Süre | Kasa Tercihi |
| :--- | :--- | :--- | :--- |
| 🏃 **Hızlı Alıcı** | 1 – 5 ürün | 2 – 5 dakika | Express / Dijital |
| 🛒 **Keyfi Alıcı** | 5 – 15 ürün | 15 – 25 dakika | Normal / Dijital |
| 🧺 **Aylık Alışverişçi** | 25 – 55 ürün | 45 – 75 dakika | Normal Kasa |

---

## 🏪 Reyon Darboğazları (İç Kuyruk Şebekesi)

| Reyon | Uğranma Oranı | Servis Süresi | Darboğaz Seviyesi |
| :--- | :--- | :--- | :--- |
| 🧀 **Süt / Peynir / Şarküteri** | %70 | 2 – 5 dk | Orta |
| 🥩 **Et / Kasap Reyonu** | %50 | 3 – 7 dk | Yüksek |
| 🐟 **Balık Reyonu** | %40 | 6 – 12 dk | **Kritik** |

---

## 📈 Örnek Analiz Sonuçları
*(Bayram Yoğunluğu + İş Çıkışı Senaryosu — 180 dakika stres testi)*

| Aktif Kasiyer | Ort. Kasa Bekleme | Ort. Reyon Bekleme | Durum Analizi |
| :--- | :--- | :--- | :--- |
| 1 Kasiyer | 14 dk 12 sn | 7 dk 45 sn | 🔴 Darboğaz |
| 2 Kasiyer | 4 dk 25 sn | 4 dk 10 sn | 🟡 Yüksek Yük |
| **3 Kasiyer** | **1 dk 15 sn** | **38 sn** | **⭐ Optimum Nokta** |
| 4 Kasiyer | 42 sn | 35 sn | 🔵 Azalan Verimler |
| 5 Kasiyer | 12 sn | 32 sn | ⚪ Atıl Kapasite |

---

## 🔧 Teknik Detaylar
* **Dil:** Python 3
* **Simülasyon Motoru:** SimPy (Ayrık Olay Benzetimi)
* **Arayüz:** IPyWidgets
* **Görselleştirme:** Matplotlib + Seaborn
* **Veri İşleme:** Pandas

---
