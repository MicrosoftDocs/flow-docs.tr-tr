---
title: Telefonlarınızdan akışları yönetin | Microsoft Docs
description: Akışlarınızın listesini görüntüleyin, bunları etkinleştirin veya devre dışı bırakın ve her akışın olay/s, eylem/sn ve çalıştırma geçmişini görüntüleyin
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
ms.openlocfilehash: 6f452f52d654d6f03a3262de8888c68cb2480704
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548628"
---
# <a name="manage-flows-in-microsoft-flow-from-your-phone"></a>Telefonunuzdaki Microsoft Flow akışlarını yönetme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Oluşturduğunuz tüm akışların bir listesini görüntüleyin, her akış için olay ve eylemleri görüntüleyin, bunu etkinleştirin veya devre dışı bırakın ve çalıştırma geçmişini bulun.

**Kaynakları**

* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulamayı [desteklenen bir cihaza](getting-started.md#use-the-mobile-app)yükler. Bu konudaki grafikler uygulamanın iPhone sürümünü yansıtır, ancak Android ve Windows Phone grafikleri de benzer şekilde görünür.
* Zaten bir akışınız yoksa, [Microsoft Flow web sitesinde](https://flow.microsoft.com/)bir tane oluşturun. Daha kolay test için, bir dış olay beklemek yerine kendi kendinize tetikleyebileceğiniz bir tane kullanın.

Bu öğreticideki akış, belirli bir adresten e-posta aldığınızda çalıştırılır:

![Belirli bir adresten posta alındığında akış Tetikle](./media/mobile-manage-flows/create-trigger.png)

Bu tür bir akışı, test için kişisel e-posta adresiniz ve bir akış, gerçek kullanıma hazırlandığınızda farklı bir adres (örneğin, yöneticinizin) ile yapılandırabilirsiniz.

Akış çalıştırıldığında, telefonunuza bu söz dizimi ile özel bir anında iletme bildirimi gönderilir:

![Bolluğu bir ileti gönder](./media/mobile-manage-flows/create-event.png)

**Note**: mobil uygulamadaki [Flow etkinliğini de izleyebilirsiniz](mobile-monitor-activity.md) .

## <a name="manage-a-flow"></a>Akış yönetme
1. Mobil uygulamayı açın ve ardından tüm akışlarınızın listesini listelemek için ekranın altındaki **Akışlarım** ' a dokunun.
   
    Her girişte akışın adı, olayları ve eylemleri için simgeler, en son çalıştırıldığı zaman ve en son çalıştırmanın başarılı olup olmadığını gösteren bir simge gösterilir.
   
    ![Akışlar listesi](./media/mobile-manage-flows/flow-list.png)
2. Bir akışa dokunarak yönetme seçeneklerini gösterin.
   
    ![Akışı yönetme seçenekleri](./media/mobile-manage-flows/flow-details.png)
3. Akışı etkinleştirmek veya devre dışı bırakmak için **akışı etkinleştir** ' e dokunun.
4. **Akışı gör** ' e dokunarak bu akışa ait olayları ve eylemleri görüntüleyin, her bir olaya veya genişletmek için bir eyleme dokunun ve ardından **geri**' ye dokunun.
   
    ![Bir akış için olaylar ve eylemler](./media/mobile-manage-flows/flow-event-action.png)
5. Akışın başarıları, başarısızlıklarını veya her ikisini de göstermek için **çalıştırma geçmişi** ' ne dokunun.
   
    ![Çalıştırmalar listesi](./media/mobile-manage-flows/history-mixed.png)
6. Bir çalıştırmaya dokunarak her bir olay ve eylemin başarılı olup olmadığını ve ne kadar süre (saniye cinsinden) sürdüğünü görüntüleyin.
   
    ![Çalıştırma ayrıntıları](./media/mobile-manage-flows/flow-run.png)

