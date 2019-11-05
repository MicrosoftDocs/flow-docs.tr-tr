---
title: Mobil cihazdaki istekleri onaylama | Microsoft Docs
description: Microsoft Flow ' de oluşturulan istekleri onaylamak için bir mobil cihaz kullanın.
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
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a71d1e53199f0dacfc2086812cc3cd2fd9585f4d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548688"
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>Microsoft Flow kullanarak mobil cihazınızdaki istekleri onaylama
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Bir akış sizi onaylayan olarak tanımlar ve mobil uygulamayı Microsoft Flow yüklediyseniz, onaylamanız istendiğinde anında iletme bildirimi alırsınız.

Bu makalede, Microsoft Flow için mobil uygulamadaki onay isteklerini yönetirken karşılaşabileceğiniz bazı yaygın senaryolar açıklanmaktadır.

> [!NOTE]
> Bu konudaki görüntüler bir Android cihazından; Ancak iOS deneyimi benzerdir.
> 
> 

## <a name="prerequisites"></a>Kaynakları
Bu yönergeyi tamamlamak için şunlar gerekir:

* Microsoft Flow için mobil uygulamayı çalıştıran bir [Android](https://aka.ms/flowmobiledocsandroid) veya [iOS](https://aka.ms/flowmobiledocsios) cihazı.
* Bir onay akışında onaylayan olarak atanmak üzere.
* Onay için bekleyen istekler.

## <a name="view-pending-requests"></a>Bekleyen istekleri görüntüle
1. Microsoft Flow için mobil uygulamayı açın.
   
    ![mobil uygulamayı Başlat](./media/mobile-approvals/open-app.png)
2. Sağ üst köşedeki **onaylar** ' ı seçin.
   
    ![onayları seçin](./media/mobile-approvals/select-approvals.png)
3. Bekleyen tüm onayları görüntüle:
   
    ![Bekleyen onay isteklerini gör](./media/mobile-approvals/show-pending-approval-requests.png)

Bekleyen onay isteğiniz yoksa, bir [onay akışı](modern-approvals.md)oluşturun, kendinizi onaylayan olarak ayarlayın ve ardından akışı tetikleyin. Onay istekleri, akış tetiklendikten ve onay için bir istek gönderdikten sonra, onay merkezinde birkaç saniye sonra görünür.

## <a name="approve-requests-and-leave-an-optional-comment"></a>İstekleri onaylama ve isteğe bağlı bir açıklama bırakma
1. Bunu yapmadıysanız, [bekleyen istekleri görüntülemek](mobile-approvals.md#view-pending-requests)için yukarıdaki adımları izleyin.
2. Onaylamak istediğiniz istekte **Onayla** ' yı seçin.
   
    ![Onayla seçeneğini belirleyin](./media/mobile-approvals/select-approve.png)
3. (İsteğe bağlı) **Açıklama Ekle (isteğe bağlı)** seçeneğini belirleyin.
   
    ![Açıklama Ekle ' yi seçin](./media/mobile-approvals/select-add-comment.png)
   
    **Yorum Ekle** ekranına bir açıklama girin.
   
    ![yorumunuzu girin](./media/mobile-approvals/enter-comment-for-approval.png)
4. Sağ üst köşede **Onayla** ' yı seçin.
   
    ![bittiğini onaylayın](./media/mobile-approvals/tap-confirm-button.png)
   
    Akış kararınızı kaydettikten sonra başarı ekranı görüntülenir.
   
    ![başarı ekranı](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>İstekleri reddetme ve isteğe bağlı bir açıklama bırakma
[Bir isteği onaylamak için adımları](mobile-approvals.md#approve-requests-and-leave-an-optional-comment)izleyin, ancak Ikinci adımda **Reddet** ' i seçin.

## <a name="learn-more"></a>Daha fazla bilgi edinin
[Modern onay akışları oluşturun](modern-approvals.md).

