# clean-code
CLEAN CODE 

“First, solve the problem. Then write the code.” -John Johnson

 

Clean Code Nedir? 
Bjarne Stroustrup: Şık ve etkindir.
Grady Booch: Basit ve doğrudandır.
Michael Feathers: Dikkatli ve önem veren birisi tarafından yazılmış gibi görünür.
Ron Jeffries: Küçük, ifade gücü yüksek, basit ve tekrarsızdır.
Dave Thomas: Temiz kod, orijinal yazarı dışında başka developer
tarafından okunabilir ve geliştirilebilir. 
 
Bazılarımızın el yazısı güzel ve okunaklıdır. Gören herkes hayran olur ve benim aklıma güzel yazı dendiğinde asla okunamayan bir yazı gelmez. Bazılarımızın ki ise gelişigüzel hatta çoğu zaman karalamadan ibarettir. Bana göre güzel bir el yazısı yetenek değildir. Çoğu zaman ilkokuldayken nasıl öğrendiysek öyle de kalmıştır. Ama güzel yazmanın da kaideleri vardır. Bunlara uyarak sürekli pratik yaparsak hayran olunası bir el yazıya kavuşmuş oluruz. Hem ne demişler, pratik mükemmelleştirir. Şimdi de bir koda clean code diyebilmemiz için (tabi ki clean code kitabına göre) bazı adımlar üstünde duralım.


   

    1.İsimlendirme 
    2.Koşullar
    3.Döngüler 
    4.Fonksiyonlar 
    5.Yorum satırları

İSİMLENDİRME 
İsimlendirme, yazılım geliştirme için çok önemli bir noktadır. Anlamsız veya kısaltmalarla verilen isimler bir süre sonra kodun okunurluğunu azaltarak kodu anlayacak kişiye zaman maliyeti olarak dönecektir. Aynı şekilde anlamlı ve doğru verilen isimler yazılımcının işini inanılmaz derecede kolaylaştırabilir. Hem geliştirici tekrar koda döndüğünde kolayca okuyabilir hem de başka geliştiriciler daha iyi anlayabilir ve okuyabilir. Özellikle telaffuz edilebilir isimler kullanmalı, aranabilir isimlere öncelik vermeliyiz.

 

Mesela burada s neyi ifade ediyor? Yorum satırı eklemeseydik nasıl anlayabilirdik? Ancak birebir kodu biz yazdığımızda bilebiliriz. Ama biz de uzun süre sonra tekrar koda bakarsak gerçekten hatırlayabilir miyiz? Bence hatırlamak yeterince zor olacaktır. Hele ki başka biri için bu kod neredeyse işkence olacaktır. Ve yazdığımız kod kendi kendini imha edecektir.

 

Şimdi ise bu koda bakalım. İlk bakışta ne yapılmak istenmiş hemen bilinebilir. Öyle ki hiç kod yazmamış biri bile anlayabilir. Ve bu kodun yorum satırına ihtiyacı yoktur. Neden yorum satırı kullanarak kendimizi açıklamak yerine bu işi kodlarımıza bırakmıyoruz ki? Yorum satırlarına harcayacağımız vakti neden kodlarımıza harcamıyoruz? 






Birkaç kod karşılaştırmasına bakacak olursak;

 
Bu kod gerçekten anlaşılır mı? Bir liste oluşturulmuş ama listenin neye ait olduğu belli değil. Ayrıca kodun amacı da belirsiz. Yani liste niçin oluşturulmuş, ne isteniyor, bir if yapısı var, if yapısı neyi sorgulayacak, bu soruların hiçbirine cevap alamıyoruz bu kodu okuduğumuzda.

 

Bu kodu okuduğumuzda ise oluşturulan listenin öğrencilerin notlarına ait olduğunu görüyoruz ve if yapısının geçme notunu sorgulayacağını öğrenmiş oluyoruz. Gerçekten de koddan koda fark var. Yüz kişiye sorsak yüzü de ikinci kodu seçer. Kimse karışık kodlarla boğuşmayı tercih etmez. Zaman hızlı akıyor. Teknoloji dünyası ise daha iyisi varken asla zaman kaybedeceği bir işi kabul etmez.
 
KOŞULLAR
Kod yazarken koşullar ayağımıza takılan küçük taşlar gibidir. Koşullar olmasa daha düz bir yolda daha rahat yürüyebilirdik. Ama eğer ki ayağımıza takılan bu küçük taşları kod yazarken büyük ve karmaşık taşlar haline getirirsek o zaman işte hiç yürüyemez oluruz. Neler yapabiliriz? Öncelikle koşullarımız, döngülerimiz olabildiğince doğal olmalı. Olumsuz koşullardan başlamak yerine her zaman pozitif olanla başlamak daha iyi olacaktır.

          

Mesela aşağıdaki if yapılarından hangisi insan diline daha yakın? Tabi ki ilki. Çünkü biz de normalde konuşurken “yaşımız 18’den büyüktür” deriz. Kimse “18 yaşımızdan küçüktür” demez.
            if (age>18)       vs          if (18<age)

İç içe if yapılarını ya da boolean operatörlerini kullanırken mantık sırasını gözetmek gerekir.
• VEYA kullanımında koşulun ilk kısmı DOĞRU (true) ise koşulun
tamamı DOĞRU olacağı için koşulun ikinci kısmı değerlendirilmez.
• VE kullanımında koşulun ilk kısmı YANLIŞ (false) ise koşulun tamamı
YANLIŞ olacağı için koşulun ikinci kısmı değerlendirilmez.
• Örnek: if ((a>b) && (a<c)) eğer (a>b) YANLIŞ ise (a<c)
değerlendirilmez.
• Örnek: if ((a>b) || (a<c)) eğer (a>b) DOĞRU ise (a<c)
değerlendirilmez.


DÖNGÜLER
Genel olarak döngü yapısını kullanırken do-while döngüsü tercih edilmez. Çünkü do/while döngüsünde kod satırı koşula göre çalıştırılabilir de, çalıştırılmayabilir de. Bu kafa karıştırıcı bir durumdur. Do-while yerine sadece while döngüsünü tercih etmek kod okunabilirliğini arttıracaktır. 

FONKSİYONLAR
Fonksiyonlarda ise kod tekrarından kurtulmak, fonksiyon parçalarını olabildiğince küçük tutmak, her fonksiyon yalnızca tek bir işlevi gerçekleştirmeli ve kodu yazan kodu okuyanda o fonksiyonu tek bir amaç için çağırmalıdır. Bu da fonksiyonun adından anlaşılmalıdır. Yani fonksiyon tek bir şeyi yapmalı ve o şeyi de iyi yapmalıdır. Fonksiyonu isimlendirirken daha açıklayıcı isimler kullanmak zihninizde daha somut verilerin şekillenmesine yardımcı olacak hem de onu daha kolay geliştirmenize yardımcı olacaktır.

YORUM SATIRLARI
İyi yazılmış bir yorum satırı okuyucu için çok faydalı olabilecek iken kötü ve düşünülmeden yazılmış yorum satırları kodu bir çöplük haline getirebilir. Yani yorum satırlarını kodlarımızı açıklamak için yazacakken onu da açıklamaya ihtiyaç duymamalıyız. Zaten yorum satırı yazmamızın en büyük nedeni kötü kod yazdığımızın farkında olmamızdır. Kötü kod yazdığının bile farkında olmadan yorum satırlarını daha da kötü yazmamalıyız. Bu durum içinden çıkılmaz bir durum hatta paradoks halini alabilir. Daha önce de söylediğim gibi yorum satırları altına gizlenmektense kodlarımızı daha da iyi hale getirebiliriz.
  int i=1; //sets i 1
Mesela bu yorum gereksiz bir yorum. Uzun lafın kısası yorum satırlarından özellikle gereksiz yorum satırlarından kaçınmalıyız.

if (isActive==2) // be sure that is active                böyle bir yorum satırı mı 
if (isActive == Status.Active)                 yoksa yoruma ihtiyaç duymayan bir kod mu

 
 
Bu koda bakacak olursak ilk bakışta anlamak gerçekten zor. Buna sebep olan ilk şey ise aralıksız ve düzensiz yazılmış olması. Bana göre bu zaten okunamayan kodu daha da okunamaz hale getirir. Kod parçalarını belli aralıklarla, girinti ve çıkıntılarına dikkat ederek yazmalıyız. İsimlendirmeye bakacak olursak okunanSayi ismi anlaşılır ama digerSayi ile ne ifade edilmek istenmiş belirsiz. İf, else, while yapıları ise birbirine girmiş durumda. Öncelikle if parantezlerini alt alta yazmak daha temiz ve anlaşılır bir görünüm sağlar. Bir başka hata ise gereksiz yorum satırları olmuş. Ve bu kalabalık görüntü clean code açısından hiç de olumlu bir durum değil.

