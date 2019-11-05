---
title: Telefonunuzdaki bir akış oluşturun | Microsoft Docs
description: Bir şablondan akış oluşturma Örneğin, belirttiğiniz bir adresten e-posta aldığınızda anında iletme bildirimi gönderir
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
ms.date: 09/18/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 095b3a7f6565afff0a944bb08aee8f3a06ea114b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549056"
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>Microsoft Flow kullanarak telefonunuzdaki bir akış oluşturun
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Bir şablon kullanarak telefonunuzdaki bir akış oluşturun, bu, bir hizmet listesini arayarak, kategorilere göz atarak veya anahtar sözcükleri belirterek bulabilirsiniz. Yöneticisinden posta alırken telefonunuza anında iletme bildirimi gönderen bir akış oluşturmak için bu konudaki adımları izleyin.

Microsoft Flow [hakkında bilgi sahibi değilseniz genel bakış alın](getting-started.md).

## <a name="prerequisites"></a>Kaynakları
* [Microsoft Flow için bir hesap](sign-up-sign-in.md).
* [Desteklenen bir cihazda](getting-started.md#use-the-mobile-app) [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows) için mobil uygulama Microsoft Flow. Bu konudaki grafikler uygulamanın iPhone sürümünü yansıtır, ancak bir Android cihazındaki veya Windows Phone arabirim benzerdir.
* Bu konuda gösterilen şablonu kullanmak için şunları da yapmanız gerekir:
  
  * Office 365 kimlik bilgileri.
  * Telefonunuzdaki anında iletme bildirimleri etkinleştirildi.

## <a name="find-a-template"></a>Şablon bulma
1. Mobil uygulamayı açın ve ardından ekranın alt kısmındaki **Araştır** ' a dokunun.
   
    ![Simgeye gözatamıyorum](./media/mobile-create-flow/browse-icon.png)
   
    Bir şablonu şu yollarla bulabilirsiniz:
   
   * Ekranın üst kısmındaki arama kutusunda bir anahtar sözcük belirtin.
   * Hizmetler listesinde bir seçeneğe dokunun.
   * Farklı kategorileri göstermek için aşağı kaydırın ve ardından herhangi bir kategoride bir şablona dokunun.
     
       ![Sekmeye gözatamazsınız](./media/mobile-create-flow/browse-tab.png)
     
     Bu öğreticide, yöneticisinden posta aldığınızda anında iletme bildirimi gönderen şablonu açarsınız.
2. Hizmetler listesinde **Tümünü göster**' e dokunun.
   
    ![Hizmet listesini göster](./media/mobile-create-flow/list-services.png)
3. **Anında iletme bildirimi**simgesine dokunun.
   
    ![Anında iletme bildirimleri](./media/mobile-create-flow/push-notifications.png)
4. Yönetim çubuğunda, **e-posta**yazın ve ardından, yöneticisinden bir ileti aldığınızda anında iletme bildirimi göndermek için şablona dokunun.
   
    ![Şablon seç](./media/mobile-create-flow/choose-template.png)
5. Seçtiğiniz şablonla ilgili ayrıntıları veren ekranda **Bu şablonu kullan**' a dokunun.
   
    ![Şablonu Onayla](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Akışı tamamlama
1. İstenirse **oturum aç**' a dokunun ve Office 365 Outlook, Office 365 kullanıcıları veya her ikisi için kimlik bilgilerinizi sağlayın.
   
    ![Office 365 ' de oturum açın](./media/mobile-create-flow/office-signin.png)
   
    Diğer akışları oluştururken aynı bağlantıları kullanabilirsiniz.
2. Sağ üst köşede **İleri**' ye dokunun.
   
    ![Ileri 'ye dokunun](./media/mobile-create-flow/next.png)
   
    Sonraki ekranda tetikleme olayı ve sonuçta elde edilen tüm eylemler gösterilmektedir.
   
    ![Etkinliği ve eylemleri tetikleme](./media/mobile-create-flow/flow-structure.png)
   
    Bu şablon için, yeni posta, bilgilerinizi alan (yöneticinizin adresi dahil) akışı tetikler ve bu adresten e-posta aldığınızda size bir anında iletme bildirimi gönderir. Bazı şablonların düzgün çalışması için bazı özelleştirmeler gerekir, ancak bu şablon değildir.
3. seçim Ekranın üst kısmındaki akış için farklı bir ad yazın.
   
    ![Akışı yeniden adlandır](./media/mobile-create-flow/rename-flow.png)
4. Sağ üst köşedeki **Oluştur**' a dokunun.
   
    ![akış oluştur](./media/mobile-create-flow/create-flow.png)
   
    Akışınız oluşturulur ve akışı duraklatana veya silme işlemi yapılıncaya kadar yöneticinizin yöneticisinden posta olup olmadığını denetler.

## <a name="next-steps"></a>Sonraki adımlar
* [Flow etkinliğinizi izleyin](mobile-monitor-activity.md).
* [Akışlarınızı yönetin](mobile-manage-flows.md).

