# PRISMACSI - TYPHOON WRITEUP 2
--------------------------------------------------

## PRISMACSI firmasının yayınladığı typhoon makinesini tomcat zafiyetini sömürerek ele geçirmemi anlatacağım.

### 1)İlk olarak yine nmap taramasıyla başlıyorum.Böylelikle tomcat'in versiyonunu ve port numarasını öğreniyorum.

![image](/tomcat/1.png)


### 2)8080 nolu porta gittiğimde karşıma böyle bir sayfa geldi.Buradan manager girişine yöneldim.

![image](/tomcat/2.png)


### 3)Manager olarak login olmak için istenilen username/password ikilisi için tomcat:tomcat olarak denedim ve başarılı olarak giriş yaptım.Ayrıca bu giriş için metasploitte bulunan <b>auxiliary/scanner/http/tomcat_mgr_login</b> modülünden de yararlanabiliriz.

![image](/tomcat/3.png)


![image](/tomcat/4.png)

### 4)Gerekli olan girdileri vererek modülümüzü çalıştırıyoruz ve login için denemeleri yapıyor 1 tane eşleşme gerçekleşiyor.

![image](/tomcat/5.png)


![image](/tomcat/6.png)

### 5)Elimizde gerekli olan username ve password bulunduğuna göre makineye giriş için yol arıyoruz.Bunun için ilk olarak metasploit üzerinde arama geerçekleştirdim ve işime yarayan exploiti buldum.

![image](/tomcat/7.png)

### 6)Exploiti ayarladıktan sonra gerekli bilgileri düzenledim ve açlıştırdım.Sonunda makine üzerinde bir oturum elde ettim.

![image](/tomcat/8.png)

### 7)Makineye girdikten sonra etrafa bakmaya başladım ve 2 tane flag elde ettim.

![image](/tomcat/9.png)


![image](/tomcat/10.png)

### 8)Şuan için başka bir yetki yükseltme yöntemi bulamadığım için yine kernel versiyonundan yararlanarak root yetkileri elde ettim.

![image](/tomcat/11.png)