---
title:  "0’dan 1’e Veri Bilimi Projesi Adımları"
date:   2021-08-22 00:00:00
categories: [Data Science, Veri Bilimi]
tags: [Data Science]
style: fill
color: dark
description: Bir veri bilimi projesinden bastan sona nasıl yaklaşılması gerektiğinden, proje boyunca nelere dikkat edilmeli ve nasıl yönetilebilir durumundan bahsedeceğiz.
---
Herkese merhaba! Son zamanlarda veri bilimi üzerine birçok yazı yazılıyor, genellikle hangi problem için model yada algoritmaları kullanmalıyız üzerine tartışılıyor.

- Hangi model bizim için iyi olur?
- Bu verileri nasıl sınıflandıracağız?
gibi benzer sorularla çözüm aranılmaktadır. Bu yazıda, model yada geliştirme süreçlerinden değil, kısaca projeye başladığımızda bizlerin en çok zamanımızı alan adımlardan ve genellikle öneminin arka planda kaldığını düşündüğümüz konulardan bahsedeceğiz.

Temel olarak;

Bir veri bilimi projesinden bastan sona nasıl yaklaşılması gerektiğinden, proje boyunca nelere dikkat edilmeli ve nasıl yönetilebilir durumundan bahsedeceğiz. Anlatacağımız her bir madde projenizin sonuna kadar size yol gösterecektir. (Bu maddeler projenize, kurumuzun kültürüne veya tecrübenize göre değişkenlik gösterebilir. Kendi isteğinize göre ekleme veya azaltmalar yapabilirsiniz.)

[![Veri Bilimleri Adımları](https://www.linkpicture.com/q/datascience_1.png)](https://www.linkpicture.com/view.php?img=LPic6125c9277b8e8611933386)

**0. Adım**<br />
**“Doğru Sorular Sorun”**<br />
Proje başlamadan önce projenizle ilgili doğru sorular sormalı ve doğru cevaplar almalısınız. Çünkü proje geliştirildikten sonra çıkan ürünü; Kimler ne kadar kullanacak? Sağladığı katma değer nedir? Üretim maliyeti, zaman vb. gibi önemli soruların her birinin hesaplanması gerekmektedir. Projenizin modeli harika kodlansa bile başından sonuna kadar iyi hesaplanmadıysa gün sonunda rafa kaldırmak zorunda olabilirsiniz.

**1. Adım**<br />
**“Potansiyel değerini ölçün”**<br />
Projeye başlamadan önce yapmanız gereken ilk şey size yada kurumunuza vb. sağlayacağı faydayı hesaplamak için zaman ayırmanız gerekmektedir. Gerçekten gerek var mı yada yok mu sorularını kesinlikle netleştirmeniz gerekmektedir.

- Projeniz diğerlerinden neden daha önemli?
- Projenin sonuçları kimlere, ne fayda sağlayacak?
- Projeyi kimlerle yürüteceksiniz?
- İlgili alan bilgisini ve doğrulamasını kimden alacaksınız?
- Proje nerelerde, ne için kullanılacak?


Bu gibi sorularla kaba taslak yaptığınız ölçüler sayesinde proje ekibinin ve şirketin hedeflerinin eşleşmesi anlamında faydalı olacaktır. Bu sayede süreç boyunca çalışacağınız ortaklarınızla netleştirmenize fayda sağlayacaktır. Bu maddeyi atlamak ve ortalama katma değer hesabı yapmadan başlamak size boşuna para, zaman, kaynak vb. harcamanıza sebep olabilir. Bu bir yaklaşımı modellemiş, geliştirmiş ve büyük ölçüde zaman harcamış, sonuç olarak gerçek hayatta doğru çalışmayan yada katma değeri düşük olan bir projeye imza atmış olabilirsiniz.

Yatırım getirinizi hesaplamak (Return on Investment = ROI ) için aşağıdaki bu basit formülü kullanabilirsiniz;

[![Return on Investment = ROI ](https://www.linkpicture.com/q/roı.jpeg)](https://www.linkpicture.com/view.php?img=LPic6125c9dc182db479829932)

**2. Adım**<br />
**“Bir yaklaşım belirleyin veya temel bir model oluşturun.”**<br />


Probleminizin tanımı içinde bir yaklaşım belirlemeniz, probleminizin çözümü için hedefiniz daha net olacaktır. Bu yaklaşım önceden var olan bir yaklaşım da olabilir yada özel bir model geliştirmeniz gerekebilir. Ancak model ilk adım için çok detaylı yada karmaşık bir model olmamalıdır. (Modeliniz bir makine öğrenmesi algoritması tasarlamak gibi karmaşık bir iş değildir.)

Probleminizi tanımlayarak oluşturarak yatırımcı yada kişiler ile bu durumun detayını paylaşmalı ve geri bildirimlerle hareket etmelisiniz.

Örneğin;

“Bizim proje için düşündüğümüz yaklaşımda ilk adım için regresif (gerileyici) bir model kullanmak, sonrası için bir optimizasyon modeli kullanacağız. Bunu kullanma amacımız şu şekildedir…” durumu açıklamalı, değerlendirmesini yapmalısınız.

Deneyimli veri bilimcileri bu adımda, önce düşünür, çözümü hangi yaklaşımı iyileştireceği konusunda bir takım yaklaşım geliştirirler. Neyin zarar, neyin fayda sağlayacağını hesaplarlar. Bu sayede düşündüğü yaklaşımı paydaşlar ile paylaşır.

Bu adıma kadar yaptıklarınızın verimliliğini ve başarı oranını belirlemiş, başarılı olması gereken her şeyi önem sırasına göre listelemiş olursunuz. Karmaşık bir model yaratıp/yaratmayacağınızı tespit edersiniz. Bu adımı gerçekleştirmeden hemen karmaşık bir modele giriş yapmanız, kesinlik kazanmamış bir işe başladığınız için sizi zarara götürebilir.

**3. Adım**<br/>
**“Takımınızla tüm detayları tartışarak paylaşın.”**<br />
Bir projeyi başarılı bir şekilde geliştirmek için takımınıza kimler varsa her biriyle konuşun.Bu sizin hem hemde takımınızla projenin geleceğini belirlemenize yardımcı olacaktır. Eksikleri erken görmek yada farklı yorumlar yaptığınız işe katkı sağlayacak ve bölümleme yaparak süreçleri hızlandırabilirsiniz.

Örnekler vermek gerekirse;

- Projede hangi aşamada olduğunuzu,
- Planlamayı
- İş bölümünün nasıl yapacağınızı,
- Hangi aşamada kimlerle birlikte çalışacağınızı,
- Oluşturduğunuz model yaklaşımınızı,
- Gerçeklemek için hangi yoldan gideceğinizi,
- Hangi veriye ihtiyacınızın olduğunu,
- Kodun nasıl yazılacağını,
- Hangi platformlar kullanılacak,
- Kodun nasıl test edileceği,
- Performans ölçütlerinizi belirlemeniz gerekir.

Takım arkadaşlarınızla sürekli konuşun ve düzenli toplantılar yaparak hızlanacaksınız. Her zaman istediğiniz gibi gitmeyebilir. Bazen takım içinde yada kurum içinde iletişimsizlik, geliştirdiğiniz modelde karşılaşacağınız herhangi bir sorunu çözmenizi çok zorlaştırabilir, modelinizin bir kısmını yazdınız ve lokalde düzgün çalıştırdınız. Ancak aynı kod canlıya çıktığında sunucularda fazla kaynak tüketiyor, işlemleri yavaşlatıyor. Bunu tespit etmek, hatayı gidermek ve belkide kodunuzu optimize etmek için farklı bakış açılarına ihtiyacınız olacaktır.

**4. Adım**<br />
**“Modelinizi Geliştirin”**<br />
Modelinizi geliştirmek için her şeyin detayına girebilir, modelinize uygun makine öğrenmesi algoritmalarını tek tek deneyebilirsiniz. İsterseniz kendi algoritmanızı oluşturabilir ve sonuçlarını deneyebilirsiniz. Modeli gerçekleştirmek isterseniz dikkat etmeniz gerek bazı noktalar var.

**Kaliteli Kod Yazmak…**
Mümkün olduğunca sade şekilde kod yazmaya önem vermeliyiz. Diğer dikkat etmemiz gereken konular ise, önemsenmeyen yorum satırları, değişken ve method isimlerinin tanımlanması, bağımlılıklar (dependency) vb. dikkate alınacak  yazılım kalite metriklerinden bazılarıdır. Kodumuzun temizliği ve sadeliği, sizden sonra o kod ile çalışacak kişiler için oldukça önemlidir. Karmaşık kodlama (Spagetti Code) yaptığımızda projenin kişi üzerindeki bağımlılığı oldukça artmaktadır. Bu sebeple bağımlılıkları minimuma düşürmek için herkesin anlayabileceği şekilde oluşturmamız gerekiyor. (Konu ile ilgili Robert C. Martin Clean Code kitabında daha detaylı inceleyebilirsiniz.)
<br/>

**Dokümantasyon…**
Proje sürekliğini etkileyen faktörlerden birisidir. Bu sebeple kodunuza sonradan baktığınızla yaptığınızı anlamanız veya sizden sonrakilerin kodunuzu anlaması için dokümantasyon önem taşıyor.
<br/>

**Test etmek…**
Geliştirme aşamasında isteseniz de istemeseniz de bir çok hata ile karşılaşacaksınız. Hataları gidermek için kodunuzu Unit Testing, System Testing vb. gibi testlerden geçirmelisiniz. Makine öğrenmesi algoritmalarını nasıl test edebileceğinizi, yapılmış örneklerini bulabilirsiniz.
<br />

Farklı ortamlarda projenizi test etmelisiniz. Örneğin,Bulut tabanlı sistemler (Microsoft Azure, AWS gibi.) veya kişisel sunucular olabilir. Docker gibi bir konteyner teknolojisi ile kullandığınız tüm araçları, kütüphaneleri, işletim sistemini vb. herkeste aynı çalışacak şekilde standart hale getirmiş ve takım çalışanlarını platform bağımlılığından kurtarmış olursunuz.
<br/>

**Süreç yönetimi…**
GitHub, Bitbucket gibi versiyon kontrol sistemlerinde projenizde kullanmanızdır. Versiyon kontrol sistemleri (VCS), siz ile  ekibinizin koordinasyonunun sağlanması, projenin yedeklenmesi ve test aşamasının kolay gerçeklenmesi açısından büyük önem taşır.


**5. Adım**<br/>
**“Geri Dönüş (Feed Back)”**<br/>
Bu adım, projenin doğru çalışıp çalışmadığını görebilmek için yapılır. Problemin çözümünün sürekli kullanılabilir olması için çıktıların düzgün, performanslı ve güvenilir olması gerekmektedir. Genellikle sorulan:

- Modelinizin performansı düşük mü?
- Çıkan veriler, istediğiniz sonucu mu veriyor?

Tüm sonuçları düzgün görsellerle görmek bize çok zaman kazandırır. Özellikle paydaşlarımıza yaptıklarımızı gösterebilmek ve açıklamak için güzel bir dashboard tasarlamak veya var olan görselleştirme araçları kullanarak ekranlar oluşturup, sonuçları raporlamak oldukça önemlidir.

<br/>
Bu sayede kullanıcılardan geri bilirim alabilir, ilave değişiklikler, eklemeler yada eksiltmeler yapabilirsiniz. Eğer geri bildirimi kullanıcıdan değil de sistemin kendisinin kaydetmesini isterseniz günlük log tutabilirsiniz. Böylelikle kullanıcı alışkanlıklarını sistemin kendisinden öğrenebilirsiniz. Bu adımı projenize uyguladığınızda projenizin kalitesi ve verimi yükselmiş olur.
