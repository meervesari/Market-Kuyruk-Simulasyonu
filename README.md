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

## 📊 Analiz ve Optimizasyon
Simülasyon iki aşamadan oluşmaktadır:
1. **Detaylı Akış:** Müşterilerin markete girişi, kasa seçimi ve bekleme sürelerinin anlık takibi.
2. **Kasiyer Sayısı Analizi:** Kasiyer sayısının (Resource) ortalama bekleme süresi üzerindeki etkisini ölçen karşılaştırmalı tablo.

## 📈 Örnek Sonuçlar
Yapılan testlerde, kasiyer sayısının 1'den 3'e çıkarılmasının bekleme sürelerini %60 oranında azalttığı, ancak 4. kasiyerden sonra verimlilik artışının yavaşladığı (Marjinal Fayda) gözlemlenmiştir.

---
**Hazırlayan:** Merve Sarı  24430070068  
**Bölüm:** Bilişim Sistemleri ve Teknolojileri
