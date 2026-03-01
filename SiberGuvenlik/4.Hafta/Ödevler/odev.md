# 🦅 Siber Güvenlik Mühendisliği Eğitimi - 2026

> **"Bir mühendisin kalitesi, bulduğu açıkla değil; süreci nasıl yönettiği ve raporladığıyla ölçülür."**

Bu repo, AnkaCORE '26 eğitim programının **101 Aşaması Bitirme Projesi (Capstone Project)** teslim merkezidir. 5 haftalık zorlu temel eğitimin sonuna geldiniz. Bu proje, sadece araç kullanan "Turistler" ile sistemin bütününe hakim olan "Mühendisleri" birbirinden ayıracak olan final operasyonudur.

---

## 📅 101 BİTİRME PROJESİ: "The Analyst & The Hunter"

| Parametre | Detay |
| :--- | :--- |
| **Durum** | 🔴 FİNAL OPERASYONU (201'e Geçiş Bileti) |
| **Kapsam** | İşletim Sistemleri, Ağ Analizi, Web Exploit ve VDP Raporlama |
| **Zorluk Seviyesi** | ⭐⭐⭐⭐⭐ (5/5) |
| **Son Teslim** | 11 Mart Çarşamba 23:59 |

---

### 🚀 Görev Özeti: "Siber Uzayda Noktaları Birleştirmek"

Geçtiğimiz 5 hafta boyunca siber güvenliğin farklı yapıtaşlarını inceledik. Wireshark ile paketlerin arasına daldık, Linux'ta terminalin gücünü keşfettik ve Burp Suite ile web mantığını manipüle ettik. Ancak siber uzayda hiçbir şey bağımsız değildir. Gerçek bir uzman, ağı, işletim sistemini ve web'i tek bir satranç tahtası gibi görebilmelidir.

Önünüzde 10 günlük geniş bir süre var. Bu final projesi iki ana fazdan oluşmaktadır. Önce laboratuvar ortamında teknik derinliğinizi kanıtlayacak, ardından sahaya inip gerçek bir avcı gibi iz süreceksiniz. 

Bu final operasyonunda iki ana cephede savaşıyoruz:

#### ⚔️ FAZ 1: "Siber Triatlon" (Teknik Derinlik ve Analiz)
Sadece web açığı arayan biri, o açığın arka planda nasıl bir sistem yetkisine dönüştüğünü veya ağda nasıl bir iz bıraktığını bilemez. Bu fazda konfor alanınızdan çıkıp 3 farklı teknik cephede savaşacaksınız.
* **Hedef:** İşletim sistemleri (Linux/Bash), Web Sunucusu Mantığı (Server-Side) ve Ağ Adli Analizi (PCAP) konularında ustalaşmak.
* **Kritik Kavramlar:** SSH Key yönetimi, Command Injection, LFI, Wireshark Filtreleri ve Zararlı Yazılım (Malware) Trafik Analizi.
* **Saha:** *OverTheWire (Bandit & Natas)* ve *TryHackMe (C2 Carnage)*.

#### 🕵️‍♂️ FAZ 2: "Saha Operasyonu" (Web Recon & VDP Raporlama)
Laboratuvarda bayrak (flag) yakalamak eğlencelidir, ancak sektörde size para ve itibar kazandıran şey; gerçek bir şirketteki açığı bulmak ve bunu profesyonelce raporlamaktır.
* **Hedef:** Gerçek bir VDP (Vulnerability Disclosure Program) üzerinde saldırı yüzeyini çıkartmak ve zafiyet aramak.
* **Kritik Kavramlar:** Attack Surface Mapping, Subdomain/Directory Fuzzing, Zafiyet Sömürüsü (PoC), CVSS Skorlama ve Yönetici Özeti Hazırlama.

> **💡 Vizyon:** Amacımız sadece ekranda rastgele komutlar çalıştırmak değil; bir hedefe sistematik olarak yaklaşmak, bulgularımızı analiz etmek ve bunu bir şirketin CEO'suna dahi sunabileceğimiz **"Milyonluk bir rapora"** dönüştürmektir.

---

### 📝 Görev 4: Bug Hunter Başlangıç Raporu (Proje Ödevi)

Aşağıdaki 4 bölümden (A, B, C, D) oluşan, analizlerinizi **ekran görüntüleri ile kanıtladığınız**, teknik bir **PDF Raporu** hazırlamanız gerekmektedir.

**⚠️ Rapor Kuralları:**
1.  **Kanıt Zorunluluğu:** Burp Suite ekran görüntüleri ve Terminal çıktıları rapora eklenmelidir.
2.  **Özgünlük:** HTTP durum kodlarını veya açıkları kitaptan kopyalamayın. Kendi cümlelerinizle yazın.
3.  **Format:** Kapak sayfası olan, düzenli bir PDF dosyası (`Ad_Soyad_Hafta4.pdf`) olarak teslim edilmelidir.

---

#### **Bölüm A: Teori ve Mimari (Research & Logic)**

Burp Suite'i açmadan önce HTTP'nin dilini anlamalıyız. Aşağıdaki soruları teknik bir dille ve kendi cümlelerinizle yanıtlayın.

**1. Web Anatomisi: HTTP Protokolü**
* Tarayıcınız bir web sitesine girerken sunucuyla konuşur. Sunucunun verdiği cevaplardaki HTTP Durum Kodlarından (Status Codes) **200**, **302**, **401**, **403** ve **500** kodlarının bir pentester (sızma testi uzmanı) için anlamı nedir? (Örn: 403 gördüğümüzde ne anlarız, pes mi ederiz?)

**2. Kimlik ve Yetki: "Sen Kimsin?"**
* **Cookie, Session ve Token:** Bu üç kavramın farkı nedir? Bir web sitesi, sayfayı her yenilediğimizde bizim "aynı kişi" olduğumuzu nasıl anlar?
* **Authentication vs Authorization:** Biri "Kimlik Doğrulama", diğeri "Yetkilendirme"dir. Sisteme başarıyla giriş yapmak (Login) hangisidir? Girdiğiniz sistemde başkasının mesajlarını okuyabilmek (IDOR) hangisinin zafiyetidir?



**3. Zafiyet Mimarisi: IDOR**
* **IDOR (Insecure Direct Object Reference)** nedir? Bir yazılımcı hangi güvenlik kontrolünü yapmayı unutursa uygulamasında IDOR zafiyeti ortaya çıkar?

---

#### **Bölüm B: Saha Eğitimi (TryHackMe & Dorking)**

Bu bölümde web dünyasının temel araçlarını kuşanıyoruz.

**Görev 1: İnternetin Röntgeni (TryHackMe)**
* **Oda:** [TryHackMe | HTTP in Detail](https://tryhackme.com/room/httpindetail) (Veya alternatif olarak *Burp Suite: The Basics* odası).
* **İstenen:** Odayı tamamlayın. HTTP Request (İstek) başlıklarındaki `User-Agent` ve `Host` parametrelerinin ne işe yaradığını kendi cümlelerinizle açıklayın.

**Görev 2: Google Dorking (Açık Kaynak İstihbaratı)**
Google sadece bir arama motoru değil, dünyanın en büyük zafiyet tarayıcısıdır.
* **Senaryo:** Hedefiniz `ankasec.co` (veya seçtiğiniz başka bir Bug Bounty hedefi).
* **Görev:** Hedefle ilgili potansiyel olarak hassas dosyaları (Admin paneli, PDF belgeleri, Backup dosyaları vb.) bulmak için kullanacağınız **3 farklı Google Dork** sorgusu yazın ve bu sorguların tam olarak ne aradığını açıklayın. (Örn: `site:hedef.com ext:pdf`).
* **Kanıt:** Yazdığınız Dork'lardan birini Google'da aratıp sonucunun ekran görüntüsünü ekleyin.

---

#### **⚔️ BÖLÜM C: Operasyonel Görev (Boss Fight)**

Simülasyon bitti, gerçek av başlıyor. Bu bölümde "Gerçek" hedefler üzerinde Recon yapacak ve PortSwigger laboratuvarlarında yetki atlatacaksınız.

### 🕵️‍♂️ Cephe 1: Hayalet Avı (Recon Haritası)
* **Hedef:** HackerOne veya Bugcrowd üzerinde "Public" (Herkese açık) ve "Safe Harbor" (Test izni olan) bir program seçin. (Örn: Yahoo, Red Bull, Ford).
* **Operasyon:**
    1.  Terminalinizi açın. `subfinder` veya `amass` kullanarak hedef domainin alt alan adlarını (subdomain) tarayın.
    2.  Bulduğunuz sonuçları `httpx` aracına vererek hangilerinin "Canlı" (Live) olduğunu kontrol edin.
* **Raporlama:** Bulduğunuz en ilginç **3 subdomain'i** ve `httpx`'ten dönen **HTTP durum kodlarını** raporlayın. (Neden bu 3'ü ilginizi çekti?). Terminal çıktısının ekran görüntüsünü ekleyin.

### 🔓 Cephe 2: Yetkiyi Delmek (PortSwigger Labs)
Web güvenliğinin kutsal mekanı PortSwigger'da gerçek IDOR senaryoları çözeceğiz.

* **Platform:** [PortSwigger Web Security Academy](https://portswigger.net/web-security/learning-path) (Kayıt olun, ücretsizdir).
* **Görev:** Aşağıdaki iki IDOR/BAC laboratuvarını çözün:
    1.  *Lab: Insecure direct object references*
    2.  *Lab: User ID controlled by request parameter*
* **Raporlama Formatı:** "Çözdüm" demek yok. Burp Suite kullanarak trafiği nasıl yakaladığınızı (Proxy), isteği **Repeater**'a nasıl attığınızı ve parametreyi (`id` veya `user`) değiştirerek başkasının verisine nasıl ulaştığınızı adım adım anlatın.
* **Kanıt:** Burp Suite Repeater ekranında başarılı response (Örn: Başkasının API anahtarını veya şifresini gördüğünüz an) açıkça görünmelidir.



---

#### **🧠 BÖLÜM D: Mühendislik Vizyonu (Reflection)**

*Analiz bitti, şimdi yorumlama zamanı.*

**1. IDOR'un Gerçek Hayat Etkisi (Impact):**
*Senaryo:* Bir hastanenin e-randevu sisteminde test yapıyorsunuz. Kendi tahlil sonucunuza bakarken URL'nin `hastane.com/tahlil?id=500` olduğunu gördünüz.
* **Soru:** `id=501` yaptığınızda başkasının HIV veya Kanser test sonucunu görebiliyorsanız, bu zafiyetin KVKK (veya GDPR) açısından şirkete maliyeti ve marka itibarına vereceği zarar nedir? Bir mühendis olarak bu açığı şirkete raporlarken **"Risk Seviyesini (Impact)"** nasıl açıklarsınız?

**2. Güvenin Bedeli (Zero Trust):**
* **Soru:** IDOR ve Broken Access Control zafiyetlerinin temelinde yatan yazılımcı hatası, "Kullanıcıdan gelen girdiye (Input) güvenmek"tir. Bir yazılımcı bu hatayı yapmamak için arka planda (Backend) nasıl bir kontrol (Check) mekanizması kurmalıdır?

---

### 📤 Teslim Formatı ve Kontrol Listesi

* **Dosya Adı:** `Ad_Soyad_Hafta4.pdf`
* **Format:** PDF (10 - 12 Sayfa Önerilir).
* **Sayfa Düzeni:**
    * [ ] Kapak Sayfası.
    * [ ] Ekran Görüntüleri (Terminal Recon çıktıları, Burp Suite ekranları, Dork sonuçları).
    * [ ] Açıklamalar (Görsellerin altında ne yapıldığına dair teknik yorumlar).
* **Yükleme:** Kendi GitHub reponuzda `Hafta-4/Odevler` klasörüne yükleyip, ana repoya **Pull Request (PR)** açın.

---

### 📚 İpucu Kutusu (Cheat Sheet)

#### 🌐 Recon (Keşif) Komutları
| Araç | Komut | Açıklama |
| :--- | :--- | :--- |
| **Subfinder** | `subfinder -d hedef.com -all` | Hedefin tüm alt alan adlarını pasif olarak bulur. |
| **httpx** | `cat subdomains.txt \| httpx -sc -title` | Bulunan domainlerin hangilerinin çalıştığını (Status Code) ve başlıklarını (Title) gösterir. |
| **Dirsearch** | `dirsearch -u https://hedef.com` | Sitedeki gizli klasörleri (admin, backup vb.) tarar. |

#### 🕷️ Burp Suite Kısayolları
* `Ctrl + R`: Seçili isteği Repeater'a gönderir (Kurcalamak için).
* `Ctrl + I`: Seçili isteği Intruder'a gönderir (Otomatize saldırı için).
* **İpucu:** IDOR ararken, tarayıcınızda normal bir işlem yapın, Burp HTTP History'de o isteği bulun ve parametrelerle oynayın!



**Başarılar, Ödül Avcıları.**
*AnkaCORE Operasyon Merkezi*