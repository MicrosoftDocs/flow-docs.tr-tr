---
title: "Sık sorulan sorular | Microsoft Docs"
description: "Microsoft Flow hakkında sıkça sorulan birkaç sorunun cevabı"
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
ms.date: 03/15/2017
ms.author: stepsic
ms.openlocfilehash: 5b8deda5f22bcc1fa7cfa37a0d4244f26c2004a4
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="frequently-asked-questions"></a>Sık sorulan sorular
## <a name="audience-and-strategy"></a>Hedef kitle ve strateji
### <a name="what-is-microsoft-flow"></a>Microsoft Flow nedir?
Microsoft Flow, iş kolu kullanıcılarının zaman harcayan iş görevlerinin yanı sıra uygulama ve hizmetlerdeki süreçleri otomatikleştirmesini pratik ve kolay hale getiren bulut tabanlı bir hizmettir.

### <a name="who-is-the-intended-audience-for-microsoft-flow"></a>Microsoft Flow’un hedef kitlesi kimdir?
Microsoft Flow iki ayrı hedef kitleye sahiptir:

* İş çözümleri sorumluluğunu işletmeye yaklaştırmak için BT ile ortaklık kuran kuruluşlardaki iş kolu “Kullanıcı Tümleştiricileri”.
* BT uzmanları ve tümleştirme uzmanlarının, Azure Logic Apps gibi daha gelişmiş tümleştirme araçlarına odaklanabilmesini sağlamak amacıyla iş kolu ortaklarına kendi çözümlerini oluşturma yetkisi vermek isteyen, BT karar alma mekanizmaları.

### <a name="how-do-microsoft-flow-and-logic-apps-relate-to-each-other"></a>Microsoft Flow ile Logic Apps arasındaki ilişki nedir?
Microsoft Flow, iş kolu kullanıcılarının otomatik iş akışları oluşturmasına yardımcı olan özellikler sağlar. Logic Apps, Microsoft Flow’daki harika özelliklere ek olarak, Azure Resource Manager ve Azure portalı ile tümleştirme, PowerShell ve xPlat CLI, Visual Studio ve diğer bağlayıcıları kullanma gibi olanaklar sunan bir Azure hizmetidir. [Logic Apps hakkında daha fazla bilgi edinin](https://azure.microsoft.com/services/app-service/logic/).

### <a name="how-does-microsoft-flow-fit-in-microsofts-overall-business-application-platform-strategy"></a>Microsoft Flow, Microsoft’un genel iş uygulaması platformu stratejisine ne kadar uygundur?
Microsoft Flow; PowerApps, Common Data Service, Dynamics 365 ve Office 365’i kapsayan güçlü ve uyarlanabilir bir iş uygulaması platformunun parçasıdır. Bu platform müşterilerimiz, ortaklarımız ve ISV ortaklarımızın kendi şirketleri, sektörleri, işlevsel rolleri ve hatta belirli coğrafyalar için amaca uygun çözümler oluşturmasını sağlar. İş gereksinimlerini en iyi şekilde anlayan iş kolu kullanıcıları artık veri ve süreçleri kolayca çözümleyebilir, oluşturabilir ve kolaylaştırabilir. Profesyonel geliştiriciler, otomasyon, analiz ve uygulama iş kolu süreçlerini kolayca genişleterek İşlevler, App Service ve Logic Apps gibi Azure hizmetlerinden yararlanabilir. API bağlayıcıları, ağ geçitleri ve Microsoft Common Data Service, bulutta veya şirket içinde kullanılmakta olan hizmetlerden veya verilerden daha iyi yararlanmayı mümkün hale getirmektedir.

## <a name="functionality"></a>İşlevsellik
### <a name="what-do-i-need-to-use-microsoft-flow"></a>Microsoft Flow kullanmak için neler gerekir?
Microsoft Flow’u kullanmak için yalnızca bir web tarayıcısı ve bir e-posta adresi gereklidir.

### <a name="what-browsers-does-microsoft-flow-support"></a>Microsoft Flow hangi tarayıcıları destekliyor?
Microsoft Flow, Microsoft Edge'in yanı sıra, Chrome ve Safari'nin güncel sürümlerini destekler.

### <a name="which-email-addresses-are-supported"></a>Hangi e-posta adresleri desteklenir?
Microsoft Flow; .gov ve .mil dışındaki etki alanlarıyla biten e-posta adreslerini destekler.  

### <a name="is-microsoft-flow-available-on-premises"></a>Microsoft Flow, şirket içinde kullanılabilir mi?
Microsoft Flow yalnızca bir genel bulut hizmetidir. Ancak, şirket içi veri ağ geçidi ile kendi şirket içi hizmetlerinize güvenli bir şekilde bağlanabilirsiniz.

### <a name="what-services-can-microsoft-flow-connect-to"></a>Microsoft Flow hangi hizmetlere bağlanabilir?
Microsoft Flow, 100’den fazla veri kaynağına (sürekli olarak yenileri eklenmektedir) hiçbir yapılandırma gerektirmeden bağlanır. Veri kaynakları ve hizmetler için bazı örnekler şunlardır:

* SharePoint
* Dynamics 365
* OneDrive
* OneDrive İş
* Google Drive
* Google E-Tablolar
* Trello
* Twitter
* Box
* Facebook
* SalesForce.com
* Mailchimp
* Müşteri API'leri

Kullanılabilir bağlayıcıların tam listesini [burada](https://go.microsoft.com/fwlink/?LinkId=832211) bulabilirsiniz.

Kendi BT altyapınızdaki veri kaynaklarına [şirket içi veri ağ geçidi](gateway-manage.md) üzerinden erişebilirsiniz.

### <a name="what-are-templates"></a>Şablon nedir?
Şablonlar, popüler ve yaygın senaryolar için önceden oluşturulmuş akışlardır. Şablon kullanmak için yalnızca ilgili şablondaki hizmetlere erişiminizin olması ve gerekli ayarların hepsini doldurmanız gerekir.

### <a name="what-data-sources-will-i-be-able-to-connect-to"></a>Hangi veri kaynaklarına bağlanabilirim?
Microsoft ve üçüncü taraflarca sağlanan Office 365, Twitter, SharePoint, OneDrive, Dropbox, SQL Server gibi 100’den fazla standart hizmete bağlanabilirsiniz. Ayrıca, Salesforce ve PowerApps için Common Data Service gibi premium hizmetlere de bağlanabilirsiniz.

### <a name="how-do-i-connect-to-a-rest-api-in-my-flow"></a>Akışımda bir REST API'ye nasıl bağlanırım?
[Özel bir bağlayıcı ](register-custom-api.md) oluşturarak JSON kullanan ve 10’dan fazla kimlik doğrulama yönteminden en az birini destekleyen tüm REST API'lere bağlanabilirsiniz.

### <a name="how-do-i-connect-to-sql-server-and-other-on-premises-data-sources"></a>SQL Server ve diğer şirket içi veri kaynaklarına nasıl bağlanırım?
Yerel ağınızdaki hizmetlere [şirket içi veri ağ geçidini](gateway-manage.md) kullanarak bağlanabilirsiniz.

### <a name="can-i-share-the-flows-i-create"></a>Oluşturduğum akışları paylaşabilir miyim?
Aşağıdaki iki yoldan birini kullanarak akış paylaşabilirsiniz:

* Kuruluşunuzdaki çalışma arkadaşlarını veya grupları akışlarınıza sahip olarak ekleyebilir ve onların da akışı düzenlemesini ve yönetmesini sağlayabilirsiniz.
* El ile çalıştırılabilen akışlar için kuruluşunuzdaki diğer kişi veya gruplara akışı yalnızca çalıştırma izni de verebilirsiniz.

### <a name="how-many-flows-can-i-have"></a>Kaç akışa sahip olabilirim?
Microsoft Flow, 50 akışla birlikte teslim edilir. Daha fazla gerekirse isteyebilirsiniz.

### <a name="where-do-i-get-started-with-microsoft-flow"></a>Microsoft Flow ile çalışmaya nasıl başlarım?
Şu kaynakları kullanarak başlayabilirsiniz:

* [Blog](https://flow.microsoft.com)
* [YouTube kanalı](https://youtube.com/playlist?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF)
* [Konu başlığı](getting-started.md)
* [Topluluk](http://powerusers.microsoft.com)

### <a name="what-operating-systems-does-the-mobile-app-for-microsoft-flow-support"></a>Microsoft Flow mobil uygulaması hangi işletim sistemlerini destekler?
Microsoft Flow mobil uygulaması [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows)’da kullanılabilir.

### <a name="what-regions-and-languages-does-microsoft-flow-support"></a>Microsoft Flow hangi bölgeleri ve dilleri destekler?
Microsoft Flow 42 dilde ve [altı bölgede](regions-overview.md) kullanılabilir.

### <a name="how-does-microsoft-flow-compare-to-sharepoint-designer-2013"></a>Microsoft Flow’un SharePoint Designer 2013’ten farkı nedir?
Microsoft Flow onaylar, belge inceleme ve ekleme/çıkarma gibi birçok yaygın iş senaryosu için SharePoint Designer’ın yerine geçmiştir. Gelecekte SharePoint’te iş otomasyonu oluşturmaya yönelik varsayılan araç olacaktır.

### <a name="how-does-microsoft-flow-ensure-that-corporate-data-isnt-accidentally-released-to-social-media-services"></a>Microsoft Flow, kurumsal verilerin yanlışlıkla sosyal medya hizmetlerinde yayınlanmasını nasıl önler?
Yöneticiler, Microsoft Flow’da yalnızca tasdikli hizmetlerin kullanıldığından emin olmak [veri kaybı önleme ilkeleri](prevent-data-loss.md) oluşturabilir.

## <a name="licensing"></a>Lisanslama
### <a name="will-microsoft-flow-still-have-a-free-or-trial-option"></a>Microsoft Flow’da ücretsiz veya deneme sürümü seçeneği olacak mı?
Evet. Sınırlı kullanıcı hakları sunan ücretsiz teklifimizden yararlanabilir ya da Microsoft Flow’un 90 günlük ücretsiz deneme sürümüne kaydolabilirsiniz. Deneme sürümü boyunca aboneliğinizi istediğiniz zaman etkinleştirebilirsiniz.

### <a name="what-pricing-plans-do-you-offer"></a>Sunduğunuz fiyatlandırma planları nelerdir?
Microsoft Flow, hem ücretsiz hem de ücretli hizmet düzeyleri sunar. [Fiyatlandırma hakkında daha fazla bilgi edinin](billing-questions.md).
