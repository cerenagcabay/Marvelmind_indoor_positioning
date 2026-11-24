# Marvelmind_indoor_positioning
Ultrasonic Indoor Positioning System – Experimental Setup and Calibration
# Marvelmind Ultrasonik İç Mekân Konum Belirleme Sistemi

## 1. Proje Hakkında

Bu proje, Marvelmind Ultrasonik İç Mekân Konum Belirleme Sistemi'nin kurulumunu, kalibrasyonunu ve deneysel performansının değerlendirilmesini kapsamaktadır.

Projenin temel amacı, GPS sinyallerinin yetersiz kaldığı kapalı ortamlarda mobil robotların ve otonom platformların konumlarının ultrasonik sinyaller aracılığıyla hassas bir şekilde belirlenmesini sağlamaktır.

Sistem, **Time of Flight (ToF)** ve **Trilaterasyon** prensiplerinden yararlanarak sabit beacon'lar ile mobil beacon arasındaki mesafeleri hesaplamakta ve mobil beacon'ın konumunu belirlemektedir.

## 2. Projenin Amaçları

- Marvelmind ultrasonik konumlandırma sisteminin kurulması.
- Sabit ve mobil beacon'ların yapılandırılması.
- Fiziksel referans koordinat sisteminin oluşturulması.
- Beacon geometrisinin ve yükseklik parametrelerinin kalibre edilmesi.
- Ultrasonik sinyal yayılımının ve akustik gürültülerin incelenmesi.
- Statik ve dinamik konumlandırma doğruluğunun değerlendirilmesi.
- Ölçüm sonuçlarının matematiksel hata metrikleriyle analiz edilmesi.
- Gelecek aşamada LiDAR referans sistemiyle karşılaştırma yapılması.

## 3. Kullanılan Donanımlar

| Donanım | Açıklama |
|---|---|
| Marvelmind Super Beacon 2 | Sabit ve mobil beacon birimleri |
| Marvelmind HW v5.1 Modem | Merkezi haberleşme ve kontrol birimi |
| Raspberry Pi 3 | Mobil sistem ve ROS entegrasyonu için işlemci |
| Ultrasonik Beacon'lar | Mesafe ve konum belirleme |
| Lazer Mesafe Ölçer | Fiziksel referans ölçümleri |
| Hassas Çelik Şerit Metre | Koordinat ve mesafe ölçümleri |

## 4. Kullanılan Yazılımlar ve Teknolojiler

- Marvelmind Dashboard v8.451
- ROS (Robot Operating System)
- Non-Inverse Architecture (NIA)
- Time of Flight (ToF)
- Time Difference of Arrival (TDoA)
- Trilaterasyon
- Recursive Least Squares (RLS)
- Extended Kalman Filter (EKF)

## 5. Deneysel Sistem Kurulumu

İlk deneysel çalışma alanı 160 cm × 120 cm boyutlarında bir masa üzerinde oluşturulmuştur.

Dört adet sabit beacon masanın köşelerine yerleştirilmiş ve masa yüzeyinden 75 cm yükseklikte konumlandırılmıştır.

Mobil konum takibi için Beacon 8 (Hedgehog) kullanılmıştır.

**Sabit Beacon Koordinatları:**

| Beacon | X (m) | Y (m) | Z (m) |
|---|---:|---:|---:|
| Beacon 3 | 0.00 | 0.00 | 0.75 |
| Beacon 4 | 1.20 | 0.00 | 0.75 |
| Beacon 5 | 1.20 | 1.60 | 0.75 |
| Beacon 7 | 0.00 | 1.60 | 0.75 |

Sistem Non-Inverse Architecture (NIA) mimarisiyle yapılandırılmıştır.

## 6. Gerçekleştirilen Çalışmalar

- Fiziksel deney masasının hazırlanması.
- Dört sabit beacon'ın fiziksel montajı.
- Modem ve beacon firmware güncellemeleri.
- Cihaz adreslerinin ve ultrasonik frekansların yapılandırılması.
- Sabit ve mobil beacon rollerinin tanımlanması.
- Beacon yüksekliklerinin sisteme girilmesi.
- Submap koordinat kayması ve rotasyon değerlerinin incelenmesi.
- Mobil Beacon 8'in Dashboard üzerinde görünür hale getirilmesi.
- İlk konum ve mesafe ölçümlerinin incelenmesi.

7. Deneysel Metodoloji

Projenin devam eden deneysel aşamalarında aşağıdaki çalışmalar gerçekleştirilecektir.

7.1 Statik Konum Doğruluğu Testleri

Masa üzerinde belirlenen 9 farklı referans noktasında mobil beacon ölçümleri alınacaktır.

Her noktada 30 saniye boyunca en az 50 koordinat örneği kaydedilmesi planlanmaktadır.

Ölçülen koordinatlar fiziksel referans koordinatlarıyla karşılaştırılacaktır.

7.2 Dinamik Konum Takibi Testleri

Mobil beacon'ın farklı doğrusal, çapraz ve dairesel hareket senaryolarındaki konum takip performansı incelenecektir.

Değerlendirilecek parametreler:

Konum takip sürekliliği

Koordinat güncelleme frekansı

Gecikme süresi (Latency)

Koordinat kararlılığı (Jitter)

Gerçek yörünge ile ölçülen yörüngenin karşılaştırılması

7.3 Hata Analizi

Konumlandırma sisteminin doğruluğunu değerlendirmek için aşağıdaki matematiksel metrikler kullanılacaktır:

Öklid Konum Hatası

Ortalama Mutlak Hata (MAE)

Kök Ortalama Kare Hata (RMSE)

Tolerans Bazlı Başarı Oranı
