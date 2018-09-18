---
title: Düğmelerinizi diğerleriyle paylaşın. | Microsoft Docs
description: Düğmelerinizi diğer kullanıcılarla paylaşarak, onları kullanmalarını ve zaman kazanmalarını sağlayın.
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
ms.openlocfilehash: 77b46d10ec3856054dcc8e1734b327bac9a01596
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690359"
---
# <a name="share-button-flows-in-microsoft-flow"></a>Microsoft Flow’da düğme akışlarını paylaşma
Microsoft Flow’un mobil uygulamasıyla, [düğme akışlarını](introduction-to-button-flows.md) (düğmeleri) kuruluşunuzdaki diğer kullanıcı veya gruplarla paylaşabilirsiniz. Düğmeyi paylaştığınızda, paylaştığınız kişi veya grup aynı kendi düğmelerini çalıştırdığı gibi düğmenizi çalıştırabilir. Ayrıca başka birinin sizinle paylaştığı düğmelere yönlendiren [bir bağlantı paylaşabilirsiniz](share-buttons.md#re-share-a-button). İstediğiniz zaman düğmelerinizi [paylaşmayı durdurabilirsiniz](share-buttons.md#stop-sharing-a-button).

> Bu belgede kullanılan ekran görüntüleri bir Android cihazından alınmıştır. iPhone kullanıyorsanız, görüntüler farklı olabilir ama işlevsellik aynıdır.
> 
> 

Başka birinin sizinle paylaştığı düğmeyi kullanmak için [bu adımları](share-buttons.md#use-shared-buttons) izleyin.

## <a name="prerequisites"></a>Önkoşullar
Düğme paylaşmak için gerekenler:

* [Microsoft Flow](https://flow.microsoft.com) erişimi olan bir hesap.
* Paylaşılacak bir akış.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulamasının yüklü olduğu bir mobil cihaz.
* Kuruluşunuzda düğmenizi paylaşacağınız bir grup veya kullanıcı.

## <a name="share-a-button"></a>Düğmeyi paylaşma
Microsoft Flow mobil uygulamasının **Düğmeler** sekmesinde düğme paylaşabilirsiniz.

1. Paylaşmak istediğiniz düğmenin yanındaki küçük simgeye dokunun.
   
    ![paylaş düğmesi](./media/share-buttons/share-button-flows-buttons-tab.png)
2. **Düğme kullanıcıları** sayfasından **Başkalarını davet et**’e dokunun.
   
    ![paylaş düğmesi](./media/share-buttons/share-button-flows-button-users.png)
3. Düğmeyi paylaşmak istediğiniz grubu veya kişiyi arayın ve seçin.
   
    ![paylaş düğmesi](./media/share-buttons/share-button-flows-invite-others-select.png)
4. **Başkalarını davet et** sayfasında **GÖNDER**’e dokunun.
   
    ![paylaş düğmesi](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Düğme paylaşma işleminin başarıyla tamamlandığını belirten sayfada **BİTTİ**’ye dokunun.
   
    ![paylaş düğmesi](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Kullanıcıların kendi bağlantılarını kullanmasını gerekli kılma
> [!NOTE]
> Bir düğmeyi paylaştığınız kişilerin, düğmenizin kullandığı tüm bağlantıları kullanmasına izin verebilirsiniz. Ayrıca kendi bağlantılarını kullanmalarını da isteyebilirsiniz. Diğer kişilerin bağlantılarınızı kullanmasına izin verirseniz, bağlantınızdaki kimlik bilgilerine erişebilir ve bunları diğer akışlarda yeniden kullanabilirler.
> 
> 

Düğmelerinizi paylaştığınız kişilerin kendi bağlantılarını kullanmasını gerekli kılmak için bu adımları izleyin.

1. Bir düğme paylaştıktan hemen sonra görüntülenen ekranda **BAĞLANTILARI YÖNET**’i seçin.
2. Yönetmek istediğiniz düğmede **DÜZENLE**’yi seçin.
3. **Kullanıcı tarafından sağlanan** seçeneğini veya e-posta adresinizi seçin.
   
    Paylaşılan düğmede kimin bağlantısının kullanılması gerektiğini belirtebilirsiniz.
   
    ![paylaş düğmesi](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    Seçiminizi istediğiniz zaman görüntüleyebilir veya değiştirebilirsiniz. Bunu yapmak için, **Akışlar** sekmesi > paylaştığınız akış > **Kullanıcılar ve bağlantılar** > **BAĞLANTILAR** sekmesi > yönetmek istediğiniz düğmede **DÜZENLE** seçeneklerini belirleyin.
   
    ![paylaş düğmesi](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>Düğme kullanıcılarının listesini görüntüleme
**Düğmeler** sekmesinde bu adımları izleyerek, düğmenin paylaşıldığı tüm grupları veya kullanıcıları görüntüleyebilirsiniz:

1. İstediğiniz düğmenin yanındaki küçük simgeye dokunun.
2. **Düğme kullanıcıları** sayfasında, düğmenin paylaşıldığı tüm grupları veya kullanıcıları görüntüleyin.
   
    ![düğme kullanıcılarını görüntüleme](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Bir düğmeyi paylaşmayı durdurma
**Düğmeler** sekmesinde bu adımları izleyerek düğmeyi paylaşmayı durdurabilirsiniz:

1. Artık paylaşmak istemediğiniz düğmenin yanındaki küçük simgeye dokunun.
2. **Düğme kullanıcıları** sayfasında, düğmeyi paylaşmayı durdurmak istediğiniz kullanıcı veya gruba dokunun.
   
    ![düğmeyi paylaşmayı durdurma](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Kullanıcının sayfası görüntülendiğinde **Kullanıcıyı kaldır**’a dokunun.
   
    ![düğmeyi paylaşmayı durdurma](./media/share-buttons/share-button-flows-remove-user.png)
4. Kaldırma işleminin tamamlanmasını bekleyin. **Düğme kullanıcıları** listesinin yenilendiğini ve kaldırdığınız kullanıcı ya da grubun artık listede olmadığını fark edebilirsiniz.
   
    ![düğmeyi paylaşmayı durdurma](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>Çalıştırma geçmişini izleme
Düğmenin paylaşıldığı kişiler tarafından başlatılan çalıştırmaları da kapsayan çalıştırma geçmişinin tamamı yalnızca, düğmeyi oluşturan kişinin Microsoft Flow mobil uygulamasındaki **Etkinlik** sekmesinde görüntülenir.

## <a name="use-shared-buttons"></a>Paylaşılan düğmeleri kullanma
Birinin sizinle paylaştığı bir düğmeyi çalıştırabilmek için, önce bunu **Düğmeleri ekleme** sayfasındaki **Düğmeler** sekmenize eklemeniz gerekir.

1. **Düğmeler** sekmesinde **DAHA FAZLASINI EDİNİN**’e (veya gösteriliyorsa **Yeni düğmeler kullanımda** başlığına) dokunun.
   
    ![sizinle paylaşılan yeni düğme](./media/share-buttons/share-button-flows-banner.png)
2. Kullanmak istediğiniz düğmeye dokunun.
   
    Dokunulan düğme hemen Microsoft Flow uygulamasının **Düğmeler** sekmesine eklenir. Daha sonra, bu düğmeyi **Düğmeler** sekmesinde listelenen diğer tüm düğmeler gibi bu sekmeden kullanabilirsiniz.
   
    ![sizinle paylaşılan yeni düğme](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Düğmeyi yeniden paylaşma
Sizinle paylaşılan bir düğmeyi yeniden paylaşabilirsiniz.

1. Paylaşmak istediğiniz düğmenin yanındaki **...** seçeneğini belirleyin.
2. **Düğmeyi paylaş bağlantısını** seçin.
   
    ![düğmeyi yeniden paylaş bağlantısı](./media/share-buttons/re-share-button.png)
3. Düğmeyi paylaşmak için kullanmak istediğiniz uygulamayı seçin ve ardından düğmeyi paylaşmak istediğiniz kişiye göndermek için adımları izleyin.

## <a name="stop-using-a-shared-button"></a>Paylaşılan düğmeyi kullanmayı durdurma
Sizinle paylaşılan bir düğmeyi artık kullanmak istemiyorsanız, aşağıdaki adımları izleyerek bu düğmeyi **Düğmeler** sekmesinden kaldırın:

1. **Düğmeler** sekmesinde, artık kullanmak istemediğiniz düğmenin yanındaki **...** işaretine dokunun.
   
    ![düğmeyi kaldırma](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Açılan menüden **Kaldır**’a dokunun.

Hepsi bu. Düğme, Microsoft Flow uygulamasının **Düğmeler** sekmesinde artık görünmez.

> [!NOTE]
> Paylaşılan bir düğmeyi kaldırdıktan sonra, **Düğmeler** sekmesinde **DAHA FAZLA EDİNİN**’i seçerek bu düğmeyi yeniden ekleyebilirsiniz.
> 
> 

