---
title: Özel yanıtlarla onay akışları oluşturma | Microsoft Docs
description: Özel yanıtlarla onay akışları oluşturma
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/04/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- maker
ms.openlocfilehash: d1f4b6d6dad3138bf935947076be4fe75661e36e
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061722"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Onay akışları için özel yanıt seçenekleri oluşturma

Çalışan SharePoint'e her gider raporu yüklediğinde bir onay isteği göndermek ve ardından onaylayanın üç seçenekten biriyle yanıt vermesini sağlamak istediğinizi varsayalım: Kabul et, Daha fazla bilgi gerekiyor, Reddet.


## <a name="prerequisites"></a>Önkoşullar

- Plan 2 lisansına sahip Microsoft Flow hesabı (Üst düzey özellikleri kullanmak için Plan 2 gerekir. Onaylar üst düzey bir özelliktir.)
- Çalışanların gider raporlarını girecekleri SharePoint listesi.

## <a name="create-approval-flow"></a>Onay akışı oluşturma
1. [Microsoft Flow](https://flow.microsoft.com)’da oturum açın.
1. Sol gezinti çubuğunda **Akışlarım**'ı seçin.
1. **Yeni** > **Boş akış oluştur**'u seçin.

    ![Boş akış oluştur seçeneği](media/create-approval-response-options/create-approval-response-options.png)

1. Açılan ekranda **Boş akış oluştur**'u seçin. 

    ![Boş akış oluştur’u seçin](media/create-approval-response-options/create-from-blank.png)

1. **Sharepoint** için arama yapın ve tetikleyiciler listesinden **Bir öğe oluşturulduğunda** tetikleyicisini seçin. 

1. SharePoint **Site Adresi** ve **Liste Adı** bilgilerini sağlayın. 

1. **Yeni adım**'ı seçin, **Onay** için arama yapın ve ardından **Başlat ve onay bekle (V2)** öğesini seçin.

1. **Başlat ve onay bekle (V2)** kartında **Onay türü** listesini seçin.

    ![Onay türü](media/create-approval-response-options/select-approval-type.png)

1. **Özel Yanıtlar - Bir yanıtı bekleyin (Premium)** öğesini seçin.

    ![Özel yanıtlar](media/create-approval-response-options/select-custom-responses.png)

    Bundan sonra onaylayanlarınızın, bir çalışan giderine yönelik onay isteğine yanıt verirken kullanacakları özel yanıtları oluşturursunuz.


1. **Yanıt seçenekleri Öğe - 1** kutusuna **Kabul Et** girin ve **Yeni öğe ekle**'yi seçin. 

    ![Özel yanıt 1](media/create-approval-response-options/enter-response-1.png)

1. **Yanıt seçenekleri Öğe - 2** kutusuna **Reddet** girin ve **Yeni öğe ekle**'yi seçin.

    ![Özel yanıt 2](media/create-approval-response-options/enter-response-2.png)

1. **Yanıt seçenekleri Öğe - 3** kutusuna **Daha fazla bilgi gerekiyor** girin.

    ![Özel yanıt 3](media/create-approval-response-options/enter-response-3.png)   
    

1. **Başlık**, **Atanan** (onaylayan için e-posta) ve **Ayrıntılar**'ı (onay isteğine dahil edilecek ayrıntılar) girin.

    Aşağıda kuruluşunuz için neler ekleyebileceğinize ilişkin bir örnek verilmiştir.

    ![Özel yanıt ayrıntıları](media/create-approval-response-options/enter-title-assigned-to-details.png)


Artık özel yanıtlarınızı oluşturduğunuza göre, onaylayandan gelen yanıta bağlı olarak akışınızda farklı işler yapmak isteyebilirsiniz.


## <a name="use-approval-responses"></a>Onay yanıtlarını kullanma 

İsteğe **Kabul Et** yanıtı verilirse, muhasebe bölümüne çalışanın giderinin karşılanmasını isteyen bir e-posta göndermek isteyebilirsiniz. 

İsteğe **Reddet** yanıtı verilirse, çalışana isteğin reddedildiğini bildiren bir e-posta göndermek isteyebilirsiniz.

Son olarak, onaylayandan gelen yanıt **Daha fazla bilgi gerekiyor** olduğunda, çalışana daha fazla bilgi sağlamasını istemek için bir e-posta göndermek isteyebilirsiniz.

Akışta bunlardan herhangi birini yapmak için, akışınıza [**Koşul**](add-condition.md) veya **Geçiş** eylemi ekleyebilir ve ardından dinamik içerik seçiciden onay isteğinin **Sonuç** alanını seçin. Değerin Kabul Et, Daha fazla bilgi gerekiyor veya Reddet olduğunu onayladığınızdan emin olun.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Onay isteklerini müşteri yanıtıyla yanıtlama

Onaylayanlar onay isteklerini e-postayla alır. İstekler Microsoft Flow'daki onay merkezinde de görüntülenir. 

![Onay isteği e-postası](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Daha fazla bilgi
- [Tek onaylayan akışları](modern-approvals.md) oluşturma
- [Sıralı onay akışları](sequential-modern-approvals.md) oluşturma
