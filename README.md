# ElvedaDPI

**ElvedaDPI**, DNS zorlamasını kaldırmak ve internet sansürünü aşmak için kullanılan bir araçtır. Bu yazılım, **GoodbyeDPI** tabanlıdır ve kullanıcıların Cloudflare gibi güvenilir DNS sunucularını kullanarak daha açık bir internet deneyimi yaşamalarına yardımcı olur. 

> **Not:** Bu araç **sadece eğitim ve araştırma amaçlı** geliştirilmiştir ve yasal olmayan herhangi bir kullanım için tasarlanmamıştır.

---

## Hukuki Uyarı ve Sorumluluk Reddi

**ElvedaDPI**, DNS yönlendirme ve sansür gibi teknik sorunların araştırılması ve çözülmesi amacıyla sunulmaktadır. Bu yazılımın kullanımı tamamen kullanıcının sorumluluğundadır ve aşağıdaki hukuki maddeler bu sorumluluğu açıkça belirtir:

1. **Eğitim Amacı:**
   - Bu araç, **eğitim ve farkındalık oluşturma** amacıyla geliştirilmiştir. Kullanıcılar, internet özgürlüğü ve ağ yönetimi konularında bilgi edinmek için aracı kullanabilirler.
   - Bu yazılım, herhangi bir ülkenin yasa veya regülasyonlarını ihlal etmeyi teşvik etmez.

2. **Sorumluluk Reddi:**
   - Araç, bireylerin kendi cihazlarında internet bağlantısını yönetmelerine ve sansür mekanizmalarını anlamalarına yardımcı olmak amacıyla geliştirilmiştir.
   - Kullanım sırasında doğabilecek sonuçlardan **geliştirici hiçbir şekilde sorumlu değildir**.
   - Kullanıcı, yazılımı kullanırken yürürlükteki tüm yasalara ve düzenlemelere uymayı kabul eder.

3. **Yasal Uygunluk:**
   - Kullanıcılar, bulundukları ülkenin yasal düzenlemelerini kontrol etmekten ve bu düzenlemelere uygun hareket etmekten sorumludur.
   - Yazılım, herhangi bir yasa dışı faaliyeti desteklemek amacıyla tasarlanmamıştır.

4. **Açık Kaynak Lisansı:**
   - Bu yazılım açık kaynak kodludur ve kullanıcılar yazılım üzerinde değişiklik yapabilir. Ancak, yapılan tüm değişikliklerin **yasalara uygun olması** zorunludur.

---

## Dosyalar ve Yapı

Proje, aşağıdaki dosya ve klasörlerden oluşur:

- **x86/**: 32-bit sistemler için gerekli dosyalar.
- **x86_64/**: 64-bit sistemler için gerekli dosyalar.
- **1.cmd**: DNS bypass hizmetini kurmak ve başlatmak için kullanılan dosya.
- **2.cmd**: DNS bypass hizmetini yeniden yapılandırmak ve başlatmak için kullanılan dosya.
- **service_remove.cmd**: Hizmeti ve ilgili dosyaları tamamen kaldırmak için kullanılan dosya.

---

## Kurulum ve Kullanım

### 1. **ElvedaDPI'yi Uygun Bir Klasöre Taşıyın**
Dosyaları uygun bir konuma taşıyın. Örneğin, masaüstünde bir klasör yerine `C:\ElvedaDPI\` gibi bir konum önerilir. Böylece dosyalar daha düzenli bir şekilde yönetilebilir.

---

### 2. **1.cmd'yi Yönetici Olarak Çalıştırın**
DNS bypass hizmetini kurmak ve başlatmak için:
1. `1.cmd` dosyasına **sağ tıklayın**.
2. **"Yönetici olarak çalıştır"** seçeneğini seçin.
3. Komut satırı işlemleri tamamlandıktan sonra DNS bypass işlemi etkin hale gelir.

Kurulum sırasında aşağıdaki işlemler yapılır:
- GoodbyeDPI hizmeti oluşturulur ve başlatılır.
- DNS sunucusu olarak güvenilir Cloudflare adresleri atanır:
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

### Yeniden Kurulum
Eğer hizmeti yeniden kurmak isterseniz:
1. `1.cmd` ve ardından `2.cmd` dosyalarını tekrar yönetici olarak çalıştırın.
2. Bilgisayarı yeniden başlatın.

---

## Dikkat Edilmesi Gerekenler

- **Yönetici Yetkileri:** Tüm komut dosyaları mutlaka **yönetici olarak** çalıştırılmalıdır.
- **Uygun Konum:** Dosyaları taşımadan çalıştırmamanız önerilir. Örneğin: `C:\ElvedaDPI\`.
- **Kurulum Sırası:** İlk olarak `1.cmd`, ardından gerekirse `2.cmd` çalıştırılmalıdır.
- **Sorun Giderme:** Eğer bir hata ile karşılaşırsanız `service_remove.cmd` dosyasını çalıştırarak yeniden yüklemeyi deneyin.

---

## Kullanım Alanları ve Önemli Hatırlatmalar

- **Eğitim Amaçlı Kullanım:** Bu yazılım, DNS sansürü ve ağ yönetimi hakkında bilgi edinmek için tasarlanmıştır.
- **Araştırma ve Test:** Araç, ağ iletişimlerini test etmek ve DNS yönlendirme sorunlarını analiz etmek için kullanılabilir.
- **Güvenlik ve Gizlilik:** Cloudflare DNS kullanımı, kullanıcıların güvenliğini ve gizliliğini artırmayı hedefler. Ancak, kullanıcılar bu aracı yasal çerçeve içinde kullanmakla yükümlüdür.

---

## Destek ve Katkı

Eğer yazılımı kullanırken bir sorunla karşılaşırsanız:
- [GitHub Issues](https://github.com/kullaniciadi/ElvedaDPI/issues) sayfasından sorun bildirebilirsiniz.
- Katkıda bulunmak isterseniz projeyi forklayıp değişikliklerinizi paylaşabilirsiniz.

---

## Lisans

Bu yazılım **açık kaynak** olarak sunulmuştur ve lisanslıdır. Yazılımın kullanımı sırasında yerel yasalara uymak tamamen kullanıcının sorumluluğundadır. 

**ElvedaDPI**, sadece eğitim, araştırma ve farkındalık oluşturma amacıyla kullanılmalıdır.
