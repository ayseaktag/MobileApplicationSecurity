# Mobil Uygulamaların Güvenlik Risk Seviyelerinin Karşılaştırılması

Günlük hayatta rutin olarak yapılan birçok işlem internet aracılığıyla, online bir biçimde
daha kısa sürede gerçekleştirilebilmektedir. Dijitalleşen dünyada internet kullanımının artması
ile mobil uygulamaların kullanımı da artmıştır. Mobil cihazlar, insan yaşamının kolaylaşması
için birçok avantaj sağlamaktadırlar. Mobil cihazlar; kolay taşınabilmeleri, bilgiye kolay
ulaşımın sağlamaları ve daha birçok sebeple, kullanıcılar tarafından tercih edilmektedirler.
Mobil uygulamaların geniş kitleler tarafından ulaşılabilir oluşu, içerisinde zafiyet
barındırmaları halinde bilgi güvenliğinin ihlaline sebep olabilmektedir. Bilgiye kolay
ulaşabilmek kadar bilginin güvenli taşınması konusu da oldukça önemlidir. Mobil
uygulamalara kayıt veya diğer işlemler için kullanıcılardan istenen kişisel bilgilerin kötü niyetli saldırganların eline geçmesi istenmeyen bir durumdur. Mobil uygulamaların güvenlik zafiyeti barındırması, bilgi güvenliğinin korunması açısından büyük risk oluşturmaktadır. Bilgi
güvenliğinin sağlanması ve kişisel veri ihlalinin yaşanmaması için mobil uygulama güvenliği
konusu önemli hale gelmektedir. 

Bu çalışmada; Android işletim sistemine sahip mobil uygulamaların mimarileri, mobil uygulamaların sınıflandırılması, Android güvenlik açığı analizi, mobil uygulama güvenliği konusundaki temel alanlar gibi birçok önemli konu hakkında bilgi verilmiştir. Verilen bilgiler desteklenmek üzere içerisinde zafiyet barındıran beş farklı mobil uygulama test edilmiştir. Test edilen mobil uygulamalar, mobil uygulama güvenliği konusunda çalışma yapan araştırmacı ve geliştiricilerin en çok kullandığı uygulamalar arasından seçilmiştir. Uygulamalar test edilip içerdikleri zafiyet oranları ve zafiyet türleri karşılaştırılmıştır. Çalışmanın sonunda bu zafiyetlerden korunmak için neler yapılabileceği konusunda tavsiyeler verilmiştir.

Elde edilen sonuçların bir kısmına aşağıdan ve detaylı bir şekilde proje raporundan erişebilirsiniz.

SONUÇ VE ÖNERİLER

![image](https://user-images.githubusercontent.com/85439997/182589907-5ab572c9-c630-4ec0-b475-8f88e338aabe.png)


Proje başlangıcında hedeflendiği şekilde, Android işletim sistemine sahip beş farklı uygulama statik,dinamik ve manuel biçimde test edilmiştir. Analiz sonuçları, araştırmanın ilgili bölümlerinde verilmiştir. Sonuçlara göre, bu beş uygulama arasında en yüksek risk seviyesine sahip uygulama “InsecureBankv2” uygulamasıdır. En az risk içeren uygulama ise, “Ovaa” uygulamasıdır. Uygulamaların OWASP TOP 10’a göre içerdikleri zafiyet çeşidi Tablo 12’de verilmiştir. Buna göre tüm uygulamaların ortak olarak barındırdıkları zafiyet “M2 Insecure Data Storage” zafiyetidir. Analiz edilen tüm uygulamalar, hassas verileri dışarıdan erişilebilecek şekilde harici
bellekte depolamaktadırlar. Bu zafiyet, kötü niyetli saldırganlar tarafından sömürülmektedir. Zafiyetin giderilebilmesi için, hassas veriler dahili depolamada tutulmalıdır. Uygulama veya kullanıcı dahili depolamaya erişememektedir. Kullanıcı uygulamayı sildiğinde dahili depolamadaki veriler de kaldırılmaktadır. Bir diğer yöntem de hizmetin dışarı aktarılıp aktarılmaması gerektiğinin belirlenmesidir. Eğer dışarı aktarılacaksa, uygulama izin dosyasında izinler ayarlanmalıdır. Eğer uygulama izin dosyasında bu değer “false” olarak ayarlanmadıysa varsayılan olarak dışarı aktarılma söz konusu olmaktadır. Bu sebeple, dışarı aktarım istenmiyorsa mutlaka “false” olacak şekilde ayarlanmalıdır. Analiz edilen uygulamalarda ortak olarak kullanılan MD5 algoritması yerine daha güçlü algoritmalar kullanılmalıdır. SHA-256, SHA-3 bu güçlü algoritmalara örnektir. İncelenen birçok uygulamada, AES/ECB/PKCS5 şifrelemesi kullanılmaktadır. Bu şifreleme güvensiz bir şifreleme türüdür. Kriptografik işlemler için ECB modu kullanılmamalıdır. ECB Modu yeribe CFB modu kullanılmalsı önerilmektedir. Mobil uygulama güvenlik analizi yapılırken kullanılan araçlardan oldukça memnun kalınmıştır. Tüm uygulamalar için, bu araçlar ile analiz gerçekleştirmenin oldukça kolay ve doğru sonuçlar verdiği görülmüştür. Manuel analiz, online araçlarla yapılan analizde bulunamayan zafiyetleri gözlemlemek için oldukça önemlidir. Online araçlarla sonuç elde edilmesi kadar kolay ve hızlı gerçekleşmese de doğru sonuçlara ve detaylara ulaşılabilmesi için gereklidir. Uygulamalar analiz edilirken kullanılan Kali Linux işletim sistemi, içerisinde birçok aracı bulundurması sebebiyle kolaylık sağlamıştır. Aynı zamanda Genymotion emulatörüyle de uyumlu olması işlemleri kolaylaştırmıştır. MobSF online analiz aracı da bir uygulama için birçok analizi aynı anda gerçekleştirme ve raporları çıktı alabilme özellikleri sayesinde sayesinde kullanım kolaylığı sağlamıştır. MobSF ile elde edilen sonuçlar, manuel analiz ile doğrulanmıştır. Bu sebeple araştırmacılara önerilmektedir. 




