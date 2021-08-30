---
title:  "Elasticsearch Nedir?"
date:   2021-08-28 00:00:00
categories: [Big Data]
tags: [elasticsearch]
---

ElasticSearch, Java tabanlı ve  açık kaynak olarak geliştirilmiş, içerik arama, veri analizi, sorgulamalar ve öneriler gibi işlemlerde özellikle performans kabiliyetleri, güçlü ve esnek olmasından dolayı tercih edilen bir arama motorudur.


![ElasticSearch](https://www.datasciencearth.com/wp-content/uploads/2020/07/elasticsearch-nedir.png)

Elasticsearch’de hem Near Realtime (Gerçek zamana yakın) hem de Distributed(dağıtık) yapısıyla veriler arasından içerik aramaları yapılıyor. 

Apache Lucene, full-text arama için geliştirilirken temelinde bazı mantık ve metodolojiler ile geliştirildi. Lucene, tek makinede “büyük boyutta” metin dosyaları üzerinde arama yaparken harika iş çıkarıyordu. Gelişen dünyada veriler de hızlı ve anlık(real-time) olarak akmaya başladı ve bunları ölçeklendirmek için dağıtık(distributed) sistemler geliştirildi. Zamanla Lucene bu sistemlere artık uyum sağlayamıyordu. Bunun için dağıtık sistemlere uyum sağlayabilecek teknolojiler üretilmeye başlandı.

Elasticsearch Özellikleri Nelerdir?
- Java tabanlıdır.
- Apache Lucene alt yapılıdır. (Shared ve Replica kavramları ES’te de aynen geçerlidir.)
- Açık kaynaktır.
- Veri saklama biçimi ilişkisel değil document-oriented şeklindedir
- Dağıtık ve ölçeklenebilir yapıda çalışabilir.
- Gerçek zamanlı verileri analiz etmeyi sağlar.
- Type, Fields, Documents, Fields, Indicates, Full-text search,  Index gibi kavramlara sahiptir
- RESTfull API üzerinden hizmet verdiğinden dolayı tüm programlama dilleriyle kullanılabilir.
- Veri tipine uygun biçimde otomatik Mapping yapabilir.
- Cluster yapıya sahiptir ve cluster yapısı oldukça basittir.
- Elasticsearch’ü monitör edebilen Kibana ve log barındırmak için Logstash araçları ile birlikte kullanılabilir.
- Dokümanları JSON olarak indexler.
- Hızlı kurulum ve kolay konfigürasyon vadeder.
- Elasticsearch’e veri aktarmak oldukça kolaydır. (Veri aktarımı için River gibi yapıları mevcuttur.)
- Kendi içinde yüksek erişilebilirlik (high availability) sunar.
- HBase, Cassandra, MongoDB gibi NOSQL veritabanlarından da ES’e aktarım yapmayı mümkün kılar.

İlişkisel veritabanları (RDBMS), indexlenmiş veriler dışındaki aramalarda oldukça yavaş bir arama performansı sağlar. E-ticaret ya da büyük ölçekli bir proje için istenmeyen bir durum oluşturmaktadır. Elasticsearch, büyük veriler arasında hız kaybı yaşanmadan arama yapılmasını sağlayan döküman tabanlı, NoSQL bir veritabanıdır. Elasticsearch’ın yapılma amacı aramalardaki bu kritik sorunun çözümünü sağlamaktır.

RDBMS’lerde “satır” olarak bilinen terim, Elasticsearch’te “döküman” olarak geçer. Her bir döküman JSON formatında saklanır. Tüm veritabanı işlemleri Elasticsearch’ün restful API servisi ile yapılır. Restful servisinin varsayılan portu 9200’dür. Kullandığı methodlar GET, POST, PUT, HEAD ve DELETE’tir.

**Temel ElasticSearch Kavramları**


**Indice**<br/>

Yukarıda görüldüğü üzerine klasik ilişkisel veri tabanlarında Veri tabanlarının yerine Elasticsearch’de Indice kavramları kullanılmaktadır. Bir Elasticsearch Cluster’ı birden fazla indexler bulundurabilir.

**Type (Tablo)**

İlişkisel veritabanlarındaki tablolar için “Type” kavramını kullanır. Bir indice, birden fazla tablo barındırabilir.

**Document( Doküman )** 

Elasticsearch’te, ilişkisel veri tabanlarındaki Rows (satılar), Documents  olarak temsil edilirler. Her type, birden fazla document’a sahiptir.

**Field (Column)** 

Klasik veritabanlarındaki Column’lar, Elasticsearch’te Field olarak nitelendirilir. Her document bir den fazla field’a sahiptir.

**Full-text search (Tam metin arama)**

Herhangi bir kaynaktan alınan metin belgeleri içinden, herhangi bir anahtar kelimenin aratılmasıyla, anahtar kelime ile eşleşen dokümanların bulduğu sonuca hızlı şekilde erişime verilen isimdir.

Örneğin, wikipedia.com sitesinde  bir kelime aratıp bununla ilgili yazılan yazıları okuyacağınızı varsayalım.

Wikipedia’nın arama çubuğuna Alan Turing yazdığınızda onunla ilgili yazıları bulmak için kayıtlı tüm yazılarda arama yapmak yerine, önceden indexlenmiş veriler içinden Alan Turing ’in adının geçtiği metinlerin olduğu index’e hemen gidip hızlıca size sonuç döndürmeyi sağlayan yapıdır.

Index

Elasticsearch’e eklenen her kayıt JSON belgesi olarak yapılandırılır. Bu sebeple, dokümanlarınızın içindeki her bir kelime(terim) için hangi doküman yada dokümanlarda o kelimenin olduğu bilgisini tutan bir endeksleme sistemi vardır. Bu veritabanı gibi düşünebilirsiniz. Veri tabanındaki verilerde olan düzen gibi, Elasticsearch’ün indexleri de JSON formatı şeklinde düzenlidir.

**Mapping**

Verileri indexlerken bu verilerin hangi tipte olduğunu göstermemiz gerekir. Yani o kelimenin hangi veri tipinde(string, integer, boolean) olduğu bilgisinin tanımlandığı işlemdir.

![ElasticSearch Mapping](https://www.datasciencearth.com/wp-content/uploads/2020/07/mapping-ornek.png)


**RESTfull API**

REST, istemci-sunucu iletişimi ile ilgili bir mimaridir. RESTfull servisler, istemci-sunucu arasında bir çok farklı tipte yanıt(response) dönebilirler (JSON, XML, CSV, HTTP). RESTfull API ise bu servisleri kullanan bir API.

**Near Realtime (Yakın gerçek zamanlı)**

Elasticsearch gerçek zamana yakın bir hızla çalışır. Gerçek zamanlı yerine “yakın gerçek zamanlı” denmesindeki sebep, bir dokumanı, gerçek zamandan çok az farklı bir gecikme süresi ile indexlenmesidir. (Bu süre genelde bir saniyelik bir gecikme oluyor.)

**Cluster**

Tüm verilerinizi bir arada tutan ve tüm indexleme ve arama yeteneklerinin yürütüldüğü birden çok  node’dan oluşan bir küme veya node koleksiyonu şeklinde adlandırılabilir.

Bir küme, varsayılan olarak “elasticsearch” şeklinde benzersiz bir adla tanımlanır Bu isimlendirme isteğe bağlı olarak değiştirilebilir. İsimlendirmeler önemlidir çünkü bir node yalnızca bir cluster’ın parçası olabilir. Node, cluster adıyla kümeye katılmak için ayarlanmışsa bu isim tanımlamalarının doğruluğuna ihtiyaç olacaktır.

**Node**<br/>

Tek bir server’a verilen isimdir. Verilerin depolandığı makinelerin her biridir. Clusterların indesleme ve arama yetenekleri bu nodelar sayesinde gerçekleşir. Clusterlardaki isimlendirme mantığındaki gibi nodelara da başlangıçta benzersiz bir id atanır (Universally Unique IDentifier (UUID)).
Bu isimlendirmeler, nodelar arasındaki bilgi alışverişinin yönetimi için oldukça önemlidir. Eğer istenirse bu isimler de değiştirilebilir.
Varsayılan olarak her node “elasticsearch” şeklinde isimlendirilen bir cluster’da çalışmak üzere ayarlanmıştır. Hangi node’un hangi cluster’a gitmesini isterseniz, o cluster ismine yönlendirmelisiniz.

**Shard**<br/>

Tek seferde milyonlarca dokumanı indexlemek için yeterli donanıma/server kapasitesine sahip olmayabilir. Tek seferde 2TB lık veriyi indexlemek zorunda kaldığınızı varsayalım, bu durumda bu indexlemeyi tek bir node ile yapmak istediğinizde, disk kapasitesinin dolması veya aşırı yavaş bir indexleme hızı ile karşı karşıya kalabilirsiniz.

Bunun önüne geçmek için Shard ve Replika kavramları bulunmaktadır.

Yapılacak olan bir index, bir node da yeniden shardlara bölünür. Bu shardları kendinize göre ayarlaya bilmektesiniz.

Shardlı mimarinin kullanılmasındaki temel amaçlar;

Birden fazla node üzerinde işlemleri dağıtımınızı ve paralelleştirmenizi sağlar. Böylece performans artar.
İçerik hacmini yatay olarak bölme ve ölçeklendirmeye olanak sağlar

**ElasticSearch Nasıl Çalışır ?**
Bir veri yani document kaydedilirken, veri içerisindeki alanlar yani fieldlar “Apache Lucene” altyapısı kullanılarak indexlenir. Bu şekilde bir kelimenin hangi row’da yani document’da geçtiği indexlenir. Daha sonra ilgili keyword aranırken bu büyük veri kümesi içerisinde değil de, bu oluşturulan index listesi içerisinde arama yapılır.  Böylece istenen arama sonucuna, çok büyük bir hızda ulaşılabilir.

**Replica**

Tamamen güvenlik amaçlı çalışan, her verinin bir kopyasının bulunduğu başka makinelerdir. Böylece bir makine çöktüğünde replica veya replicalarından biri devreye girebilecektir. Örneğin aşağıda 3 Node’lu 3 Shardingli bir yapı söz konusudur. Her bir shard’ın 1 yedeği, yani 1 replicası bulunmaktadır. Sonuçta aşağıdaki örnekte 3 Node, 3 Shard ve 1 Replica mevcuttur. Toplamda 6 sunucu bulunmaktadır.

NOT:  Her bir Shard’ın Replicasının başka bir Node’da bulunması gerekir.


![ElasticSearch Mapping](http://www.borakasmer.com/wp-content/uploads/2016/12/3s1r1n.png)


Terminal ekranına aşağıdaki komutlar yardımı ile ilk index dokümanımızı oluşturalım;

```bash
        curl -XPOST -H 'Content-Type: application/json’ ‘localhost:9200/first-index/message‘ -d '

        { “text”: “Merhaba emrebalikci.com”}'
        
```

Şimdi Elasticsearch’e ‘merhaba’ kelimesini aratacağımız bir istek gönderelim;

```json
        {
        "query": {
        "query_string": {
        "query": "merhaba"
                        } 
                }
        }'
```

Sonuç olarak aşağıdakine benzer bir çıktı alacaksınız.


```json
        {
            "took": 12,
            "timed_out": false,
            "_shards": {
            "total": 12,
            "successful": 12,
            "failed": 0
            },
            "hits": {
                "total": 1,
                "max_score": 0.19178301,
                "hits": [{ "_index": "first-index",
                            "_type": "message",
                            "_id": "AUqiBnvdK4Rpq0ZV4-Wp",
                            "_score": 0.19178301,
                            "_source": {
                            "text": "merhaba emrebalikci"}
                        }]
                    }
        }
```


Yukarıdaki çıktıda içinde merhabanın geçtiği dokümana ait bilgiyi size döndürülüyor. Eğer birden fazla içinde merhaba geçen dokümanınız olsaydı, onları da getirecekti. Burada dikkatinizi çeken bir başka şey de biz “Merhaba” kelimesinin ilk harfini büyük yazdık ama aratırken “merhaba” diye arattık. Ancak yine de buldu çünkü varsayılan değer olarak büyük/küçük harf önemsemiyor. Fakat isterseniz Elasticsearch’ün harf büyük/küçüklük hassasiyetini ayarlayabiliyorsunuz.

İlk Elasticsearch örneğinizi böylece tamamladınız.

Umarım faydalı bir yazı olmuştur.
İyi çalışmalar dilerim 