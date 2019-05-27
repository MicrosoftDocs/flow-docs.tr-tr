---
title: Herkesin onaylamasını gerektiren bir onay akışı oluşturma| Microsoft Docs
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
ms.openlocfilehash: 141eb19018e080191bf0fe2ba6f47f0739d347d7
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456650"
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Herkesin onaylamasını gerektiren bir onay akışı oluşturma

Bu kılavuzda, bir izin isteğinin onaylanması için herkesin (atanan tüm onaylayanların) kabul etmesi gereken, ancak herhangi bir onaylayanın tüm isteği reddedebileceği bir onay iş akışı oluşturma açıklanmaktadır.

Bu onay iş akışı türü, izin isteğinin onaylanması için kişinin yöneticisinin ve yöneticinin yöneticisinin onay vermesini gerektiren kuruluşlar için kullanışlıdır. Ancak herhangi bir yönetici diğer yöneticinin girdisine gerek olmadan isteği reddedebilir.

> [!NOTE]
> Bu kılavuzda bir tatil onayı senaryosu vurgulanıyor olsa da bu türde bir onay akışını, bir isteğin birden çok onaylayan tarafından onaylanması gereken tüm durumlarda kullanabilirsiniz.
>
>

## <a name="prerequisites"></a>Önkoşullar

* [Microsoft Flow](https://flow.microsoft.com), Office 365 Outlook ve Microsoft Office 365 Kullanıcıları için erişim.
* SharePoint [listesi](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194).

    Bu kılavuzda, tatil istekleri için kullanılan bir SharePoint Online listesini oluşturmuş olduğunuz varsayılır. SharePoint listenizin nasıl görünebileceği hakkında ayrıntılı bir örnek için [paralel onaylar](parallel-modern-approvals.md) kılavuzuna bakın.
* Akış oluşturma hakkındaki temel bilgileri edinme.

    [Eylemler, tetikleyiciler](multi-step-logic-flow.md#add-another-action) ve [koşulları](add-condition.md) nasıl ekleyeceğinizi gözden geçirebilirsiniz. Aşağıdaki adımlarda bu eylemleri nasıl gerçekleştireceğinizi bildiğiniz varsayılmaktadır.

> [!NOTE]
> Bu kılavuzda SharePoint ve Office 365 Outlook uygulamalarını kullanacağız. Ancak dilerseniz Zendesk, Salesforce, Gmail veya Microsoft Flow’un desteklediği [200’den fazla hizmetten birini](https://flow.microsoft.com/connectors/) de kullanabilirsiniz.
>
>

## <a name="create-the-flow"></a>Akışı oluşturma

> [!NOTE]
> Önceden SharePoint veya Office 365’e bir bağlantı oluşturmadıysanız, oturum açmanız istendiğinde yönergeleri izleyin.
>
>

Bu kılavuzda belirteçler kullanılmaktadır. Belirteçlerin listesini görüntülemek için, herhangi bir giriş denetimine dokunun veya tıklayın ve açılan **Dinamik içerik** listesinde belirteci arayın.

[Microsoft Flow](https://flow.microsoft.com)’da oturum açarak akışınızı oluşturmak için aşağıdaki adımları uygulayın.

1. Ekranın sağ üst tarafında **Akışlarım** > **Boş akış oluştur** seçeneğini belirleyin.
1. **SharePoint - Bir öğe oluşturulduğunda veya değiştirildiğinde** tetikleyicisini ekleyin.
1. Tatil isteği listenizi barındıran SharePoint sitesinin **Site Adresini** girip **Liste Adı**’ndan listeyi seçin.
1. **Office 365 Kullanıcıları - Yöneticiyi al V2** eylemini ekleyin ve sonra **Kullanıcı (UPN)** kutusunu seçip bu kutuya **Oluşturan E-postası** belirtecini ekleyin.

    **E-posta ile Oluşturuldu** belirteci, **Dinamik içerik** listesinin **Bir öğe oluşturulduğunda veya değiştirildiğinde** kategorisinde bulunur. Bu belirteç, SharePoint'te öğeyi oluşturan kişiye yönetici hakkında veriler için dinamik olarak erişim sağlar.

1. Başka bir **Office 365 Kullanıcıları - Yöneticiyi al V2** eylemi ekleyin ve sonra **Kullanıcı (UPN)** kutusuna **E-posta** belirtecini ekleyin.

    **E-posta** belirteci, **Dinamik içerik** listesinin **Yöneticiyi al C2 2** kategorisinde bulunur. Bu belirteç dinamik olarak yöneticinin yöneticisinin e-postasına erişim sağlar.

    Ayrıca **Yöneticiyi al V2 2** kartını "Düzey yöneticisini atla" gibi anlamlı bir şekilde yeniden adlandırabilirsiniz.
1. **Onay başlatın** eylemini ekleyin ve ardından **Onay türü** listesinden **Atanan listesindeki herkes**’i seçin.

   > [!IMPORTANT]
   > Herhangi bir onaylayan isteği reddederse, onay isteği tüm onaylayanlar için reddedilmiş olarak değerlendirilir.
   >
   >
1. **Bir onay başlatın** kartını tamamlamak için aşağıdaki tabloyu kılavuz olarak kullanın.

   | Alan | Açıklama |
   | --- | --- |
   |  Onay türü |Onaylayanlardan herhangi birinin isteği onaylayabileceğini veya reddedebileceğini belirtmek için **Atanan listesinden herhangi biri**’ni seçin. </p>Bir isteğin yalnızca herkes onayladığında onaylandığını ve tek bir kişi reddettiğinde reddedildiğini belirtmek için **Atanan listesindeki herkes**’i seçin. |
   |  Başlık |Onay isteği başlığı. |
   |  Atanan |Onaylayanların e-posta adresleri. |
   |  Ayrıntılar |**Atanan** alanında listelenen onaylayanlara göndermek istediğiniz ek bilgiler. |
   |  Öğe bağlantısı |Onay öğesi URL’si. Bu örnekte bu, SharePoint öğesine yönlendiren bir bağlantıdır. |
   |  Öğe bağlantısı açıklaması |**Öğe bağlantısı** için bir metin açıklaması. |

   > [!TIP]
   > **Onay başlatın** eylemi **Yanıt** ve **Yanıt özeti** dahil birkaç belirteç sağlar. Bir onay isteği akışının sonuçlarına ilişkin zengin raporlama sağlamak için akışınızda bu belirteçleri kullanın.
   >
   >

    **Onay başlatın** kartı, onaylayanlara gönderilen onay isteğine yönelik bir şablondur. Bunu kuruluşunuza uygun olacak şekilde yapılandırabilirsiniz. İşte bir örnek:

    ![bir onay başlatma](media/all-assigned-must-approve/start-an-approval-card.png)

1. **Office 365 Outlook - E-posta gönder** eylemini ekleyin ve istek sonuçlarını e-posta ile göndermek için yapılandırın.

    **E-posta gönder** kartı şu örnekteki gibi görünebilir.

    ![e-posta gönder](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> **Onay başlatın** eylemini izleyen eylemler, **Onay başlatın** kartındaki **Onay türü** listesindeki seçiminize göre çalıştırılır. Aşağıdaki tabloda seçiminize dayanan davranışlar listelenmektedir.
>
>

| Onay türü | Davranış |
| --- | --- |
| Atanan listesinden herhangi biri |**Onay başlatın** eylemini izleyen eylemler, onaylayanlardan herhangi biri karar verdikten sonra çalıştırılır. |
| Atanan listesindeki herkes |**Onay başlatın** eylemini izleyen eylemler, bir onaylayan isteği onayladıktan veya reddettikten sonra çalıştırılır. |

Ekranın en üstünde, **Akış adı** kutusuna akışınız için bir ad girin ve kaydetmek için **Akış oluştur**’u seçin.

Tebrikler, akışınız tamamlandı! Buradaki adımları izlediyseniz, akışınız şu resme benzer şekilde görünür.

![genel akış görüntüsü](media/all-assigned-must-approve/overall-flow.png)

Artık SharePoint listenize öğe eklendiğinde veya bir öğe değiştirildiğinde akışınız tetiklenir ve **Onay başlatın** kartının **Atanan** kutusunda listelenen tüm onaylayanlara onay istekleri gönderilir. Akışınız onay isteklerini Microsoft Flow mobil uygulaması ve e-posta üzerinden gönderir. SharePoint’te öğeyi oluşturan kişi, sonuçları özetleyen ve isteğin onaylandığını veya reddedildiğini açıkça belirten bir e-posta alır.

Her onaylayana gönderilen onay isteği için aşağıda bir örnek verilmiştir.

![onay isteği](media/all-assigned-must-approve/approval-request.png)

Akışınız çalıştıktan sonra bir yanıtın ve yanıt özetinin nasıl görünebileceğine ilişkin bir örneği aşağıda bulabilirsiniz.

![yanıt belirteçleri](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>Onaylar hakkında daha fazla bilgi edinin

* [Tek onaylayanlı modern onaylar](modern-approvals.md)
* [Sıralı modern onaylar](sequential-modern-approvals.md)
* [Paralel modern onaylar](parallel-modern-approvals.md)
* [Onaylar ve Microsoft Common Data Service](common-data-model-approve.md)
* [İstekleri hareket halinde onaylama](mobile-approvals.md)
