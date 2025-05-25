KAGGLE LİNKLERİ
https://www.kaggle.com/code/erdemcarus/maas-tahmin-uygulamasii

#Bonus uygulama:
https://www.kaggle.com/code/erdemcarus/maas-tahmin-unsupervised


San Francisco Maaş Veri Seti Üzerinde Lineer Regresyon Modeli
Bu projede, San Francisco çalışanlarının maaş verileri kullanılarak bir makine öğrenmesi modeli geliştirilmiştir. Amaç, çalışanların toplam maaşlarını (Toplam Maaş ve Yan Haklar - TotalPayBenefits) çeşitli özelliklere dayanarak tahmin etmektir.

Kullanılan Veri ve Ön İşleme
Veri seti, San Francisco Şehri Çalışanlarının Maaş Bilgilerini içermektedir.

Ana sütunlar:

JobTitle (iş unvanı)

BasePay (temel maaş)

OvertimePay (mesai ücreti)

Benefits (yan haklar)

TotalPayBenefits (toplam maaş ve yan hakların toplamı, hedef değişken)

Eksik ve geçersiz (negatif veya sıfır) maaş değerleri temizlenmiştir.

Kategorik değişken olan JobTitle, one-hot encoding yöntemi ile sayısal verilere dönüştürülmüştür.

Model ve Öğrenme Yöntemi
Kullanılan model: Doğrusal Regresyon (Linear Regression)

Öğrenme tipi: Denetimli Öğrenme (Supervised Learning)

Amaç: Bağımsız değişkenlerden (BasePay, OvertimePay, Benefits, JobTitle kategorileri) bağımlı değişken olan TotalPayBenefits değerini tahmin etmek.

Model, eğitim verisi ile eğitilmiş ve test verisi üzerinde performansı ölçülmüştür.

Model Performansı ve Değerlendirme
Model performansı Root Mean Squared Error (RMSE) ve R-kare (R²) metriği ile değerlendirilmiştir.

Özellik ölçeklendirme (StandardScaler) uygulanmış, ancak model performansında anlamlı değişiklik olmamıştır.

Elde edilen sonuçlar:

RMSE ≈ 6732

R² ≈ 0.9894 (Model veri setindeki varyansın %98.94'ünü açıklayabilmektedir.)

Görselleştirmeler
Gerçek ve tahmin edilen toplam maaşların dağılımı karşılaştırılmıştır.

Yıllara göre ortalama toplam maaşların değişimi çizgi grafiği ile gösterilmiştir.

En yüksek ortalama maaşa sahip ilk 10 iş unvanı bar grafikte sunulmuştur.

Toplam maaş dağılımı histogram ile görselleştirilmiştir.

Model Kaydetme
Eğitilen model joblib kütüphanesi kullanılarak 'sf_salaries_model.pkl' dosyasına kaydedilmiştir.

Özet
Bu proje, doğrusal regresyon modeli kullanılarak San Francisco çalışanlarının maaşlarını tahmin etmeye odaklanmıştır. Veri ön işleme, kategorik değişkenlerin dönüştürülmesi ve model değerlendirme adımları detaylı bir şekilde gerçekleştirilmiş; sonuçlar yüksek doğrulukla tahmin yapıldığını göstermiştir.

Not: Veri setindeki bazı sütunlarda karışık veri tipleri ve eksik değerler bulunmakta olup, bunlar uygun şekilde temizlenmiştir.


Diğer uygulamam:Maas_Tahmin_Unsupervised

San Francisco Maaş Veri Seti Üzerinde K-Means Kümeleme Analizi
Bu projede, San Francisco çalışanlarının maaş verileri kullanılarak K-Means kümeleme algoritması uygulanmıştır. Amaç, çalışanları maaş ve diğer ilgili özelliklerine göre benzer gruplara ayırmaktır.

Veri ve Ön İşleme
Veri seti, San Francisco şehrine ait maaş bilgilerini içerir.

Eksik değerler özellikle BasePay, Benefits gibi alanlarda bulunmakta ve bu eksik değerler 0 ile doldurulmuştur.

Anlamsız veya analiz için gereksiz sütunlar (Id, EmployeeName, Notes, Agency, Status) çıkarılmıştır.

Kategorik değişkenler (JobTitle, Year) sayısal kodlara dönüştürülmüştür.

Sayısal olması gereken sütunlardaki metinsel veya hatalı değerler NaN yapılmış ve ardından doldurulmuştur.

Model için kullanılacak sütunlar:
JobTitle, BasePay, OvertimePay, OtherPay, Benefits, TotalPay, TotalPayBenefits, Year

Kümeleme Modeli: K-Means ve Unsupervised Learning
Bu proje denetimsiz öğrenme (unsupervised learning) yöntemleri kapsamında değerlendirilir. Çünkü elimizdeki verilerde herhangi bir hedef değişken (label) yoktur; yani önceden belirlenmiş doğru cevaplar veya sınıflar bulunmamaktadır.

K-Means algoritması, veriler arasındaki benzerliklere göre otomatik olarak kümeler oluşturur. Böylece, çalışanlar maaş, yan ödemeler ve diğer finansal özelliklere göre anlamlı gruplara ayrılır.

Veriler, StandardScaler ile standartlaştırılmıştır. Bu, değişkenlerin farklı ölçeklerden dolayı modelde baskın olmalarını engeller.

K-Means algoritması ile veriler 3 kümeye ayrılmış ve her veri noktasının hangi kümeye ait olduğu belirlenmiştir.

Sonuçlar, PCA (Principal Component Analysis) kullanılarak iki boyutta görselleştirilmiş ve kümelerin yapısı incelenmiştir.

Neden Unsupervised Learning?
Denetimsiz öğrenme, verilerde gizli kalıpları veya yapıları keşfetmek için kullanılır.

Bu analizde herhangi bir etiketli çıktı (örneğin, çalışanların hangi gruba ait olduğu gibi önceden tanımlanmış bilgiler) yoktur.

Kümeler, verilerin doğal yapısına göre oluşturulur ve bu sayede maaş gibi finansal özelliklere göre benzer profildeki çalışanlar gruplanır.

Denetimsiz öğrenme, yeni veri kümeleri üzerinde gizli yapıları anlamak ve segmentasyon yapmak için idealdir.

Sonuçlar ve Görselleştirme
Kümeler, PCA ile iki boyuta indirgenmiş ve görselleştirilmiştir.

Kümeler arasındaki farklılıklar ortalama maaş, yan ödeme gibi değerlerle ortaya konmuştur.

Bu kümeler iş analizi, insan kaynakları stratejileri veya maaş politikalarının iyileştirilmesi için kullanılabilir.

Özet
Bu projede, maaş ve yan haklar verileri kullanılarak denetimsiz öğrenme yöntemi olan K-Means ile çalışanlar arasında anlamlı segmentasyon yapılmıştır. Böylece farklı maaş gruplarını tanımlamak ve analiz etmek mümkün olmuştur.


