---
title: E-posta özelliklerine göre akışları çalıştırın | Microsoft Docs
description: Konu, gönderenin adresi veya alıcının e-posta adresi gibi özelliklere göre bir akış başlatın.
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
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b1dcb98d5bb99c9eaf2843ec75a8bdfaf03fa913
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544950"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>E-posta özelliklerine göre akış tetikleme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Aşağıdaki e-posta özelliklerinden biri veya daha fazlası sağladığınız ölçütlerle eşleşiyorsa çalışan bir akış oluşturmak için **Yeni bir e-posta geldiğinde** tetikleyicisi kullanın:

| Özelliði | Ne zaman kullanılır? |
| --- | --- |
| Klasörde |Belirli bir klasöre her e-posta geldiğinde bir akış tetikleyin. Bu özellik, e-postaları farklı klasörlere yönlendiren kurallarınız varsa yararlı olabilir. |
| Hedef |Bir e-postanın gönderildiği adrese göre bir akış tetikleyin. Aynı gelen kutusunda farklı e-posta adreslerine gönderilen e-posta alırsanız bu özellik yararlı olabilir. |
| Kaynak |Gönderenin e-posta adresine göre bir akış tetikleyin. |
| Önem |E-postaların gönderildiği önem derecesine göre bir akış tetikleyin. Yüksek, normal veya düşük öneme sahip e-posta gönderilebilir. |
| Eki vardır |Gelen e-postalardaki eklerin varlığına göre bir akış tetikleyin. |
| Konu filtresi |E-posta konusunun belirli sözcüklerin varlığını arayın. Akışınız daha sonra aramanızın sonuçlarını temel alan *eylemleri* çalıştırır. |

> [!IMPORTANT]
> Her [Microsoft Flow planı](https://flow.microsoft.com/pricing/) bir çalıştırma kotası içerir. Mümkün olduğunda akışın tetikleyicisinde her zaman özellikleri denetleyin. Bunu yaptığınızda, çalıştırma kotayı gereksiz şekilde kullanmaktan kaçınmayın. Bir koşuldaki bir özelliği denetlemeniz durumunda, tanımladığınız filtre koşulu karşılanmasa bile, her bir çalıştırma planınızın çalışma kotasına göre sayılır. 

Örneğin, bir e-postanın *Kimden* adresini bir koşula göre denetleseniz, ilgilendiğiniz adresten olmasalar bile her çalıştırma, planınızın çalıştırma kotasına göre sayılır.
> 
> 

Aşağıdaki izlenecek yollarda, **Yeni bir e-posta geldiğinde** tetikleyiciden tüm özellikleri denetliyoruz. [Sık sorulan faturalandırma sorularını](billing-questions.md#what-counts-as-a-run) ve [fiyatlandırma](https://ms.flow.microsoft.com/pricing/) sayfasını ziyaret ederek daha fazla bilgi edinin.

## <a name="prerequisites"></a>Kaynakları
* [Microsoft Flow](https://flow.microsoft.com) erişimi olan bir hesap
* Office 365 Outlook hesabı
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows) için mobil uygulama Microsoft Flow
* Office, Outlook ve anında iletme bildirimi hizmeti bağlantıları

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>E-postanın konusuna göre akış tetikleme
Bu kılavuzda, yeni e-postaların konusu içinde "Loma" sözcüğü varsa cep telefonunuza anında iletme bildirimi gönderen bir akış oluşturacağız. Daha sonra akışınız bu tür e-postaları *okundu*olarak işaretler.

>[!NOTE]
>Bu kılavuzda bir anında iletme bildirimi gönderilirken, iş akışı gereksinimlerinize uyan diğer işlemleri kullanabilirsiniz. Örneğin, e-posta içeriklerini Google sayfaları gibi başka bir depoda veya Dropbox 'ta depolanan bir Microsoft Excel dosyası ile saklayabilirsiniz.

Tamam, haydi başlayalım:

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. **Konu filtresi** kutusunda, akışlarınızın gelen e-postaları filtrelemek için kullandığı metni girin.
   
     Bu örnekte, konusunun "Loma" sözcüğünün bulunduğu tüm e-postalar ilginizi çekiyoruz.
   
    ![Gelişmiş Seçenekler](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Daha önce belirttiğiniz **Konu filtresiyle** eşleşen bir e-posta aldığınızda, almak istediğiniz mobil bildirime ilişkin ayrıntıları girin.
   
    ![Bildirim ayrıntıları](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Akışınıza bir ad verin. Ardından sayfanın üst kısmında **akış oluştur** ' u seçerek kaydedin.
   
    ![akışı Kaydet](./media/email-triggers/email-triggers-subject-notification.png)

Mühendisi! Artık konu içinde "Loma" sözcüğünü içeren bir e-posta aldığınızda anında iletme bildirimi alırsınız.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>E-posta göndericisine göre akış tetikleme
Bu kılavuzda, belirli bir gönderenden (e-posta adresi) gelen yeni bir e-posta geldiğinde cep telefonunuza anında iletme bildirimi gönderen bir akış oluşturacağız. Akışta Ayrıca bu e-postaları *okundu*olarak işaretler.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. **Kimden** kutusunda, gönderenin e-posta adresini girin. 
   
     Akışınız, bu adresten gönderilen tüm e-postalarda işlem gerçekleştirir.
   
    ![Email özelliği](./media/email-triggers/email-triggers-from.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Daha önce girdiğiniz e-posta adresinden bir ileti geldiğinde almak istediğiniz mobil bildirime ilişkin ayrıntıları girin.
   
    ![Bildirim ayrıntıları](./media/email-triggers/email-triggers-sender-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Akışınıza bir ad verin ve ardından sayfanın üst kısmında **akış oluştur** ' u seçerek kaydedin.
   
    ![akışı Kaydet](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>E-postalar belirli bir klasöre ulaştığında bir akış Tetikle
E-postayı adres gibi belirli özelliklere göre farklı klasörlere yönlendiren kurallarınız varsa, bu tür bir akışa isteyebilirsiniz.

Haydi başlayalım:

> [!NOTE]
> E-postayı gelen kutunuza ait bir klasöre yönlendiren bir kuralınız yoksa, böyle bir kural oluşturun ve bir sınama e-postası göndererek çalıştığını onaylayın.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Belirli e-postaları yönlendirçalıştığınız klasörü seçin. Tüm e-posta klasörlerini görüntülemek için önce **Yeni bir e-posta geldiğinde** sayfasında **klasör** kutusunun sağ tarafında yer alan **seçiciyi göster** simgesini seçin.
   
    ![Klasör Seç](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Daha önce seçtiğiniz klasöre bir e-posta geldiğinde almak istediğiniz mobil bildirime ilişkin ayrıntıları girin. Henüz yapmadıysanız, bildirimler hizmeti için kimlik bilgilerini girin.
   
    ![Bildirim ayrıntıları](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Akışınıza bir ad verin ve ardından sayfanın üst kısmında **akış oluştur** ' u seçerek kaydedin.
   
    ![akışı Kaydet](./media/email-triggers/email-triggers-7.png)

Bu izlenecek yolda daha önce seçtiğiniz klasöre yönlendirilen bir e-posta göndererek akışı test edin.

