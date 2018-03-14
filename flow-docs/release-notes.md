---
title: "Sürüm notları | Microsoft Docs"
description: "Microsoft Flow sürümlerinde sık karşılaşılan sorunlar ve yenilikler"
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/12/2018
ms.author: stepsic
ms.openlocfilehash: 57a86fa86633e040cf788443d54bd60cfd340844
ms.sourcegitcommit: 6308b1f4ec4ed18a8a7c89911a83cd2f12ed6dc4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="release-notes"></a>Sürüm notları
## <a name="top-questions"></a>En çok sorulan sorular
1. Akışım başarısız oldu. Nasıl düzeltebilirim?
   
   1. Hatayı tanımlayın. Web portalının üst kısmındaki bildirimler simgesine giderek veya mobil uygulamadaki **Etkinlik** sekmesini seçerek işe başlayın. Akışınızı orada görüp seçebilirsiniz.
   2. Şu anda akış ayrıntılarına bakıyorsunuz. Kırmızı ünlem simgesi eklenmiş adımı bulun ve akışınızın hata iletisini görüntüleyin.
   3. Hata iletisine bağlı olarak, akışı **Düzenleyebilir** ve düzeltebilirsiniz. [Genel akış hatalarını düzeltme hakkında bilgi için okumaya devam edin](fix-flow-failures.md).
2. Gelişmiş bir koşulu veya ifadeyi nasıl kullanabilirim?
   
   * [Koşul ekleme](add-condition.md) hakkında bilgi edinin.
   * Bir akışa birden çok durum eklemek için, mevcut bir koşulun içinden **Koşul ekle**’ye tıklayın veya dokunun.
   * [Logic Apps'teki bir işleve](https://docs.microsoft.com/rest/api/logic/definition-language) başvurarak gelişmiş bir ifade oluşturun.
3. Office 365 ile lisanslama nasıl çalışır?
   
   * Office 365 kullanıcısıysanız, Office 365 için Microsoft Flow planı aracılığıyla tam erişim elde edebilirsiniz. Daha fazla bilgi için bkz. [Microsoft Flow için fiyatlandırma planları](https://flow.microsoft.com/pricing/) .
   * Yöneticiyseniz, Office 365 kapsamında kullanımı da içeren [Microsoft Flow lisanslama seçenekleri](organization-q-and-a.md) ile ilgili bilgi edinin.

## <a name="known-issues-and-resolutions"></a>Bilinen sorunlar ve çözümleri
1. Sitelerim’deki SharePoint listeleri ve *Özel Liste* türünde olmayan listeler desteklenmez. Bu soruna geçici çözüm olarak, standart bir SharePoint sitesinde özel liste oluşturun.
2. Akışlar, SharePoint listelerindeki Sınıflandırma alanlarına yazamaz. Bu sorun düzeltilene kadar basit bir dize alanı kullanmanızı öneririz.
3. Dosya tetikleyicileri, seçtiğiniz klasördeki iç içe geçmiş klasörlere eklenmekte olan dosyalar için tetiklenmez.

## <a name="whats-new"></a>Yenilikler

### <a name="release-2018-02-09"></a>Sürüm 2018-02-09

- **Ağ Geçidi Yüksek Kullanılabilirliği** - Tek tek makineler kapandığında bağlantıların açık kalmasını sağlamak için şirket içi veri ağ geçitlerinin yüksek kullanılabilirlik özelliğine sahip kümelerini oluşturun.
- **Her birine uygula geliştirildi** - Flow Plan 1 veya Flow Plan 2 ile tek bir çalıştırmada 100.000’e kadar öğe çalıştırın ve Her birine uygula döngüleriyle paralel olarak 50 eylem gerçekleştirin. 

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/).

### <a name="release-2018-01-29"></a>Sürüm 2018-01-29

- **Microsoft Teams’de Flow** - Teams’den akış oluşturup bu akışları yönetebilir, aldığınız ve gönderdiğiniz onayları gözden geçirebilir ve doğrudan Teams masaüstü uygulamasının içinden veya teams.microsoft.com adresinden akış başlatabilirsiniz - [buradan daha fazla bilgi edinebilirsiniz](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Paylaşılan düzenleme bildirimleri** - Sahip olduğunuz bir akış bir iş arkadaşınız tarafından her değiştirildiğinde, hangi akışı kimin değiştirdiği konusunda bilgi sağlayan bir e-posta bildirimi alırsınız.
- **Yeni ifadeler** - Biri URL'leri ayrıştırmaya, diğeri JSON nesneleriyle çalışmaya yönelik iki yeni ifade kümesi eklendi.
- **Üç yeni bağlayıcı** - Bu hafta, Plumsail SP ve Plumsail Forms adlı iki yeni Plumsail bağlayıcısının yanı sıra bir kintone bağlayıcısı sunuldu.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/shared-notifications-and-expressions/).

### <a name="release-2018-01-17"></a>Sürüm 2018-01-17

- **Office 365 profil bilgileri** - Office 365 Kullanıcıları bağlayıcısına kullanıcı profilleri ve fotoğraflarla çalışan yeni eylemler ekledik.
- **Dize değişkenlerine ekleme** - Döngülerin içindeki dizelere ekleme yaparak tablolar veya başka listeler oluşturabilirsiniz.
- **Infobip bağlayıcısı** - Infobip, sesli aramalar ve SMS geldiğinde tetiklenme dahil olmak üzere kurumsal düzeyde iletişim imkanı sağlayan bir hizmettir.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/o365-profile-infobip/).

### <a name="release-2017-12-20"></a>Sürüm 2017-12-20

Microsoft Flow Analytics, tüm Microsoft Flow bölgelerinde kullanılabilir durumdadır. Başka bir deyişle ortamınızda çalışan akışların durumu hakkında daha fazla öngörüye sahip olabilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/).


### <a name="release-2017-12-14"></a>Sürüm 2017-12-14

- **Outlook bağlayıcısı geliştirmeleri** -E-postaları ".eml" dosyası olarak kaydedebilir, takvim davetlerine otomatik olarak yanıt verebilir ve bir e-posta ileti dizisinde sizden söz edildiğinde akışları tetikleyebilirsiniz.
- **Bağlantı geliştirmeleri** - Microsoft Flow en son kullandığınız bağlantıları hatırlar ve yeni eklenen bağlayıcıları gösterir.
- **Beş yeni bağlayıcı** - Azure Kapsayıcısı Örnekleri, Azure Kusto, Metatask, Microsoft To-Do ve Plumsail Documents.
- **HTTP geliştirmeleri** - HTTP eylemi artık parçalı kodlamayı destekliyor.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/outlook-connector-more/).

### <a name="release-2017-12-05"></a>Sürüm 2017-12-05

Microsoft Flow Başlatma Paneli artık tüm bölgelerde kullanılabilir. Bu paneli kullanarak SharePoint listesi veya belge kitaplığı içinde çalıştırdığınız akışlara değer ekleyebilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/).


### <a name="release-2017-11-28"></a>Sürüm 2017-11-28

- **Yönetilen Meta Veri** - SharePoint'te Yönetilen Meta Veri ( Sınıflandırma) türünü kullanan sütunlardaki verileri okuyabilir ve bu sütunlara veri yazabilirsiniz.
- **Dizilere Ekleme** - Yeni Dizi değişkenine ekle eylemini kullanarak dizi sonuna öğe ekleyebilirsiniz.
- **Tago** - Yeni Tago bağlayıcısı bağlama dayalı çözümleme kullanarak daha akıllı kararlar almayı sağlamak üzere dış verilere sahip elektronik cihazlarla kolayca bağlantı kurulmasını sağlar.
- **iPhone X** - Microsoft Flow uygulamasının yeni sürümü iPhone X ekranının tamamını kullanır ve görüntü yükleme için yükseltilmiş hıza sahiptir.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/managed-metadata-tago/).

### <a name="release-2017-11-09"></a>Sürüm 2017-11-09

- **OneDrive İş tümleştirmesi** - [OneDrive İş'in içindeki akış düğmesini](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) kullanarak seçilen dosyaları veya klasörleri temel alan akışlar oluşturabilir veya tümleştirebilirsiniz.
- **Planlayıcı tetikleyicileri** - Yeni bir görev oluşturulduğunda, size bir görev atandığında veya bir görev tamamlandığında akış başlatın.
- **SharePoint ekleri** - SharePoint liste öğelerinin ekleri üzerinde çalışın: ekleri listeleme, indirme, ekleme veya silme.
- **Akış yönetimi bağlayıcısı** - Ortamınızdaki diğer akışların yönetimini otomatik hale getiren akışlar oluşturun (örneğin akışlara otomatik olarak izin ekleyin).
- **Dört yeni bağlayıcı** - Azure Özel Görüntü İşleme Hizmeti, D&B Optimizer, Enadoc ve Derdak SIGNL4 desteği eklendi. 
- **Daha fazla bağlayıcı eylemi** - SQL sorgularını çalıştırın, daha hızlı e-posta tetikleyicisi alın, Azure AD ile istediğiniz HTTP yöntemini kullanın ve daha fazlasını yapın.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/).

### <a name="release-2017-11-02"></a>Sürüm 2017-11-02

- **Denetim Günlüğü** - Microsoft Flow denetim olaylarını artık tüm kiracılar için Office 365 Güvenlik ve Uyumluluk Merkezi'nden takip edebilirsiniz.
- **Akış pencere öğesi düzeltmeleri** - Flow mobil uygulamasında pencere öğesi düğmelerinin yüklenmemesine neden olan bir sorun giderildi.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/security-and-compliance-center/).

### <a name="release-2017-10-19"></a>Sürüm 2017-10-19

- **İç içe her birine uygula** - Her birine uygula eylemleri ekleyebilir, diğer her birine ekle kapsayıcı eylemlerini filtreleyebilir ve seçebilirsiniz.
- **Tarih Saat eylemleri** - Yerel saatleri alma, ekleme, çıkarma veya saatleri biçimlendirme için yeni eylemler.
- **Dört yeni bağlayıcı** - Content Moderator, Docparser, Microsoft Kaizala ve Pitney Bowes Veri Doğrulama eklendi.
- **Geliştirilmiş bağlantı deneyimi** - Bağlantı kesildiğinde Flow portalında görüntülenen bildirimler ve daha zengin bağlantı ayrıntıları.
- **Hareket halinde koleksiyonu** - [Hareket halindeki çalışanlar](https://flow.microsoft.com/collections/onthego/) için yeni bir şablon koleksiyonu.
- **E-posta adresi düğmesi girişleri** - Düğmeleri çalıştıran kullanıcıların e-posta adreslerini toplayın.
- **Dosya düğmesi girişleri** - Düğmeyi çalıştıran kullanıcılardan fotoğraf gibi yüklenen dosyaları alın.
- **İlk çalıştırma ve otomatik oturum açma** - Otomatik oturum açma dahil olmak üzere mobil uygulamada geliştirilmiş ilk çalıştırma deneyimleri.
- **Daha hızlı Microsoft Forms tetikleyicileri** - Forms, akışları öncekinden daha hızlı tetikler (önceki süre: bir saat).
- **Oturumlar arasında düğme girişleri** - Cep telefonunuzda tetiklenen düğmeler önceki girişleri hatırlar.
- **Mobil etkinlik akışı** - Daha ayrıntılı çalıştırma özetlerini ve sorun giderme ayrıntılarını içeren geliştirilmiş etkinlik akışı.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/nested-apply-to-each/).

### <a name="release-2017-10-03"></a>Sürüm 2017-10-03

- **Tümü onaylamalıdır** - İsteği alan herkesin onaylaması için bir onay isteğinin birden fazla kişiye gönderilmesini isteyin.
- **Yeni OneDrive İş eylemleri** - OneDrive İş'te depolanan dosyalar için PDF oluşturma ve dört yeni eylem.
- **Apache Impala bağlayıcısı** - Apache Impala (incubating), Apache Hadoop için açık kaynak, yerel analiz veritabanıdır.
- **Akış açıklamaları ekleme** - Akışlarınıza açıklama ekleyerek paylaştığınızda iş arkadaşlarınızın akış eylemlerinin özetini görmesini sağlayın.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/).

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>Sürüm 2017-09-25 - Microsoft Flow Ç3 Güncelleştirmesi

- **İlk Sürümde Daha Ayrıntılı SharePoint tümleştirmesi** - Yeni "hazır" incelemeye gönder akışları ve ilk sürüm kiracıları için bir akış çalıştırdığınızda girişleri toplamak üzere bir Flow paneli mevcuttur.
- **Dynamics 365 for Customer Engagement** - Flow artık Dynamics 365 for Customer Engagement arabirimine tümleşiktir.
- **Microsoft Güven Merkezi** - Flow, Microsoft Güven Merkezi'nde listelenerek HIPAA, ISO ve SOC gibi sertifikaları göstermektedir.
- **Kullanım analizi** - Her akışta temel kullanım analizini içeren ekli bir Power BI panosu mevcuttur.
- **İlk Sürümde Denetim Günlüğü** - Tüm akış yönetim olayları ilk sürüm kiracıları için Office 365 Güvenlik ve Uyumluluk Merkezi'ne kaydedilir.
- **Altı yeni bağlayıcı** - LinkedIn, Office 365 Grupları, Skype Kurumsal, Adobe Sign, Bizzy ve Azure Log Analytics Veri Koleksiyonu eklendi.
- **SQL tetikleyicileri** - SQL tablosuna yeni bir satır eklendiğinde veya satırlardan biri güncelleştirildiğinde akış çalıştırın.
- **Şirket içi özel bağlayıcılar** - Özel bağlayıcılar artık ağınızdaki iç uç noktalara bağlanmak için şirket içi veri ağ geçidini kullanabilir.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/q3-2017-update/).

### <a name="release-2017-09-21"></a>Sürüm 2017-09-21

- **Akış Geçmişini İndirme** - Bir akışın çalıştırma geçmişini CSV dosyası olarak indirip Excel'de açabilirsiniz.
- **Gelişmiş yineleme** - Akışlarınız için yalnızca hafta içi günlerde çalıştırma gibi yineleme zamanlamaları oluşturun.
- **IntelliSense** - IntelliSense ifade yazma sırasında parametre önerisinde bulunur.
- **Dört yeni bağlayıcı** - Azure AD HTTP hizmetleri, Amazon Redshift, Azure Event Grid Publish ve FlowForma bağlayıcıları eklendi.
- **Bağlantı paylaşımı** - OneDrive dosyaları veya Azure Depolama Blob'ları için paylaşılabilir bağlantı oluşturan yeni bir eylem.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/download-history-recurrence/).


### <a name="release-2017-08-25"></a>Sürüm 2017-08-25
* **SharePoint için belge özellikleri ve daha fazlası** - [SharePoint belge kitaplığı özelliklerini okuyup ayarlayın](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/) ve SharePoint öğesine yönelik bağlantılar gibi ek alanları kullanın.
* **Akış koleksiyonları** - Akış koleksiyonları role ya da dikeye göre düzenlenmiş şablon koleksiyonları kümesidir.
* **Düğme yeniden paylaşımı** - Düğmeleri paylaştığınız çalışma arkadaşlarınız bu düğmeleri başka kişilerle paylaşabilir.
* **Düğmelerden liste toplama** - Kullanıcıların bir düğmeye dokunarak içinden seçim yapabileceği açılan seçenek listeleri tanımlayın.
* **Yedi yeni bağlayıcı** - AWeber, Azure Log Analytics, Azure Tables, DocFusion365, Azure Event Grid, Azure Event Hubs ve StaffHub. 
* **Slack ve MySQL geliştirmeleri** - Slack içinde kanal oluşturduğunuzda veya kanalları birleştirdiğinizde MySQL veritabanlarına yazabilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/button-updates-seven-connectors/).

### <a name="release-2017-08-02"></a>Sürüm 2017-08-02
* **Kişi, Seçim ve Arama alanlarına yazma**: SharePoint’in Öğe oluştur ve Öğeyi güncelleştir eylemleri artık Kişi, Seçim ve Arama alanlarını ayarlama [özelliğini destekler](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/).
* **Daha fazla eylem ayarı**: Artık yeniden deneme ilkelerini ve sayfalandırmayı yapılandırma dahil olmak üzere tetikleyici ve eylemlerin çalışma şekli üzerinde daha yüksek bir denetim düzeyi sağlanabilir.
* **Dört yeni bağlayıcı**: Artık Azure Dosya Depolama, Elastic Forms, Plivo ve Video Indexer’ı kullanabilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/four-connector-action-settings/).

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Sürüm 2017-07-27 - Microsoft Flow Ç2 Güncelleştirmesi
* **İçeri ve dışarı aktarma**: Akış çözümlerini farklı ortamlar arasında veya test ile üretim arasında içeri ve dışarı aktarın. 
* **Eylemlerde ifade kullanın**: Herhangi bir eyleme ifade girdiğinizde, ifadelerin nasıl kullanılacağına ilişkin satır içi yardım alırsınız.
* **Azure Logic Apps boyutuna çıkın**: Akışlarınızı Visual Studio veya Azure portalı üzerinden dağıtılabilen bir Azure Logic Apps kaynağı olarak kaydedin.
* **Yönetici görünürlüğü**: Akışların tam olarak nerede ve nasıl kullanıldığını anlamak için kiracınızdaki Microsoft Flow kullanımı bilgilerini indirin.
* **Dynamics 365’te akışlar**: Dynamics 365 for Operations & Financials, Business Edition içinde akışları kullanın.
* **Senaryoları daha kolay bulun**: Bağlayıcıların yapabileceği her şeye göz atın ve akış oluşturmak için dilediğiniz tetikleyiciyi bir sıçrama noktası olarak kullanın.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/q2-2017-update/).

### <a name="release-2017-07-13"></a>Sürüm 2017-07-13
* **Geliştirilmiş şablon yayımlama**: Oluşturduğunuz akışlardan dilediğinizi kategorileriyle birlikte genel galeriye yayınlayın.
* **Outlook Takviminizdeki etkinlikleri alın**: Takviminizde iki zaman arasındaki tüm etkinlikleri döndürmeye yönelik yeni bir eylem.
* **Yeni mobil işlevsellik**: Mobil uygulamada isteğe bağlı olarak akışlar çalıştırın ve başarısız çalıştırmaları yeniden gönderin.
* **Özel bağlayıcılarda dinamik açılan listeler**: Dinamik açılan listeler ve yoklama tetikleyicileri oluşturarak özel bağlayıcılarınızı sınayın.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/publishing-and-custom-connectors/).

### <a name="release-2017-06-28"></a>Sürüm 2017-06-28
* **Dil ayarlarınızı güncelleştirme** - Microsoft Flow’un kullanacağı Dil ve Bölge seçeneklerini Ayarlar menüsü üzerinden özelleştirebilirsiniz.
* **Beş yeni bağlayıcı** -Adobe Creative Cloud, Bing Haritalar, Bing Arama, JotForm ve Freshservice desteği eklendi.
* **Zaman aşımlarını yapılandırma** - Onaylar gibi uzun süre çalışan eylemlerin, akışın devam edeceği “zaman aşımı” noktasından önce çalışacağı süreyi ayarlayabilirsiniz.
* **Outlook’ta onaylara yorum ekleyin**: Bir onay isteği aldığınızda, Outlook’tan çıkmadan yorum sağlayabilirsiniz.
* **Özel bağlayıcı markası renkleri** - Artık Özel Bağlayıcılarınız için arka plan işlemlerinde kullanılacak bir renk girebilirsiniz.
* **Ekip akışları için Farklı Kaydet seçeneği** - Ekip akışları dahil dilediğiniz akışın kopyalarını oluşturun
* **Akış silme bilgileri** - Bir akışı sildiğinizde, ilgili akış için bekleyen tüm çalıştırmaların listesi gösterilir.
* **Bağlayıcılar sayfasını filtreleme** - Bağlayıcılar sayfasında istediğiniz aracılar için arama yapın ve bağlayıcı türüne göre filtre uygulayın.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/language-settings-3-connectors/).

### <a name="release-2017-06-19"></a>Sürüm 2017-06-19
Artık, sizin tarafınızdan gönderilen ve onay bekleyen tüm isteklerin durumunu görüntüleyebilirsiniz. Ayrıca, onay bekleyen isteklerinize doğrudan mobil cihazınızdan göz atabilir ve bunlarla ilgili eylem gerçekleştirebilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/sent-requests-flow-mobile/).

### <a name="release-2017-06-15"></a>Sürüm 2017-06-15
* **İçerik dönüştürme** -  HTML içeriğini düz metne çevirmenize olanak tanıyan ve HTML olarak biçimlendirilmiş e-postalar için kullanışlı olan yeni bir bağlayıcı.
* **Üç yeni veritabanı bağlayıcısı** - MySQL, PostgreSQL ve Teradata için salt okuma desteği eklendi. Bu bağlayıcılar, Şirket içi veri ağ geçidi aracılığıyla bağlanır.
* **Üç bağlayıcı daha** - Azure Application Insights, Calendly ve Teamwork Projects’e bağlanın.
* **Hata işleme için daha iyi görselleştirme** - Hatalardan sonra çalışan adımlar, kolayca tanımlayabilmeniz için artık kırmızı noktalı oklarla gösteriliyor.
* **Çalıştırma ayrıntıları bölmesi** - Bir akış başarısız olduğunda, sorunu nasıl düzeltebileceğinize ilişkin bazı kullanışlı adımları sağ taraftaki yeni bölmede görebilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/seven-connectors-and-html/).

### <a name="release-2017-06-04"></a>Sürüm 2017-06-04
* **Windows Phone için genel kullanılabilirlik** - [Microsoft Flow mobil uygulaması, Windows Phone için Genel Kullanıma sunuldu](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **Akış hatası oluşunca e-posta alma** - Akışlarınızdan biri başarısız olduğunda e-posta aracılığıyla bildirim alabilirsiniz. Bu hata e-postaları, yalnızca haftada bir kez gönderilir. Kullanıcı bu seçeneği istediği zaman açabilir veya kapatabilir.
* **Tablolar için Seçme eylemi** -  Tablolara eklenecek sütunları değiştirmek için yeni Seçme eylemini kullanın.
* **Microsoft Forms bağlayıcısı** - Microsoft Forms, öğretmen ve öğrencilerin özel testler, anketler ve kayıtlar gibi kaynakları hızla ve kolayca oluşturmasına olanak tanıyan yeni bir Office 365 Eğitim özelliğidir.
* **Office 365 Kurumsal K1 planı** - PowerApps ve Microsoft Flow, belirli kotalar uygulanarak Office 365 Kurumsal K1 planına eklendi.
* **HTTP üst bilgileriyle ilgili işlemler artık daha kolay** - Seçme eyleminde olduğu gibi, yalnızca eylemdeki metin kutularını doldurarak bir üst bilgi adı ve üst bilgi değeri sağlayabilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/).

### <a name="release-2017-05-23"></a>Sürüm 2017-05-23
* **Microsoft Teams bağlayıcısı** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/), Office 365’te insanların, konuşmaların ve içeriğin yanı sıra ekiplerin ihtiyacı olan araçları da bir araya getirerek daha fazlasını başarmak için kolayca işbirliği yapabilmelerini sağlayan, sohbet tabanlı bir çalışma alanıdır.
* **iOS ve Android üzerinde pencere öğeleri** - Microsoft Flow pencere öğeleri, doğrudan giriş sayfanızdan düğmeleri tetiklemenin daha kolay ve daha hızlı bir yolunu sağlayan düğme kısayollarıdır.
* **"Hata işleme" adımları oluşturma** -  Eylem başarısız olduğunda çalıştırılmak üzere bir veya birden çok adım tanımlayın. Örneğin, akışınız Dynamics 365’te kayıt oluşturamazsa hemen bir bildirim alın.
* **Tamsayı ve kayan değişkenler** - Belirli bir mantık kümesinin kaç kez çalıştırıldığını saymak için akış çalıştırması içindeki sayaçları başlatın ve artırın veya azaltın.
* **Akış ayrıntıları sayfası** - **Akışlarım** listenizde bir akış seçtiğinizde, söz konusu akış hakkındaki ayrıntıları (erişimi olan kişiler ve çalıştırma geçmişi gibi) içeren bir sayfa görürsünüz.
* **Yöneticiler için akış çalıştırma kotaları** - Yöneticiler şimdi kuruluş genelindeki akış çalıştırma kullanımını ortak şirket çalıştırma kotası açısından izleyebilir ve kotaya hangi lisansların katkıda bulunduğunu anlamak için kotanın dökümünü alabilir.
* **HTTP istek tetikleme geliştirmeleri** - Farklı HTTP yöntemleri kullanın ve İstek tetikleyicisi için yol kesimleri ekleyin.
* **İki iş ortağı bağlayıcısı** - Microsoft Flow şimdi e-posta ayrıştırma hizmeti Parserr’a ve çevrimiçi form hizmeti Cognito Forms’a bağlanabilir.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/error-handling/).

### <a name="release-2017-05-12"></a>12.05.2017 sürümü
* **SharePoint Belge Kitaplıkları tümleştirmesi** - Bir belge kitaplığında herhangi bir dosya seçerek akış başlatabilir ve bu akışı, onay için yöneticinize gönderme gibi [pek çok amaçla](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/) kullanabilirsiniz.
* **Microsoft Planner bağlayıcısı** - Microsoft Planner’ı kullanarak, daha iyi sonuçlar elde etmek için ekip, görev, belge ve konuşmaları kolayca bir araya getirebilirsiniz.
* **Lisanslar için yönetici görünümü** - Yöneticiler Microsoft Flow Yönetim Merkezi’nde tüm Microsoft Flow ve PowerApps lisanslarını (hem deneme sürümü hem de ücretli sürüm) görebilir.
* **PowerApps Topluluk Planı** - PowerApps Topluluk planı, kullanıcıların PowerApps, Microsoft Flow ve Common Data Service’e yönelik becerileri araştırması, öğrenmesi ve oluşturması için sunulan ücretsiz bir plandır.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/planner-community-and-licenses/).

### <a name="release-2017-05-09"></a>Sürüm 2017-05-09
* **Azure AD bağlayıcısı** - Microsoft Flow’dan yönetici eylemlerini gerçekleştirmek, örneğin kullanıcı oluşturmak veya kullanıcıları gruplara eklemek için yeni bir bağlayıcı vardır.
* **Office 365 Outlook geliştirmeleri** - Akışlar artık Paylaşılan Posta Kutuları tarafından tetiklenebilir ve Paylaşılan Posta Kutusu’na posta gönderebilir. Ayrıca otomatik yanıtları ayarlayabilir veya okuyabilir.
* **Kanada’da kullanılabilir** - Artık Kanada’da kendi akışlarınızı oluşturabilirsiniz.
* **Özel API web kancaları oluşturma** - Özel bağlayıcı sağlayıcıları artık web kancalarıyla kendi özel API’lerine tetikleyiciler ekleyebilir.
* **Yönetim merkezinde akış sahiplerini yönetme** - Ortam yöneticileri Microsoft Flow yönetim merkezinde akış sahiplerini yönetebilir.
* **Bağlayıcı belgeleri başvurusu** -  Artık [docs.microsoft.com’da eksiksiz bir bağlayıcı başvurumuz](https://docs.microsoft.com/Connectors/) vardır.
* **İki iş ortağı hizmeti** - İki yeni iş ortağı hizmeti kullanıma sunuldu: Nexmo ve Paylocity.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/canada-mailboxes-aad).

### <a name="release-2017-04-27"></a>Sürüm 2017-04-27
* **Paralel adımlarla akışları oluşturma** - Paralel yürütmeyle akışları oluşturma: iki veya daha çok adımı tam olarak aynı anda çalıştırabileceğiniz anlamına gelir.
* **Desteklenen beş yeni hizmet** - Beş yeni hizmet: Onaylar, Karşılaştırma E-postası, Capsule CRM, LiveChat ve Outlook Customer Manager.
* **Eylemler için yeniden denemeleri izleme** - Hizmetlerde hatalar olduğunda Microsoft Flow yeniden deneyecektir. Şimdi kaç otomatik yeniden deneme yapıldığını ve olayların ayrıntılarını görebilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/parallel-actions/).

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Sürüm 2017-04-17 - Microsoft Flow Ç1 Güncelleştirmesi
* **Modern onay deneyimleri** - Onaylayanların Microsoft Flow mobil uygulamasının içinden veya Microsoft Flow web sitesindeki birleştirilmiş onay merkezinden güvenle onaylayabilecekleri iş akışları oluşturun.
* **Ekip akışları genel kullanılabilirliği** - Artık genel kullanıma sunulan ekip akışlarıyla, birden çok kişi birlikte bir akışın sahibi olabilir ve akışı yönetebilir.
* **Microsoft Flow için bağlayıcılar oluşturma** - Herkes, dünyanın geri kalanında kullanılması için kendi ücretsiz Microsoft Flow bağlayıcısını gönderebilir.
* **"Diyet" tasarımcısı** - Tasarımcının yeni sürümü, bazı şablonlarda yalnızca akışı oluşturmak için gereken alanları göstererek deneyimi basitleştirir.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/q1-2017-update/).

### <a name="release-2017-04-11"></a>Sürüm 2017-04-11
* **Tabloları ve listeleri oluşturmaya yönelik yeni eylemler** - Öğe listelerini işleyebilen yeni HTML Tablosu Oluştur, CSV Tablosu Oluştur ve Birleştir eylemleri (daha önce Her birine uygula yerine).
* **Her yere adım ekleme** - Artık sürükleyip bırakmanız gerekmeden iş akışının her yerine yeni adım ekleyebilirsiniz.
* **Dört yeni hizmet** - Flow artık, 10 to 8 Scheduling, Act!, Inoreader ve Görüntü İşleme API’sini destekliyor. Görüntü İşleme API’si ile, metin içeriğini almak için resimleri işleyebilir (OCR olarak bilinir) veya resimleri içeriği temelinde otomatik olarak etiketleyebilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/).

### <a name="release-2017-04-03"></a>Sürüm 2017-04-03
* **Windows Phone Beta** - Windows Phone cihazınızdaki uygulamanın önizlemesini almak için Windows Phone App beta programı sağlanır. [Daha fazla bilgi edinin](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **Muhimbi PDF** - Muhimbi PDF ile artık Microsoft Word dosyalarını PDF’ye dönüştürebilir, filigranlar ekleyebilir, belgeleri birleştirebilir ve daha bir çok şey yapabilirsiniz. [Daha fazla bilgi edinin](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **Fiziksel düğmelerden akışları tetikleme** - Fiziksel düğme alanında lider konumdaki ürünlerden ikisiyle iş ortaklığı duyuruldu: Shortcut Labs’ten Flic ve The Button Corporation’dan Bttn. [Daha fazla bilgi edinin](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Sürüm 2017-03-22
* **Akışınızın kopyasını alma** - Artık taslak sürümler üzerinde çalışmak için akışınızın kopyasını alabilir veya geçmişte oluşturduğunuz bir akışı çoğaltabilirsiniz.
* **İki yeni hizmet** - Görevleri oluşturarak ve güncelleştirerek yapılacaklar listenizi yönetmeye yönelik Toodledo desteğiyle, bir müşteri hizmetleri ve destek bileti oluşturma platformu sağlayan Zendesk desteği ekleniyor.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/make-a-copy/).

### <a name="release-2017-03-15"></a>Sürüm 2017-03-15
* **Çalışma arkadaşlarıyla düğme paylaşma** - Akış düğmelerini başka kişilerle paylaşarak tüm işletme kullanıcılarının hızlı görevler gerçekleştirmesini kolaylaştırabilirsiniz.
* **Giriş ekranından düğme tetikleme** - Giriş ekranına ve mobil ekranların kilit ekranlarına eklenebilen akış düğmesi kısayolları, akış tetiklemeyi önemli ölçüde hızlandırır.
* **Microsoft Flow uygulamasındaki ekip akışları** - iOS veya Android için Microsoft Flow uygulamasında, başkalarına ait akışları görebilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/button-sharing/).

### <a name="release-2017-03-10"></a>Sürüm 2017-03-10
* **Geliştirilmiş özel bağlayıcı deneyimi** - Artık özel bağlayıcı oluşturmak ve eylemleri düzenlemek, eklemek ve test etmek için Postman Collection dosyası kullanabilirsiniz.
* **İki yeni hizmet** - PowerApps Bildirimleri ve PivotalTracker desteği eklendi.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/new-updates-custom-api/).

### <a name="release-2017-02-27"></a>Sürüm 2017-02-27
* **Akış düğmelerinizi tetikleme** - Akış düğmelerinizi doğrudan Microsoft Flow web sitesinden tetikleyebilirsiniz. Akış listeniz görüntülendiğinde, "..." menüsünü ve ardından Şimdi çalıştır komutunu seçin.
* **Beş yeni hizmet** - Oracle Database, Intercom, FreshBooks, LeanKit ve WebMerge desteği eklendi.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/trigger-flow-buttons-web/).

### <a name="release-2017-02-21"></a>Sürüm 2017-02-21
* **Ortam akışlarını görüntüleme** - Ortam yöneticileri, belirli bir ortamdaki tüm akışların listesini görüntüleyebilir, akışları etkinleştirebilir, devre dışı bırakabilir ve silebilir.
* **İki yeni hizmet** - Azure Otomasyonu ve Basecamp 2 desteği eklendi.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/).

### <a name="release-2017-02-16"></a>Sürüm 2017-02-16
* **Beş yeni hizmet** - Azure Data Lake, Bitbucket (GIT sürüm denetimi kullanan projeler için web tabanlı bir barındırma hizmeti), Eventbrite, Infusionsoft ve Pipedrive desteği eklendi.
* **Özel HTTP kimlik doğrulaması** - Akış tasarımcısında, özel HTTP uç noktalarıyla kimlik doğrulama kullanılabilir.
* **JSON iletilerini ayrıştırma** - HTTP İsteği tetikleyicisinden edinilen ya da HTTP işleminden döndürülen JSON verilerini ayrıştırabilirsiniz.
* **Akış çalıştırmasını filtreleme** - Akış çalıştırma işlemleri için Çalışan akışlar veya İptal edilen akışları görme seçeneği de dahil olmak üzere daha belirgin seçenekler içeren geliştirilmiş filtreleme.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/).

### <a name="release-2017-02-06"></a>Sürüm 2017-02-06
* **Takım akışları** - Takım akışları, birden çok kişinin birlikte bir akışın sahipliğini üstlenmesine ve akışı yönetmesine olanak sağlar. Böylece bir kişi kuruluştan ayrılırsa bu kişinin oluşturduğu akışlar çalışmaya devam edebilir.
* **Özel bağlayıcıları paylaşma** -takım akışları gibi özel bağlayıcılar kuruluş içinde paylaşılabilir ve kolektif olarak yönetilebilir.
* **Gmail ve LUIS desteği** - Gmail ve Azure Bilişsel Hizmetler Language Understanding Intelligent Service’e bağlanın.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/team-flows/).

### <a name="release-2017-01-30"></a>Sürüm 2017-01-30
* **Akış düğmesi girişleri** - Akış düğmeleri artık çalıştırma zamanında kullanıcı girişlerini alabilir. Böylece akış yazarları, düğmeye dokunulduğunda iletilen bilgileri tanımlayabilir.
* **Outlook Görevleri ve HelloSign** - Outlook Görevleri hizmeti, görevleri yönetmenize ve HelloSign, güvenli elektronik imzaları etkinleştirmenize olanak sağlar.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/button-user-inputs/).

### <a name="release-2017-01-23"></a>Sürüm 2017-01-23
* **Hizmete göre arama** - Tetikleyici ya da eylem eklerken, her hizmete ilişkin tüm eylemleri görmek için hizmete göre gözatın.
* **Durum değiştir** - Çok sayıda paralel mantık dalına sahip olmak için Durum blokları ekleyin.
* **Daha fazla e-posta eylemi** - Office 365 Outlook ve Outlook.com hizmetlerinde bayrak eklenmiş postalarla çalışmaya yönelik yeni işlevler.
* **Beş yeni hizmet** - Yerel veya Ağ Dosya Sistemleri, Stripe ödeme hizmeti , IBM Informix, IBM DB2 ve UserVoice’a bağlanın.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/search-by-service/).

### <a name="release-2017-01-14"></a>Sürüm 2017-01-14
* **Çalıştırmaları yeniden gönderme** - Başarısız olan bir akışı düzeltip yeniden çalıştırmak isterseniz, başarısız çalıştırmayı yeniden gönderebilirsiniz.
* **Çalıştırmaları iptal etme** - Artık, bir akış takıldığında çalıştırmayı açıkça iptal edebilirsiniz.
* **İki yeni hizmet** - GoToTraining ve GoToWebinar desteği eklendi.
* **Mobil bağlantılar** - Doğrudan mobil uygulamadan şablon paylaşabilirsiniz. Bunun yanı sıra web sitesinin üst kısmına uygulamalar için hızlı indirme bağlantısı eklendi.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/managing-runs/).

### <a name="release-2016-12-29"></a>Sürüm 2016-12-29
Microsoft Flow artık, elektronik imza ve Dijital İşlem Yönetimi için DocuSign’ı, web tabanlı anketler için SurveyMonkey’i ve OneNote not alma uygulamasını (yalnızca iş hesapları için) destekliyor.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/final-2016-services/).

### <a name="release-2016-12-20"></a>Sürüm 2016-12-20
* **Şimdi çalıştır** - Artık, yinelenen bir tetikleyiciyi isteğe bağlı olarak gönderebilirsiniz. Örneğin, her gün için zamanlanmış bir raporunuz varsa ancak raporun **şimdi** de çalıştırılması gerekiyorsa, bu özelliği kullanabilirsiniz.
* **Altı yeni hizmet** - MSN Weather, Medium, Google Contacts, Buffer, Harvest ve TypeForm’a bağlanan akışlar oluşturun.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/run-now-and-six-more-services/).

### <a name="release-2016-12-14"></a>Sürüm 2016-12-14
Artık, bir düğme akışını tetiklerken düğmenin nereden, kim tarafından ve ne zaman tetiklendiği gibi değerli bilgilerden yararlanabilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/button-trigger-tokens/).

### <a name="release-2016-12-06"></a>Sürüm 06.12.2016
* **Destekli Öğrenme Tanıtımı** - Microsoft Flow’un kapsamlı ve güçlü özelliklerini anlamanıza yardımcı olacak video ve belgeleri birlikte sunan sıralı bir kurs koleksiyonu ile öğrenmeye başlayın.
* **İki yeni hizmet** - Akışlar artık bir müşteri destek çözümü olan Freshdesk ve bir çevrimiçi toplantı aracı olan GoToMeeting kullanabilir.
* **HTTP Web Kancası desteği** - Bir akış artık, otomatik olarak kendini kaydeden ve kaydını kaldıran, web kancalarına yönelik bir uç nokta olabilir.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/guided-learning-and-two-services/).

### <a name="release-2016-11-23"></a>Sürüm 23.11.2016
* **Flow’da Power BI uyarı desteği** - Power BI veri uyarılarından akışları tetikleyerek bilgileri eyleme dönüştürün.
* **Mobil uygulama geliştirmeleri** - .Sunulmakta olan şablonlardan akış oluşturma deneyimine ek olarak, sıfırdan akış oluşturma özelliği eklendi. Ayrıca akış çalıştırmalarını görüntüleme performansı iyileştirildi.
* **Sekiz yeni hizmet** - Azure Resource Manager, Azure Kuyrukları, Chatter, Disqus, Azure DocumentDB, Bilişsel Hizmetler Yüz Tanıma API’si, HipChat ve Wordpress hizmetlerine bağlanabilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/).

### <a name="release-2016-11-15"></a>Sürüm 15.11.2016
* **Microsoft Flow İş Ortağı Programı** - Microsoft Flow, bağlantı kurmak ve Microsoft Flow ile dünyanın her yerinden farklı şirketlerin yetenek ve deneyimlerinden yararlanmak için bir sertifikalı iş ortağı programı sunuyor.
* **Altı yeni hizmet** - Bu hafta altı hizmeti daha kullanıma sunuyoruz: Asana, Campfire, EasyRedmine, JIRA, Redmine ve Vimeo.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/partner-program-six-new-services/).

### <a name="release-2016-10-31---general-availability"></a>Sürüm 2016-10-31 - Genel Kullanılabilirlik
* **Fiyatlandırma ve lisans** - Artık hem ücretsiz hem de ücretli planlar kapsamındadır, Office 365 ve Dynamics 365’e dahildir.
* **Microsoft Flow Yönetim Merkezi** - Yeni Yönetim Merkezi ile kurumsal kullanıma hazırdır. Yönetim Merkezi’nde kuruluş dahilindeki ortamları yönetebilirsiniz.
* **Veri kaybı önleme ilkeleri** - Yöneticiler, hizmetler arasında veri akışını denetlemek için veri kaybı önleme ilkeleri oluşturabilir.
* **Android ile kullanılabilirlik** - Microsoft Flow telefon uygulaması artık hem iOS hem de Android’de kullanılabilir. Uygulama tek bir düğmeye dokunarak bildirimleri almanıza, etkinlikleri izlemenize ve akışları başlatmanıza olanak tanır.
* **Yeni tasarımcı deneyimleri** - Artık, iletilen dinamik içeriklerde adım adım arama yapabilir, böylece istediğiniz verilere daha hızlı başvurabilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/announcing-ga/).

### <a name="release-2016-10-26"></a>Sürüm 2016-10-26
* **Düğme akışları** - Dilediğimiz zaman ve dilediğimiz yerde tetikleyebilmek istediğimiz sayısız işlem vardır. Düğme Akışları ile bundan böyle bu işlemleri mobil cihazınızdan tek bir tıklamayla gerçekleştirebilirsiniz.
* **Duyuru ortamları** - Ortamlar, kuruluşunuzun akışlarını depolayıp yönetmeye yönelik özel alanlardır. Ortamlar coğrafi olarak konumlandırılmıştır; diğer bir deyişle bir ortamda bulunan akışlar, uygulamalar ve iş verileri ortamın bulunduğu bölgede olacaktır.
* **Altı yeni hizmet** - Bit.ly, Bilişsel Hizmetler Metin Analizi, Dynamics NAV, Dynamics 365 for Financials, Instapaper ve Pinterest desteği eklendi.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/environments-for-makers/).

### <a name="release-2016-10-16"></a>Sürüm 2016-10-16
* **Özel bağlayıcılar daha fazla kimlik doğrulama türünü destekliyor** - Artık özel bağlayıcılar API Anahtarı kimlik doğrulamasını destekliyor ve tam OAuth 2.0 belirtimini destekleyen tüm hizmetlerde kimlik doğrulaması yapabiliyor.
* **Üç yeni hizmet destekleniyor** - Basecamp 3, Blogger ve PagerDuty için destek vermeye başladık.
* **Tasarımcı iyileştirmeleri** - Gelişmiş performans sayesinde artık her eylem için “...” menüsünden bağlantılarınızı güncelleştirebilir ve onarabilirsiniz. Ayrıca, akışın çalıştırmasını sonlandırmak için kullanabileceğiniz Sonlandır adında yeni bir adım ekledik.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/early-october-updates/).

### <a name="release-2016-09-25"></a>Sürüm 2016-09-25
Artık cep telefonunuzdan akış oluşturabilirsiniz. Zengin şablon galerimize göz atın, hizmet listemizde gezinin veya ayrıntılı olarak incelemek istediğiniz bir şablon kategorisi seçin. Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/mobile-creation/).

### <a name="release-2016-09-22"></a>Sürüm 2016-09-22
* **Microsoft Graph Kişi Seçici** - Doğru kişiyi veya e-posta adresini seçmenize yardımcı olmak için Microsoft Flow kullanıcı arabirimi ile yeni bir Microsoft Graph kişi seçici tümleştirilmiştir.
* **Microsoft Dynamics AX desteği** - Artık akışlarınızın içinden, yeni kayıtlar oluşturmak ve verileri sorgulamak gibi Dynamics AX Online işlem verilerinizle ilgili eylemler gerçekleştirebilirsiniz.
* **İş ortaklarından iki yeni hizmet** - Artık akışlarınızda appFigures veya Insightly’yi kullanabilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/more-september-updates/).

### <a name="release-2016-09-14"></a>Sürüm 2016-09-14
* **Web sitesine veya uygulamanıza ekleme** - Geliştiriciler, kullanıcılarına kişisel veya profesyonel görevlerini otomatik hale getirmenin kolay bir yolunu sunmak için artık Microsoft Flow’u uygulamalarına veya web sitelerine ekleyebilir.
* **Bir akışı HTTP uç noktası olarak kullanma** - Artık bir akışı HTTP API’si olarak kullanabilirsiniz. Akışın içinde İstek adında bir tetikleyici bulunur. Bir Yanıt kartı ekleyerek gelen isteği yanıtlamayı seçebilirsiniz.
* **Todoist desteği** - Todoist, ister iş yerinizde ister evinizde tüm projelerinizi ayrıntılı şekilde incelemenizi sağlar.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/extend-web-site-application/).

### <a name="release-2016-09-01"></a>Sürüm 2016-09-01
Artık herkes Microsoft Flow’u kullanabilir - Önizleme sürümünü, başlangıçta yalnızca iş yeriniz veya okulunuz tarafından verilen, Office 365 İş veya Office 365 Kurumsal gibi e-posta adreslerinin kullanımına sunmuştuk. Bugün, e-posta adresleri ne olursa olsun tüm kullanıcıların önizleme sürümünü ücretsiz bir şekilde kullanılabileceğini duyuruyoruz. Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/available-for-everyone/).

### <a name="release-2016-08-31"></a>Sürüm 2016-08-31
* **İç içe geçmiş koşullar** - Artık bir koşulun içine ikinci (veya üçüncü vb.) bir koşul ekleyebilirsiniz.
* **Her birine uygula** - Her birine uygula döngüsü, yinelediğiniz listeleri denetlemenizi sağlar.
* **Do-until** - Do-until döngüsü, bir döngüyü belirli bir koşul karşılanana kadar yinelemenizi sağlar.
* **Filtre dizileri** - Listedeki her öğenin belirlediğiniz ifadeyle eşleştiğini doğrulayabilen tek bir yerel filtre adımı bulunur.
* **Dize değişkenleri oluşturma** - Artık bir dize değişkeni oluşturabilirsiniz.
* **Kapsamlar** - Kapsamlar, iki veya daha fazla eylemi gruplandırmanın kolay yoludur.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/build-advanced-flows/).

### <a name="release-2016-08-27"></a>Sürüm 2016-08-27
* **Adımlarla ilgili açıklamalar** - Açıklamalar, akışların ihtiyaçlarını kolayca hatırlayabilmeniz için eylemlere not eklemenizi kolaylaştırır.
* **Smartsheet desteği** - Bu hafta, Smartsheet ile bağlantı kurma desteği ekledik. Smartsheet, buluttaki sayfalarda işbirliği yapmayı kolaylaştıran bir hizmettir.
* **Akış yazmaya yönelik kullanıcı arabirimi iyileştirmeleri** - Akış adını ön plana çıkardık ve kaydet düğmesini kolayca erişilmesi için sayfanın en üstüne taşıdık.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/add-comments-smartsheet/).

### <a name="release-2016-08-18"></a>Sürüm 2016-08-18
Artık Microsoft Flow tümleştirmesini içeren yeni SharePoint Online modern listeleri deneyimini önizleyebilirsiniz. Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/).

### <a name="release-2016-08-13"></a>Sürüm 2016-08-13
* **Visual Studio Team Services** - Artık Flow’u kullanarak VSTS’yi O365 E-posta, Slack, Trello ve Wunderlist gibi çeşitli hizmetlere bağlayabilirsiniz.
* **SharePoint geliştirmeleri** - SharePoint listeleri, Tek satırlık metinler ve Tarih ve Saat gibi basit nesnelerden Kişi veya Grup, Arama ve Seçim gibi karmaşık nesnelere kadar çeşitli veri türlerini destekler.
* **O365 Outlook Bağlantılarını test etme** - Yeni bir O365 Outlook bağlantısı oluşturduğunuzda, bağlantıyı kullanmaya hazır olduğunuzu kontrol etmek için artık bu testi yapacağız.
* **Boole Denetimi** - Boole giriş alanları için girmeniz gereken değerleri (ör. Yeni bir e-posta geldiğinde tetikleyicisinde Ek Var) belirlemeniz için bir boole denetimi ekledik.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/).

### <a name="release-2016-08-08"></a>Sürüm 2016-08-08
Microsoft Flow ile tümleştirilen Microsoft Common Data Service’in genel önizlemesi. Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/flow-and-common-data-model/).

### <a name="release-2016-08-05"></a>Sürüm 2016-08-05
* **SharePoint Şirket İçi** - SharePoint Online’da olduğu gibi, önceden tanımlanmış şablonları kullanarak veya sıfırdan şablon oluşturarak SharePoint şirket içi listelerinde ve belge kitaplıklarında akışlar oluşturabilirsiniz.
* **Tasarımcıda bilgi balonları** - Her tetikleyicinin ve eylemin özelliklerini ayrıntılı olarak incelemeniz için akışınızdaki her adımın üzerine bilgi balonları ekledik.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/).

### <a name="release-2016-07-15"></a>Sürüm 2016-07-15
* **Dört yeni hizmet eklendi** - Google Takvim, Google Görevleri, YouTube ve SparkPost’a bağlanın.
* **Eylemlerinizi yeniden adlandırma** - Artık farklı eylemleri yeniden adlandırarak birbirinden ayırt edebilirsiniz.
* **Farklı sürelerde geciktirme** - Artık Saniye, Dakika veya Gün için istediğiniz sayıyı seçebilirsiniz.
* **Kullanımı daha kolay klasör tarayıcı** - Klasör tarayıcıyı basitleştirdik. Artık sol tarafta yaptığınız seçim bu klasörün seçilmesini, sağ tarafta yaptığınız seçim ise klasörü açarak içindeki alt klasörlerin seçilmesini sağlar.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/new-google-services-rename-more/).

### <a name="release-2016-07-08"></a>Sürüm 2016-07-08
Microsoft Flow için şirket içi veri ağ geçidini kullanarak şirket içi bağlantı oluşturma. Bu, SQL Server ile güvenli bağlantılar oluşturmanızı ve bunları akışlarınızla tümleştirmenizi sağlar. Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/on-premises-data-gateway/).

### <a name="release-2016-07-02"></a>Sürüm 2016-07-02
* **Google E-Tabloları desteği** - Bugüne kadar hem Excel’i hem de Google Drive’ı kullanabiliyorduk. Bu hafta, yerel Google E-Tablolar desteği de sunmaya başlıyoruz.
* **Şablonlardan daha hızlı başlangıç yapma** - Şablonları kullanmaya başlarken yaparken izlediğiniz yolda da bazı iyileştirmeler yaptık. Artık şablon için kullanmak istediğiniz hesapları, şablon sayfasının içinden seçebilirsiniz.
* **SharePoint ve Office 365 için süresi dolan yetkilendirme yok** - Artık Microsoft Flow, Azure Active Directory tabanlı hizmetlere erişiminizi otomatik olarak yenileyecektir. Böylece tüm akışlarınız, parola değişikliklerinden sonra çalışmaya devam edecektir.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/more-june-updates/).

### <a name="release-2016-06-20"></a>Sürüm 2016-06-20
* **Microsoft Flow için yeni mobil uygulama kullanıma hazır** - Bugün, büyük bir memnuniyetle hizmetimizin önemli bir parçasını daha kullanıma sunuyoruz: Artık iOS’a (yakında Android’de de kullanıma sunulacaktır) otomatik iş akışlarınızı istediğiniz zaman istediğiniz yerden yönetmenizi, izlemenizi ve keşfetmenizi sağlayan mobil bir uygulama indirebilirsiniz.  
* **Çoklu oturum açma** - Microsoft Flow’da kimliğinizi Office 365 gibi diğer Microsoft hizmetleriyle doğrulamanızı sağlayacak çoklu oturum açma özelliğini uygulamaya başladık.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/).

### <a name="release-2016-06-18"></a>Sürüm 2016-06-18
* **Yeni Posta hizmeti** - Artık Microsoft Flow’un içinde kişisel veya iş e-posta hesaplarınıza bağlanmak zorunda kalmadan, doğrudan Microsoft Flow’dan e-posta gönderebilirsiniz.
* **Portalda bildirimler** - Artık akışlarınızda bir sorun olduğunda portalın en üstünde Bildirimler göreceksiniz.
* **Portalda Tüm Etkinlikler** - Artık akış web sitesinde yeni Etkinlik sekmesine tıklayarak tüm akışlarınızdaki etkinlikleri görebilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/mail-and-all-activity/).

### <a name="release-2016-05-27"></a>Sürüm 2016-05-27
* **Hizmete göre şablonlara göz atma** - Artık desteklediğimiz tüm hizmetleri (oturum açmak zorunda kalmadan) görmenizi sağlayacak bir yöntem var. Bu sayfada, her hizmetin açıklamasını görebilir ve bu hizmet için sunduğumuz şablonları inceleyebilirsiniz.
* **Özel bağlayıcılarınızı oluşturma ve kullanma** - Aynı PowerApps’te özel bağlayıcılar oluşturabildiğiniz gibi, flow.microsoft.com’da da kendi API’lerinize bağlanabilirsiniz:
* **Akışlarınızı tamamlamadan önce test etme** - Artık bir akışı kaydettiğinizde başlatma eylemini gerçekleştirirseniz akış çalıştırmasının sonuçlarını canlı olarak sayfada görebilirsiniz.

Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/).

### <a name="release-2016-05-07"></a>Sürüm 2016-05-07
İki yeni hizmet eklendi: Microsoft Project Online ve Mandrill by Mailchimp. Bu sürüm hakkında [daha fazla bilgi edinin ve soru sorun](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/).

### <a name="release-2016-04-27---public-preview"></a>Sürüm 2016-04-27 - Genel Önizleme
[Microsoft PowerApps](https://powerapps.microsoft.com)'in bir parçası olarak Logic akışlarını kullandıysanız Microsoft Flow Önizleme sürümü ile sunulan şu yeni özelliklere göz atın:

* Artık düzinelerce şablonun bulunduğu bir galeriye göz atabilmenin yanı sıra Popülarite, Ad veya yayımlama Tarihine göre sıralama yapabilirsiniz.
* Bir akışı özelleştirdikten sonra galeride [kendi şablonlarınızı yayımlayabilirsiniz](publish-a-template.md).
* Akışınızın tüm denetleme ve çalıştırma geçmişini görebilirsiniz.
* Bir akışı kaydettiğinizde, yalnızca tetikleyici eylemi gerçekleştirerek [akışı anında çalışırken izleyebilirsiniz](see-a-flow-run.md).
* Flow hakkında tartışabileceğiniz veya [fikirlerinizi paylaşabileceğiniz](https://go.microsoft.com/fwlink/?LinkID=787474) [yeni bir topluluğumuz](https://go.microsoft.com/fwlink/?LinkID=787467) var.

## <a name="next-steps"></a>Sonraki adımlar
Bu sürüm notlarında veya [SSS](frequently-asked-questions.md)'de değinilmemiş herhangi bir sorununuz varsa lütfen sorularınızı sormak için [topluluğumuza katılın](https://go.microsoft.com/fwlink/?LinkID=787467) veya [destek ekibi ile iletişime geçin](http://go.microsoft.com/fwlink/?LinkID=787479).

