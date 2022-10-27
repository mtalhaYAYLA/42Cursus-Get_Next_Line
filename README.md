# 42Cursus-Get_Next_Line

🧜‍♀️Read:Daha önce bir dosyaya yazılmış verileri okur. Normal bir dosyanın dosyanın sonundan önce herhangi bir kısmı yazılmamışsa, read() 0 değerine sahip baytlar döndürecektir.

🧜‍♀️Static Char:Kullanıldığı yere bağlı olarak static
 anahtar sözcüğünün iki değişik anlamı vardır. Blok içinde, static
 kalıcı
 anlamına gelir. Yani, blok içinde değişkenlerin tanımlarının önüne static
 anahtar sözcüğü kullanılırsa, bu değişkenlerin değerleri blok sona erdiğinde yok olmazlar. Blok dışına çıkıldığında değişkenler erişilmez hale gelir, fakat blok tekrar işletilirse, blok sona erdiği zamanki değerleriyle programın yürütülmesine katılırlar.

🧜‍♀️BUFFER_SIZE**:Kaçar kaçar saymasını istiyorsam o kadar değer veririz.

👉char *get_next_line(int fd)

🧜‍♀️2 tane değişken tanımlıyoruz staticle tanımlamamızın sebebi içinde girdiğimiz baştaki değeri tutmamızı sağlamak.

🧜‍♀️Eğer dosyam yoksa ya da BUFFER_SIZE=Kaçar kaçar okumasını istediğim karakter sayım 0’dan küçükse direkt “0” döndür dedik çünkü dosyam yoksa veya arayacağım karakter sayısı “-”li bir değer olduğu durumda arayamam.

🧜‍♀️Dosyamı ve içindekileri *read_to_left_str’ye gönderdim.

👉char *ft_read_to_left_str(int fd, char *left_str)**

🧜‍♀️2 tane değişken tanımladım.

🧜‍♀️BUFFER_SIZE’nin 1’fazlası (”NULL” karakter) kadar “buff”ın içine malloc ile yer açtım.

🧜‍♀️Eğer yer tahsis edemediysem “NULL” döndürdüm.

🧜‍♀️rd_bytes’ı 1’e eşitledim.

🧜‍♀️left_str’in içinde ”\n” karakter görmediği durumlarda veya rd_bytes’ın 0’a eşit olmadığı durumlarda,

🧜‍♀️Read ile “BUFFER_SIZE” kadar okuyor buff’ın içine atıyor.rd_bytes’a da “BUFFER_SIZE” boyutunu atıyor.

=READ=
<img width="483" alt="Screen Shot 2022-03-02 at 4 54 50 PM" src="https://user-images.githubusercontent.com/97165826/156412685-0c7a569a-0c9a-439c-b660-06770c12de76.png">



🧜‍♀️Eğer “-1”e eşit olursa buff’ı freeleyip “NULL” döndürür.Sonrasında buff’ın sonuna “NULL” atar ve başta boş olan left_str’ye buff’ı atar.Buff’ bellekte yer kaplamaması için free’ler ve left_str’de yeni oluşan dizeyi döner.

 👉char *get_next_line(int fd)

🧜‍♀️Eğer left_str oluşmadıysa “NULL” döndürür.

🧜‍♀️left_str’mizi ft_get_line’ye gönderir.

👉char	*ft_get_line(char *left_str)**

🧜‍♀️2 tane değişken tanımlarız.

🧜‍♀️Sayacımızı 0’a eşitleriz.

🧜‍♀️Stringimiz “NULL”ı görene kadar sayacmızı arttıracağız.

🧜‍♀️Malloc ile str’nin içine i+2 kadar yani ilk satırdaki dizemizin 2 fazlası yani (“\n”+”\0”) kadar yer açıyoruz.

🧜‍♀️Yer tahsis edilemediyse “NULL” dönderiyoruz.

🧜‍♀️Sayacımız dizemizde “\n” görene kadar left_str’mizi tek tek str’nin içine atıyoruz.

🧜‍♀️Sonuna “\0” ekleyip dizemizi dönüyoruz.

👉char *get_next_line(int fd)

🧜‍♀️left_str’mizi ft_new_left_str’ye gönderiyoruz.

👉char	*ft_new_left_str(char *left_str)

🧜‍♀️3 tane değişken tanımlıyoruz. 

🧜‍♀️“i” sayacımızı 0’a eşitliyoruz.

🧜‍♀️“i” sayacımız dizemizde “\n” görene kadar sayacımızı arttırıyoruz.

🧜‍♀️Dönücek karakter olmadığı durumda dizeyi freeleyip “NULL” dönderiyor.

🧜‍♀️Malloc ile left_str’nin uzunluğu - sayacımın index’i +1 kadar str’de yer ayırıyor bu işlemle birlikte ilk satırda sayacım “\n”i görüp durduğu için çıkartarak ilk satırı almamış oluyoruz ve 1 fazlası kadarda “\0”a yer ayırmış oluyoruz.

🧜‍♀️Yer tahsis edilmediyse “NULL” dönderiyoruz.

🧜‍♀️Sonrasında sayacımızı arttırıyoruz.

🧜‍♀️j sayacımızı 0’a eşitliyoruz.

🧜‍♀️left_str dizemde karakerimin bulunduğu durumda

🧜‍♀️left_str dizemdeki karakterleri tek tek str’ye atıyorum aynı karakterlerin üst üste gelmemesi için str dizemin “j” sayacını da arttırıyorum.

🧜‍♀️Son index’e “\0” koyuyorum.

🧜‍♀️left_str dizemi serbest bırakıyorum.

🧜‍♀️Ve str’yi dönüyorum.
