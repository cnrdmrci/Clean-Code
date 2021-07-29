# Clean Code

Robert C. Martin'in Clean Code kitabının bir özetidir.

### Temiz Kod Nedir?
Farklı programcılar tarafından en kolay anlaşılacak biçimde geliştirilen, değiştirilebilir ve sürdürülebilir kodları ifade eder.

### Genel Kurallar
- Kodumuz daima basit ve anlaşılır olmalıdır.
- Geliştirme alanı bulundugundan daha temiz bırakılmalıdır.
- Her zaman bir sorunun temel nedeni aranmalıdır.
- Programın çalışması işimizin bittiği anlamına gelmemelidir.


### İsimlendirme Kuralları
- Açıklayıcı ve net isimler seçilmelidir.
- Küçük L ve büyük O kullanırken dikkatli olunmalıdır.
- Kısaltmalardan kaçınılmalıdır.
- Aramaya uygun isimlendirmeler yapılmalıdır.
- Class adları isim olmalıdır. Method adları ise fiil olarak isimlendirilmelidir.
- Constructor overload yerine static factory method yöntemi kullanılmalıdır.
- Belirsiz sayı veya karakterler constant olarak tanımlanmalıdır. 

### Fonksiyon Kuralları
- Methodlar olabildigince küçük boyutlu olmalıdır.
- Sadece bir işlem yapmalıdır.
- En az sayıda parametre içermeli ve parametre üzerinde flag(true,false) gönderiminden kaçınılmalıdır. 
- Çok sayıda parametre için farklı bir class kullanılmalıdır.
- Side effect durumundan kaçınılmalıdır. (Side effect: Method içerisinde bambaşka bir işe dahil olan methodun barındırılması durumu.)
- Fonksiyonlar ya bir şey yapmalı ya da bir şeye cevap vermelidir, ancak ikisini birden değil. - Command Query Separation 
- Hata kodu yerine exception kullanılmalıdır.
- Çıktı argüman(out) kullanımından kaçınılmalıdır. Kullanılması gerekliyse; appendFooter(report); yerine report.appendFooter();  kullanımı daha uygundur.
- if ifadeleri 1 veya 2 satırı geçmemelidir.

### Yorum Kuralları
- Programda anlatılmak istenen, anlaşılır kod yazımıyla sağlanmalıdır.
- Yorumlar ile kod anlatımı yapılmamalıdır. Koda yorum yazmak yerine daha temiz tekrar yazılmalıdır.
- Yasal, bilgilendirici ve TODO yorumları yerine göre kullanılabilir.

### Formatlama Kuralları
- Takım ile birlikte genel kurallar belirlenmelidir.
- Programın girişinden aşağı doğru diğer methodlara inildikçe method ayrıntısı artmalıdır. Giriş kısmında ayrıntılara girilmemelidir.
- Her satır grubu bir düşünceyi temsil eder. Bu düşünceler birbirinden bir boşluk ile ayrılmalıdır.
- Yerel değişkenler her zaman methodların üst kısmında belirtilmelidir.
- Kavramsal yakınlık gösteren methodlar birbirine yakın olmalıdır.
- Satır genişliğine dikkat edilmelidir. Satırı okumak için sağa kaydırma önlenmelidir.
- İlişkili bölümleri daha iyi okumak için yatay boşluk kullanımına özen gösterilmelidir.
- Girintilere özen göstermek okunabilirlik açısından önemlidir.

### Sınıf Kuralları
- Class içeriğindeki sıralamaya özen gösterilmelidir.
- Kapsüllemeyi gevşetmek her zaman son çaredir. Ancak bir metodun testinin olması o metodun kapsüllenmesinden daha önemlidir.
- Sınıfların ilk kuralı, küçük olmaları gerektiğidir. Sınıfların ikinci kuralı, bundan daha küçük olmaları gerektiğidir.
- Sistemlerimizin birkaç büyük sınıftan değil, birçok küçük sınıftan oluşmasını istiyoruz. Böylece SRP ilkesini sağlamış oluruz.

### Nesneler ve Veri Yapıları Kuralları
- Dışardan erişimleri ve bağımlılıkları önlemek amacıyla nesnelerin private olarak tanımlanması gereklidir.
- İçerik bağımlılıklarını önlemek amacıyla da abstract yapılar kullanılması gerekir. interface gibi.
- Demeter Kuralına uyulmalıdır. : Bir modülün manipüle ettiği nesnelerin iç kısımlarını bilmemesi gerektiğini söyler.
- Tren şeklinde çağırılan method yapılarından kaçınılmalıdır.
- Nesneler davranışı ortaya çıkarır ve verileri gizler.
- Bir veri yapısının en önemli biçimi, genel değişkenleri olan ve işlevleri olmayan bir sınıftır. Buna bazen veri aktarım nesnesi veya DTO denir.
- Switch bloklarının SRP ve OCP prensiplerini genellikle sağlamaması nedeniyle abstract factory pattern kullanılmalıdır.


### Hata İşleme Kuralları
- Hata durumunda, hata kodu dönmek yerine exception kullanmak daha iyidir.
- Exceptionları özelleştirerek yönetmek faydalı olabilir.
- Özel hata durumlarını yönetmek için Special Case Pattern uygulanabilir.
- Methodlardan Null dönülmemelidir.
- Method parametrelerine Null deger gönderilmemelidir.
- Null durumlarını yönetmek için Null Object Pattern uygulanabilir.

### Sınırları Belirleme Kuralları
- Kodumuzun üçüncü taraf yazılımların ayrıntılarıyla ilgili çok fazla şey bilmesini önlemeliyiz. Bu entegrasyonu kapsülleme ile yapabiliriz.
- Üçüncü taraf yazılımlar için öğrenme testleri yazabiliriz. Yeni versiyonlarda davranış farklılıkları tespit edilebiliriz.

### Unit Test Kuralları
- Kötü kod yazmak gibi kötü test yazmak da hiç test yazmamayla eşdeğerdir. Her yeni eklemede düzeltme gerektiren testler oldukça fazla zaman alacaktır.
- Test kodu, üretim kodu kadar önemlidir. İkinci sınıf vatandaş değildir. Düşünce, tasarım ve özen gerektirir. Üretim kodu kadar temiz tutulmalıdır.
- Kodumuzun esnek, bakımı yapılabilir ve yeniden kullanılabilir olmasını sağlayan birim testleridir. Testleriniz varsa, kodda değişiklik yapmaktan korkmazsınız.


- Çeşitli durumları test eden bölümleri ayrı methodlar halinde kontrol etmeliyiz ve test işlevi başına yalnızca bir kavramı test etmeliyiz.
- Testleri Build-Operate-Check kuralına uyarak geliştirmeliyiz. (Given-When-Then)

- Bir testi temiz yapan 3 şey; Okunabilirlik, okunabilirlik ve okunabilirliktir.

- TDD yazmanın 3 kuralı;
  - Birinci Kural, başarısız bir birim testi yazmadan üretim kodu yazmamalısın.
  - İkinci Kural, aynı anda birden fazla başarısız birim testi yazmamalısın.
  - Üçüncü Kural, o anda başarısız olan testi geçmek için yeterli olandan daha fazla üretim kodu yazmamalısın.

- TDD - FIRST Kuralı;
  - Fast: Testler hızlı olmalıdır.
  - Independent: Testler birbirine bağlı olmamalıdır. Her testi bağımsız olarak çalıştırabilmeli ve testleri istediğimiz sırada çalıştırabilmeliyiz.
  - Repeatable: Testler her ortamda tekrarlanabilir olmalıdır.
  - Self-Validating: Testler ya geçerler ya da başarısız olurlar. Testlerin kontrolü için manuel bir değerlendirme gerekmemelidir.
  - Timely: Testlerin zamanında yazılması gerekir. Birim testleri, onları başarılı kılan üretim kodundan hemen önce yazılmalıdır.


