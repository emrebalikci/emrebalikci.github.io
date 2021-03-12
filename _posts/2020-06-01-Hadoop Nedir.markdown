---
title:  "Hadoop Nedir?"
date:   2020-06-01 00:00:00
categories: [Big Data]
tags: [data analysis]
---
Big Data, büyük ölçekli verilerin oluşturduğu veri setlerine (Data Set) verilen isim ve biz bu büyük veri setlerini kaydetmek ve işlemek için çeşitli dosya sistemleri ve veritabanları kullanıyoruz. Hadoop da büyük veri setleri ile birden fazla makinede paralel olarak işlem yapmamızı, verileri kaydetmemizi ve yönetmemizi sağlayan, M

MapReduce özelliklerini bir araya getiren, Java ile yazılmış açık kaynak kodlu kütüphanedir.

>Hadoop içinde büyük verileri sakladığımız bileşene HDFS (Hadoop Distributed File System) denir.

![Hadoop ](https://miro.medium.com/max/2760/1*kPKoXmHBDmGthbah-0549A.png)

**HDFS** nedir?
Hadoop Distributed File System ( Hadoop Dağıtık Dosya Sistemi )

Petabyte seviyesindeki büyük verileri saklamak için pahalı bir donanım satın almak yerine sıradan sunucuların disklerini bir araya getirerek büyük, tek bir sanal disk oluştururlar. Bu sunucu disklerine **Cluster** adı verilmektedir. 

Clusterların her biri aynı yerde durmak durumunda değildirler, farklı bölgelerde, farklı şehirlerde hatta farklı ülkelerde aynı sisteme hizmet edebilirler.

HDFS içine büyük boyuttaki veriler kopyalandıktan sonra bir çok kaynak üzerinden aynı anda ve oldukça hızlı erişim sağlanabilir. Bu dosya sistemi içinde büyük veriler küçük dosya blokları halinde saklanırlar.

HDFS, **NameNode** ve **DataNode** olarak iki ayrı süreçten oluşur.

**NameNode**, master(ana) düğümdür. Verilerin bloklar halinde parçalanarak dağıtıldığını düşünürsek bu parçaların her birinin diğer makinelere DataNode) dağılımından, yaratılmasından, silinmesinden, yeniden oluşturulmasından sorumlu düğümdür. (Serverlar arasındaki configürasyonu sağlayan ana makine)

**DataNode**, slave(işçi) düğümdür. Ona verilen blockları kendi yerel diskinde saklamaktan sorumludur. İlave olarak diğer DataNode’lardaki verilerin yedeklerini de saklayabilirler. Bir HDFS sistemde birden fazla olabilirler.


![HDFS Architecture](https://hadoop.apache.org/docs/r1.2.1/images/hdfsarchitecture.gif)


**MapReduce** ise HDFS üzerindeki büyük verileri işleyebilmek amacıyla kullanılan bir yöntemdir.Map-Reduce tanım olarak büyük verilerin işlendiği programlama yapısı olarak açıklanabilir.

Tipik bir Map-Reduce veri işleme biçimi birkaç adımdan oluşur. 
Bu adımlar 
- **Input**, 
- **Splitting** (Veriyi Bölmek), 
- **Mapping** (İlgili Düğümlerde İşlemek) , 
- **Shufling** (Her düğümde saymak),
- **Reducing** (Sonuçları Toplamak) 
- **Final Result** (Raporlamak) 
şeklindedir.

Map-Reduce’un  temel çalışma şeklini  örnek ile anlatmaya çalışacağım.

Farz edelim ki, büyük veri olmadığını ve oldukça küçük bir müşteri bilgi sistemi geliştirdiğimizi düşünelim.

Bu ufak sistemin veritabanında yalnızca 100 müşterinin bazı bilgileri olsun.
Bu bilgiler, TC Kimlik Numarası, Ad, Soyad, Yaş alanları olsun.
Biz bu 100 kişi içinden soyadları ‘Balıkçı’ olan kişilerin içindeki en genç müşteriyi bulmak istesek

SELECT MIN(yas) FROM müsteri WHERE soyad=‘Balıkçı’

şeklinde bir SQL sorgusu ile sonuca rahatça ulaşabiliriz.

Peki, ya bu 100 kişilik sistem yerine, 100.000.000 olsa.. Ne yapardınız?

Hatta veritabanındaki alanlara nüfus bilgisi, adres, telefon, meslek, maaşını, kullandıkları kredi kartları bilgileri,sipariş durumu, eğitim durumu alanları ekleseydik?
Daha sonra, soyadı ‘Balıkçı’, eğitim durumu ‘Üniversite’ olan insanların sayılarını bulmak istesek ne yapardık?

Oldukça büyük bir veri ile karşı karşıyayız ve klasik SQL sorgularını kullanarak bu analizi yapmak bir hayli uzun zaman alacaktır.

Bu durumda devreye **Map-Reduce** giriyor. Bu denli büyük verilerin onlarca sunucu(cluster) üzerinde(clusterlar daha fazla da olabilir) dağıtık olarak kayıtlandığını düşünelim.


**Map-Reduce** her bir clusterdaki verileri dolaşarak istediğimiz analizi hızlı ve etkin şekilde yapabilmemize olanak sağlıyor.

Yazılışı çeşitli dökümanlarda birleşik gibi görünsede Map-Reduce aslında **Map**(Mapping) ve **Reduce**(Reducing) iki ayrı işlem yapan, bir arada çalışarak dağıtık dosya sistemlerinde veri analizinin oldukça kolaylaştırılmasını sağlayan methodlardır.
- **Map**, bir listedeki her bir elemana tek tek bir kuralı uygular.
- **Reduce**, Map ile elde edilen sonuçları belli bir sistematik ile analiz ederek birleştirir.
Yaptığı analiz sonunda da bir değer döndürür.


![HDFS Architecture](https://imgs.developpaper.com/imgs/3247464597-5d7ee172e7cc6_articlex.png)
Hadoop şuanda Facebook, Twitter, Yahoo, Alibaba, EBay, Adobe(…) ve daha bir çok  firmada büyük verileri analiz etmek amacı ile kullanılıyor.

Bunların yanısıra Hadoop projesi büyük verileri işlemek için başka projelere bir çatı görevi görüyor. Bu projelerden bazıları, **Hive, Mahout, Cassandra, Pig, Zookeper**.




