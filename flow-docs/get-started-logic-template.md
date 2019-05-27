---
title: Şablondan akış oluşturma | Microsoft Docs
description: Çeşitli yerleşik şablonlardan birini kullanarak akış oluşturun.
services: ''
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
ms.author: anneta
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 52aae570f65eaae537f548e686f437592eb5ef03
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461266"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>Microsoft Flow'da şablondan akış oluşturma
Birçok yerleşik şablondan birini (örneğin, yöneticiniz Office 365'te bir e-posta gönderdiğinde size Slack iletisi gönderecek bir şablon) kullanarak bir akış oluşturun.

**Not:** [Sıfırdan bir akış oluşturma](get-started-logic-flow.md) zaten aklınızda bir işlem varsa ve bir şablon bulamıyorsanız.

**Önkoşullar**

* [flow.microsoft.com](https://flow.microsoft.com)'da bir hesap
* Slack hesabı
* Office 365 kimlik bilgileri

## <a name="choose-a-template"></a>Şablon seçme
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. [flow.microsoft.com](https://flow.microsoft.com)'da, üst gezinti çubuğunda bulunan **Şablonlar**'ı seçin.
2. Arama çubuğuna **Slack** yazın ve arama simgesini seçin.
3. Yalnızca Slack ile ilgili şablonları görürsünüz. Böylece artık **Yöneticim e-posta gönderdiğinde Slack üzerinden ileti gönder**'i seçebilirsiniz.
   
    ![Sol gezinti çubuğundaki yeni seçenek](./media/get-started-logic-template/select-template.png)
4. Bu şablonun istediklerinizi yapacağını onaylayın ve **Bu şablonu kullan**’ı seçin.
5. Office veya Slack’te oturum açmadıysanız, **Oturum aç**’ı seçin ve yönergeleri takip edin.
   
    ![Şablon için gerekli bağlantılar listesi](./media/get-started-logic-template/confirm-connections.png)
6. Bağlantılarınızı onayladıktan sonra **Devam**’ı seçin.
   
    Her bir eylemin turuncu bir başlık çubuğuyla gösterildiği akışınız görüntülenir.
   
    ![Şablona ilişkin eylemler ve varsayılan olaylar](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Akışınızı özelleştirme
1. Bir olayı genişletmek için başlık çubuğunu seçin ve ardından olayı özelleştirin. Örneğin, e-postada ilgilendiğiniz olaya ilişkin bir filtre belirtin.
2. Giriş sağlamanız gereken eylemler otomatik olarak genişletilir.
   
    Örneğin, bir kanal (ör. *\@kullanıcı adınız*) girmeniz gerektiği için **İleti gönder** eylemi genişletilir. Ayrıca, ileti içeriğini de özelleştirebilirsiniz. İleti, varsayılan olarak yalnızca konuyu içerir ancak iletiye diğer bilgileri de ekleyebilirsiniz.
   
    ![Slack için kanal belirtme](./media/get-started-logic-template/specify-keyword.png)
3. Ekranın üst kısmında, akışınız için bir ad belirtin ve ardından **Akış oluştur**'u seçin.
4. Son olarak, akışınızla ilgili herhangi bir sorununuz yoksa **Bitti**'yi seçin.
   
    ![Bitti düğmesi](./media/get-started-logic-template/done.png)

Artık yöneticiniz size bir e-posta gönderdiğinde, belirttiğiniz bilgileri içeren bir Slack iletisi alacaksınız.

## <a name="next-steps"></a>Sonraki adımlar
* [Akışınızı çalışırken izleme](see-a-flow-run.md)
* [Kendi şablonunuzu yayımlama](publish-a-template.md)
* [Common Data Service için bir şablon kullanma](common-data-model-intro.md)
* [Takım akışlarını kullanmaya başlayın](create-team-flows.md) ve akış tasarlamak üzere sizinle birlikte çalışmaları için diğer kişileri davet edin.

