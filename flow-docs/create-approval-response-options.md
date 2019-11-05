---
title: Özel yanıtlarla onay akışları oluşturun | Microsoft Docs
description: Özel yanıtlarla onay akışları oluşturun.
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
ms.openlocfilehash: eaaa87f9213c5ed04aee65e37ee642436e49dfca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547219"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Onay akışları için özel yanıt seçenekleri oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bir çalışan, SharePoint 'e bir gider raporu yükleyen her seferinde onay isteği göndermek istediğinizi ve onaylayanın üç seçenekten biriyle yanıt vermesini sağlar: kabul etme, daha fazla bilgi gerekli veya Reddet.


## <a name="prerequisites"></a>Kaynakları

- Microsoft Flow hesabı.
- Çalışanların gider raporlarını girmesi için bir SharePoint listesi.

## <a name="create-approval-flow"></a>Onay akışı oluştur
1. [Microsoft Flow](https://flow.microsoft.com)oturum açın.
1. Sol gezinti çubuğundan **akışlarımı** seçin.
1. **Yeni** > oluştur ' u seçerek **boş bırakın**.

    ![Boş seçenekten oluştur](media/create-approval-response-options/create-approval-response-options.png)

1. Açılan ekranda, **boş oluştur**' u seçin. 

    ![Boş oluştur ' u seçin](media/create-approval-response-options/create-from-blank.png)

1. **SharePoint** araması yapın ve ardından tetikleyiciler listesinden **bir öğe oluşturulduğunda öğesini** seçin. 

1. SharePoint **sitesi adresini** ve **liste adını**belirtin. 

1. **Yeni adım**' ı seçin, **onay**araması yapın ve ardından **Başlat ' ı seçin ve onay için bekleyin (v2)** .

1. **Bir onay Için başlangıç ve bekleme (v2)** kartında **onay türü** listesini seçin.

    ![Onay türü](media/create-approval-response-options/select-approval-type.png)

1. **Özel yanıtları seçin-bir yanıt Için bekleyin (Premium)** .

    ![Özel yanıtlar](media/create-approval-response-options/select-custom-responses.png)

    Ardından, onaylayanlarınızın bir çalışan gideri için onay isteğine yanıt vermesi durumunda kullanacağı özel yanıtları oluşturacaksınız.


1. **Yanıt seçenekleri öğesi-1** kutusunda **kabul et** ' i girin ve ardından **Yeni öğe Ekle**' yi seçin. 

    ![Özel yanıt 1](media/create-approval-response-options/enter-response-1.png)

1. **Yanıt seçenekleri öğesi-2** kutusuna **Reddet** ' i girin ve ardından **Yeni öğe Ekle**' yi seçin.

    ![Özel yanıt 2](media/create-approval-response-options/enter-response-2.png)

1. **Yanıt seçenekleri öğesi-3** kutusuna **daha fazla bilgi gerekiyor**yazın.

    ![Özel yanıt 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Bir **başlık**girin, bu kişiye **atandı** (onaylayan için e-posta) ve **Ayrıntılar** (onay isteğinde yer alan ayrıntılar).

    Kuruluşunuz için neleri dahil edebileceğinize ilişkin bir örnek aşağıda verilmiştir.

    ![Özel yanıt ayrıntıları](media/create-approval-response-options/enter-title-assigned-to-details.png)


Özel yanıtlarınızı oluşturduğunuza göre, Onaylayandan alınan yanıta bağlı olarak, akışınızda farklı şeyler yapmak isteyebilirsiniz.


## <a name="use-approval-responses"></a>Onay yanıtlarını kullanma 

İstek yanıtı **kabul**ediyorsanız, hesap departmanına bir e-posta göndermek isteyebilirsiniz, bu da çalışanların gider için tarafımızca kuruluşlarımız olmasını ister. 

Yanıt reddedildiğinde, çalışana bir e-posta **göndermeniz ve isteğin**reddedildiğini bildirmek isteyebilirsiniz.

Son olarak, onaylayanın yanıtı **daha fazla bilgiye Ihtiyaç duydıysa**çalışana bir e-posta göndermek ve daha fazla bilgi sağlamak için çalışanı istemek isteyebilirsiniz.

Akışta bunlardan herhangi birini yapmak için akışınıza bir [**koşul**](add-condition.md) veya bir **geçiş** eylemi ekleyin ve ardından dinamik içerik seçicisinden onay isteğinin **sonuç** alanını seçin. Değerin kabul edilip edilmeyeceğini doğrulayın, daha fazla bilgi gerekiyor veya Reddet.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Özel bir Yanıt ile onay isteklerine yanıt verme

Onaylayanlar e-postada onay istekleri alır. Ayrıca, istekler Microsoft Flow onay merkezinde de görüntülenir. 

![Onay isteği e-postası](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Daha fazla bilgi edinin
- [Tek onaylayan akışları](modern-approvals.md) oluştur
- [Sıralı onaylayan akışları](sequential-modern-approvals.md) oluşturma
