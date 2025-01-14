# ElvedaDPI

**ElvedaDPI**, DNS zorlamasını kaldırmak ve internet sansürünü aşmak için kullanılan bir araçtır. Bu yazılım, **[GoodbyeDPI](https://github.com/ValdikSS/GoodbyeDPI)** projesinden esinlenilerek geliştirilmiş ve Türkiye gibi ülkelerdeki DNS zorlamalarını bypass etmek amacıyla optimize edilmiştir. Kullanıcıların Cloudflare gibi güvenilir DNS hizmetlerini kullanmasını sağlayarak, daha açık ve güvenli bir internet deneyimi yaşamasına yardımcı olur.

> **Not:** Bu yazılım **eğitim ve araştırma amaçlı** geliştirilmiştir. Yasal olmayan bir amaçla kullanımı kesinlikle teşvik edilmemektedir.

---

## Hukuki Uyarı ve Sorumluluk Reddi

Bu yazılım, ağ yönetimi ve internet sansürüyle ilgili teknik konuların anlaşılması amacıyla sunulmaktadır. Kullanımı tamamen kullanıcının sorumluluğundadır. Yazılımın herhangi bir yasa dışı kullanımı veya kötüye kullanımı, geliştiricinin sorumluluğunda değildir.

1. **Eğitim Amacı:**
   - Yazılım, yalnızca teknik bilgi edinme ve farkındalık yaratma amacıyla tasarlanmıştır.
   - Yasal olmayan hiçbir aktiviteyi teşvik etmez.

2. **Sorumluluk Reddi:**
   - Yazılımın kullanımı sırasında meydana gelebilecek sonuçlardan **geliştirici sorumlu değildir**.
   - Kullanıcılar, kendi ülkelerindeki yasal düzenlemelere uymakla yükümlüdür.

3. **GoodbyeDPI Kaynakları:**
   - **ElvedaDPI**, [GoodbyeDPI](https://github.com/ValdikSS/GoodbyeDPI) projesini temel alır. GoodbyeDPI'nin sağladığı açık kaynak araçlar, Türkiye gibi ülkelerde DNS zorlamasını aşmak için optimize edilmiştir.

---

## Dosyalar ve Yapı

Proje aşağıdaki dosya ve klasörlerden oluşur:

- **x86/**: 32-bit işletim sistemleri için gerekli dosyalar.
- **x86_64/**: 64-bit işletim sistemleri için gerekli dosyalar.
- **1.cmd**: DNS bypass hizmetini kurmak ve başlatmak için kullanılan dosya.
- **2.cmd**: DNS bypass hizmetini yeniden yapılandırmak ve başlatmak için kullanılan dosya.
- **service_remove.cmd**: Hizmeti ve ilgili dosyaları tamamen kaldırmak için kullanılan dosya.

---

## Kurulum ve Kullanım

### 1. **ElvedaDPI'yi Uygun Bir Klasöre Taşıyın**
Dosyaları uygun bir konuma taşıyın. Örneğin, `C:\ElvedaDPI\` gibi bir klasöre yerleştirmeniz önerilir. Bu, yazılımın daha düzenli bir şekilde çalışmasını sağlar. Masaüstü gibi geçici alanlarda dosyaları çalıştırmaktan kaçının.

---

### 2. **1.cmd'yi Yönetici Olarak Çalıştırın**
DNS bypass hizmetini kurmak ve başlatmak için:
1. `1.cmd` dosyasına **sağ tıklayın**.
2. **"Yönetici olarak çalıştır"** seçeneğini seçin.
3. Komut satırı işlemleri tamamlandıktan sonra DNS bypass işlemi etkin hale gelir.

Kurulum sırasında aşağıdaki işlemler yapılır:
- GoodbyeDPI hizmeti oluşturulur ve başlatılır.
- DNS sunucusu olarak güvenilir **Cloudflare** adresleri atanır:
  - **IPv4**: `1.1.1.1` (Port: 53)
  - **IPv6**: `2606:4700:4700::1111` (Port: 53)

> **Not:** Bu işlem tamamlandığında, ayrıca Windows ayarlarından DNS değiştirmenize gerek kalmaz.

---

### 3. **2.cmd'yi Yönetici Olarak Çalıştırın**
Hizmeti yeniden yapılandırmak veya başlatmak için:
1. `2.cmd` dosyasına **sağ tıklayın**.
2. **"Yönetici olarak çalıştır"** seçeneğini seçin.
3. Komut satırında hizmet başarıyla başlatıldığında, DNS bypass işlemi aktif hale gelir.

---

### 4. **Bilgisayarı Yeniden Başlatın**
Yapılandırmaların doğru şekilde uygulanabilmesi için bilgisayarınızı yeniden başlatın.

---

## Hizmeti Kaldırma ve Sorun Giderme

### Hizmeti Kalıcı Olarak Kaldırmak
Hizmeti tamamen kaldırmak veya hataları düzeltmek için:
1. `service_remove.cmd` dosyasına **sağ tıklayın**.
2. **"Yönetici olarak çalıştır"** seçeneğini seçin.
3. Komut satırı işlemi tamamlandıktan sonra:
   - GoodbyeDPI hizmeti durdurulur ve kaldırılır.
   - Olası WinDivert hizmetleri durdurulur ve kaldırılır.

---

## Alternatif DNS Sunucuları

Eğer Cloudflare DNS (1.1.1.1) bağlantınızda sorun yaşanırsa, alternatif DNS sağlayıcılarını kullanabilirsiniz. Aşağıdaki ayarları, `1.cmd` ve `2.cmd` dosyasında belirtilen DNS adresleri yerine koyabilirsiniz.

### 1. **Google DNS**
- **IPv4**: `8.8.8.8` ve `8.8.4.4`
- **IPv6**: `2001:4860:4860::8888` ve `2001:4860:4860::8844`

### 2. **OpenDNS**
- **IPv4**: `208.67.222.222` ve `208.67.220.220`
- **IPv6**: `2620:119:35::35` ve `2620:119:53::53`

### 3. **Quad9**
- **IPv4**: `9.9.9.9` ve `149.112.112.112`
- **IPv6**: `2620:fe::fe` ve `2620:fe::9`

> **Not:** DNS adreslerini değiştirmek için `.cmd` dosyalarındaki `--dns-addr` ve `--dnsv6-addr` parametrelerini güncellemeniz yeterlidir.

---

## Çalışmazsa Ne Yapmalı?

Eğer yazılım çalışmazsa veya beklenmedik hatalar alırsanız, aşağıdaki adımları deneyebilirsiniz:

1. **Yönetici Olarak Çalıştırmayı Doğrulayın**  
   - Komut dosyalarının her biri mutlaka **yönetici olarak** çalıştırılmalıdır.

2. **Hizmeti Kaldırın ve Yeniden Yükleyin**  
   - `service_remove.cmd` dosyasını çalıştırarak tüm hizmetleri kaldırın. Ardından `1.cmd` dosyasını yönetici olarak yeniden çalıştırın.

3. **Alternatif DNS Kullanımı**  
   - Cloudflare yerine başka bir DNS sağlayıcısını deneyin (Google DNS, OpenDNS, Quad9 gibi).

4. **Windows Güvenlik Duvarını Kontrol Edin**  
   - GoodbyeDPI'nin çalışması, güvenlik duvarı veya antivirüs tarafından engelleniyor olabilir. Gerekirse izin verin.

5. **GoodbyeDPI’nin Orijinal Sürümünü Deneyin**  
   - Orijinal [GoodbyeDPI](https://github.com/ValdikSS/GoodbyeDPI) projesini inceleyerek ilgili araçları çalıştırmayı deneyebilirsiniz.

---

## Kullanım Alanları ve Önemli Hatırlatmalar

- **Eğitim Amaçlı Kullanım:** Bu yazılım, DNS sansürü ve ağ yönetimi hakkında bilgi edinmek için tasarlanmıştır.
- **Araştırma ve Test:** Araç, ağ iletişimlerini test etmek ve DNS yönlendirme sorunlarını analiz etmek için kullanılabilir.
- **Güvenlik ve Gizlilik:** Cloudflare DNS gibi güvenilir DNS hizmetlerini kullanarak, çevrimiçi güvenliği ve gizliliği artırmayı hedefler.

---

## Destek ve Katkı

Eğer yazılımı kullanırken bir sorunla karşılaşırsanız:
- [GitHub Issues](https://github.com/kullaniciadi/ElvedaDPI/issues) sayfasından sorun bildirebilirsiniz.
- Katkıda bulunmak isterseniz projeyi forklayıp değişikliklerinizi paylaşabilirsiniz.

---

## Lisans

Bu yazılım açık kaynak olarak sunulmuştur ve lisanslıdır. Kullanımı sırasında yerel yasalara uyulması, tamamen kullanıcının sorumluluğundadır.

**ElvedaDPI**, sadece eğitim, araştırma ve farkındalık oluşturma amacıyla kullanılmalıdır.
