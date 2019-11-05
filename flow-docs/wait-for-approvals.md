---
title: Akışta onay bekle | Microsoft Docs
description: Akışlar, bir kullanıcı tarafından bir değişikliği onaylama veya reddetme gibi bir eylem yapmadan önce bir dış olayın gerçekleşmesini bekleyebilir (örneğin, karar bildirimi gönderme).
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ea6be2d1deae080df58afd94c1f1e8d0c13c9fcd
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548348"
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Microsoft Flow onay bekle
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


SharePoint 'te bir öğe oluşturursanız, onay e-postası gönderdiğinde ve sonra öğenin onaylanmış veya reddedildi olduğunu bildiren bir akış oluşturun. Bu öğreticiyi izlemek için tetikleyici eylemi olarak basit bir SharePoint listesi oluşturun, ancak Dropbox veya OneDrive gibi başka bir veri kaynağını kullanabilirsiniz.

**Kaynakları**

* **Proje izleyici**adlı basit bir SharePoint listesi oluşturun, **title**adlı bir sütun ekleyin ve ardından **atanan**adlı bir kişi veya grup sütunu ekleyin.

   ![Proje Izleyici SPO listesinin görüntüsü](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Akışı tetiklemek için bir olay ekleyin

1. [Microsoft Flow](https://flow.microsoft.com)oturum açın, üst gezinti çubuğunda **Akışlarım** ' ı seçin ve sonra **boş oluştur**' u seçin.

1. **Yüzlerce bağlayıcı ve tetikleyici ara** kutusunu seçin, **Yeni öğe**girin ve ardından **SharePoint-bir öğe oluşturulduğunda SharePoint**'e gidin.

1. İstenirse, SharePoint 'te oturum açın.
1. **Site adresi**altında, listenizi içeren SharePoint sitesinin URL 'sini girin.

1. **Liste adı**altında, daha önce oluşturduğunuz listeyi seçin. ' Yi takip ediyorsanız, ad **Proje izleyici**olur.

    ![SPO listesi adının görüntüsü](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>Ortaya çıkan eylemi ekleyin

1. **Yeni adım** düğmesini seçin ve ardından **Eylem Ekle** ' yi seçin.

1. **Tüm bağlayıcıları ve eylemleri ara** kutusuna **e-posta gönder**yazın veya yapıştırın ve ardından **Office 365 Outlook-e-posta Gönder seçeneklerini**belirleyin.

1. İstenirse, Office 365 Outlook 'Ta oturum açın.

1. **To** alanını seçin ve ardından **atanan e-posta** belirtecini seçin.

    **Atanan** sütunundaki Kullanıcı, öğeleri onaylamak veya reddetmek için e-postayı alır. Akışı test etmek için bir öğe oluşturduğunuzda, bu alanda kendinizi belirtin. Bu şekilde, yalnızca öğeyi onaylayıp reddetmezsiniz, ancak bildirim e-postasını de alırsınız.

    > [!NOTE]
    > **Konu** ve **Kullanıcı seçenekleri** alanlarını gereksinimlerinize uyacak şekilde özelleştirebilirsiniz.

    ![Alana onay e-postası gönder görüntüsü](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Koşul ekleme

1. **Yeni adım** düğmesini seçin ve ardından **Koşul Ekle**' yi seçin.

    ![Koşul ekleme görüntüsü](./media/wait-for-approvals/add-a-condition.png)
1. İlk kutuyu seçin ve ardından **SelectedOption** belirtecini seçin.
1. Son kutuyu seçin ve ardından **Onayla**yazın.

    ![Koşul kartının görüntüsü](./media/wait-for-approvals/condition-card-2.png)

1. **Evet** alanında **Eylem Ekle**' yi seçin.

1. **Tüm bağlayıcıları ve eylemleri ara** kutusuna **e-posta gönder**' i yazın veya yapıştırın ve ardından **Office 365 Outlook-e-posta gönder**' i seçin.

1. **Kime** alanına, **e-posta ile oluşturulan**gibi bir alıcı girin.

1. **Konu** kutusunda bir konu belirtin.

    Örneğin, **atanan DisplayName**' i seçin, türü her tarafta bir boşluk ile **onaylanır** ve **başlık**' ı seçin.

1. **Gövde** kutusunda, **projenin sonraki aşamasına devam etmek için hazırlanma** gibi bir e-posta gövdesi belirtin.

    > [!NOTE]
    > SharePoint listesinde öğeyi oluşturan kişiye projenin onaylanıp reddedildiğini bildirilir.

    ![Evet-Gönder-e-posta resmi](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. **Hayır ise** alanında, projenin reddedildiğini yansıtacak şekilde **konuyu** ve **gövdesini** değiştirme haricinde son beş adımı yineleyin.

     ![Gönder-e-posta görüntüsü](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Akışınızı tamamlama ve test etme

1. Akışınıza bir ad verin ve ardından **akış oluştur**' u seçin.

     ![Oluşturma-akış görüntüsü](./media/wait-for-approvals/create-flow.png)
1. SharePoint listenizde bir öğe oluşturun.

    Belirttiğiniz alıcıya bir onay e-postası gönderilir. Alıcı bu e-postadaki **Onayla** veya **Reddet** seçeneğini belirlediğinde, yanıtı belirten bir e-posta alırsınız.

## <a name="learn-more"></a>Daha fazla bilgi edinin

* [Tek onaylayan modern onaylar Kılavuzu](modern-approvals.md)
* [Sıralı onaylar](sequential-modern-approvals.md) oluşturma
* [Paralel onaylar](parallel-modern-approvals.md) oluştur
* [Go 'da istekleri](mobile-approvals.md) onaylama
