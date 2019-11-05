---
title: Şablondan akış oluşturma | Microsoft Docs
description: Birkaç yerleşik şablondan herhangi birinden bir akış oluşturun.
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
ms.date: 02/07/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 874a942c4422fb402bc564609aff6ea06449ef78
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548242"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>Microsoft Flow şablondan akış oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Örneğin, yöneticinizin Office 365 ' de size bir e-posta göndermesi durumunda size bir bolluk iletisi gönderebilecekleri birçok yerleşik şablondan bir akış oluşturun.

**Not:** zaten bir işleminiz varsa ve kendisi için bir şablon bulamıyorsanız [sıfırdan bir akış oluşturun](get-started-logic-flow.md) .

**Kaynakları**

* [Flow.Microsoft.com](https://flow.microsoft.com) üzerinde bir hesap
* Bir bolluk hesabı
* Office 365 kimlik bilgileri

## <a name="choose-a-template"></a>Şablon seçin
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. [Flow.Microsoft.com](https://flow.microsoft.com)' de, üst gezinti çubuğunda **Şablonlar** ' ı seçin.
2. Arama çubuğunda **bolluk**yazın ve arama simgesini seçin.
3. Yalnızca bolluk ile ilgili şablonlar görürsünüz, bu nedenle artık **yönetici bana e-posta geldiğinde bolluk üzerinde Ileti gönder**' i seçebilirsiniz.
   
    ![Sol gezinti çubuğundaki yeni seçenek](./media/get-started-logic-template/select-template.png)
4. Bu şablonun istediğiniz şeyi yaptığını onaylayın ve ardından **Bu şablonu kullan**' ı seçin.
5. Office veya bolluk içinde oturum açmadıysanız, **oturum aç** ' ı seçin ve ardından istemleri izleyin.
   
    ![Şablonun gerektirdiği bağlantıların listesi](./media/get-started-logic-template/confirm-connections.png)
6. Bağlantılarınızı doğruladıktan sonra **devam**' ı seçin.
   
    Akışınız, turuncu başlık çubuğu ile her bir eylemi gösteren görüntülenir.
   
    ![Şablondaki varsayılan olaylar ve eylemler](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Akışınızı özelleştirme
1. Genişletilecek bir olay için başlık çubuğunu seçin ve sonra (örneğin, ilgilendiğiniz e-postada bir filtre belirterek) özelleştirin.
2. Sizin için giriş gerektiren eylemler otomatik olarak genişletilir.
   
    Örneğin, *\@Kullanıcı adı*gibi bir kanal girmeniz gerektiği Için **ileti gönder** eylemi genişletilir. İleti içeriğini de özelleştirebilirsiniz. Varsayılan olarak, ileti yalnızca konuyu içerir, ancak diğer bilgileri de ekleyebilirsiniz.
   
    ![Bolluk için kanal belirtme](./media/get-started-logic-template/specify-keyword.png)
3. Ekranın üst kısmında, akışınız için bir ad belirtin ve ardından **akış oluştur**' u seçin.
4. Son olarak, akışınız hakkında memnunsanız **bitti**' yi seçin.
   
    ![Bitti düğmesi](./media/get-started-logic-template/done.png)

Artık yöneticiniz size bir e-posta gönderdiğinde, belirttiğiniz bilgileri içeren bir bolluk iletisi alırsınız.

## <a name="next-steps"></a>Sonraki adımlar
* [Akışınızı işlem içinde izleyin](see-a-flow-run.md)
* [Kendi şablonunuzu yayımlayın](publish-a-template.md)
* [Common Data Service için bir şablon kullanın](common-data-model-intro.md)
* [Ekip akışlarını kullanmaya](create-team-flows.md) başlayın ve başkalarının akışları tasarlayabilmeniz için sizinle işbirliği yapmasını isteyin.

