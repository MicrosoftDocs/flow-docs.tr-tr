---
title: Akışları telefonunuzdan yönetme | Microsoft Docs
description: Akışlar listenizi görüntüleme, akışları etkinleştirme veya devre dışı bırakma ve her bir akışa ilişkin olayları, eylemleri ve çalıştırma geçmişini görüntüleme
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
ms.openlocfilehash: 4a04fec70ae70ff17ddf6e1f93e6461ec432e8d2
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440109"
---
# <a name="manage-flows-in-microsoft-flow-from-your-phone"></a>Microsoft Flow'daki akışları telefonunuzdan yönetme
Oluşturduğunuz tüm akışların listesini görüntülemenin ve akışları etkinleştirip devre dışı bırakmanın yanı sıra her bir akışa ilişkin olayları, eylemleri ve çalıştırma geçmişini görüntüleyin.

**Önkoşullar**

* [Desteklenen bir cihazda](getting-started.md#use-the-mobile-app) [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulamasını yükleyin. Bu konu başlığında kullanılan grafikler, uygulamanın iPhone sürümünden alınmıştır ancak Android ve Windows Phone için de benzer grafikler sunulur.
* Akışınız yoksa [Microsoft Flow'un web sitesinde](https://flow.microsoft.com/) bir akış oluşturun. Daha kolay test edebilmek için, bir dış olay beklemek yerine kendi kendinize tetikleyebileceğiniz bir akış kullanın.

Bu öğreticideki akış, belirli bir adresten e-posta aldığınızda çalıştırılır:

![Belirli adreslerden e-posta alındığında akış tetikleme](./media/mobile-manage-flows/create-trigger.png)

Bu tür bir akışı; test etme amaçlı olarak kişisel e-posta adresinizle ve akış hazır olduğunda gerçek kullanım için farklı bir adresle (örneğin, yöneticinizin adresi) yapılandırabilirsiniz.

Akış çalıştırıldığında telefonunuza şu söz diziminin bulunduğu özel bir anında iletme bildirimi gönderilir:

![Slack'e ileti gönderme](./media/mobile-manage-flows/create-event.png)

**Not**: Mobil uygulamadan [akış etkinliğini de izleyebilirsiniz](mobile-monitor-activity.md).

## <a name="manage-a-flow"></a>Akışı yönetme
1. Mobil uygulamayı açın ve ardından tüm akışlarınızı listelemek için ekranın altındaki **Akışlarım**'a dokunun.
   
    Her bir girişte akışın adı, akışın olaylarına ve eylemlerine ilişkin simgeler ve akışın son çalıştırma zamanının yanı sıra son çalıştırmanın başarılı olup olmadığını belirten bir simge gösterilir.
   
    ![Akışlar listesi](./media/mobile-manage-flows/flow-list.png)
2. Yönetme seçeneklerini görüntülemek için bir akışa dokunun.
   
    ![Akışları yönetme seçenekleri](./media/mobile-manage-flows/flow-details.png)
3. Akışı etkinleştirmek veya devre dışı bırakmak için iki durumlu **Enable flow** (Akışı etkinleştir) düğmesine dokunun.
4. Bu akışın olay ve eylemlerini görüntülemek için **See flow** (Akışı gör) düğmesine dokunun. Genişletmek için ise her bir olaya veya eyleme dokunun ve ardından **Geri**'ye dokunun.
   
    ![Bir akışa ilişkin olaylar ve eylemler](./media/mobile-manage-flows/flow-event-action.png)
5. Akışın başarılı olduğu zamanları, başarısız olduğu zamanları veya her ikisini birden görüntülemek için **Run history**'ye (Çalıştırma geçmişi) dokunun.
   
    ![Çalıştırma listesi](./media/mobile-manage-flows/history-mixed.png)
6. Her bir olay ve eylemin başarılı olup olmadığını ve başarılı olmuşsa ne kadar sürdüğünü (saniye cinsinden) göstermek için bir çalıştırmaya dokunun.
   
    ![Çalıştırma ayrıntıları](./media/mobile-manage-flows/flow-run.png)

