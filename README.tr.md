# Sızma Testi, Brute-Force ve Web Fuzzing için Nihai Wordlist Koleksiyonu

> 🌐 **Kendi dilinizde okuyun:** 🇬🇧 [English](README.md) | 🇨🇳 [中文](README.zh.md) | 🇷🇺 [Русский](README.ru.md) | 🇪🇸 [Español](README.es.md) | 🇯🇵 [日本語](README.ja.md) | 🇮🇷 [فارسی](README.fa.md) | 🇸🇦 [العربية](README.ar.md) | 🇹🇷 [Türkçe](README.tr.md) | 🇩🇪 [Deutsch](README.de.md) | 🇮🇳 [हिन्दी](README.hi.md)


[![Security](https://img.shields.io/badge/Security-Pentesting-red.svg)](#)


<p align="center"><img src="shot.jpg?raw=true"></p>


GitHub üzerindeki en kapsamlı depo; güvenlik uzmanları, sızma testi uzmanları ve etik hackerlar için özel olarak hazırlanmış wordlistlerin, sözlük saldırısı verilerinin ve gelişmiş fuzzing payload'larının merkezîleştirilmiş ve son derece optimize edilmiş bir ana koleksiyonu olarak hizmet vermektedir.

---

## 🎯 Bu Depo Neden Var?

Güvenlik değerlendirmeleri ve sızma testleri sırasında, iyi yapılandırılmış ve yüksek kaliteli verilere anında erişebilmek kritik öneme sahiptir. Standart wordlistler genellikle dağınık, güncelliğini yitirmiş ya da brute-force saldırılarını ve web fuzzing işlemlerini yavaşlatan gereksiz verilerle dolu durumdadır.

Bu depo, söz konusu boşluğu kapatmak amacıyla oluşturulmuştur. Bir güvenlik test uzmanının iş istasyonu için vazgeçilmez bir altyapı bileşeni işlevi görmektedir. Çok amaçlı listeleri tek ve yapılandırılmış bir depoda birleştirerek, herhangi bir test ortamına hızla klonlayabilir ve hedef odaklı sözlük saldırılarını, dizin keşfini veya payload enjeksiyonlarını anında devreye alabilirsiniz.

---

## 📂 Depo İçeriği ve Yapısı

Bu depodaki veri kümeleri; hızı en üst düzeye çıkarmak, gürültüyü en aza indirmek ve aktif sızma testleri ile etik hackleme operasyonları sırasında yüksek başarı oranları sağlamak için stratejik biçimde kategorize edilmiş ve optimize edilmiştir. Aşağıda, deponun yapısal taslağının kapsamlı bir dökümü yer almaktadır:

### 🤖 1. Yapay Zekâ (AI) ve LLM Güvenliği (`/Ai`)
Modern LLM ve yapay zekâ modellerinin çekişmeli (adversarial) testleri, güvenlik hizalama doğrulaması ve red-team operasyonları için tasarlanmış öncü bir koleksiyon:
* **Önyargı ve Adalet Testi:** Model hizalanmasını denetlemek için standartlaştırılmış sözlükler (`gender_bias.txt`, `race_ethnicity_bias.txt`).
* **Veri Sızıntısı ve Gizlilik:** Kazara PII alımı ve meta veri ifşası senaryolarını simüle etmek için hedefli payload'lar (`personal_data.txt`).
* **Çekişmeli ve Jailbreak Prompt'ları:** Model sınırlarını aşmak ve katı hizalama kısıtlamalarını test etmek üzere tasarlanmış tarihsel ve evrimleşmiş prompt enjeksiyon setleri.

### 🔍 2. Web Fuzzing, Varlık Keşfi ve Keşif (`/Discovery`)
Kurumsal saldırı yüzeyini ağ, uygulama ve altyapı katmanlarında agresif şekilde haritalamak için yapılandırılmış kapsamlı listeler:
* **Dizin ve Dosya Sayımı:** Gizli web yollarını, sistem arka kapılarını ve shell konumlarını tespit etmek için özenle hazırlanmış `raft` ve `DirBuster` serileri gibi yüksek hassasiyetli wordlistleri içerir.
* **Altyapı ve Ağ:** Subdomain sayım listeleri (Top 1M birleşik varyantları dahil), yaygın web uzantıları, servis adları ve özelleştirilmiş SNMP community string'leri (`snmp.txt`).
* **CMS ve Ortam Bağlamları:** WordPress eklenti/temaları, Drupal, Joomla, Apache, Nginx, Tomcat ve WebSphere için kapsamlı yollar dahil olmak üzere kurumsal sistemler ve İçerik Yönetim Sistemleri için son derece spesifik uç noktalar.

### 🔑 3. Kimlik Doğrulama ve Kimlik Bilgileri (Şifreler ve Sızıntı Veri Kümeleri)
Yüksek hızlı credential stuffing, varsayılan erişim denetimi ve karmaşık brute-force sözlük saldırılarına odaklanan ana listeler:
* **Sızdırılmış Kimlik Bilgileri ve Dökümler:** Efsanevi sızıntı veri kümelerinin optimize edilmiş varyantları (sıralanmış `rockyou` parçaları, `myspace` ve tarihsel sızdırılmış topluluk örüntüleri gibi) — tekrar sayılarıyla birlikte veya sayısız olarak.
* **Varsayılan Erişim Kayıtları:** Üretici varsayılan hesapları, standart yönlendirici şifreleri, CICS işlem kimlikleri ve çoklu üretici CCTV/DVR kimlik profilleri için kapsamlı eşleştirmeler.
* **Hedeflenmiş Ortamlar:** Belirli ağ protokolleri (SSH, Telnet, veritabanı root hesapları ve IPMI profilleri) için yapılandırılmış özel kimlik bilgisi dosyaları.

### ⚡ 4. Enjeksiyon, Fuzzing ve Mutasyon Payload'ları
Uygulama katmanı zafiyetlerini doğrulamak ve istismar edilemeyen sınır durumlarını elemek için derlenmiş gelişmiş payload'lar:
* **Sunucu Tarafı Zafiyetler:** Unix/Windows yolları için optimize edilmiş Local File Inclusion (LFI), Remote File Inclusion ve sistem değişkeni geçersiz kılma işlemlerini hedefleyen dinamik listeler.
* **Yerel Web Bileşenleri:** Parametre madenciliği (`burp-parameter-names.txt`), API keşfi (`api-endpoints.txt`) ve girdi doğrulama filtrelerini aşmak için tasarlanmış özel PHP fuzz listelerine yönelik kapsamlı eşleştirmeler.


---

## ⚖️ Yasal Uyarı

**Önemli Bildirim:** Bu depo ve burada sunulan veri kümeleri yalnızca eğitim amaçlı, yetkili sızma testleri ve güvenlik denetimleri için oluşturulmuştur.

*   **Kullanıcı Sorumluluğu:** Bu wordlistlerin kullanımına ilişkin nihai sorumluluk tamamen son kullanıcıya aittir. Sürdürücü; bu dosyaların kullanımından kaynaklanan herhangi bir kötüye kullanım, yetkisiz saldırı, veri ihlali veya yasal sonuç için hiçbir sorumluluk üstlenmez.
*   **Uyum:** Herhangi bir güvenlik değerlendirmesi, sözlük saldırısı veya fuzzing işlemine başlamadan önce hedef kuruluştan veya varlık sahibinden açık ve yazılı izin aldığınızdan emin olun.

Bu depoyu klonlayarak veya kullanarak bu şartları kabul etmiş ve faaliyetlerinizin yerel ve uluslararası siber güvenlik mevzuatına sıkı sıkıya uyacağını taahhüt etmiş olursunuz.



## 🐛 Sorun Bildirimi

Herhangi bir sorunla karşılaşırsanız veya yapılandırma sorunlarınız olursa, lütfen Prof.Shafiei@Gmail.com adresinden e-posta ile iletişime geçin. Ayrıca sorunları GitHub üzerinden de bildirebilirsiniz.


## ❤️ Bağış

Bu projeyi faydalı bulduysanız ve daha fazla geliştirilmesine destek olmak isterseniz, lütfen bağış yapmayı değerlendirin:

- [Buradan Bağış Yapın](https://t.me/AbdalDonationBot)


## 🤵 Sürdürücü

Tutkuyla sürdürülmektedir — **Ebrahim Shafiei (EbraSha)**

- **E-posta**: Prof.Shafiei@Gmail.com

- **Telegram**: [@ProfShafiei](https://t.me/ProfShafiei)
