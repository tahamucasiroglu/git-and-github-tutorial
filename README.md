
## git-and-github-tutorial
<br>Notları tuttuğum eğitim serisine [buradan](https://www.youtube.com/watch?v=rWG70T7fePg&list=PLPrHLaayVkhnNstGIzQcxxnj6VYvsHBHy) ulaşabilirsiniz.<br>

>Öncelikle git programını indirmek için [buradaki](https://git-scm.com/) adrese gidiniz.<br>
Siteden programı indirip kurduktan sonra ilk açılış için;<br>
`git config --global user.name "Taha Mücasiroğlu"`  yazınız. Burada ismimizi tanıtıyoruz. Sonrasında ise,<br>
`git config --global user.email "tahamucasiroglu@gmail.com"` Burada da mail adresimizi kaydediyoruz.<br>
burada mail adresinizin github hesabı ile aynı olması gerekmemektedir.<br>
Şimdi işlemler başarılı olup olmadığını anlamak için,<br>
`git config --global user.name` ve `git config --global user.email` yazarak geri dönen değerleri kontrol ediyoruz.<br>
---
### Başlangıçta bilinmesi gereken komutlar
|Komutlar|İşlevi|
|--------|------|
|pwd | Komutu bulunan adresi verir bize|
|ls | Bulunan yerdeki dosya ve klasörleri listeler|
|cd  | Gidilmek istenen yere götürür "cd Desktop" gibi|
|cd.. | Bir üst dizine gitmeye yarar|
|clear | Komut satırını temizlemeyi sağlar kısa yoldan ctrl+L ile de yapılabilir|
|mkdir| Klasör oluşturmayı sağlar|
|touch | Git üzerinden dosya oluşturur. örneğin touch dosya{1..5}.html dersek dosya1.html dosya2.html olarak 5 tane dosya açar proje oluşturma|
---
### Başlangıç
Öncelikle proje dosyasına gidilir `cd Desktop/git`<br>
proje dosyasına girdikten sonra ilk önce `git init` diyerek proje dosyamızı git programına uyumlu hale getiriyoruz.<br>
burada git gizli bir dosya oluşturdu bunu `ls` komutu ile göremeyiz ama `ls -a` yazarak .git klasörünü görebiliriz.<br>![Dosya yüklenemedi](https://raw.githubusercontent.com/tahamucasiroglu/git-and-github-tutorial/main/image/1.png)<br>
Şimdi içine örnek bir deneme.txt oluşturalım. Daha sonra bu dosyayı göndermek için `git add .` yazarız. Burada .(nokta) bize tüm projeyi gönder demek. Bu proje şuan ara bölgeye gitti. Bunu depoya tam olarak göndermek için `git commit -m "mesaj"` yazarız ve mesaj kısmına gönderim notunu yazarız.<br>![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/2.png)
<br>
daha sonra `git log` yazarak gönderi geçmişimizi görebiliriz.<br>![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/3.png)<br>

---

### Proje kontrolü

`git status` projede değişiklik olduğu zaman bu değişikliği gösterir. Değişiklik sizdeki dosya ile ortak depodaki dosya farklarını verir. Değişiklik olduğu zaman ise kırmızı
olarak değişik dosyaları bize söyler. Eğer `c\304\261kartma.py` böyle saçma bir dizin verirse türkçe karakter sıkıntısından kaynaklanması muhtemeldir. Türkçe karakter kullanılmaz. normali `cikartma.py` olmalıdır.<br>![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/4.png)<br>
<br>![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/5.png)<br>
Eğer elinizde değişiklik yapılan birden fazla dosya var fakat siz bunlardan birini göndermek isterseniz.
<br>
![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/6.png)
<br>
şimdi çıkartma dosyası ara yere taşındı ve yeşil olarak git status komutuna çıktı verdi.
<br>
![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/7.png)
<br>
Artık commit edilmeye hazır demek geçiş bölgesinden ana depoya atmak için `git commit -m" cikartma ekledim"` gibi yazarak ayarlayabiliriz.

---

### Projede değişiklik yapma

Projede commit edilen bir dosyayı yerel dosyada içini değiştirdiğimiz zaman  `" modified:   cikartma.py "`
<br>
![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/8.png)
<br>
şeklinde kırmızı bir uyarı verecektir. Bu dosyanın içeriğinin güncellendiğini ifade eder. Burada `git deff` yazarsak git bize değişiklik yapılan kısımları yeşil renkle ve başında + yazarak sunacaktır.
<br>
![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/9.png)
<br>
Daha sonra yeniden `git add .` ve `git commit -m "mesaj"` yazarak dosyayı güncelliyoruz. Eğer `git diff` yazılınca her hangi bir geri dönüş olmaz ise demekki değiştirilen dosya yok demektir. `git diff cikartma.py` dersek sadece o dosyayı kontrol edebiliriz demek. Ayrıca eklenen satırlarda + işareti ve yeşil renkte gösterildiği gibi çıkartılan satırlarda - işaretli ve kırmızı renkte gösterilir. `git diff --staged` dersek staged alanı ile git deposu arasındaki farklılıkları kotrol eder.
<br>
![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/10.png)
<br>

---
### Projeden dosya silme
#### Yöntem 1-)
Dosyayı yerel klasörden sildikten sonra `git status` deriz ve `git rm carpma.py` deriz. Son adım olarak bunu bildiricez. Bunuda `git commit -m "carpma.py silindi"` yazarız.
#### Yöntem 2-)
`git rm bolme.py` sonrasında `git commit -m "bölme silindi"` der ve bitiririz.<br>
Klasör silmek istersek `git rm -r silinecekler/` ile silinecekler klasörünün içindeki dosyaları sildik fakat klasör içinde klasör varsa klasörleri silmez. Dosyaları yinede siler.
---
### Projeden dosya taşıma ve isim değiştirme
Elle bu işlemi yapıp commit ederek yapılabilir. Silme 1. yöntem gibi, her şeyi komut satırından yapmak için `git mv main.py ana.py` yazarak main adını ana adında değiştirdik ve commit ederek bunu bildirdik.<br>![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/11.png)<br>

`git mv ana.py anadepo/depo` yazarak ana.py adlı dosyamızı aynı dizindeki anadepo klasörünün içindeki depo klasörüne taşıdık. Bu sayede taşıma işlemide yapılabilir.
---
### Değişiklikleri geri alma
`git restore -- metin.txt` dediğimiz zaman git deposundaki metin.txt yi bize geri yükler. Retore yerine önceden checkout kullanılıyordu fakat bu restore olarak güncellendi.
Eğer dosyanızı ara bölgeye gönderdikten sonra geri almak istediniz. Metin.txt adlı dosyayı `git add metin.txt` dedikten sonra bunu geri almak isterseniz `git reset HEAD metin.txt` yazarak ara bölgeden dosyayı alabilirsiniz.

---
### Versiyon değiştirme
`git log` kısmından alınan sarı renkli yer olan `"commit f537b42d7275fe508ed57e8f66d2c2046b5096be"` gibi olan kod kısmında uzun kodu alarak(hash kodu oluyor)
`git checkout f537b42d7275fe508ed57e8f66d2c2046b5096be  -- .` yazarız. Brada nokta bu versiyondaki her şeyi almak istediğimizi belirtiyor.<br>![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/12.png)<br>
---
### Github kullanımı
Repositories açtıktan sonra Repositories'nin linkini alıp.<br>![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/13.png)<br>
Git terminalini açarız. Daha sonra yüklemek istediğimiz projeye gideriz. `git remote add "gönderim mesajı" "gönderilecek link"` olarak yazarız.<br>![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/14.png)<br>
Sonra kontrol için `git remote` yazarız ve gönderim mesajı geri dönerse işlem tamam demektir.<br>![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/15.png)<br>
Simdi bunu Github'a yüklemek için `git push -u "gönderim mesajı" master` yazarak yükleme yapılır `-u` tüm dosyalar demek ve `master` projenin ana dalıdır.
Sonra git sizden kullanıcı adı ve şifre isteyecek bilgileri doğru girdikten sonra işlem tamamlanacaktır.

Eğer projenizde gözükmesini istemediğiniz önemli dosyalar varsa `.gitignore` kullanılabilir. Terminale `cat >> .gitignore` yazdıktan sonra bizden bir metin isteyecek ve buraya gönderilmesini istemediğiniz dosyaların isimlerini yazacaksınız(uzantısı ile beraber) yazıp enter dedikten sonra  ctrl+c ile geri terminale çıkacaksınız. Burada çıkmasını istemediğiniz dosyaları add veya commit demeden gitignore'a eklemeniz gerekmektedir.<br>
.gitignore dosyasını metin belgesi ile açarak içine komut yazabilirsiniz.<br>
` belgeler/*`  belgeler klasöründeki herşeyi `.gitignore'a` ekler.
`!belgeler/dosya1.html` ise üst satırdan tüm belgeler klasörünü ignore ettiğimiz için bize lazım olanı ayırmamızı sağlıyor yani bu iki satır sonunda belgeler klasörü tamamen dışlanacak sadece dosya1.html alınacak.
Burada `git status` dersek bize sadece belgeler/dosya1.html var diyecek
---
### Branch
Master ana dal branch ise dalın kopyasıdır. branch dal oluşturarak birden fazla kişi çalışmasında kolaylık sağlanır. Github proje kısmında master yazan yere tıkladıktan sonra arama yerine istediğiniz ismi yazıp enter dedikten sonra branch oluşturulacaktır.<br>![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/16.png)<br>
Eğer branchlar üzerinden Github'da değişiklikler olmuş ise ve bunları local bilgisayarınıza almak isterseniz `git pull` yazarak tüm projeyi kendiniz ile eşleştirebilirsiniz.

`git branch` yazarak mevcut dallar gösterilir. Github'daki branch'ları görmek için `git branch --all` yazarız.
`git branch kopya2` yazarak kopya2 adında localde bir tane yandal oluşturduk.
bu dala geçmek için ise `git checkout kopya2` yazarız. 
`git branch` yazarak olduğumuz dalı kontrol edebiliriz
Buradan sonra yapılacak değişikliklerde yandal etkilenecektir. Bunları birleştirmek istersek master dalına geri geçmemiz gerekir. `git checkout master` yazarız.
İkisi arasındaki farkı görmek için `git diff master kopya2` yazarak bu iki dal arasındaki farkı görebiliriz.
`git merge kopya2` diyerek zaten master da olduğumuz için kopya2 dalını master ile birleştirecektir.
Sonrasında `git push -u "gönderi mesajı" master` yazarak Github'a gönderebiliriz.
---
### Readme.md işlemleri
[https://docs.github.com/en/free-pro-team@latest/github/writing-on-github](Buraya) tıklayarak Github'ın kendi sitesindeki tutorial kısmına ulaşabilirsiniz.
<h1>
#en büyük başlık<br>
######en küçük başlık<br>
Burada # sayısı arttıkça size küçülür.<br></h1></h1>
<h1>**kalın yazı**</h1>   **kalın yazı**<br>
<h1>*italik yazı*</h1>    *italik yazı*<br><h1>
[buraya tıklayın](tıklanıınca açılacak link) bağlantı ekleme </h1>[google.com.tr](google)<h1> gibi <br></h1>
![hata durumunda mesaj](resim linki)<h1><br> 
</h1>

### Genel bilgiler
<br>![Dosya yüklenemedi](https://github.com/tahamucasiroglu/git-and-github-tutorial/blob/main/image/17.png)<br>
Birinin projesinde `watch` seçerseniz projedeki değişikliklerde bildirim alırsınız.<br>
`star` seçilirse hem beğendiğinizi hemde daha sonra bakmak için yer imi ekler.<br>
`fork` seçeneğinde projenin bir kopyasını kendinize eklemiş olursunuz.<br>
`issues` seçeneği projenizde herhangi sorunları belirtmek için kullanılır.<br>

`issuse` ve `fork` kısımlarını bu proje üzerinden deneyebilirsiz.









``
