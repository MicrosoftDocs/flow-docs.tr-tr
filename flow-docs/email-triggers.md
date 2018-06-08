---
title: E-posta özelliklerine göre akışları çalıştırın. | Microsoft Docs
description: Konu, gönderen adresi veya bir e-postanın alıcısı gibi özellikler temelinde bir akış başlatın.
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
ms.openlocfilehash: 395cb9bc1d58e50e5ac8ebac9afaed544f3261ec
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440019"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>E-posta özelliklerine göre akış tetikleme
Bu e-posta özelliklerinden biri veya birden fazlası, sağladığınız ölçütlerle eşleştiğinde çalışan bir akış oluşturmak için **Yeni bir e-posta geldiğinde** tetikleyicisini kullanın:

| Özellik | Ne zaman kullanılır? |
| --- | --- |
| Klasör |Belirli bir klasöre her e-posta gelişinde bir akış tetikler. Bu özellik, e-postaları farklı klasörlere yönlendiren kurallarınız varsa yararlı olabilir. |
| Kime |E-postanın alıcısı olan adrese göre bir akış tetikler. Bu özellik, aynı gelen kutusundaki farklı e-posta adreslerinde e-posta almanız durumunda yararlı olabilir. |
| Kimden |Gönderenin e-posta adresine göre bir akış tetikler. |
| Önem |E-postaların gönderildiği önem derecesine göre bir akış tetikler. E-postalar yüksek, normal veya düşük önem derecesiyle gönderilebilir. |
| Ekleri Var |Gelen e-postalarda ek olup olmamasına göre bir akış tetikler. |
| Konu Filtresi |Bir e-postanın konusunda belirli sözcüklerin olup olmadığını belirlemek için arama yapar. Böylece akışınız aramanızın sonuçlarına göre *eylemler* çalıştırır. |

> [!IMPORTANT]
> Her [Microsoft Flow planı](https://flow.microsoft.com/pricing/) bir çalıştırma kotası içerir. Akışın tetikleyicisindeki özellikleri her zaman kontrol etmeye çalışın; bu şekilde, çalıştırma kotanızın gereksiz yere kullanılmasını önlemiş olursunuz. Bir koşulda yer alan bir özelliği kontrol etmeniz durumunda, tanımladığınız filtre koşulu karşılanmamış olsa bile her çalıştırma, planınızın çalıştırma kotasında hesaba katılır. Örneğin, bir koşulda e-postanın *kimden* adresini kontrol etmeniz durumunda, e-postanın *göndereni* sizin ilgilendiğiniz adres olmasa bile her çalıştırma, planınızın çalıştırma kotasında hesaba katılır.
> 
> 

Aşağıdaki incelemelerde **Yeni bir e-posta geldiğinde** tetikleyicisindeki tüm özellikleri ele alacağız. [Faturayla ilgili sık sorulan sorular](billing-questions.md#what-counts-as-a-run) ve [fiyatlandırma](https://ms.flow.microsoft.com/pricing/) sayfasını ziyaret ederek daha fazla bilgi edinebilirsiniz.

## <a name="prerequisites"></a>Önkoşullar
* [Microsoft Flow](https://flow.microsoft.com) erişimi olan bir hesap.
* Bir Office 365 Outlook hesabı.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulaması.
* Office 365 Outlook’a ve anında iletme bildirimi hizmetine bağlantı.

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>E-postanın konusuna göre akış tetikleme
Bu incelemede, yeni herhangi bir e-postanın konusunda "kura" sözcüğünün olması durumunda cep telefonunuza anında iletme bildirimi gönderecek bir akış oluşturacağız. Bu durumda, akışınız söz konusu e-postaları *okundu* olarak işaretler.

Not: Bu incelemede anında iletme bildirimi gönderiliyor olsa da siz kendi iş akışı gereksinimlerinize uyan diğer herhangi bir eylemi kullanabilirsiniz. Örneğin, e-posta içeriklerini Google E-Tablolar veya Dropbox'ta saklanan Microsoft Excel dosyası gibi başka bir depoda saklayabilirsiniz.

Haydi başlayalım:

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. **Konu Filtresi** kutusuna, akışınızın gelen e-postaları filtrelemek için kullanacağı metni girin.
   
     Bu örnekte, konusunda "kura" sözcüğü bulunan tüm e-postalarla ilgileniyorum.
   
    ![Gelişmiş seçenekler](./media/email-triggers/email-triggers-subject-text.png)

[!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Daha önce **Konu Filtresi** kutusunda belirttiğiniz konuyla eşleşen bir e-posta geldiğinde almak istediğiniz mobil bildirime ilişkin ayrıntıları girin.
   
    ![Bildirim ayrıntıları](./media/email-triggers/email-triggers-4.png)

[!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Akışınıza bir ad verin ve sayfanın üst tarafındaki **Akış oluştur** seçeneğini belirleyerek akışı kaydedin.
   
    ![Akışı kaydedin](./media/email-triggers/email-triggers-subject-notification.png)

Tebrikler! Artık konusunda "kura" sözcüğü bulunan bir e-posta aldığınız her seferde anında iletme bildirimi alacaksınız.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>E-postanın gönderenine göre akış tetikleme
Bu incelemede, belirli bir gönderenden (e-posta adresi) yeni e-posta almanız durumunda cep telefonunuza anında iletme bildirimi gönderecek bir akış oluşturacağız. Akış aynı zamanda bu e-postaları *okundu* olarak işaretler.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Gönderenin e-posta adresini **Kimden** alanına girin.
   
     Akışınız bu adresten gönderilen tüm e-postalarda işlem gerçekleştirir.
   
    ![E-posta özelliği](./media/email-triggers/email-triggers-from.png)

[!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Daha önce girdiğiniz e-posta adresinden her ileti alışınızda almak istediğiniz mobil bildirime ilişkin ayrıntıları girin.
   
    ![Bildirim ayrıntıları](./media/email-triggers/email-triggers-sender-notification.png)

[!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Akışınıza bir ad verin ve sayfanın üst tarafındaki **Akış oluştur** seçeneğini belirleyerek akışı kaydedin.
   
    ![Akışı kaydedin](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>Belirli bir klasöre her e-posta gelişinde bir akış tetikler.
E-postaları adres gibi belirli özelliklere göre farklı klasörlere yönlendiren kurallarınız varsa bu akış türü ilginizi çekebilir.

Haydi başlayalım:

> [!NOTE]
> E-postaları gelen kutunuz dışında bir klasöre yönlendiren bir kuralınız yoksa böyle bir kural oluşturun ve test amaçlı bir e-posta göndererek kuralın çalışıp çalışmadığını kontrol edin.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Oluşturduğunuz kuralın belirli e-postaları yönlendireceği hedef klasörü seçin. Tüm e-posta klasörlerini görüntülemek için öncelikle **Yeni bir e-posta geldiğinde** kartındaki **Klasör** kutusunun sağ tarafında yer alan **Seçiciyi Göster** simgesini seçin.
   
    ![Klasörü seçin](./media/email-triggers/email-triggers-2.png)

[!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Daha önce seçtiğiniz klasöre e-posta geldiğinde almak istediğiniz mobil bildirime ilişkin ayrıntıları girin. Henüz yapmadıysanız bildirim hizmetine ilişkin kimlik bilgilerini girin.
   
    ![Bildirim ayrıntıları](./media/email-triggers/email-triggers-folder-notification.png)

[!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Akışınıza bir ad verin ve sayfanın üst tarafındaki **Akış oluştur** seçeneğini belirleyerek akışı kaydedin.
   
    ![Akışı kaydedin](./media/email-triggers/email-triggers-7.png)

Bu incelemede daha önce seçtiğiniz klasöre yönlendirilecek bir e-posta göndererek akışı test edin.

