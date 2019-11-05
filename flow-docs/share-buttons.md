---
title: Düğmelerinizi başkalarıyla paylaşabilirsiniz. | Microsoft Docs
description: Düğmelerinizi kullanabilmeniz ve zamandan tasarruf etmek için düğmelerinizi başkalarıyla paylaşabilirsiniz.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 098ebf9d8e02ede22a7914a2458375eb3641544a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548427"
---
# <a name="share-button-flows-in-microsoft-flow"></a>Düğme akışlarını Microsoft Flow içinde paylaşma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Microsoft Flow mobil uygulamada, [düğme akışlarını](introduction-to-button-flows.md) (düğmeleri) kuruluşunuzdaki diğer Kullanıcı veya gruplarla paylaşabilirsiniz. Bir düğmeyi paylaştığınızda, paylaştığınız kişi veya Grup, kendi düğmelerini çalıştırdıkları gibi düğmenizi de çalıştırabilir. Ayrıca, başka bir kişinin sizinle paylaştığı düğmelere [bir bağlantı paylaşabilirsiniz](share-buttons.md#re-share-a-button) . İstediğiniz zaman düğmelerinizi [paylaşmayı durdurabilirsiniz](share-buttons.md#stop-sharing-a-button) .

> Bu belgede kullanılan ekran görüntüleri bir Android aygıtından alındı. İPhone kullanıyorsanız, görüntüler farklı görünebilir, ancak işlevsellik aynıdır.
> 
> 

Birisinin sizinle paylaştığı bir düğmeyi kullanmak için [aşağıdaki adımları](share-buttons.md#use-shared-buttons) izleyin.

## <a name="prerequisites"></a>Kaynakları
Düğmeleri paylaşmak için şunlar gerekir:

* [Microsoft Flow](https://flow.microsoft.com)erişimi olan bir hesap.
* Paylaşılacak akış.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows)için Microsoft Flow mobil uygulamasına sahip bir mobil cihaz.
* Kuruluşunuzun içindeki düğmenizi paylaşmak için bir grup veya Kullanıcı.

## <a name="share-a-button"></a>Düğme paylaşma
Microsoft Flow mobil uygulamanın **düğmeler** sekmesinden bir düğme paylaşabilirsiniz.

1. Paylaşmak istediğiniz düğmenin yanındaki küçük simgeye dokunun.
   
    ![Paylaşma düğmesi](./media/share-buttons/share-button-flows-buttons-tab.png)
2. **Düğme kullanıcıları** sayfasından **diğerlerini davet et** ' e dokunun.
   
    ![Paylaşma düğmesi](./media/share-buttons/share-button-flows-button-users.png)
3. Öğesini arayın ve ardından düğmeyi paylaşmak istediğiniz grubu veya kişiyi seçin.
   
    ![Paylaşma düğmesi](./media/share-buttons/share-button-flows-invite-others-select.png)
4. Başkalarını **davet et** sayfasında **Gönder** ' e dokunun.
   
    ![Paylaşma düğmesi](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Düğme paylaşma işleminin başarıyla tamamlandığını belirten sayfada **bitti** ' ye dokunun.
   
    ![Paylaşma düğmesi](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Kullanıcıların kendi bağlantılarını kullanmasını gerektir
> [!NOTE]
> Bir düğmeyi paylaştığınızda, düğmeyi paylaştığınız kişilere düğme tarafından kullanılan tüm bağlantıları kullanma izni verebilirsiniz. Ayrıca, kendi bağlantılarını kullanmalarını da zorunlu kılabilirsiniz. Başkalarının bağlantılarınızı kullanmasına izin verirseniz, bağlantılarınızda kimlik bilgilerine erişemez veya bunları başka bir akışta yeniden kullanabilirler.
> 
> 

Kendi bağlantılarını kullanmak üzere düğmelerinizi paylaştığınız kişileri gerektirmek için bu adımları izleyin.

1. Bir düğmeyi paylaştıktan hemen sonra görüntülenen ekranda **Bağlantıları Yönet** ' i seçin.
2. Yönetmek istediğiniz düğme üzerinde **Düzenle** ' yi seçin.
3. Kullanıcı veya e-posta adresiniz **tarafından sağlanmış** ' ı seçin.
   
    Seçiminiz, bağlantıları paylaşılan düğmesinde kullanılması gereken anlamına gelir.
   
    ![Paylaşma düğmesi](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    Seçiminizi dilediğiniz zaman görüntüleyebilir veya değiştirebilirsiniz. Bunu yapmak için, **Kullanıcılar ve bağlantılar** > paylaştığınız Flow > **akışlar** **sekmesini seçin** > yönetmek istediğiniz düğme üzerinde **düzenleme** >.
   
    ![Paylaşma düğmesi](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>Düğme kullanıcılarının listesini görüntüleme
**Düğmeler** sekmesinden aşağıdaki adımları izleyerek bir düğmenin paylaşıldığı tüm grupları veya kullanıcıları görüntüleyebilirsiniz:

1. İlgilendiğiniz düğmenin yanındaki küçük simgeye dokunun.
2. **Düğme kullanıcıları** sayfasında, düğmenin paylaşıldığı tüm grupları veya kullanıcıları görüntüleyin.
   
    ![düğme kullanıcılarını görüntüle](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Düğme paylaşmayı durdur
**Düğmeler** sekmesinden bu adımları izleyerek bir düğme paylaşmayı durdurabilirsiniz:

1. Artık paylaşmak istemediğiniz düğmenin yanındaki küçük simgeye dokunun.
2. **Düğme kullanıcıları** sayfasında, düğme paylaşımını durdurmak istediğiniz kullanıcıya veya gruba dokunun.
   
    ![Paylaşımı Durdur düğmesi](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Kullanıcının sayfası görüntülendiğinde **kullanıcıyı kaldır** ' a dokunun.
   
    ![Paylaşımı Durdur düğmesi](./media/share-buttons/share-button-flows-remove-user.png)
4. Kaldırma işleminin tamamlanmasını bekleyin. **Kullanıcıların** listesi yenilendiğine ve kaldırdığınız Kullanıcı veya grup artık listelenmediğine dikkat edin.
   
    ![Paylaşımı Durdur düğmesi](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>Çalıştırma geçmişini izleme
Bir düğmenin paylaşıldığı bir kişi tarafından başlatılan çalıştırmalar da dahil olmak üzere tüm çalıştırma geçmişi yalnızca düğme oluşturucusunun Microsoft Flow mobil uygulamasının **etkinlik** sekmesinde görünür.

## <a name="use-shared-buttons"></a>Paylaşılan düğmeleri kullanma
Birisinin sizinle paylaştığı bir düğmeyi çalıştırmadan önce **düğmeleri ekle** sayfasından **düğmeler** sekmesine eklemeniz gerekir.

1. **Düğmeler** sekmesinde **daha fazla al** (veya varsa **yeni düğmeler kullanılabilir** başlık) seçeneğine dokunun.
   
    ![benimle paylaşılan yeni düğme](./media/share-buttons/share-button-flows-banner.png)
2. Kullanmak istediğiniz düğmeye dokunun.
   
    Dokunduğunuz düğme, Microsoft Flow uygulamasının **düğmeler** sekmesine hemen eklenir. Daha sonra düğme sekmesinden, burada listelenen diğer tüm **düğmelerde** olduğu gibi düğmeyi de kullanabilirsiniz.
   
    ![benimle paylaşılan yeni düğme](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Bir düğmeyi yeniden paylaşma
Sizinle paylaşılan bir düğmeye bir bağlantı paylaşabilirsiniz.

1. Paylaşmak istediğiniz düğmenin yanındaki **..** . seçeneğini belirleyin.
2. **Paylaşma düğme bağlantısını**seçin.
   
    ![düğme bağlantısını yeniden paylaşma](./media/share-buttons/re-share-button.png)
3. Düğmeyi paylaşmak için kullanmak istediğiniz uygulamayı seçin ve ardından düğmeyi paylaşmak istediğiniz kişiye göndermek için adımları izleyin.

## <a name="stop-using-a-shared-button"></a>Paylaşılan bir düğme kullanmayı durdur
Sizinle paylaşılan bir düğmeyi artık kullanmak istemiyorsanız, aşağıdaki adımları uygulayarak **düğmeleri Düğmeler** sekmesinden kaldırın:

1. **Düğmeler** sekmesinde, artık kullanmak istemediğiniz düğmenin yanındaki **...** seçeneğine dokunun.
   
    ![Kaldır düğmesi](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Görüntülenen menüden **Kaldır** ' a dokunun.

Bu,. Düğme, Microsoft Flow uygulamasının **düğmeler** sekmesinde artık görünmez.

> [!NOTE]
> Paylaşılan bir düğmeyi kaldırdıktan sonra **düğmeler** sekmesinden **daha fazla al** seçeneğini belirleyerek geri ekleyebilirsiniz.
> 
> 

