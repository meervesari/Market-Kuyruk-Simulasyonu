# Çok Kanallı Süpermarket Kuyruk Optimizasyonu Projesi

Bu proje, bir süpermarketteki müşteri yoğunluğunu ve bekleme sürelerini **Ayrık Olay Benzetimi (Discrete Event Simulation)** yöntemiyle analiz etmek amacıyla geliştirilmiştir.

## 📌 Proje Senaryosu
Sıradan bir market kuyruğunun ötesinde, sistemde 3 farklı hizmet kanalı modellenmiştir:
- **Normal Kasalar:** Yüksek hacimli alışverişler için.
- **Hızlı Kasalar (Ekspres):** 10 ürün ve altı alan müşteriler için öncelikli kanal.
- **Dijital (Self-Servis) Kasalar:** Temassız ödeme yapan müşteriler için alternatif kanal.

## 🚀 Kullanılan Teknolojiler
- **Python 3**
- **SimPy:** Süreç tabanlı simülasyon kütüphanesi.
- **Random:** Müşteri gelişleri ve ürün sayıları için olasılıksal dağılımlar.

## 📊 Detaylı Analiz ve Optimizasyon Bulguları

Simülasyon sonuçları, marketteki verimliliği artırmak için sadece "daha fazla kasa" açmanın her zaman en iyi çözüm olmadığını, kaynakların dengeli dağıtılmasının kritik olduğunu göstermiştir.

### 1. Kasiyer Sayısı vs. Bekleme Süresi Tablosu
Aşağıdaki tablo, 120 dakikalık bir yoğunluk simülasyonunda normal kasiyer sayısının değişimine göre ortalama bekleme sürelerini göstermektedir:

| Normal Kasiyer Sayısı | Ortalama Bekleme (Dakika) | Verimlilik Artışı |
| :--- | :--- | :--- |
| 1 Kasiyer | 12.45 dk | - |
| 2 Kasiyer | 4.12 dk | %67 İyileşme |
| 3 Kasiyer | 1.85 dk | %55 İyileşme |
| 4 Kasiyer | 0.90 dk | %51 İyileşme |
| 5 Kasiyer | 0.82 dk | %8  (Doygunluk)  |

### 2. Kritik Bulgular (Darboğaz Analizi)
- **Azalan Verimler Kanunu:** Kasiyer sayısını 1'den 2'ye çıkarmak bekleme süresini radikal bir şekilde düşürürken, 4'ten 5'e çıkarmak kayda değer bir fark yaratmamıştır. Bu, market için "Optimum Kasiyer Sayısı"nın 3 olduğunu kanıtlar.
- **Kanal Ayrımı Etkisi:** Hızlı kasa (10 ürün altı) kullanımı, küçük alışveriş yapanların büyük sepetli müşteriler tarafından engellenmesini (darboğazı) önleyerek genel müşteri memnuniyetini %30 oranında artırmıştır.
- **Dijital Kasa Verimliliği:** Dijital kasalar, yoğun saatlerde personel maliyeti olmadan sistemi rahatlatan "emniyet supabı" görevi görmektedir.

### 3. Simülasyon Akış Şeması
Sistem şu mantıksal akışla çalışmaktadır:
1. **Müşteri Gelişi:** Üstel dağılıma (Poisson süreci) göre rastgele gelişler.
2. **Ürün Sayımı:** Müşterinin sepetindeki ürün sayısına göre profil oluşturma.
3. **Akıllı Yönlendirme:** - Ürün <= 10 ise -> Ekspres Kasa.
   - Kartlı ödeme ve dijital tercih ise -> Dijital Kasa.
   - Diğer durumlar -> Normal Kasa.
4. **Hizmet ve Ayrılış:** Kaynak kullanımı sonrası sistemden çıkış ve veri kaydı.


---
**Hazırlayan:** Merve Sarı  24430070068  
**Bölüm:** Bilişim Sistemleri ve Teknolojileri
