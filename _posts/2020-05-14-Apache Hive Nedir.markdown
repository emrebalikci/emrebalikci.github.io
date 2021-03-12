---
title:  "Apache Hive Nedir?"
date:   2020-06-01 00:00:00
categories: [Big Data]
tags: [data analysis]
---

Apache Hive projesi SQL benzeri bir arayüz yardımıyla Hadoop üzerinde Java kullanmadan sorgulama ve analiz işlemlerini yapmak amacıyla Facebook tarafından geliştirilmiş, daha sonrasında Apache’ye devredilmiş açık kaynaklı bir projedir. Özellikle Veri Ambarı (Datawarehouse) uygulamalarını Hadoop kümeleri üzerinde geliştirebilmek için Hive projesi birçok firma tarafından kullanılmaktadır. 



![Apache Hive ](https://www.tertiarycourses.com.my/media/catalog/product/cache/2/image/512x/040ec09b1e35df139433887a97daa66f/a/p/apache-hive_1_1.jpg)

Hadoop gibi dağıtık dosya sistemlerinde kayıtlı olan büyük verileri sorgulamak için kullanılıyor.
Alışık olduğumuz SQL sorgularını, Hive ile birlikte büyük verileri analiz etmek için yazabiliyoruz.Gerçek zamanlı sorgulama yapamaz.

Hive ile yazılan sorgular aslında arkaplanda MapReduce komutlarına çevriliyorlar. Ancak iç içe onlarca sub-query(alt sorgu)’nin olduğu bir sorguda MapReduce ile sorgu yapmak oldukça güçleşecektir.MapReduce her ne kadar Hive’a göre daha güçlü bir kontrol sağlasa da Hive, SQL ile çok benzeyen sorgu dili ile hadoop ve diğer dağıtık dosya sistemlerini kullanan bix geliştiriciler için oldukça kolaylık sağlıyor.
Biraz Hive’ın sorgu biçimi inceleyim.

Hive’ın Select deyiminin yazım biçimini şu şekildedir:

```sql
     SELECT [ALL | DISTINCT] select_expr, select_expr, ...
        FROM table_reference
        [WHERE where_condition]
        [GROUP BY col_list]
        [HAVING having_condition]
        [CLUSTER BY col_list | [DISTRIBUTE BY col_list] [SORT BY col_list]]
        [LIMIT number]
```

Eğer daha önce SQL kullandıysanız muhtemelen bu tarz bir sorguya aşinasınız. Ama ben yine de biraz açıklamak istiyorum.

-   **SELECT**, SQL’deki projeksiyon operatörüdür.
-   **SELECT, FROM** yan tümcesi tarafından belirtilen tabloyu tarar
-   **WHERE**, neyin filtreleneceğini belirtir
-   **GROUP BY**, kayıtların nasıl toplanacağını belirten sütunların bir listesini verir
-   **CLUSTER BY**, DISTRIBUTE BY, SORT BY sıralama düzenini ve algoritmasını belirtin.
-   **LIMIT** kaç adet kayıt alınacağını belirtir

Gördüğünüz gibi tıpkı SQL de olduğu gibi Hive’da bu şekilde kullanılarak büyük verileri rahatlıkla analiz etmeye yardımcı oluyor.

Hive’ın MapReduce ile farklı olarak sağladığı kolaylıktan biraz bahsedecek olursak,
Hive’da çeşitli tool’lar(araçlar) kullanarak Şema(Hive Shema) oluşturabiliyoruz. Şema mantığı aslında klasik SQL sorguları ile oluşturduğumuz tablo mantığı gibidir. Kolon isimleri ve veri tipleri ile oluşturulan tablolar, Hive’da da şema şeklinde oluşturuluyor. Hive ile belirli formattaki dosyaların(.csv, json vs.), metadataları içerisine girerek tablo gibi tanımlayabiliyoruz.

Bir örnek ile kavramaya çalışalım...
        
```json
        {
             "name": "Emre",
             "surname": "Balıkçı",
             “student_info”: {
                “id": 123,
                "department": Bilgisayar Mühendisliği,
                “class": “4"
            }
        }
```

şeklinde bir örnek JSON dökümanımız olsun. İsmini de student.json verelim.

Buradaki verileri Hive’ı kullanarak tablo haline getirelim:
        
        
```sql
CREATE TABLE json_student_table ( json string );
 
LOAD DATA LOCAL INPATH  '/tmp/student.json' INTO TABLE json_student_table;

```

Biçimide bir sorgu query ile json dosyasının içeriğini json_student_table isimli bir tablo yaratıp aktarmış olduk.

Bu tablodaki her bir objeyi sorgulamak için Hive’da çeşitli yöntemler mevcut, bunlardan ilki olan get_json_object ile bir sorgu yazmayı deneyelim.

    
```sql
select  get_json_object(json_student_table.json, '$.name') as Name, 
        get_json_object(json_student_table.json, '$.surname') as Surname,
        get_json_object(json_student_table.json, '$.student_info.id') as Sid,
        get_json_object(json_student_table.json, '$.student_info.department') as Sdepartment,
        get_json_object(json_student_table.json, '$.student_info.class') as SClass
from json_table;

```

Bu sorgudan elde edilen sonuç şu şekildedir:
        
        Name   Surname  Sid     Sdepartment                 SClass
        Emre   Balıkçı  123     Bilgisayar Mühendisliği     4

Tıpkı get_json_object gibi json_tuple,json-servede gibi fonksiyonlarını kullanarakta sorgular yazabiliriz.
Bunları ileriki yazılarımda örnekleyerek açıklamaya çalışacağım.






