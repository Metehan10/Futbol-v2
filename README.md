# Futbol-v2
Bu çalışma daha önce yapmış olduğum Futbol-Analiz adlı çalışmamın genişletilmiş versiyonudur.
---------------------------------------------------------------------------------------------
Datasetimde Avrupada bulunan 5 büyük ligten seçilmiş 3 farklı takımın, 3 farklı oyuncunun AD-UYRUK-BOY-MEVKI-OYNADIGI_TAKIM-OYNADIGI_LIG-KULLANILAN_AYAK-DOGUM_TARIHI-YAS-YAS_GRUP-OYNADIGI_MAC_SAYISI-GOL_SAYISI-ASIST_SAYISI	OYNADIGI_SURE-OYNAN_DOKSAN_DAKIKA_SAYISI-OYNANAN_DOKSAN_DAKIKA_BASINA_GOL-xG-2020_piyasa_değeri-2021_piyasa_değeri-2022_piyasa_değeri-2023_piyasa_değeri-EN_YUKSEK_PIYASA_DEGERI gibi 22 farklı değişkeni bulunmaktadır.
---------------------------------------------------------------------------------------------
Veriler https://www.transfermarkt.com.tr ve https://fbref.com/en sitelerinden alınmıştır. 
Lakin veriler daha sonra SQL ortamında düzenlenmiş ve değişkenlere eklemeler yapılmıştır. Ayrıca yine SQL ortamında birtakım analizler yapılmıştır.
---------------------------------------------------------------------------------------------
Dataset daha sonra Pythona aktarılmıştır. Burada 'OYNADIGI_MAC_SAYISI', 'GOL_SAYISI', 'ASIST_SAYISI','OYNADIGI_SURE','OYNAN_DOKSAN_DAKIKA_SAYISI','OYNANAN_DOKSAN_DAKIKA_BASINA_GOL','xG' değişkenlerinin arasındaki korelasyon değerlerine bakılmıştır."xG" ve "GOL_SAYISI" arasındaki korelasyon katsayısı 0.930245 olarak bulunmuştur. Bu değişkenler arasında en yüksek katsayıdır. Korelasyon katsayıları bulunan bu iki değişkenin Linear Regresyon algoritması yardımı ile makine öğrenmesi yapılmıştır. Train-Test split yapılmadan önce OLS Regresyon değerleri;

R-squared = 0.865
Adj. R-squared = 0.862

      coef	 std err	
const	1.2536	0.720	
xG	  1.0361	0.062	

değerleri bu şekildedir. Buna göre; söz konusu değişkenler arasındaki bağımsız değişkenin(Gol_Sayısı), bağımlı değişkeni(xG) 0.865(%86) düzeyinde açıkladığını göstermektedir. Bu oranın 1'e oldukça yakın olması modelin başarılı olduğunu vurgulamaktadır.
Ayrıca OLS Regresyon işlemi sonrasında oluşturulacak denklemde bu şekildedir. --> xG=1.25+GOL_SAYISI*1.04

•	Makine öğrenmesi yapılan modelin [15] değeri için tahmini [17.08501038] olmuştur. Gerçek verilerle karşılaştırıldığında modelimizin oldukça iyi iş çıkardığını söyleyebiliriz
-------------------------------------------------------------------------------------------------
Son olarakta verisetimizin oyuncu,takım,mevki,kullanılan_ayak ve lig bazlı grafik analizleri Power BI ortamında yapılmıştır.
