---
title: Herkesin onaylamasını gerektiren bir onay akışı oluşturun | Microsoft Docs
description: Herkesin onaylamasını veya bir kişinin bir isteği reddetmesini gerektiren bir onay akışı oluşturun.
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
ms.date: 02/27/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 191792c356dc6b5e3a285a16050a306d4e6039f2
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545194"
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Herkesin onaylamasını gerektiren bir onay akışı oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bu izlenecek yol, herkesin (atanan tüm onaylayanlar) bir tatil isteğinin onaylanmasını kabul etmesi için bir onay iş akışı oluşturmayı ve tüm onaylayanın tüm isteği reddedediğini gösterir.

Bu tür bir onay iş akışı, bir kişinin yöneticisinin ve yöneticisinin yöneticisinin onaylanabilmesi için bir tatil isteğini kabul etmesi gereken bir kuruluşta yararlıdır. Ancak, yönetici diğer kişinin girdisi olmadan isteği reddedebilirler.

> [!NOTE]
> Bu kılavuzda bir tatil onayı senaryosu vurgularken, bir isteği onaylamak için birden çok onaylayan gereken herhangi bir durumda bu tür onay akışını kullanabilirsiniz.
>
>

## <a name="prerequisites"></a>Kaynakları

* [Microsoft Flow](https://flow.microsoft.com), Microsoft Office 365 Outlook ve Microsoft Office 365 kullanıcılarına erişin.
* Bir SharePoint [listesi](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194).

    Bu izlenecek yol, tatilleri istemek için kullanılan bir SharePoint listesi oluşturduğunuzu varsayar. SharePoint listenizin nasıl görüneceğine ilişkin ayrıntılı bir örnek için [paralel onaylar](parallel-modern-approvals.md) kılavuzuna bakın.
* Akış oluşturma hakkında temel bilgiler.

    [Eylemlerin, tetikleyicilerin](multi-step-logic-flow.md#add-another-action)ve [koşulların](add-condition.md)nasıl ekleneceğini gözden geçirebilirsiniz. Aşağıdaki adımlarda, bu eylemlerin nasıl gerçekleştirileceğini bildiğiniz varsayılmaktadır.

> [!NOTE]
> Bu kılavuzda SharePoint ve Office 365 Outlook 'U kullandığımızda, Zendesk, Salesforce, Gmail veya Microsoft Flow tarafından desteklenen [200](https://flow.microsoft.com/connectors/) ' den fazla hizmetten herhangi biri gibi diğer hizmetleri de kullanabilirsiniz.
>
>

## <a name="create-the-flow"></a>Akışı oluşturma

> [!NOTE]
> Daha önce SharePoint veya Office 365 'e bir bağlantı oluşturmadıysanız, oturum açmanız istendiğinde yönergeleri izleyin.
>
>

Bu izlenecek yol belirteçleri kullanır. Belirteçlerin listesini göstermek için herhangi bir giriş denetimine dokunun veya tıklayın ve ardından açılan **dinamik içerik** listesinde belirteci arayın.

[Microsoft Flow](https://flow.microsoft.com)oturum açın ve ardından akışınızı oluşturmak için aşağıdaki adımları gerçekleştirin.

1. Ekranın sağ üst kısmındaki **Akışlarım** > **boş oluştur**' u seçin.
1. **SharePoint-bir öğe oluşturulduğunda veya değiştirildiğinde** tetikleyiciyi ekleyin.
1. Tatil isteği listenizi barındıran SharePoint sitesinin **site adresini** girin ve liste **listesi adını**seçin.
1. **Office 365 Users-Manager 'ı al v2** eylemini ekleyin, **Kullanıcı (UPN)** kutusunu seçin ve sonra **oluşturulan e-posta** belirtecini buna ekleyin.

    **Oluşturulan e-posta** belirteci, **dinamik içerik** listesinin **bir öğe oluşturulduğunda veya değiştirildiğinde** altında bulunur. Bu belirteç, SharePoint 'te öğeyi oluşturan kişi için yönetici hakkındaki verilere dinamik olarak erişim sağlar.

1. Başka bir **Office 365 kullanıcıları-yönetici v2 al** eylemi ekleyin ve ardından **posta** belirtecini **Kullanıcı (UPN)** kutusuna ekleyin.

    **Posta** belirteci, **dinamik Içerik** listesinin **yöneticiyi al v2 2** kategorisinin altında bulunur. Bu belirteç dinamik olarak yöneticinin yöneticisinin e-posta adresine erişim sağlar.

    Ayrıca **Get Manager v2 2** kartını "düzey yöneticisini atla" gibi anlamlı bir şekilde yeniden adlandırabilirsiniz.
1. **Onay Başlat** eylemini ekleyin ve ardından **onay türü** listesinden **atanan listesinden herkes** ' i seçin.

   > [!IMPORTANT]
   > Herhangi bir onaylayan reddederse, onay isteği tüm onaylayanlar için reddedildi olarak değerlendirilir.
   >
   >
1. **Bir onay başlangıcı** kartını tamamlamaya yönelik kılavuz olarak aşağıdaki tabloyu kullanın.

   | alanla | Açıklaması |
   | --- | --- |
   |  Onay türü |Onaylayanlardan herhangi birinin isteği onaylayamayacağını veya reddedemeyeceğini belirtmek için **atanan listesindeki herkesi** kullanın. </p>Bir isteğin yalnızca herkes kabul ederse onaylandığını ve tek bir kişi tarafından reddederse isteğin reddedildiğini belirtmek için **atanan listeden herkes** ' i kullanın. |
   |  Başlığın |Onay isteğinin başlığı. |
   |  Şuna atandı |Onaylayanlara ait e-posta adresleri. |
   |  Bilgileri |**Atanan** alanında listelenen onaylayanlara gönderilmesini istediğiniz ek bilgiler. |
   |  Öğe bağlantısı |Onay öğesinin URL 'SI. Bu örnekte, SharePoint içindeki bir öğe bağlantıdır. |
   |  Öğe bağlantısı açıklaması |**Öğe bağlantısı**için bir metin açıklaması. |

   > [!TIP]
   > **Onay Başlat** eylemi, **Yanıt** ve **Yanıt Özeti**dahil olmak üzere birkaç belirteç sağlar. Bir onay isteği akışı çalıştırmasının sonuçlarını zengin olarak raporlamak için akışınızda bu belirteçleri kullanın.
   >
   >

    **Onay başlatma** kartı, onaylayanlara gönderilen onay isteği için bir şablondur. Kuruluşunuz için yararlı bir şekilde yapılandırın. İşte bir örnek.

    ![onay başlatma](media/all-assigned-must-approve/start-an-approval-card.png)

1. **Office 365 Outlook-e-posta gönder** eylemini ekleyin ve ardından isteğin sonuçlarıyla birlikte bir e-posta gönderecek şekilde yapılandırın.

    **E-posta gönder** kartının nasıl görünebileceğini bir örnek aşağıda verilmiştir.

    ![e-posta gönder](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> Onay **Başlat** eylemini izleyen herhangi bir eylem, onay **başlatma** kartındaki **onay türü** listesinde yer alan seçiminize göre çalışır. Aşağıdaki tabloda, seçiminize göre davranış listelenmiştir.
>
>

| Onay türü | Durum |
| --- | --- |
| Atanan listeden herkes |Onaylayanlardan herhangi biri karar verdiğinde, **onay Başlat** eylemini izleyen eylemler çalışır. |
| Atanan listeden herkes |Bir onaylayanın reddetme veya herkes isteği onayladıktan sonra **onay Başlat** eylemini izleyen eylemler çalıştırılır. |

Ekranın üst kısmında Flow **adı** kutusuna akışınız için bir ad girin ve ardından **akış oluştur** ' u seçerek kaydedin.

Tebrikler, akışınız tamamlanmıştır! Daha sonra, akışınız bu görüntüye benzer.

![genel akış görüntüsü](media/all-assigned-must-approve/overall-flow.png)

Artık, SharePoint listenize bir öğe eklendiğinde veya bir öğe değişirse, akış, onay **başlatma** kartının **atanan** kutusunda listelenen tüm onaylayanlara onay istekleri tetikler ve gönderir. Akışınız Microsoft Flow mobil uygulama ve e-posta aracılığıyla onay istekleri gönderir. SharePoint 'te öğeyi oluşturan kişi, sonuçları özetleyen, isteğin onaylanmış veya reddedilmiş olduğunu açıkça belirten bir e-posta alır.

Her onaylayana gönderilen onay isteğine bir örnek aşağıda verilmiştir.

![onay isteği](media/all-assigned-must-approve/approval-request.png)

Flow çalıştıktan sonra yanıt ve yanıt özetinin nasıl görünebileceklerini aşağıda görebilirsiniz.

![Yanıt belirteçleri](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>Onaylar hakkında daha fazla bilgi edinin

* [Tek onaylayan modern onaylar](modern-approvals.md)
* [Sıralı modern onaylar](sequential-modern-approvals.md)
* [Paralel modern onaylar](parallel-modern-approvals.md)
* [Onaylar ve Microsoft Common Data Service](common-data-model-approve.md)
* [Go 'da istekleri onaylama](mobile-approvals.md)
