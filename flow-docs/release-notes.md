---
title: Sürüm notları | Microsoft Docs
description: Microsoft Flow sürümlerindeki yaygın sorunlar ve yenilikler
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/31/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6c414538c31aa17ed5ab6ba1498812576a8024ae
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548862"
---
# <a name="release-notes"></a>Sürüm notları
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="top-questions"></a>En çok sorulan sorular
1. Akışım başarısız oldu. Nasıl yaparım? düzeltilsin mi?
   
   1. Hatayı tespit edin. Web portalının üst kısmındaki bildirimler simgesine giderek veya mobil uygulamadaki **etkinlik** sekmesini seçerek başlayın. Akışınızı orada görmeniz gerekir ve bunu seçebilirsiniz.
   2. Artık akış ayrıntılarına bakıyorsunuz. Kırmızı ünlem simgesiyle adımı bulun ve akışlarınızın hata mesajını oraya görmeniz gerekir.
   3. Hata iletisine bağlı olarak, akışı **düzenleyip** çözebilmelisiniz. [Yaygın akış başarısızlıklarını çözme hakkında daha fazla bilgi edinin](fix-flow-failures.md).
2. Nasıl yaparım? gelişmiş bir koşul mı yoksa ifade mi kullanıyorsunuz?
   
   * [Koşulları ekleme](add-condition.md)hakkında bilgi edinin.
   * Akışta birden çok durum istiyorsanız, mevcut bir koşulun içinden **Koşul Ekle** ' yi seçin.
   * [Logic Apps bir işleve](https://docs.microsoft.com/rest/api/logic/definition-language)başvurarak gelişmiş bir ifade oluşturun.
3. Lisanslama Office 365 ile nasıl çalışır?
   
   * Office 365 kullanıcısı kullanıyorsanız, Office 365 için Microsoft Flow plan aracılığıyla tam erişim edinirsiniz. Daha fazla bilgi için bkz. [Microsoft Flow için fiyatlandırma planları](https://flow.microsoft.com/pricing/) .
   * Yöneticiyseniz, Office 365 dahil olmak üzere [Microsoft Flow için lisanslama](organization-q-and-a.md)hakkında bilgi bölümüne bakın.

## <a name="known-issues"></a>Bilinen sorunlar
1. Sitelerimde SharePoint listeleri ve *özel liste* türünde olmayan, desteklenmez. Bu sorunu geçici olarak çözmek için, standart bir SharePoint sitesinde özel bir liste oluşturun.
2. Dosya Tetikleyicileri, seçtiğiniz klasörün içinde iç içe geçmiş klasörlerin içine eklenmekte olan dosyalar için başlatılmıyor.

## <a name="whats-new"></a>Yenilikler

> [!IMPORTANT]
>
> **Sürüm notları duyurusu**
>
> Microsoft Flow ' de yaklaşan ve son yayınlanan özellikleri merak ediyor musunuz?
>[Ekim 2018 sürüm notlarını görüntüleyin](https://docs.microsoft.com/business-applications-release-notes/October18/microsoft-flow/). Planlama için kullanabileceğiniz tüm ayrıntıları, uçtan uca, yukarıdan aşağıya yakaladık. Daha fazla ayrıntı için, içerdiği özellikler ve geliştirmelerle [her haftalık sürümü](https://docs.microsoft.com/business-applications-release-notes/powerplatform/released-versions/flow) gözden geçirin.
>
> Ekim 2018 sürümünden önceki sürüm notları ileride başvurmak üzere burada kalır, ancak tüm yeni sürümler bu sayfada değil yukarıdaki konumlara dahil edilir.

### <a name="release-2018-09-24"></a>Sürüm 2018-09-24

- **Yardım ve destek Için yönetici erişimi** -Power platformu yönetim merkezinde Microsoft Flow için destek biletlerini açın ve iş akışı arızasından ilgili ek ayrıntılar sağlayın.
- Yeniden **tasarlanan akış topluluğu** -daha kolay bir şekilde akış topluluğu.
- **Microsoft ekipleri Bağlayıcısı** Ile ilgili geliştirmeler-bir kanalda yeni iletiler olduğunda bir akış çalıştırabilmeniz Için Microsoft ekipleri için yeni tetikler.
- **Daha fazla SharePoint eylemi** -SharePoint bağlayıcısında dosyaları ve daha fazlasını taşımaya yönelik yeni eylemler vardır.
- **Yeni yönetici analiz raporları** -Iş uygulaması platformu yönetim merkezine ortam ve kiracı genelinde analiz eklendi.
- **Power Query tümleştirme** -karmalar Power Query bir deneyim inşa edilecek ve bu, mekanizmalarının veri SQL Server.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/support-tickets-teams-sharepoint/) bu sürüm hakkında soru sorun.

### <a name="release-2018-08-31"></a>Sürüm 2018-08-31

- **Örnek veri kullanarak akışınızı test edin** -Microsoft Flow tasarımcı içinden oluştururken akışınızı test etmek için bağlayıcılardan örnek verileri kullanın. Akışınızı örnek verilerle test ettiğinizde, akışın üretime dağıtıldığında beklendiği gibi çalışacağını onaylamanız gerekir.
- **Beş yeni bağlayıcı** -dört yeni yönetim Bağlayıcısı ekledik: uygulama üreticileri Için PowerApps, yöneticiler için Power platformu, Yöneticiler Için PowerApps, yöneticiler için Microsoft Flow ve Microsoft okul veri eşitleme.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/test-data-management-connectors/) bu sürüm hakkında soru sorun.

### <a name="release-2018-08-24"></a>Sürüm 2018-08-24

- **Yeni Takvim eşitleme şablonları** -Google Takvim ve Office 365 veya Outlook.com arasında olayları kopyalayasağlayan yeni takvim şablonları.
- SharePoint **Için çoklu değer desteği** -SharePoint 'te seçim, kişi veya arama türü olan birden çok değerli alanlar için okuma ve yazma.
- **Kuruluşunuzdaki diğer kullanıcıların adına onay gönderin** -kuruluşunuzdaki diğer kullanıcılar adına onay gönderin; Örneğin, dosyayı, akışı oluşturan kişi yerine SharePoint listesinde karşıya yükleyen kişi.
- **Daha fazla düğme giriş türü** -düğme iki yeni giriş türüne sahiptir: numara ve Evet/Hayır.
- **Bağlayıcı güncelleştirmeleri** -yeni bir NetDocuments Bağlayıcısı, Azure bağlayıcılarına yönelik geliştirmeler ve daha fazlası.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/button-types-more/) bu sürüm hakkında soru sorun.

### <a name="release-2018-08-02"></a>Sürüm 2018-08-02

Microsoft Flow Preview programı, yaklaşan işlevlere ve Microsoft Flow yönelik güncelleştirmelere erken erişim sağlamanın yoludur. En yeni özelliklere erken erişim sağlamak için Önizleme bölgesinde bir ortam oluşturmanız ve daha sonra kullanmanız yeterlidir.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/flow-preview-program/) bu sürüm hakkında soru sorun.

### <a name="release-2018-07-23"></a>Sürüm 2018-07-23

- **Excel 'den akış oluşturma ve çalıştırma** -yeni **akış** düğmesi (şeridin **veri** sekmesinden erişilir) ile, Excel 'deki tablo verilerinizde Microsoft Flow için tahmin oluşturabilir ve tetikleyebilirsiniz. Veri işlemeyi veya verilerin kopyalanmasını/içeri aktarılmasını otomatikleştirin.
- **İş süreci akışı oluşturma** -iş süreci akışı, Common Data Service göre yeni bir durum bilgisi olan insan etkileşimli akış türüdür. Kullanıcıların takip etmek için bir dizi aşama ve adım tanımlamak üzere bu yeni akışları kullanın. Gerektiğinde ileri ve geri hareket edebilirler.
- **Outlook Web App 'Te Microsoft to-do için bir akış oluşturun** : \@birisi Outlook Web App 'te bahsedildiğinde, akış oluşturmak için bir kısayol görürler. Bu akış, e-postanın içeriğine bağlı olarak, Microsoft tarafından yapılacak \@söz konusu kişiye ait görevleri otomatik olarak oluşturur.
- **SharePoint görünüm desteği** -SharePoint Bağlayıcısı artık Tetikleyiciler ve eylemler üzerinde belirli bir SharePoint görünümünü seçmeyi desteklemektedir. Bu, sütunları yalnızca seçili görünümdeki alanlara göre filtreler.
- **Dört yeni bağlayıcı** -Azure IoT Central eklendi-hizmet olarak ölçeklendirilebilir IoT yazılım (SaaS) çözümü-anket 123, LMS365 ve Projectwıse tasarım tümleştirmesi.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/excel-bpf-todo-and-more/) bu sürüm hakkında soru sorun.

### <a name="release-2018-06-29"></a>Sürüm 2018-06-29

- **SharePoint 'te yerleşik olan oturum açma akışı isteği** -SharePoint 'te bir dosya veya öğe seçtiğinizde, **oturum açma akışı Için** yeni bir istek görürsünüz. Bu akış herhangi bir yapılandırma veya kurulum gerektirmez ve tek bir tıklama ile bir oturum açma isteği gönderir.
- **İki yeni bağlayıcı** -Cloud Connect Studio ve PoliteMail eklendi.
- **Geçmiş ve oluşturma sayfası geliştirmeleri** -çalışma geçmişi listesini, tam çalışma süreleri ve yeni bir gözden geçirme videosu ekleyerek Oluştur sayfası dahil ederek yenileiyoruz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/request-sign-off-four-connectors/) bu sürüm hakkında soru sorun.

### <a name="release-2018-06-08"></a>Sürüm 2018-06-08

- **PowerShell cmdlet 'leri** -hem akış üreticileri hem de kiracı yöneticileri, artık akışları program aracılığıyla yönetmek için PowerShell kullanabilir.
- **Takımlar Flow bot 'Ta geliştirmeler** -Microsoft ekiplerindeki akış bot, akış düğmeleri çalıştırabilir ve akışlarınızı tanımlayabilir.
- **Üç yeni bağlayıcı** -Marketo, ElasticOCR ve dynamicsignal için destek eklendi. 
- **Ek paylaşım bilgileri** -diğer kişilerin hangi izinlerin alacağını tam olarak öğrendiğinizde, veya paylaşılan akışlar çalıştırdığınızda ek bilgiler eklenmiştir.
- **SharePoint URL 'Leri otomatik olarak kırpma** -tarayıcıda bir SharePoint URL 'sini kopyalayıp yapıştırdığınızda sitenin ötesinde ek metin bulunabilir. bu metin, yalnızca siteye bağlanabilmeniz için otomatik olarak kaldırılır.
- **GDPR isteklerle Ilgili belgeler** -kurumsal kuruluşların veri sahibi hakları isteklerini işlemesini sağlayan kapsamlı bir kılavuz ve araç takımı oluşturduk.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/powershell-flow-bot-marketo/) bu sürüm hakkında soru sorun.

### <a name="release-2018-05-21"></a>Sürüm 2018-05-21

- " **SharePoint listelerine ve kitaplıklarına ait" akışlar** , SharePoint listeleri ve kitaplıkları ile çalışan akışlar bu listeler veya kitaplıklarla paylaşılabilir. Bu nedenle, bireyler veya gruplarla paylaşılmak yerine, listeye erişimi olan herkese paylaşılır. Kullanıcılar liste veya kitaplıktan eklendiğinde veya kaldırıldığında üyelik otomatik olarak değişir.
- **Hata ayrıntıları Analizi** -bir akış içinde gerçekleşen tüm hatalar hakkında bilgi sağlayan yeni bir katıştırılmış rapor.
- **Akışları office 365 gruplarıyla paylaşma** -bir Office 365 modern grubunu bir akışın sahibi yapabilir ve gruptaki kişilerin akışı çalıştırabilmesi için Office 365 gruplarıyla düğme akışlarını paylaşabilirsiniz.
- **SharePoint bağlayıcı geliştirmeleri** -Iki yeni SharePoint bağlayıcı özelliği vardır: öğeler veya Dosyalar silindiğinde ve SharePoint REST API desteklediği HERHANGI bir HTTP uç noktasını çağırmak için akışları tetikler.
- **İki yeni bağlayıcı** -Azure Data Factory ve mailparser desteği eklendi

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/share-with-sharepoint-office-365/) bu sürüm hakkında soru sorun.

### <a name="release-2018-05-01"></a>Sürüm 2018-05-01

- **Onay Iletilerinde zengin metin** -göndereceğiniz onay ayrıntılarını biçimlendirmek Için markaşağı kullanın.
- **Birden çok seçim girişi olan düğmeler** -tek seferde birden fazla değer toplamak için birden çok seçim listesi kullanan akış düğmeleri oluşturun.
- **Daha geniş akışlarla çalışma** -Microsoft Flow Mobile App artık yatay görünümü destekliyor ve Web Tasarımcısı yatay bir kaydırma çubuğuna sahip.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/rich-approvals-text-and-multiselect/) bu sürüm hakkında soru sorun.

### <a name="release-2018-04-12"></a>Sürüm 2018-04-12

- PowerApps ile oluşturulmuş bir uygulamadan çağrılabilen ve verileri uygulamaya geri döndüren **bir akış oluşturma akışından verileri PowerApps 'e döndürün** . Uygulamalarınız için ihtiyacınız olan mantığı oluşturmak için görsel sürükle ve bırak akış tasarımcısını kullanın. 
- **Dizi girdilerine birden çok kayıt ekleme** -bir e-postaya birden çok ek eklemek için kullanılabilecek Microsoft Flow bir liste Oluşturucu eklediniz.
- **Önceki çalışma verileriyle test akışları** -yeni bir test akışı düğmesi eklediniz ve bu, akışınızı önceki akış çalıştırmalarının tetiklemesi ile test etmenizi sağlar.
- **Yeni iş akışı () alanları** -artık, iş akışı () ifadesiyle ortam adına ve akış görünen adına erişebilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/return-data-to-powerapps/) bu sürüm hakkında soru sorun.

### <a name="release-2018-04-04"></a>Sürüm 2018-04-04

- **Common Data Service onayları** -modern onaylar, Common Data Service en son sürümü üzerine kurulmuştur. Bu, Common Data Service Bağlayıcısı ile gönderme veya alma yaptığınız onayların durumunu okuyan akışlar oluşturabileceğiniz anlamına gelir.
- **Her birine** , döngüde yüzlerce öğe olsa bile akış çalışma görünümündeki Döngülerde bulunan hatalara doğrudan atlayın.
- **Onayları yeniden atama** -kuruluşunuzdaki başka bir kişiye, onlara onay vermek için sahip olduğunuz herhangi bir onayı atayabilirsiniz. 
- **Oda listeleri** -Office 365 Outlook Bağlayıcısı, kuruluşunuzda yer alan verileri almak için Eylemler ekledi.
- **Akış düğmelerinin ayrıntılarına bakın** -sizinle paylaşılan bir akışı çalıştırdığınızda, artık akışın kullandığı tüm eylemleri görebilirsiniz.
- **Birleşik Krallık bölgesi** -ortamları Birleşik Krallık 'ta depolamak için artık ortamlar oluşturulabilir.
- **İki yeni bağlayıcı** -Atbot Yöneticisi ve pazarlama Içerik hub 'ı için destek eklendi.
- **Yeni belge giriş sayfası** -belgeler giriş sayfası, kim, bir ara Kullanıcı veya uzman, sizin tarafınızdan gruplanmış içeriğe sahip olacak şekilde güncelleştirildi. 

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/) bu sürüm hakkında soru sorun.

### <a name="release-2018-03-13"></a>Sürüm 2018-03-13

- **Onay geçmişi** -gönderdiğiniz tüm onay isteklerine yanıtlar, gönderilen yorumlar ve tam olarak gerçekleştikleri zaman dahil olmak üzere.
- **Dört yeni bağlayıcı** -Excel Online (iş), Excel Online (OneDrive), Azure SQL veri ambarı ve Iş kolu Bowes vergi Hesaplayıcısı eklendi.
- **Dinamik içerik araç ipuçları** -tüm eylemlerin içinden geldiğini görmek için dinamik içeriğin üzerine gelin ve tam ifade düzenleyicisini açmadan önizleme ifadeleri.
- **Eşzamanlılık denetimi** -belirli bir akışa tek seferde yalnızca bir çalıştırma sağlamak için eşzamanlılık denetimini etkinleştirin.
- **Üstel yeniden deneme** -zaman içinde zaman içinde çok daha fazla boşluk alan yeni bir yeniden deneme ilkesi türü.
- **Erişilebilirlik uygunluğu** -Microsoft Flow erişilebilirlik standartlarını nasıl karşıladığını betimleyen yeni uyumluluk belgeleri yayınlandı.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/approval-history-accessibility/) bu sürüm hakkında soru sorun.

### <a name="release-2018-02-09"></a>Sürüm 2018-02-09

- **Ağ geçidi yüksek kullanılabilirlik** -tek makineler çalışırken bağlantıları yukarı tutmaya devam etmek için, şirket içi veri ağ geçitlerinin yüksek düzeyde kullanılabilir kümelerini oluşturun.
- Her bir döngüyle birlikte tek bir çalıştırma ve 50 eylemlerinde en fazla 100.000 öğeye kadar olan her bir akış planı 1 veya Flow plan 2 işlemi **Için Iyileştirilmiş uygulama geliştirilmiştir** . 

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) bu sürüm hakkında soru sorun.

### <a name="release-2018-01-29"></a>Sürüm 2018-01-29

- **Microsoft ekiplerinin içinde** , ekiplerden akış oluşturup bunları yönetebilir, aldığınız ve gönderilen onayları inceleyebilir ve doğrudan takımlar masaüstü uygulamasında veya Teams.Microsoft.com üzerinde akışları başlatabilirsiniz. [buradan daha fazla bilgi edinebilirsiniz](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Paylaşılan düzenleme bildirimleri** -her bir akış ortak çalışan tarafından değiştirildiğinde, hangi akışın değiştiğini bildiren bir e-posta bildirimi alırsınız.
- **Yeni ifadeler** : biri URL 'leri ayrıştırmaya, DIĞERI de JSON nesneleriyle çalışacak şekilde iki yeni ifade kümesi eklendi.
- **Üç yeni bağlayıcı** -bu hafta, Iki yeni pınsersaıl Bağlayıcısı vardır: PıNSERSAıL SP ve Pınsersaıl Forms ve Kintone 'a yeni bir bağlayıcı.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) bu sürüm hakkında soru sorun.

### <a name="release-2018-01-17"></a>Sürüm 2018-01-17

- **Office 365 profil bilgileri** -Kullanıcı profilleri ve fotoğraflarla çalışan Office 365 kullanıcıları bağlayıcısına yeni eylemler ekledik.
- **Dize değişkenlerine ekleme** -tabloları veya diğer listeleri oluşturmak için döngülerin içindeki dizelere ekleyebilirsiniz.
- **İnfobıp Bağlayıcısı** -infobıp, sesli çağrılar ve gelen SMS üzerinde tetikleme dahil olmak üzere kurumsal düzeyde iletişim sağlayan bir hizmettir.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/o365-profile-infobip/) bu sürüm hakkında soru sorun.

### <a name="release-2017-12-20"></a>Sürüm 2017-12-20

Microsoft Flow Analytics artık tüm Microsoft Flow bölgelerde kullanılabilir, yani ortamınızda çalışan akışların sistem durumu hakkında daha fazla bilgi edinebilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) bu sürüm hakkında soru sorun.


### <a name="release-2017-12-14"></a>Sürüm 2017-12-14

- **Outlook Bağlayıcısı geliştirmeleri** -bir e-postayı ". eml" dosyası olarak kaydedebilir, takvim davetlerini otomatik olarak yanıtlayabilir ve bir e-posta iş parçacığında bahsedildiğinde akışları tetikleyebilirsiniz.
- **Bağlantı geliştirmeleri** -en son kullanılan bağlantılarınızı anımsar Microsoft Flow ve yeni eklenen tüm bağlayıcıları gösterir.
- **Beş yeni bağlayıcı** -Azure Container Instances, Azure kusto, Metatask, Microsoft yapılacak do ve Ptik SAIL belgeleri eklendi.
- **Http geliştirmeleri** -http eylemi artık öbekli kodlamayı destekliyor.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/outlook-connector-more/) bu sürüm hakkında soru sorun.

### <a name="release-2017-12-05"></a>Sürüm 2017-12-05

Microsoft Flow başlatma paneli artık tüm bölgelerde kullanılabilir. Bu panel, SharePoint listenizin veya belge kitaplığınızın içinde çalıştırdığınızda bir akışa değer eklemenize olanak tanır.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) bu sürüm hakkında soru sorun.


### <a name="release-2017-11-28"></a>Sürüm 2017-11-28

- **Yönetilen meta veriler** -SharePoint 'Te yönetilen meta verileri (aka) kullanan sütunları okuyun ve üzerine yazın. Taksonomi) türü.
- **Dizilere Ekle** -yeni bir dizi değişkeni Ekle eylemini kullanarak dizilerin sonuna öğe ekleyin.
- **Tago** -bağlama analizi kullanarak daha akıllı kararları vermek için dış verileri olan elektronik cihazların kolay bir şekilde bağlantısını sağlayan yeni bir Tago Bağlayıcısı.
- **IPhone x** -iPhone x üzerinde tam ekran kullanan ve resim yüklemeleri için bir hız geliştirmesi olan Microsoft Flow uygulamasının yeni bir sürümü.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/managed-metadata-tago/) bu sürüm hakkında soru sorun.

### <a name="release-2017-11-09"></a>Sürüm 2017-11-09

- **OneDrive iş tümleştirmesi** - [artık OneDrive iş içinde](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) seçili dosya veya klasörlerde akış oluşturabileceğiniz veya tetikleyemeyen bir akış düğmesi vardır.
- **Planner Tetikleyicileri** -yeni bir görev oluşturulduğunda, size bir görev atandığında veya bir görev tamamlandığında akışları başlatın.
- **SharePoint ekleri** -SharePoint liste öğelerinde eklerle çalışma: ekleri listeleme, indirme, ekleme veya silme.
- **Flow yönetimi Bağlayıcısı** -ortamınızdaki diğer akışların yönetimini otomatikleştiren akışlar oluşturun (örneğin, akışlara otomatik olarak izin ekleyin).
- **Dört yeni bağlayıcı** -Azure özel görüntü işleme hizmeti, D & B Idealleştirici, Enadoc ve Derdak sıgnl4 eklendi. 
- **Diğer bağlayıcı eylemleri** -SQL sorguları çalıştırın, daha hızlı e-posta Tetikleyicileri alın, Azure AD ile http ile herhangi bir yöntemi kullanın ve daha fazlasını yapın.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) bu sürüm hakkında soru sorun.

### <a name="release-2017-11-02"></a>Sürüm 2017-11-02

- **Denetim günlüğü** -Microsoft Flow denetim olayları artık tüm kiracılar için Office 365 güvenlik ve Uyumluluk Merkezi kullanılabilir.
- **Akış pencere öğesi düzeltmeleri** -akış mobil uygulamasında, düğmelerin pencere öğesinde yüklenmelerine neden olan bir sorun düzeltildi.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/security-and-compliance-center/) bu sürüm hakkında soru sorun.

### <a name="release-2017-10-19"></a>Sürüm 2017-10-19

- **Her birine yönelik Iç içe Uygula** -her bir eyleme Uygula ekleyebilirsiniz, her bir kapsayıcı eylemi için diğer Uygula ' da filtre ve seçim yapabilirsiniz.
- **Tarih saat eylemleri** -yerel zaman alma, ekleme, çıkarma veya biçimlendirme zamanları için yeni eylemler.
- **Dört yeni bağlayıcı** -Content moderator, Docparser, Microsoft Kaizala ve üney Bowes veri doğrulaması eklendi.
- **Gelişmiş bağlantı deneyimi** -bağlantı kesildiğinde Microsoft Flow portalındaki bildirimler ve daha zengin bağlantı ayrıntıları.
- **Go koleksiyonu** - [Go çalışanları](https://flow.microsoft.com/collections/onthego/)için yeni bir şablon koleksiyonu.
- **E-posta adresi düğme girişleri** -kullanıcılara düğme çalıştırmaları durumunda e-posta adresleri toplayın.
- **Dosya düğmesi girişleri** -düğmeleri çalıştırdıklarında kullanıcılardan fotoğraflar gibi karşıya yüklenen dosyaları alın.
- Ilk çalıştırma ve otomatik oturum açma gibi, mobil uygulama üzerinde **otomatik oturum açma ile** geliştirilmiş ilk çalıştırma deneyimleri.
- **Daha hızlı Microsoft Forms Tetikleyicileri** -formlar, akışları daha önce daha çabuk (bir saatte bir saat) tetikler.
- **Oturumlar arasında düğme girişleri** -cep telefonunuzdaki tetiklenen düğmeler önceki girişleri anımsayacaktır.
- **Mobil etkinlik akışı** -daha ayrıntılı çalıştırma özetleri ve sorun giderme ayrıntılarını içeren etkinlik akışı geliştirildi.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/nested-apply-to-each/) bu sürüm hakkında soru sorun.

### <a name="release-2017-10-03"></a>Sürüm 2017-10-03

- **Tümü onaylaması gerekir** -bir onay isteğinin, isteği onaylaması isteğini alan herkese sahip olması için birden fazla kişiye gönderilmesini gerektir.
- **Yeni OneDrive iş eylemleri** -OneDrive iş 'te depolanan dosyalar için PDF oluşturma ve dört diğer yeni eylem.
- **Apache Impala Bağlayıcısı** -Apache Impala (ınubating), Apache Hadoop için açık kaynak, yerel analitik veritabanıdır.
- **Akış açıklamalarını ekleyin** -iş arkadaşlarınızın Flow 'un bir özetini görebilmesi için akışlarınızın açıklamalarını paylaştığınız kişilere verin.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) bu sürüm hakkında soru sorun.

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>Sürüm 2017-09-25-Microsoft Flow için Q3 güncelleştirmesi

- **Ilk yayında daha derin SharePoint tümleştirmesi** -ilk sürüm kiracılar için bir akış çalıştırdığınızda girişlerin toplanması için yeni "kutu içi" gönderme akışları ve akış paneli bulunur.
- **Dynamics 365 uygulamaları** -Flow, Dynamics 365 Sales ve Dynamics 365 Customer Service gibi Dynamics 365 uygulamaları için artık Kullanıcı arabiriminde tümleşiktir.
- **Microsoft Güven Merkezi** -Microsoft Flow HIPAA, ISO ve SOC gibi sertifikaları gösteren Microsoft Güven Merkezi 'nde listelenmiştir.
- **Kullanım Analizi** -her akışta temel kullanım analiziyle birlikte gömülü bir Power BI panosu vardır.
- **Ilk yayında denetim günlüğü** -tüm akış yönetimi olayları, ilk sürüm kiracıları için Office 365 güvenlik ve Uyumluluk Merkezi 'ne kaydedilir.
- **Altı yeni bağlayıcı** ; LinkedIn, Office 365 grupları, Skype Kurumsal, Adobe Sign, Bizzy ve Azure Log Analytics veri koleksiyonu eklenmiştir.
- **SQL Tetikleyicileri** -yeni bir satır eklendiğinde veya bir satır bir SQL tablosunda güncelleştirildiği zaman akışlar çalıştırın.
- **Şirket içi özel bağlayıcılar** -özel bağlayıcılar artık ağınızdaki iç uç noktalara bağlanmak için şirket içi veri ağ geçidini kullanabilir.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/q3-2017-update/) bu sürüm hakkında soru sorun.

### <a name="release-2017-09-21"></a>Sürüm 2017-09-21

- **Indirme akışı geçmişi** -Excel 'de açmak için bir akışın çalıştırma geçmişini CSV dosyası olarak indirin.
- **Gelişmiş yinelenme** -akışlarınızın tetiklenmesi için yinelenen zamanlamalar oluşturun, örneğin yalnızca hafta içi olarak tetikleyin.
- **IntelliSense** -ifadelerde yazarken, IntelliSense parametreler için öneriler sağlar.
- **Dört yeni bağlayıcı** -Azure AD HTTP Hizmetleri, Amazon Redshift, Azure Event Grid Publish ve flowforma için bağlayıcı eklenmiştir.
- **Paylaşım bağlantıları** -OneDrive dosyaları veya Azure depolama Blobları için paylaşılabilir bağlantılar oluşturmak üzere yeni bir eylem.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/download-history-recurrence/) bu sürüm hakkında soru sorun.


### <a name="release-2017-08-25"></a>Sürüm 2017-08-25
* SharePoint **Için belge özellikleri ve daha fazlası** SharePoint - [SharePoint belge kitaplığı özelliklerini okuyun ve ayarlayın](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/)ve SharePoint öğesine bağlantılar gibi ek alanları kullanın.
* **Akış koleksiyonları** -akış koleksiyonları, role göre veya dikey olarak düzenlenmiş bir şablon koleksiyonu kümesidir.
* **Button paylaşmasını** -düğmeleri iş arkadaşlarınızla paylaştığınızda, bunları diğer kişilerle birlikte yeniden paylaşabilirsiniz.
* **Düğmelerden liste topla** -kullanıcıların düğmeye dokunduklarında aralarından seçim yapmak için seçeneklerin açılan listelerini tanımlayın.
* **Yedi yeni bağlayıcı** -AWeber, Azure Log Analytics, Azure tabloları, DocFusion365, Azure Event Grid, Azure Event Hubs ve eleman hub 'ı. 
* **Bolluk ve MySQL geliştirmeleri** -kanallarda kanal oluşturun veya katın ve MySQL veritabanlarına yazabilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/button-updates-seven-connectors/) bu sürüm hakkında soru sorun.

### <a name="release-2017-08-02"></a>Sürüm 2017-08-02
* **Kişiye, seçeneğe ve arama alanlarına yazma** -SharePoint 'In öğe oluşturma ve güncelleştirme öğesi artık kişi, seçim ve arama alanlarını ayarlama [özelliğini destekliyor](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) .
* **Daha fazla eylem ayarı** -şimdi, yeniden deneme ilkelerini ve sayfalandırmayı yapılandırma dahil, Tetikleyiciler ve eylemlerin nasıl çalıştığı konusunda daha fazla denetim vardır.
* **Dört yeni bağlayıcı** -artık Azure dosya depolama, elastik formlar, Plivo ve video Indexer kullanabilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/four-connector-action-settings/) bu sürüm hakkında soru sorun.

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Sürüm 2017-07-27-Microsoft Flow için S2 güncelleştirmesi
* **İçeri ve dışarı aktarma** -akış çözümlerini ortamlar arasında veya testten üretimden üretime aktarma ve içeri aktarma. 
* **Eylemler ' de Ifadeleri kullanın** -herhangi bir eylemde ifadeler girin ve bunların nasıl kullanılacağına ilişkin satır içi yardım alın.
* **Azure Logic Apps Için büyüyerek** Visual Studio veya Azure Portal üzerinden dağıtılabilecek Azure Logic App kaynağı olarak akışlarınızı kaydedin.
* **Yönetici görünürlüğü** -tam olarak nerede ve nasıl kullanıldığını anlamak için kiracınızda Microsoft Flow kullanımı indirin.
* **Dynamics 365 ' deki akışlar** -finans, iş sürümü & Işlemler için Dynamics 365 içindeki akışları kullanın.
* **Senaryoları daha kolay bulun** -bağlayıcının yapabileceği her şeye gözatıp, akış oluşturmak için herhangi bir tetikleyiciyi bir atlama noktası olarak kullanabilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/q2-2017-update/) bu sürüm hakkında soru sorun.

### <a name="release-2017-07-13"></a>Sürüm 2017-07-13
* **Geliştirilmiş şablon yayımlama** -oluşturduğunuz her akışı, kategorileriyle birlikte genel galeriye yayımlayın.
* **Outlook takviminizdeki olayları alın** . takviminizde iki kez tüm olayları döndürmek için yeni bir eylem.
* **Yeni mobil işlevsellik** -mobil uygulamada, isteğe bağlı akışları çalıştırın ve başarısız olan çalıştırmaları yeniden gönderin.
* **Özel bağlayıcılardaki dinamik açılan** listeler-dinamik açılan listeler oluşturun, yoklamalar tetikler ve özel bağlayıcılarınızı test edin.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) bu sürüm hakkında soru sorun.

### <a name="release-2017-06-28"></a>Sürüm 2017-06-28
* **Dil ayarlarınızı güncelleştirme** -Microsoft Flow hem dil hem de bölge ayarlarını ayarlar menüsünde kullanarak özelleştirebilirsiniz.
* **Beş yeni bağlayıcı** -Adobe Creative Cloud, Bing haritalar, Bing arama, JotForm ve yeni hizmet için destek eklendi.
* **Zaman aşımlarını yapılandırma** -onaylar gibi uzun süre çalışan eylemlerin "zaman aşımı" olmadan önce çalıştırılmasını ve akışın devam etmesini değiştirin.
* **Onaylar Için Outlook 'a yorum ekleme** -onay isteği aldığınızda, Outlook 'tan çıkmadan yorum sağlayabilirsiniz.
* **Özel bağlayıcı marka renkleri** -artık, arka planlar Için kullanılacak özel bağlayıcılarınız için bir renk girebilirsiniz.
* **Ekip akışları Için farklı kaydet** -takım akışları dahil olmak üzere tüm akışların kopyalarını oluşturma
* **Akış bilgilerini silme** -bir akışı sildiğinizde, bu akış için bekleyen tüm çalıştırmaların listesi gösterilir.
* **Bağlayıcılar sayfasında filtreleme** -bağlayıcılar sayfasında istediğiniz bağlayıcıları arayın ve bağlayıcı türüne göre filtreleyin.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/language-settings-3-connectors/) bu sürüm hakkında soru sorun.

### <a name="release-2017-06-19"></a>Sürüm 2017-06-19
Artık gönderdiğiniz bekleyen onay isteklerinin tümünün durumunu görüntüleyebilirsiniz. Ayrıca, tüm bekleyen onaylarınız için doğrudan mobil cihazınızdan gözatıp üzerinde işlem yapabilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) bu sürüm hakkında soru sorun.

### <a name="release-2017-06-15"></a>Sürüm 2017-06-15
* **İçerik dönüştürme** -HTML içeriğini düz metne dönüştürebilecek, HTML biçimli e-postaları işlemek için faydalı olan yeni bir bağlayıcı.
* **Üç yeni Veritabanı Bağlayıcısı** -MySQL, PostgreSQL ve Teradata için salt okuma desteği eklendi. Bu bağlayıcılar şirket içi veri ağ geçidi aracılığıyla bağlanır.
* **Diğer üç bağlayıcı** -Azure Application Insights, tava ve takım iş projelerine bağlanın.
* **Hata işleme Için daha iyi görselleştirme** -hatalar sonrasında çalışan adımlar artık kırmızı noktalı oklarla gösterilerek bunları kolayca tanımlayabilmenizi sağlayabilirsiniz.
* **Çalıştırma ayrıntıları bölmesi** -bir akış başarısız olduğunda, akışınızı nasıl düzeltebileceğiniz konusunda bazı yararlı adımlar içeren yeni bir sağ bölme artık vardır.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/seven-connectors-and-html/) bu sürüm hakkında soru sorun.

### <a name="release-2017-06-04"></a>Sürüm 2017-06-04
* **Windows Phone Için GA** - [Microsoft Flow mobil uygulama Windows Phone için genel kullanıma sunuldu](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **Akış hatalarıyla ilgili** e-postalar-başarısız olan bir akışınız olduğunda e-posta ile bildirim alın. Bu hata e-postaları yalnızca haftada bir kez gönderilir ve Kullanıcı tarafından açılabilir veya kapatılabilir.
* **Tablolar için eylem seçeneğini belirleyin** -tablolarda yer alacak olan sütun kümesini değiştirmek Için yeni seçme eylemini kullanın.
* **Microsoft Forms Bağlayıcısı** -Microsoft Forms, öğretmen ve öğrencilerin özel sınavlar oluşturup kolayca, anketler, soru formları, kayıtlar ve daha fazlasını oluşturmalarına olanak tanıyan, Office 365 eğitimin yeni bir parçasıdır.
* **Office 365 Enterprise K1 plan** -PowerApps ve Microsoft Flow artık belirli kotalarla Office 365 Enterprise K1 planına dahildir.
* **Http üstbilgileri daha kolay** -seçme eyleminde olduğu gibi, yalnızca eylemde bulunan metin kutularını doldurarak bir başlık adı ve üst bilgi değeri sağlayabilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) bu sürüm hakkında soru sorun.

### <a name="release-2017-05-23"></a>Sürüm 2017-05-23
* Microsoft ekipleri **bağlayıcısı** - [Microsoft ekipleri](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) , Office 365 ' de kişiler, konuşmalar ve içerikler sunan, ekipler için gereken araçlarla birlikte, daha fazla bilgi almak için kolayca işbirliği yapabilmeleri için sohbet tabanlı bir çalışma alanıdır.
* **İOS ve Android Microsoft Flow pencere öğeleri üzerindeki pencere öğeleri** , giriş ekranınızdan kolayca bir düğme tetiklemenin daha kolay ve daha hızlı bir yolunu sağlayan düğme kısayollardır.
* **"Hata işleme" adımları oluşturma** -bir eylem başarısız olduktan sonra çalıştırılacak bir veya daha fazla adım tanımlayın. Örneğin, akışınız Dynamics 365 ' de kayıt oluşturamazsa hemen bir bildirim alın.
* **Tamsayı ve kayan değişkenler** -belirli bir mantık kümesinin kaç kez çalıştığını saymak için bir akış çalıştırmasının içindeki sayaçları başlatın ve artırın veya azaltın.
* **Akış ayrıntıları sayfası** - **Akışlarım** listenizde bir akış seçtiğinizde, bu Flow hakkında, erişimi olan kim ve çalıştırma geçmişi gibi ayrıntıları içeren bir sayfa görürsünüz.
* Yöneticiler **Için akış çalıştırma kotaları** -Yöneticiler artık ortak şirket çalıştırma kotasına karşı bir kuruluştaki akış çalıştırması kullanımını izleyebilir ve kotalarına hangi lisansların katkıda bulunduğunu anlamak için bir kota dökümü alabilir.
* **Http istek tetikleyicisi geliştirmeleri** -farklı http yöntemleri kullanın ve istek tetikleyicisi için yol kesimleri ekleyin.
* **İki iş ortağı Bağlayıcısı** -Microsoft Flow artık bir çevrimiçi formlar hizmeti olan parserr, bir e-posta ayrıştırma hizmeti ve Bilito formlarına bağlanabilir.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/error-handling/) bu sürüm hakkında soru sorun.

### <a name="release-2017-05-12"></a>Sürüm 2017-05-12
* **SharePoint belge kitaplıkları tümleştirmesi** -bir belge kitaplığındaki herhangi bir dosyayı seçebilir ve bir akışı başlatabilir, örneğin bunu onay için yöneticinize gönderebilir [ve çok daha fazlasını](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/)yapabilirsiniz.
* **Microsoft Planner Bağlayıcısı** -Microsoft Planner, daha iyi sonuçlar elde etmek için kolayca takımlar, görevler, belgeler ve konuşmalar birlikte yer almanızı sağlar.
* **Lisansların yönetici görünümü** -yöneticiler, Microsoft Flow Yönetim merkezinde tüm Microsoft Flow ve PowerApps lisanslarını (hem deneme sürümü hem de ücretli) görebilir.
* **PowerApps topluluk planı** -PowerApps topluluk planı, kişilerin powerapps, Microsoft Flow ve Common Data Service yeteneklerini keşfetmesi, öğrenmesi ve derlemek için ücretsiz bir plandır.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/planner-community-and-licenses/) bu sürüm hakkında soru sorun.

### <a name="release-2017-05-09"></a>Sürüm 2017-05-09
* **Azure AD Bağlayıcısı** -Kullanıcı oluşturma veya gruplara ekleme dahil olmak üzere Microsoft Flow 'den yönetici eylemleri gerçekleştirmek için yeni bir bağlayıcı vardır.
* **Office 365 Outlook iyileştirmeleri** -akışlar artık paylaşılan posta kutuları tarafından tetiklenebilir ve paylaşılan bir posta kutusuna e-posta gönderebilir. Ayrıca otomatik yanıtları ayarlayabilir veya okuyabilirler.
* **Kanada 'Da kullanılabilir** -şimdi, akışlarınızı Kanada 'da oluşturabilirsiniz.
* **Özel API web kancaları oluşturma** -özel bağlayıcı geliştiricileri, artık Web kancaları Ile özel API 'lerine Tetikleyiciler ekleyebilir.
* **Yönetim merkezinde akış sahiplerini yönetme** -ortam yöneticileri Microsoft Flow Yönetim merkezinde akış sahiplerini yönetebilir.
* **Bağlayıcı belge başvurusu** -artık [docs.Microsoft.com üzerinde bir tam bağlayıcı başvurusuna](https://docs.microsoft.com/Connectors/)sahipsiniz.
* **İki iş ortağı hizmeti** -iki yeni iş ortağı hizmeti yayımlanmıştır: NEXMO ve Paylııity.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/canada-mailboxes-aad) bu sürüm hakkında soru sorun.

### <a name="release-2017-04-27"></a>Sürüm 2017-04-27
* **Paralel adımlarla akış** oluşturma-paralel yürütme ile akış oluşturma: Yani, tam olarak aynı anda çalışan iki veya daha fazla adım olabilir.
* **Desteklenen beş yeni hizmet** -beş yeni hizmet: onaylar, kıyaslama e-posta, kapsül CRM, LiveChat ve Outlook müşteri yöneticisi.
* **Eylemler için yeniden denemeleri izleme** -Microsoft Flow hizmetlerle ilgili hatalardan sonra yeniden denenecek. Şimdi kaç otomatik yeniden deneme gerçekleştiğini ve ne olduğuna ilişkin ayrıntıları görün.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/parallel-actions/) bu sürüm hakkında soru sorun.

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Sürüm 2017-04-17-Microsoft Flow için S1 güncelleştirmesi
* **Modern onay deneyimleri** -onaylayanlara, Microsoft Flow web sitesindeki Microsoft Flow mobil uygulamanın veya Birleşik onay merkezinin içinden güvenli bir şekilde onaylayabilecekleri iş akışları oluşturun.
* **Ekip akışları genel kullanılabilirlik** -birden fazla kişi, artık genel kullanıma sunulan ekip akışlarıyla birlikte bir akışa sahip olabilir ve bir akışı yönetebilir.
* **Microsoft Flow için bağlayıcılar oluşturun** -herkes, dünyanın geri kalanı için kendi Microsoft Flow bağlayıcısını ücretsiz olarak gönderebilir.
* **"Diet" Tasarımcısı** -bazı şablonlar için, tasarımcı 'nın yeni bir sürümü yalnızca bir akış oluşturmak için gereken alanları gösterir ve bu da deneyimi basitleştirir.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/q1-2017-update/) bu sürüm hakkında soru sorun.

### <a name="release-2017-04-11"></a>Sürüm 2017-04-11
* **Tablo ve listelere yönelik yeni eylemler** -yeni HTML tablosu oluşturma, CSV tablosu oluşturma ve öğe listelerini işleyebilen eylemler (yalnızca önceki uygulama yerine).
* **Adımları her yere ekleyin** -şimdi sürükleyip bırakmaya gerek kalmadan iş akışında herhangi bir yerde yeni bir adım ekleyebilirsiniz.
* **Dört yeni hizmet** akışı artık 10 Ila 8 zamanlama, Yasası!, Inoreader ve görüntü işleme API'si desteklemektedir. Görüntü İşleme API'si, metin içeriğini almak için görüntüleri işleyebilir (OCR olarak bilinir) veya görüntüleri içeriğine göre otomatik olarak etiketleyebilir.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) bu sürüm hakkında soru sorun.

### <a name="release-2017-04-03"></a>Sürüm 2017-04-03
* **Windows Phone Beta** -Windows Phone uygulamanın önizlemesini almak Için Windows Phone app beta programı kullanılabilir. [Daha fazla bilgi edinin](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **MUHIMBI PDF** -artık Microsoft Word dosyalarını PDF 'ye dönüştürebilir, Filigranlar ekleyebilir, belgeleri ve daha FAZLASıNı Muhimbi PDF ile birleştirebilirsiniz. [Daha fazla bilgi edinin](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* Fiziksel **düğmelerdeki akışları** , fiziksel düğme alanındaki önde gelen ürünlerden oluşan ortaklıklarla duyuruyor: kısayol laboratuvarları ve bttn 'Yi Button Corporation tarafından [Daha fazla bilgi](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Sürüm 2017-03-22
* **Akışlarınızın bir kopyasını oluşturun** -artık, taslak sürümlerde çalışmak için akışlarınızın bir kopyasını oluşturabilir veya geçmişte oluşturduğunuz bir akışı çoğaltabilirsiniz.
* **İki yeni hizmet** -görevler oluşturup güncelleştirerek yapılacaklar listenizi yönetme ve müşteri hizmetleri ve destek anahtar platformu desteği sunan Toodeldo için destek ekleme.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/make-a-copy/) bu sürüm hakkında soru sorun.

### <a name="release-2017-03-15"></a>Sürüm 2017-03-15
* **Çalışma arkadaşlarınızla düğme paylaşma** -artık akış düğmelerini diğer kişilerle paylaşabilir, böylece tüm iş kullanıcıları hızlı görevler gerçekleştirmesini kolaylaştırır.
* **Giriş ekranından düğme tetikleme** -mobil cihazların giriş ve kilitleme ekranlarından akış düğmelerine giden kısayollar, akışın tetiklenmesi için her zamankinden daha hızlı hale getirir.
* **Microsoft Flow uygulamasında ekip akışları** -artık IOS veya Android için Microsoft Flow uygulamasındaki diğer sahipleri içeren akışları görebilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/button-sharing/) bu sürüm hakkında soru sorun.

### <a name="release-2017-03-10"></a>Sürüm 2017-03-10
* **Geliştirilmiş özel bağlayıcı deneyimi** -artık bir Postman koleksiyonu kullanarak özel bir bağlayıcı oluşturabilir ve eylemleri düzenleyebilir, ekleyebilir ve test edebilirsiniz.
* **İki yeni hizmet** -PowerApps bildirimleri ve PivotalTracker desteği eklendi.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/new-updates-custom-api/) bu sürüm hakkında soru sorun.

### <a name="release-2017-02-27"></a>Sürüm 2017-02-27
* **Akış düğmelerinizi tetikleme** -artık Microsoft Flow akış düğmelerini doğrudan tetikleyebilirsiniz. Akışlar listenize baktığınızda, "..." öğesini seçmeniz yeterlidir. menüsünde Şimdi Çalıştır komutunu seçin.
* **Beş yeni hizmet** -eklenen Oracle Database, Intercom, yeni kitaplar, Liankit ve WebMerge desteği.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) bu sürüm hakkında soru sorun.

### <a name="release-2017-02-21"></a>Sürüm 2017-02-21
* **Ortam akışlarını görüntüleme** -ortam yöneticileri artık belirli bir ortamdaki tüm akışların tam listesini görüntüleyebilir, ayrıca akışları etkinleştirebilir, devre dışı bırakabilir veya silebilir.
* **İki yeni hizmet** -Azure Otomasyonu ve Basecamp 2 desteği eklendi.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) bu sürüm hakkında soru sorun.

### <a name="release-2017-02-16"></a>Sürüm 2017-02-16
* **Beş yeni hizmet** -Azure Data Lake, Bitbucket (GIT düzeltme denetimini kullanan projeler için Web tabanlı bir barındırma hizmeti), Eventbrite, InfusionSoft ve Pipedrive desteği eklendi.
* **Özel http kimlik doğrulaması** -akış tasarımcısında, artık özel HTTP uç noktalarıyla kimlik doğrulaması kullanmak mümkündür.
* **JSON Iletilerini ayrıştırma** -http istek tetikleyicisinden veya http EYLEMINDEN döndürülen JSON verilerini ayrıştırabilirsiniz.
* **Akış çalıştırma filtrelemesi** -akış çalıştırmaları için Iyileştirilmiş, çalışan akışları görme veya iptal edilen çalıştırmalar gibi daha belirli seçeneklerle geliştirilmiş filtreleme.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) bu sürüm hakkında soru sorun.

### <a name="release-2017-02-06"></a>Sürüm 2017-02-06
* **Ekip akışları** -takım akışları, birden çok kişinin bir akışı birlikte sahip olmasını ve yönetmesine olanak sağlar ve bir kuruluştan ayrıldıklarında, oluşturduğu akışlar çalışmaya devam edebilir.
* **Özel bağlayıcılar paylaşma** -takım akışları gibi özel bağlayıcılar, bir kuruluş içinde paylaşılabilir ve toplu olarak yönetilebilir.
* **Gmail ve lusıs desteği** -Gmail ve Azure bilişsel hizmetler ' Language Understanding Intelligent Service bağlayın.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/team-flows/) bu sürüm hakkında soru sorun.

### <a name="release-2017-01-30"></a>Sürüm 2017-01-30
* Akış **düğmesi girişleri** -akış düğmeleri artık çalışma zamanında Kullanıcı girişlerini alabilir, bu nedenle akış yazarları düğme dokunduğunda geçirilen bilgileri tanımlayabilir.
* **Outlook görevleri ve HelloSign** -Outlook görevleri hizmeti görevleri yönetmenizi sağlar ve HelloSign, güvenli elektronik imzalara olanak tanır.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/button-user-inputs/) bu sürüm hakkında soru sorun.

### <a name="release-2017-01-23"></a>Sürüm 2017-01-23
* **Hizmete göre arama** -her hizmet için tüm eylemleri görmek üzere bir tetikleyici veya eylem eklediğinizde hizmete göre inceleyin.
* **Anahtar örneği** -paralel mantığın çeşitli dallarına sahip olmak için anahtar blokları ekleyin.
* **Diğer e-posta eylemleri** -Office 365 Outlook ve Outlook.com hizmetlerindeki yeni işlevler bayraklı mesajlarla birlikte çalışır.
* **Beş yeni hizmet** -yerel veya ağ dosya sistemlerine, ödeme hizmeti STRIPE, IBM ıNFORMIX, IBM DB2 ve UserVoice 'a bağlanın.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/search-by-service/) bu sürüm hakkında soru sorun.

### <a name="release-2017-01-14"></a>Sürüm 2017-01-14
* **Çalıştırmaları yeniden gönder** -bir akış başarısız olursa ve tekrar çalıştırmayı denemek istiyorsanız, başarısız olan çalışmayı yeniden gönderebilirsiniz.
* **Çalıştırmaları Iptal et** -bir akış takıldığında, artık çalıştırmayı açıkça iptal edebilirsiniz.
* **İki yeni hizmet** -sayfaytraining ve Sayfayweb semineri için destek eklendi.
* **Mobil bağlantılar** -şablonları doğrudan mobil uygulamadan paylaşabilir ve Web sitesinin en üstündeki uygulamalar için bir hızlı indirme bağlantısı ekledik.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/managing-runs/) bu sürüm hakkında soru sorun.

### <a name="release-2016-12-29"></a>Sürüm 2016-12-29
Microsoft Flow, Eimzaları ve dijital Işlem yönetimini işlemek için artık DocuSign 'ı destekliyor; Web tabanlı anketler için araştırma, ve OneNote not alma uygulaması (yalnızca iş hesapları).

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/final-2016-services/) bu sürüm hakkında soru sorun.

### <a name="release-2016-12-20"></a>Sürüm 2016-12-20
* **Şimdi Çalıştır** -artık yinelenen bir tetikleyiciyi isteğe bağlı olarak tetikleyebilirsiniz (örneğin, her gün zamanlanmış bir raporunuz varsa, ancak raporun **Şimdi** de çalışması gerekir.
* **Altı yeni hizmet** -MSN Hava durumu, orta, Google kişileri, arabellek, toplama ve typeform 'a bağlanan akışlar oluşturun.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/run-now-and-six-more-services/) bu sürüm hakkında soru sorun.

### <a name="release-2016-12-14"></a>Sürüm 2016-12-14
Artık düğmenin nerede tetiklendiği, ne zaman, ne zaman ve daha fazlası gibi bir düğme akışını tetiklerken değerli bilgilerden yararlanabilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/button-trigger-tokens/) bu sürüm hakkında soru sorun.

### <a name="release-2016-12-06"></a>Sürüm 2016-12-06
* **Destekli öğrenme tanıtımı** -Microsoft Flow kapsamlı ve güçlü özellikleri anlamanıza yardımcı olmak üzere videoları belgeler Ile eşleştirerek sıralanmış bir kurs koleksiyonuyla çalışmaya başlama.
* **İki yeni hizmet** -akış artık, bir çevrimiçi toplantı aracı olan yeni bir müşteri destek çözümünü ve sayfaytoplantısını kullanabilir.
* **Http Web kancası desteği** -bir akış artık Web kancaları için otomatik olarak kaydedilecek ve kaydını kaldıran bir uç nokta olabilir.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/guided-learning-and-two-services/) bu sürüm hakkında soru sorun.

### <a name="release-2016-11-23"></a>Sürüm 2016-11-23
* **Flow 'da uyarı desteğini Power BI,** Power BI veri uyarılarından akışlar tetikleyerek öngörüleri eyleme dönüştürün.
* **Mobil uygulama geliştirmeleri** -şablonlardan, mevcut bir oluşturma deneyimine ek olarak boş akış oluşturma özelliği eklenmiştir. Ayrıca akış çalıştırmalarını görüntülerken performansı geliştirdik.
* **Sekiz yeni hizmet** -artık Azure Resource Manager, Azure kuyrukları, chatter, Disqus, Azure Cosmos DB, bilişsel Hizmetler Yüz Tanıma API'si, HipChat ve WordPress 'e bağlanabilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) bu sürüm hakkında soru sorun.

### <a name="release-2016-11-15"></a>Sürüm 2016-11-15
* **Microsoft Flow Iş ortağı programı** -Microsoft Flow artık bağlantı kurmak ve dünyanın dört bir yanındaki Microsoft Flow farklı şirketin tamerklarından ve deneyimlerinden yararlanmak için bir sertifikalı iş ortağı programı vardır.
* **Altı yeni hizmet** -bu hafta altı hizmet yayınlıyoruz: Asana, Kampeli ateş, EasyRedmine, JIRA, Redmine ve Vimeo.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/partner-program-six-new-services/) bu sürüm hakkında soru sorun.

### <a name="release-2016-10-31---general-availability"></a>Sürüm 2016-10-31-genel kullanılabilirlik
* **Fiyatlandırma ve lisanslama** -artık hem ücretsiz hem de ücretli planlarda, ayrıca Office 365 ve Dynamics 365 ' de yer alan ücretsiz olarak kullanılabilir.
* **Microsoft Flow Yönetim Merkezi** -kurumsal-yeni Yönetim Merkezi ile hazırlanın. Yönetim merkezinde kuruluş içindeki ortamları yönetebilirsiniz.
* **Veri kaybı önleme ilkeleri** -Yöneticiler, hizmetler arasında veri akışını denetlemek için veri kaybı önleme ilkeleri oluşturabilir.
* **Android kullanılabilirliği** -Microsoft Flow Phone uygulaması artık hem iOS hem de Android için kullanılabilir. Uygulama, bir düğmeye dokunarak bildirimler almanızı, etkinliği izlemenizi ve akışları başlatmayı sağlar.
* **Yeni tasarımcı deneyimleri** -artık adımla adım adım geçen dinamik içeriği arayabilir ve istediğiniz verilere başvurmak çok daha hızlı hale getirebilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/announcing-ga/) bu sürüm hakkında soru sorun.

### <a name="release-2016-10-26"></a>Sürüm 2016-10-26
* **Düğme akışları** -istediğiniz zaman ve herhangi bir yerden tetikleyebilmemiz için sayaçsuz işlemler vardır. Artık düğme akışlarıyla, mobil cihazınızdan bir düğmeye tıklayarak bu işlemi gerçekleştirebilirsiniz.
* Sunulan **ortamlar** -ortamlar, kuruluşunuzun akışlarını depolamak ve yönetmek için farklı boşluklardır. Ortamlar coğrafi olarak bulunur, bu da bir ortamda yer alan akışlar, uygulamalar ve iş verilerinin ortamın bulunduğu bölgede bulunacağı anlamına gelir.
* **Altı yeni hizmet** -bit.ly, bilişsel hizmetler metin analizi, Dynamics nav, Finans için Dynamics 365, mali bir kağıt ve pilgi için destek ekleme.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/environments-for-makers/) bu sürüm hakkında soru sorun.

### <a name="release-2016-10-16"></a>Sürüm 2016-10-16
* **Özel bağlayıcılar daha fazla kimlik doğrulama türünü destekler** -özel BAĞLAYıCıLAR artık API anahtarı kimlik doğrulamasını destekliyor ve tam OAuth 2,0 belirtimini destekleyen herhangi bir hizmette kimlik doğrulaması yapabilir.
* **Desteklenen üç yeni hizmet** -Basecamp 3, Blogger ve pagerharcı için destek ekledik.
* **Tasarımcı geliştirmeleri** -gelişmiş performans, artık "..." ile bağlantılarınızı güncelleştirebilir ve onarabilirsiniz Her eylem için menü ve bir akışın çalıştırmasını sonlandırmak için kullanabileceğiniz Sonlandır adlı yeni bir adım ekledik.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/early-october-updates/) bu sürüm hakkında soru sorun.

### <a name="release-2016-09-25"></a>Sürüm 2016-09-25
Akış oluşturma artık cep telefonlarınızın kullanımına sunuldu. Zengin şablon galerimize göz atarak hizmetler listemize gidin veya detaydan çıkmak için bir şablon kategorisi seçin. [Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/mobile-creation/) bu sürüm hakkında soru sorun.

### <a name="release-2016-09-22"></a>Sürüm 2016-09-22
* **Microsoft Graph kişi Seçicisi** -yeni bir Microsoft Graph kişi seçici, doğru iletişim veya e-posta adresini seçmenize yardımcı olmak için doğrudan Microsoft Flow Kullanıcı arabirimine tümleştirilir.
* **Microsoft DYNAMICS AX desteği** -akışlarınızın içinden, verileri sorgulamak için yeni kayıtlar OLUŞTURMAKTAN Dynamics AX Online Operations verileriniz üzerinde işlem gerçekleştirebilirsiniz.
* **İş ortaklarından iki yeni hizmet** -artık akışlarınızdan apprakamları veya Insightly kullanın.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/more-september-updates/) bu sürüm hakkında soru sorun.

### <a name="release-2016-09-14"></a>Sürüm 2016-09-14
* **Web sitenize veya uygulamanıza ekleme** -geliştiriciler artık kendi uygulamalarına veya web sitelerine Microsoft Flow ekleyerek kullanıcılara kişisel veya profesyonel görevlerini otomatik hale getirmeye yönelik basit bir yol ekleyebilir.
* Bir **akışı http uç noktası olarak kullanma** -artık BIR akışı http API 'si olarak kullanabilirsiniz. Flow içinde Istek adlı bir tetikleyici vardır ve bir yanıt kartı ekleyerek gelen isteğe yanıt vermeyi tercih edebilirsiniz.
* **Todoist support** -Todoist, tüm projelerinize, çalışmalara ve evde bir perspektife sahip olmanızı sağlar.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/extend-web-site-application/) bu sürüm hakkında soru sorun.

### <a name="release-2016-09-01"></a>Sürüm 2016-09-01
Artık herkes için kullanılabilir Microsoft Flow-başlangıçta, Office 365 Iş veya Office 365 Enterprise ile kullanılanlarla birlikte yalnızca işiniz veya okulunuz tarafından sağlanan e-posta adreslerine yönelik önizlemeyi açtık. Bugün, önizleme resmi olarak kullanılabilir olduğunu duyuruyoruz. Bu, tüm kullanıcılar için ücretsiz olan e-posta ile herhangi bir şey olabilir. [Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/available-for-everyone/) bu sürüm hakkında soru sorun.

### <a name="release-2016-08-31"></a>Sürüm 2016-08-31
* **Iç içe** koşullar-artık diğerinin içine ikinci (veya üçüncü, vb.) bir koşul ekleyebilirsiniz.
* Her birine **Uygula** -her döngü için bir uygulama, yinelemek istediğiniz listeyi denetlemenizi mümkün kılar.
* **Do-Until** -bir do-Until döngüsü, belirli bir koşul karşılanana kadar bir adımı yinelemenize olanak tanır.
* **Dizileri filtrele** -listedeki her öğenin tanımladığınız bir ifadeyle eşleştiğinden emin olmak için tek bir yerel filtre adımı vardır.
* **Dize değişkenlerini oluşturma** -artık bir dize değişkeni oluşturabilirsiniz.
* **Kapsamlar** -kapsamlar iki veya daha fazla eylemi birlikte gruplamak için basit bir yoldur.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/build-advanced-flows/) bu sürüm hakkında soru sorun.

### <a name="release-2016-08-27"></a>Sürüm 2016-08-27
* **Adımlar ile Ilgili açıklamalar** -Yorumlar, her bir eyleme Not eklemeyi kolaylaştırırken, akışın ihtiyaçlarını kolayca hatırlayabilmenizi sağlar.
* **Smartsheet desteği** -bu hafta Smartsheet 'e bağlanmak için destek ekledik. Smartsheet, buluttaki sayfalarla işbirliği yapmayı kolaylaştıran bir hizmettir.
* Akış **yazma sırasında UI işlevselliklerindeki** -akış adı ön ve-Orta ' i yaptık ve kolay erişim için Kaydet düğmesini sayfanın en üstüne taşıdık.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/add-comments-smartsheet/) bu sürüm hakkında soru sorun.

### <a name="release-2016-08-18"></a>Sürüm 2016-08-18
Artık Microsoft Flow tümleştirmesini içeren yeni SharePoint Online modern liste deneyiminin önizlemesini yapabilirsiniz. [Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) bu sürüm hakkında soru sorun.

### <a name="release-2016-08-13"></a>Sürüm 2016-08-13
* **Visual Studio Team Services** , artık VSTS 'Yi O365 e-posta, bolluk, Trello ve Wunderlist gibi çok çeşitli hizmetlere bağlayabilirsiniz.
* SharePoint-SharePoint listelerine **yönelik iyileştirmeler** , tek satırlık metin ve Tarih ve saat gibi basit nesnelerden kişi veya Grup, arama ve seçim gibi karmaşık nesnelere kadar olan veri türlerini destekler.
* **O365 Outlook bağlantılarını test** etme-yeni bir O365 Outlook bağlantısı oluşturduğunuzda, artık bunu kullanmaya hazır olduğunuzdan emin olmak için test edeceğiz.
* **Boole denetimi** -Ayrıca, yeni bir e-posta geldiğinde tetikleyiciden ek olan gibi Boole giriş alanları için hangi değerlerin girilmesi gerektiğini açıklığa kavuşturmak üzere bir Boole denetimi ekledik.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) bu sürüm hakkında soru sorun.

### <a name="release-2016-08-08"></a>Sürüm 2016-08-08
Microsoft Flow tümleştirilmiş Microsoft Common Data Service Genel önizlemesi. [Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/flow-and-common-data-model/) bu sürüm hakkında soru sorun.

### <a name="release-2016-08-05"></a>Sürüm 2016-08-05
* SharePoint Şirket **içi** -SharePoint Online ile tıpkı, önceden tanımlanmış şablonlar kullanarak veya sıfırdan oluşturarak SharePoint şirket içi listelerinizi ve belge kitaplıklarınızın etrafında akışlar oluşturabilirsiniz.
* **Tasarımcıda bilgi-kabarcıklar** -her tetikleyicinin ve eylemin özelliklerine ilişkin ayrıntılı bilgi için akışlarınızın her bir adımının üzerine bilgi balonları ekledik.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) bu sürüm hakkında soru sorun.

### <a name="release-2016-07-15"></a>Sürüm 2016-07-15
* **Dört yeni hizmet eklendi** -Google takvimine, Google görevlerine, YouTube 'A ve mini posta 'e bağlanın.
* **Eylemlerinizi yeniden adlandırın** . artık bu farklı eylemlere onları yeniden adlandırarak ayırt edebilirsiniz.
* **Farklı süreler Için gecikme** -artık Istediğiniz sayıda saniye, dakika, saat veya gün seçebilirsiniz.
* **Daha kolay klasör tarayıcısı** -klasör tarayıcısını basitleştik. Şimdi sol taraftaki seçim bu klasörü seçeceğiz ve sağ tarafta seçim bu klasörü açacak ve alt klasörleri seçebilmenizi sağlayacak.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/new-google-services-rename-more/) bu sürüm hakkında soru sorun.

### <a name="release-2016-07-08"></a>Sürüm 2016-07-08
Şirket içi veri ağ geçidini kullanarak Microsoft Flow için şirket içi bağlantı. Bu, SQL Server için güvenli bağlantı kurup akışlarınızla tümleştirmenize olanak tanır. [Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/on-premises-data-gateway/) bu sürüm hakkında soru sorun.

### <a name="release-2016-07-02"></a>Sürüm 2016-07-02
* **Google sayfa desteği** -geçmişte, Google Drive 'ın yanı sıra Excel 'i de kullanma imkanımız vardı, ancak bu hafta yerel Google sayfaları desteğini ekliyoruz.
* **Şablonlardan daha hızlı** bir şekilde çalışmaya başlayın-Ayrıca şablonlardan başlayabilmeniz için bazı iyileştirmeler yaptık. Artık şablon sayfasında, bir şablon için kullanmak istediğiniz hesapları seçebilirsiniz.
* **SharePoint ve Office 365 için süresi dolan yetkilendirme yok** -şu anda Microsoft Flow Azure Active Directory tabanlı hizmetlere erişiminizi otomatik olarak yenileyecek ve tüm akışlarınız parola değişikliklerinde çalışmaya devam edecektir.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/more-june-updates/) bu sürüm hakkında soru sorun.

### <a name="release-2016-06-20"></a>Sürüm 2016-06-20
* **Yeni mobil uygulamayı Microsoft Flow** kullanıma sunma-bugün, sunduğumuz başka bir büyük parçasını kullanıma sunmaktan mutluluk duyuyoruz: bir mobil uygulama artık iOS 'ta (kısa bir zamanda Android 'de) indirilebilir her zaman ve her yerden otomatik iş akışları.  
* **Çoklu oturum** açma-Office 365 gibi diğer Microsoft hizmetleriyle Microsoft Flow kimlik doğrulaması yapmanıza olanak sağlayan çoklu oturum açma uyguladık.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) bu sürüm hakkında soru sorun.

### <a name="release-2016-06-18"></a>Sürüm 2016-06-18
* **Yeni posta hizmeti** -artık Microsoft Flow içindeki kişisel veya iş e-posta hesaplarınıza bağlanabilmek gerekmeden Microsoft Flow doğrudan e-posta gönderebilirsiniz.
* **Portalda bildirimler** -artık akışlarınızla her şey kesildiğinde portalın en üstünde bildirimler görürsünüz.
* **Portaldaki tüm etkinlikler** -artık Flow web sitesindeki yeni etkinlik sekmesine tıklayarak akışlarınızın tümünde etkinlik görebilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/mail-and-all-activity/) bu sürüm hakkında soru sorun.

### <a name="release-2016-05-27"></a>Sürüm 2016-05-27
* **Hizmete göre şablonlara gözatıyor** -artık desteklediğimiz tüm hizmetleri (oturum açmadan) görmeniz için bir yol vardır. Bu sayfadan her bir hizmetin açıklamasını görebilir ve bu hizmet için sahip olduğumuz şablonlara göz atın.
* **Özel bağlayıcılarınızı oluşturma ve kullanma** -tıpkı PowerApps 'te özel bağlayıcılar oluşturabileceğiniz gibi, Flow.Microsoft.com adresinde kendi API 'lerinize de bağlanabilirsiniz:
* **Akışlarınızın tamamlanmasını test etmeden önce test** edin. bir akışı kaydettiğinizde, Başlangıç eylemini gerçekleştirirseniz, sayfada canlı olarak çalışan akışının sonuçlarını görebilirsiniz.

[Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) bu sürüm hakkında soru sorun.

### <a name="release-2016-05-07"></a>Sürüm 2016-05-07
İki yeni hizmet eklendi: Microsoft Project Online ve MailChimp 'e göre Mandetaya git. [Daha fazla bilgi edinin ve](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) bu sürüm hakkında soru sorun.

### <a name="release-2016-04-27---public-preview"></a>Sürüm 2016-04-27-genel önizleme
[Microsoft PowerApps](https://powerapps.microsoft.com)kapsamında Logic Flow kullandıysanız, Microsoft Flow önizleme sürümü birkaç yeni özellik sunar:

* Artık düzinelerce şablon galerisine gözatabilir, popülerlik, ad veya Yayımlanma tarihine göre sıralama yapabilirsiniz.
* Bir akışı özelleştirdikten sonra [kendi şablonlarınızı galeriye yayımlayabilirsiniz](publish-a-template.md) .
* Akışınızı her denetim ve çalıştırmaya ilişkin geçmişi görebilirsiniz.
* Bir akışı kaydettiğinizde, yalnızca tetikleyici eylemini gerçekleştirerek, [Bu işlemi hemen eylemde izleyebilirsiniz](see-a-flow-run.md) .
* Akışı tartışmak veya [fikirlerinizi göndermek](https://go.microsoft.com/fwlink/?LinkID=787474)için [Yeni bir topluluk](https://go.microsoft.com/fwlink/?LinkID=787467) sunuyoruz.

## <a name="next-steps"></a>Sonraki adımlar
Bu sürüm notlarında veya [SSS](frequently-asked-questions.md)'de henüz kapsanmayan bir sorununuz varsa, lütfen sorularınızı sormak için [topluluğumuza katılarak](https://go.microsoft.com/fwlink/?LinkID=787467) veya [desteğe başvurun](https://go.microsoft.com/fwlink/?LinkID=787479).

