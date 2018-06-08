---
title: Akış içinde onay bekleme | Microsoft Docs
description: Akışlar, bir eylem (örneğin, karar bildirimi gönderme) gerçekleştirmeden önce bir dış olayın gerçekleşmesini (örneğin, kullanıcının değişiklikleri onaylaması veya reddetmesi) bekleyebilir.
services: ''
suite: flow
documentationcenter: na
author: merwanhade
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
ms.author: merwanhade
ms.openlocfilehash: b75cacf14da7d1b339e8a2f9e35eece389c2a6f7
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "29563167"
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Microsoft Flow'da onay bekleme

> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


SharePoint'te öğe oluşturduğunuzda size bir onay e-postası gönderecek ve ardından öğenizin onaylandığını veya reddedildiğini bildirecek bir akış oluşturun. Bu öğreticiyi tam olarak uygulamak için, tetikleyici eylem olarak basit bir SharePoint listesi oluşturun; Dropbox veya OneDrive gibi farklı bir veri kaynağı kullanabilirsiniz.

**Önkoşullar**

* **Project Tracker** (Proje İzleyici) adlı basit bir SharePoint listesi oluşturun, **Title** (Başlık) adlı bir sütun ekleyin ve daha sonra **Assigned To** (Atanan) adlı bir Kişi veya Grup sütunu ekleyin.

   ![Project Tracker (Proje İzleyici) SPO listesinin görüntüsü](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Akışı tetiklemek için bir olay ekleme

1. [Microsoft Flow](https://flow.microsoft.com)'da oturum açın, üst gezinti çubuğunda bulunan **Akışlarım**'ı ve sonra **Boş akış oluştur**'u seçin.

1. **Yüzlerce bağlayıcı ve tetikleyicide arama yapın** kutusunu seçin, **yeni öğe** girin ve daha sonra **SharePoint - when an item is created** (SharePoint - bir öğe oluşturulduğunda) seçeneğine gidin.

1. İstenirse SharePoint'te oturum açın.
1. **Site Adresi** kutusuna, listenizi içeren SharePoint sitesi URL'sini girin.

1. **Liste Adı** bölümünde, daha önce oluşturduğunuz listeyi seçin. Daha önceki adımları uyguladıysanız listenin adı **Project Tracker** (Proje İzleyici) şeklindedir.

    ![SPO liste adının görüntüsü](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>Sonuç eylemini ekleme

1. **Yeni adım** düğmesini ve sonra **Eylem ekle**’yi seçin.

1. **Tüm bağlayıcılar ve eylemler içinde arayın** yazılı kutuya **e-posta gönder** yazın veya bu ifadeyi yapıştırın, daha sonra **Office 365 Outlook - Send email with options** (Office 365 Outlook - Seçeneklerin bulunduğu bir e-posta gönder) seçeneğini belirleyin.

1. İstenirse Office 365 Outlook’ta oturum açın.

1. **Kime** alanını ve sonra **Atanan E-postası** belirtecini seçin.

    **Atanan** sütunundaki kullanıcı, öğeleri onaylayabileceği veya reddedebileceği bir e-posta alır. Akışı test etmek için bir öğe oluşturduğunuzda, bu alanda kendinizi belirtin. Bu şekilde, hem öğeyi onaylayabilir veya reddedebilir hem de bildirim e-postasını alırsınız.

    > [!NOTE]
    > **Konu** ve **Kullanıcı Seçenekleri** alanlarını, ihtiyaçlarınıza uygun şekilde özelleştirebilirsiniz.

    ![Alana onay e-postası gönder görüntüsü](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Koşul ekleme

1. **Yeni adım** düğmesini ve sonra **Koşul ekle**’yi seçin.

    ![Koşul ekle görüntüsü](./media/wait-for-approvals/add-a-condition.png)
1. İlk kutuyu ve sonra **Belirlenen Seçenek** belirtecini seçin.
1. Son kutuyu seçin ve sonra **Onayla** yazın.

    ![Koşul kartı görüntüsü](./media/wait-for-approvals/condition-card-2.png)

1. **Evet ise** alanında, **Eylem ekle**'yi seçin.

1. **Tüm bağlayıcılar ve eylemler içinde arayın** yazılı kutuya **e-posta gönder** yazın veya bu ifadeyi yapıştırın, sonra **Office 365 Outlook - E-posta gönder**’i seçin.

1. **Kime** alanına **Created by Email** (Oluşturan E-posta) gibi bir alıcı girin.

1. **Konu** kutusunda bir konu belirtin.

    Örneğin, **Assigned To DisplayName**'i (Atanan Görünen Adı) seçip her iki tarafında boşluk olacak şekilde **has approved** (şunu onayladı:) yazın ve ardından **Title**'ı (Başlık) seçin.

1. **Gövde** kutusunda, **Projenin bir sonraki aşamasına geçilebilir** gibi bir e-posta gövdesi belirtin.

    > [!NOTE]
    > SharePoint listesinde öğeyi oluşturan kullanıcıya, projenin onaylandığı veya reddedildiği bildirilir.

    ![Evet-e-posta gönder görüntüsü](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. **Hayır ise** alanında, projenin reddedildiğini belirtmek için **Konu** ve **Gövde**'yi değiştirme dışındaki son beş adımı tekrar edin.

     ![Hayır-e-posta gönder görüntüsü](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Akışınızı sonlandırma ve test etme

1. Akışınıza bir ad verin ve ardından **Akış oluştur**'u seçin.

     ![Akış-oluştur görüntüsü](./media/wait-for-approvals/create-flow.png)
1. SharePoint listenizde bir öğe oluşturun.

    Belirttiğiniz alıcıya bir onay e-postası gönderilir. Alıcı, e-postadaki **Onayla** veya **Reddet** seçeneğini belirlediğinde alıcının yanıtını gösteren bir e-posta alırsınız.

## <a name="learn-more"></a>Daha fazla bilgi

* [Tek onaylayan modern onayları incelemesi](modern-approvals.md)
* [Sıralı onaylar](sequential-modern-approvals.md) oluşturma
* [Paralel onaylar](parallel-modern-approvals.md) oluşturma
* [İstekleri hareket halinde](mobile-approvals.md) onaylama
