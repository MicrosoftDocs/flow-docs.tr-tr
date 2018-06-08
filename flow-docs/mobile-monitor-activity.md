---
title: Etkinlikleri telefonunuzdan izleme | Microsoft Docs
description: Her bir akışın kaç kez başarılı veya başarısız olduğunu, her bir çalıştırmanın ne zaman gerçekleştiğini ve ne kadar sürdüğünü görüntüleme
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
ms.openlocfilehash: a9318a1571d46635babbb0b061ff65734ad172fe
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440163"
---
# <a name="monitor-activity-in-microsoft-flow-from-your-phone"></a>Microsoft Flow'daki etkinlikleri telefonunuzdan izleme
Her bir akışın bugün, dün ve önceki günlerde kaç kez başarılı veya başarısız olduğunun bir özetini görüntüleyin. Her bir çalıştırmayla ilgili ayrıntıları (örneğin, çalıştırılma zamanı; her bir adımın ne kadar sürdüğü ve başarısız olduysa başarısız olma nedeni) keşfedin.

**Önkoşullar**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* [Desteklenen bir cihazda](getting-started.md#use-the-mobile-app) [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulamasını yükleyin. Bu konu başlığında kullanılan grafikler, uygulamanın iPhone sürümünden alınmıştır ancak Android ve Windows Phone için de benzer grafikler sunulur.
* Akışınız yoksa [Microsoft Flow'un web sitesinde](https://flow.microsoft.com/) bir akış oluşturun. Daha kolay test edebilmek için, bir dış olay beklemek yerine kendi kendinize tetikleyebileceğiniz bir akış kullanın.

Bu öğreticideki akış, belirli bir adresten e-posta aldığınızda çalıştırılır:

![Belirli adreslerden e-posta alındığında akış tetikleme](./media/mobile-monitor-activity/create-trigger.png)

Bu tür bir akışı; test etme amaçlı olarak kişisel e-posta adresinizle ve akış hazır olduğunda gerçek kullanım için farklı bir adresle (örneğin, yöneticinizin adresi) yapılandırabilirsiniz.

Akış çalıştırıldığında telefonunuza şu söz diziminin bulunduğu özel bir anında iletme bildirimi gönderilir:

![Anında iletme bildirimi gönderme](./media/mobile-monitor-activity/create-event.png)

**Not:** Mobil uygulamanızdan da [akışlarınızı yönetebilirsiniz](mobile-manage-flows.md).

## <a name="display-a-summary-of-activity"></a>Etkinlik özetini görüntüleme
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Akışınız daha önce çalıştırılmadıysa veri oluşturmak için bir çalıştırma tetikleyin.
   
    Verilerin uygulamada görünmesi biraz zaman alabilir.
2. Mobil uygulamayı açtığınızda, **Etkinlik** sekmesi varsayılan olarak gösterilir.
   
    Bu sekme, bugünün verileri en üstte olacak şekilde verileri güne göre düzenler.
   
    ![Güne göre düzenlenen etkinlikler](./media/mobile-monitor-activity/activity-day2.png)
   
    Her bir giriş, tetikleyici olaylarına ve eylemlerine karşılık gelen simgelerle birlikte bir akışın adını gösterir.
   
    ![Her bir akışa ilişkin ad ve simgeler](./media/mobile-monitor-activity/activity-flow-name.png)
   
    Bir gün içinde en az bir akış çalıştırması başarılı olduysa bir giriş, akışın başarılı olma sayısını ve en son ne zaman başarılı olduğunu gösterir. Akış başarısız olduysa farklı bir giriş, buna ilişkin benzer bilgiler gösterir.
   
    ![Başarılı ve başarısız olma özeti](./media/mobile-monitor-activity/activity-summary.png)
   
    Akış bir anında iletme bildirimi gönderirse girişin altında, başarılı çalıştırmalar için gönderilen en son bildirimin metni görünür.
   
    ![Anında iletme bildirimi örneği](./media/mobile-monitor-activity/activity-notification.png)
3. Bir gün içinde birden fazla anında iletme bildirimi gönderilmişse son üç çalıştırmaya ilişkin bildirimleri görüntülemek için bildirim üzerinde sola kaydırın. Bir gün içinde dörtten fazla bildirim gönderilmişse **Daha fazla** seçeneği görünene kadar sola kaydırın ve tüm bildirimlerin listesini görüntülemek için bu seçeneğe dokunun.
   
    ![Anında iletme bildirimi örneği](./media/mobile-monitor-activity/activity-notification-list.png)
4. Etkinlik özetine dönmek için **Geri**'ye dokunun.
5. Etkinlik özetini filtrelemek için sağ üst köşedeki simgeye dokunun.
   
    Tüm girişleri, yalnızca başarısız olunan girişleri veya yalnızca anında iletme bildirimi içeren girişleri görüntüleyebilirsiniz.
   
    ![Tüm çalıştırmaları, yalnızca başarısız olunan durumları veya yalnızca bildirimleri gösterme](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>Çalıştırma ayrıntılarını gösterme
1. Etkinlik özetinde, en son çalıştırmaya ilişkin ayrıntıları göstermek için bir girişe dokunun.
   
     Her bir olay ve eylemle birlikte bunların başarılı veya başarısız olduğunu belirten bir simge görünür. Başarılı olduysa işlemin süresi de (saniye cinsinden) görünür.
   
    ![Çalıştırma ayrıntıları](./media/mobile-monitor-activity/activity-icons.png)
2. Ekranın alt kısmında, akışın tüm çalıştırmalarını listelemek için **See previous runs**'a (Önceki çalıştırmaları göster) ve ardından ayrıntılarını görüntülemek için bir çalıştırmaya dokunun.
   
    ![Başarı/başarısızlık geçmişi](./media/mobile-monitor-activity/history-mixed.png)

