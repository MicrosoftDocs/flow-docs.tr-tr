---
title: Bir akış oluşturarak görevleri otomatikleştirme | Microsoft Docs
description: E-posta gönderme gibi bir veya daha fazla eylemi otomatik olarak gerçekleştiren bir akış oluşturun; örneğin, bir SharePoint listesine satır ekleme gibi olaylar oluşur.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/04/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 494a5f978b7792fa971a53cfda85addd9b78f929
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548300"
---
# <a name="create-a-flow-in-microsoft-flow"></a>Microsoft Flow akış oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

Bir olay tarafından tetiklendikten sonra bir veya daha fazla görevi otomatik olarak gerçekleştiren bir akış oluşturun. Örneğin, bir Kullanıcı belirttiğiniz anahtar sözcüğü içeren bir tweet gönderdiğinde size e-posta ile bildirimde bulunan bir akış oluşturun. Bu örnekte, Tweet gönderme olayıdır ve posta gönderme eylemi olur.

## <a name="prerequisites"></a>Kaynakları

* [Flow.Microsoft.com](https://flow.microsoft.com) üzerinde bir hesap
* Twitter hesabı
* Office 365 kimlik bilgileri

## <a name="specify-an-event-to-start-the-flow"></a>Akışı başlatmak için bir olay belirtin

İlk olarak, hangi olay veya *tetikleyiciyi*seçmeniz gerekir, akışınızı başlatır.

1. [Flow.Microsoft.com](https://flow.microsoft.com)' de, üst gezinti çubuğunda **Akışlarım** ' ı seçin ve sonra **boş oluştur**' u seçin.

    ![Sol gezinti çubuğundaki akışlar seçeneği](./media/get-started-logic-flow/create-logic-flow.png)
1. Ekranın alt kısmındaki **yüzlerce bağlayıcı ve tetikleyici ara** kutusunu seçin, **tüm bağlayıcılar ve Tetikleyiciler ara**' nın ardından Twitter **' ı** seçin ve **Yeni bir tweet gönderildiğinde Twitter**' ı seçin.

    ![Twitter olayı](./media/get-started-logic-flow/twitter-search.png)

1. Twitter hesabınızı Microsoft Flow için zaten bağladıysanız **Twitter 'Da oturum aç**' ı seçin ve ardından kimlik bilgilerinizi sağlayın.

1. **Arama metin** kutusuna bulmak istediğiniz anahtar sözcüğü yazın.

    ![Twitter anahtar sözcüğü](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Bir eylem belirtin

1. **Yeni adım**' ı seçin ve ardından **Eylem Ekle**' yi seçin.

    ![Eylem Ekle](./media/get-started-logic-flow/add-action-icon.png)

1. **Tüm bağlayıcılar ve eylemler ara**' yı gösteren kutuya **e-posta gönder**yazın veya yapıştırın ve ardından **Office 365 Outlook-e-posta gönder**' i seçin.

    ![Eylemlerin listesi](./media/get-started-logic-flow/send-email.png)

1. İstenirse, oturum aç düğmesini seçin ve ardından kimlik bilgilerinizi sağlayın.

1. Görüntülenen **formda, kimden kutusuna e** -posta adresinizi yazın veya yapıştırın, ardından görüntülenen kişiler listesinden adınızı seçin.

    ![Boş e-posta iletisi](./media/get-started-logic-flow/blank-email.png)
1. **Konu** kutusuna **Yeni Tweet From:** yazın veya yapıştırın ve ardından bir boşluk yazın.

    ![Yer tutucu içeren konu satırı](./media/get-started-logic-flow/message-token.png)
1. Belirteç listesinde, için bir yer tutucu eklemek üzere belirtece **göre doldurulabilir** ' i seçin.

    ![Parametre Ekle](./media/get-started-logic-flow/add-parameter.png)
1. **Gövde** kutusunu seçin ve ardından **Tweet metin** belirtecini seçerek bunun için bir yer tutucu ekleyin.
1. seçim E-postanın gövdesine daha fazla belirteç, diğer içerik veya her ikisini birden ekleyin.
1. Ekranın üst kısmındaki akışınızı adlandırın ve ardından **akış oluştur**' u seçin.

    ![Akış Oluştur düğmesini seçin](./media/get-started-logic-flow/create-button.png)
1. Akışlar listesini güncelleştirmek için **bitti** ' yi seçin.

     ![Bitti düğmesini seçin](./media/get-started-logic-flow/done-button.png)
1. Belirttiğiniz anahtar sözcüğü içeren bir tweet gönderin veya başka birisinin böyle bir tweet göndermesini bekleyin.

     Tweet nakledildikten sonra bir dakika içinde, bir e-posta iletisi size yeni Tweet.

> [!TIP]
> Yazı tipini özelleştirdiğiniz e-postayı biçimlendirmek için **e-posta gönder (v2)** eylemini kullanın, kalın, italik veya alt çizgi kullanın, renk ve açıkton ' yi özelleştirin, listeler veya bağlantılar oluşturun ve daha fazlasını yapın.

![Zengin e-posta düzenleme](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>Akış yönetme

1. [Flow.Microsoft.com](https://flow.microsoft.com)' de, üst gezinti çubuğunda **Akışlarım** ' ı seçin.
1. Akışlar listesinde aşağıdakilerden birini yapın:

   * Bir akışı duraklatmak için, geçişi **kapalı**olarak ayarlayın.

       ![Akışı Duraklat](./media/get-started-logic-flow/pause-flow.png)
   * Bir akışı geri almak için, geçiş işlemini **Açık**olarak ayarlayın.

       ![Akışı sürdürür](./media/get-started-logic-flow/resume-flow.png)
   * Bir akışı düzenlemek için, düzenlemek istediğiniz akışa karşılık gelen kurşun kalem simgesini seçin.

       ![Akış seçin](./media/get-started-logic-flow/select-flow.png)
   * Bir akışı silmek için **...** simgesini seçin, **Sil**' i seçin ve ardından görüntülenen ileti kutusunda **Sil** ' i seçin.

       ![Simgeyi Sil](./media/get-started-logic-flow/delete-icon.png)
   * Bir akışın çalıştırma geçmişini görüntülemek için **Akışlarım** sayfasından akışı seçin ve açılan SAYFANıN **çalıştırma geçmişi** bölümünün altında geçmişi görüntüleyin.

       ![çalıştırma geçmişi](./media/get-started-logic-flow/run-history.png)

     Her adımın giriş ve çıkışlarını görmek için çalıştırmalar listesinden bir akış çalıştırması seçin.

> [!NOTE]
> Hesabınızda en fazla 600 akış olabilir. Zaten 600 akışlarınız varsa, başka bir akış oluşturmadan önce bir tane silin.
>
>

## <a name="next-steps"></a>Sonraki adımlar

* Akışınız için farklı yollar gibi [adımları ekleyin](multi-step-logic-flow.md).
* Bir eylemin her gün, belirli bir tarihte veya belirli bir dakika sayısından sonra gerçekleşmesini istediğinizde [görevleri bir zamanlamaya göre çalıştırın](run-scheduled-tasks.md).
* Uygulamanızın bulutta mantığı çalıştırmasına izin vermek için [bir uygulamaya akış ekleyin](https://powerapps.microsoft.com/tutorials/using-logic-flows/) .
* [Ekip akışlarını kullanmaya](create-team-flows.md) başlayın ve başkalarının akışları tasarlayabilmeniz için sizinle işbirliği yapmasını isteyin.
