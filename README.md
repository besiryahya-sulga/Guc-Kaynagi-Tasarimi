#  0-24V / 0-5A Ayarlanabilir DC Güç Kaynağı Tasarımı

## Proje Amacı
Bu proje, 220V AC şebeke gerilimini kullanarak laboratuvar ortamında elektrik motorlarının testlerinde, batarya gruplarının şarj/deşarj deneylerinde ve aydınlatma sistemlerinin beslenmesinde kullanılmak üzere tasarlanmış **izole, kararlı ve ayarlanabilir bir DC güç kaynağı** prototipidir. 

## Test ve Tasarım Revizyonu
*İlk teorik tasarımda 0-100V aralığı hedeflenmiş olsa da, prototipleme ve yük testleri aşamasında karşılaşılan donanım tolerans limitleri ve stabilite gereksinimleri doğrultusunda sistem optimize edilmiştir. Tam yükte (5A) en kararlı ve güvenli çalışmanın sağlanabilmesi için çıkış gerilimi maksimum 24V DC olacak şekilde revize edilmiş ve başarıyla devreye alınmıştır.*

##  Sistem Mimarisi ve Çalışma Prensibi
Sistem donanımı temel olarak şu aşamalardan oluşmaktadır:
1. **Gerilim Düşürme:** 220V AC şebeke gerilimi, izolasyonlu transformatör ile uygun AC seviyesine düşürülür.
2. **Doğrultma:** Transformatör çıkışındaki AC gerilim, ≥10A kapasiteli köprü doğrultucu ile titreşimli DC'ye dönüştürülür.
3. **Filtreleme (Kaba ve Hassas):** Yüksek kapasiteli elektrolitik kondansatörler kullanılarak dalgalanma (ripple) minimuma indirilir.
4. **Akım ve Gerilim Regülasyonu:** Çıkışın 0-5A ve 0-24V arasında hassas ayarlanabilmesi için güç MOSFET'leri ve Op-Amp tabanlı CC-CV (Sabit Akım - Sabit Voltaj) kontrol kartı kullanılmıştır.

##  Kullanılan Temel Komponentler ve Koruma Sistemleri
* **Güç Katı:** Transformatör, Köprü Diyot, Filtre Kondansatörleri.
* **Kontrol Katı:** CC-CV Lineer/Switching Regülatör Modülü, Hassas Potansiyometreler.
* **Güvenlik ve Koruma:** * **Ani Akım (Inrush) Koruması:** NTC Termistör
  * **Şebeke Şok Koruması:** MOV (Metal Oksit Varistör)
  * **Aşırı Akım ve Isı Koruması:** Sigortalar, Alüminyum Soğutucu Bloklar ve aktif topraklama hattı.
