---
title: Cihazınızı telefonunuzdan izleme | Microsoft Docs
description: Her bir akışın kaç kez başarılı veya başarısız olduğunu, her bir çalıştırmanın ne kadar sürdüğünü ve ne kadar sürdüğünü görüntüleyin
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9696ff09f41822b9daeb84b748f32e1babaf5af1
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549012"
---
# <a name="monitor-activity-in-microsoft-flow-from-your-phone"></a>Telefonunuzdaki Microsoft Flow etkinliğini izleme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Her akışın bugün, dün ve önceki günlerde kaç kez başarılı veya başarısız olduğunu gösteren bir Özet görüntüleyin. Her çalıştırma hakkında, ne zaman çalıştığı, her adımın ne kadar süreceğine ilişkin ayrıntıları ve neden başarısız olursa, nedenini keşfet.

**Kaynakları**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulamayı [desteklenen bir cihaza](getting-started.md#use-the-mobile-app)yükler. Bu konudaki grafikler uygulamanın iPhone sürümünü yansıtır, ancak Android ve Windows Phone grafikleri benzerdir.
* Zaten bir akışınız yoksa, [Microsoft Flow web sitesinde](https://flow.microsoft.com/)bir tane oluşturun. Daha kolay test için, bir dış olay beklemek yerine kendi kendinize tetikleyebileceğiniz bir tane kullanın.

Bu öğreticideki akış, belirli bir adresten e-posta aldığınızda çalıştırılır:

![Belirli bir adresten posta alındığında akış Tetikle](./media/mobile-monitor-activity/create-trigger.png)

Bu tür bir akışı, test için kişisel e-posta adresiniz ve bir akış, gerçek kullanıma hazırlandığınızda farklı bir adres (örneğin, yöneticinizin) ile yapılandırabilirsiniz.

Akış çalıştırıldığında, telefonunuza bu söz dizimi ile özel bir anında iletme bildirimi gönderilir:

![Anında iletme bildirimi gönder](./media/mobile-monitor-activity/create-event.png)

**Note:** Ayrıca, mobil uygulamadan [akışlarınızı yönetebilirsiniz](mobile-manage-flows.md) .

## <a name="display-a-summary-of-activity"></a>Etkinliğin özetini görüntüleme
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Akışınız daha önce çalıştırılmadıysa, veri oluşturmak için bir çalıştırma tetikleyin.
   
    Verilerin uygulamada görünmesi biraz zaman alabilir.
2. Varsayılan olarak **etkinlik** sekmesini gösteren mobil uygulamayı açın.
   
    Bu sekme, verileri güne göre, bugünün verileri en üstte olacak şekilde düzenler.
   
    ![Güne göre düzenlenen etkinlik](./media/mobile-monitor-activity/activity-day2.png)
   
    Her giriş, tetikleyici olaylarına ve eylemlerine karşılık gelen simgelerle birlikte bir akışın adını gösterir.
   
    ![Her akış için ad ve simgeler](./media/mobile-monitor-activity/activity-flow-name.png)
   
    Bir gün içinde en az bir akış çalıştırması başarılı olduysa, bir giriş başarı sayısını ve en son başarılı olma süresini gösterir. Bir akış başarısız olursa, farklı bir giriş benzer bilgiler gösterir.
   
    ![Başarı veya başarısızlık Özeti](./media/mobile-monitor-activity/activity-summary.png)
   
    Akış bir anında iletme bildirimi gönderdiğinde en son bildirimin metni, başarılı çalıştırmalar için girişin en altında görünür.
   
    ![Anında iletme bildirimi örneği](./media/mobile-monitor-activity/activity-notification.png)
3. Günde birden fazla anında iletme bildirimi gönderildiyse, en fazla üç önceki çalıştırmanın bildirimlerini görüntülemek için bildirimde sola kaydırın. Günde dörtten fazla bildirim gönderildiyse, **daha fazla** bilgi görünene kadar sola kaydırın ve ardından tüm bildirimlerin listesini görüntülemek için bu seçeneğe dokunun.
   
    ![Anında iletme bildirimi örneği](./media/mobile-monitor-activity/activity-notification-list.png)
4. Etkinlik özetine dönmek için **geri** ' ye dokunun.
5. Etkinlik özetini filtrelemek için sağ üst köşedeki simgeye dokunun.
   
    Tüm girişleri, yalnızca hata girdilerini veya anında iletme bildirimleri içeren girdileri gösterebilirsiniz.
   
    ![Tüm çalıştırmaları, yalnızca arızaları veya yalnızca bildirimleri göster](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>Bir çalıştırmanın ayrıntılarını göster
1. Etkinlik özetinde, en son çalıştırmanın ayrıntılarını göstermek için bir girişe dokunun.
   
     Her olay ve eylem, olay veya eylemin başarılı veya başarısız olduğunu belirten bir simgeyle görüntülenir. Başarılı olduysa, geçen süre (saniye cinsinden) de görüntülenir.
   
    ![Bir çalıştırmanın ayrıntıları](./media/mobile-monitor-activity/activity-icons.png)
2. Ekranın alt kısmında, akışın tüm çalıştırmalarını listelemek için **önceki çalıştırmaları görüntüle** ' ye dokunun ve sonra ayrıntılarını göstermek için bir çalıştırmaya dokunun.
   
    ![Başarı/başarısızlık geçmişi](./media/mobile-monitor-activity/history-mixed.png)

