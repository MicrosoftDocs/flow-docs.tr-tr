---
title: "Microsoft Flow oluştururken ortamlar arasında geçiş yapma | Microsoft Docs"
description: "Oluşturucular Microsoft Flow oluştururken nasıl farklı ortamlar kullanabilir?"
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: bcbb566c20291da14881d771c538dd89689b6b1d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="choosing-an-environment"></a>Ortam seçme
Microsoft Flow ile farklı ortamlarda çalışabilir ve bunlar arasında kolayca geçiş yapabilirsiniz. Bu makalede, ortamla ilgili aşağıdaki konular ele alınmaktadır:

* Ortamların sunduğu olanaklar hakkında ayrıntılı bilgi
* Ortamlar arasında geçiş yapma
* Akışı doğru ortamda oluşturma

## <a name="environments-overview"></a>Ortamlara genel bakış
Ortamlar; akışlarınız, bağlantılarınız, ağ geçitleriniz ve diğer kaynaklarınız için yalıtım sınırı sağlar. Bir akış oluştururken, akışı barındıracak ortamı ve bu akışın kullanacağı kaynakları seçersiniz. Farklı senaryolar için farklı ortamlar kullanabilirsiniz.

Bazı örnekler:

* Microsoft Common Data Service bağlantısı kullanan bir akış oluşturuyorsunuz. Bu senaryoda, akış ve Common Data Service aynı ortamda yer alıyor. Bu, tüm verilerin bu ortamda yalıtılmasını sağlar (yalıtım sınırı).
* İnsan Kaynakları departmanınız için bir akış oluşturuyorsunuz. Yalnızca İnsan Kaynakları departmanınızdaki kullanıcıların bu akışa erişebilmesini sağlamak istiyorsunuz. Örneğin, Satış grubunuzun akışı kullanmasını istemiyorsunuz. Bu senaryoda, akışı ve ağ geçitleri ya da bağlantılar dahil olmak üzere akışın kullandığı tüm kaynakları barındıracak ve yalnızca İK kullanıcılarının izinlere sahip olacağı ayrı bir ortam kullanabilirsiniz.
* Avrupa’da SharePoint verilerini göstermek için akış kullanan kullanıcılar bulunur. Bu senaryoda, akışı ve SharePoint bağlantısını barındırmak üzere Avrupa’da bulunan bir ortam oluşturun. Bu Avrupa ortamı, tüm kaynaklar Avrupa’da bulunduğu için (yerel veri konumu) Avrupa’daki kullanıcılara en iyi performansı sunar.

Ortamlar, Microsoft Flow yöneticileri tarafından oluşturulur. Bu yöneticiler, farklı ortamlara kimlerin erişebileceğini de denetler.

Bu konuda, farklı ortamlar arasında nasıl gezinebileceğiniz gösterilmektedir. Ortamları oluşturma ve yönetme hakkında ayrıntılı bilgi için bkz. [Ortamları yönetme](environments-overview-admin.md).

## <a name="switching-environments"></a>Ortamlar arasında geçiş yapma
Microsoft Flow, ortamlar arasında geçiş yapmayı çok kolaylaştırır. Geçiş yaptığınızda o ortamdaki tüm öğeleri görür, diğer ortamlardaki öğeleri görmezsiniz.

İşte bir örnek:

*İnsan Kaynakları* ortamında *YeniÇalışan* adında bir akış oluşturursunuz. [flow.microsoft.com](http://flow.microsoft.com) adresinde *Satış* ortamını açarsınız. *YeniÇalışan* akışı listelenmez. *YeniÇalışan* akışını görmek için *İnsan Kaynakları* ortamını açın. Bunun bağlantılar, ağ geçitleri, PowerApps uygulamaları vb. dahil ortamda oluşturduğunuz tüm öğeler için geçerli olacağını unutmayın.

1. [Flow.microsoft.com](http://flow.microsoft.com) adresini açın.
2. Sağ üst köşede adınızı ve bulunduğunuz ortamı görürsünüz:  
   ![](./media/environments-overview-maker/default-environment.png)
   
    Resimdeki bildirimlere dikkat edin. Bu bildirimler, bu varsayılan ortamdaki akışa özeldir.
3. Adınızı seçin. Açılır listede, kullanabileceğiniz tüm ortamlar listelenir. Şu anda bulunduğunuz ortam işaretlidir:  
   ![](./media/environments-overview-maker/all-environments.png)
4. Farklı bir ortama geçmek için listeden o ortamı seçin:  
   ![](./media/environments-overview-maker/select-europe.png)
5. Microsoft Flow otomatik olarak yeni ortama geçer:  
   ![](./media/environments-overview-maker/europe-environment.png)
   
    Resimde hiç bildirim olmadığına dikkat edin. Yeni Avrupa ortamında hiç bildirim yok.

## <a name="create-flows-in-the-right-environment"></a>Akışı doğru ortamda oluşturma
Akış oluşturmadan önce, her zaman akışın bulunmasını istediğiniz ortamı seçtiğinizden emin olun. Aksi takdirde, akışı silip doğru ortamda yeniden oluşturmanız gerekecektir.

Akışlarınızın oluşturulacağı ortamı seçerken aşağıdaki unsurları göz önünde bulundurun:

* Ağ geçitleri, Varsayılan ortamda oluşturulur. Ağ geçitleri diğer ortamlarda oluşturulamaz, bu nedenle Şirket içi verilere bağlanmak isterseniz Varsayılan ortamı kullanmanız gerekir.
* Akışlar, yalnızca bağlantıları ve aynı ortamdaki diğer kaynakları kullanabilir. Başka bir ortamdaki kaynakları kullanamazlar. Örneğin, özel bağlayıcıyı kullanan bir akış oluşturuyorsunuz. Bu özel bağlayıcı, akışla aynı ortamda yer almalıdır.
* Microsoft Common Data Service veritabanı, her zaman tek bir ortama bağlı olur. Bu nedenle, Common Data Service verileriyle çalışmak istediğinizde veritabanının bulunduğu ortamı seçmeniz gerekir.
* Kaynakları düzenleyebileceğiniz tüm ortamları görürsünüz. Ancak bu durum, her ortamda yeni kaynaklar oluşturabileceğiniz anlamına gelmez. Bu nedenle, bazı ortamlarda yeni akışlar oluşturamayabilirsiniz. Yöneticiden sizi bu ortama **Oluşturucu** olarak eklemesini istemeniz veya akışı oluşturmak için farklı bir ortam seçmeniz gerekir (varsayılan ortamda istediğiniz zaman akış oluşturabilirsiniz).

## <a name="what-you-did"></a>Şu ana kadar yaptıklarımız
Bu adımları uygulayarak kullanma izninizin olduğu ortamlar arasında geçiş yaptınız. Şimdi akışlarınızı oluşturmaya başlayın.

## <a name="next-steps"></a>Sonraki adımlar
[Şablondan akış oluşturma](get-started-logic-template.md)  
[Akış oluşturma](get-started-logic-flow.md)  
[Yöneticiler için ortamlara genel bakış](environments-overview-admin.md)

