---
title: Microsoft ekiplerine Uyarlamalı kartlar veren akışlar oluşturmayı öğrenin | Microsoft Docs
description: Uyarlamalı kartlara sahip zengin biçimli içerikleri Microsoft ekiplerine nakletmekte olan akışlar oluşturmayı öğrenin.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 0aa5b4727bea569732fe5b76f717a87d8d7ddb02
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546490"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Microsoft ekiplerinde Uyarlamalı kartlar kullanma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Microsoft ekipleri kanalına [Uyarlamalı kartlar](https://adaptivecards.io) gönderen bir akış oluşturabilirsiniz. Uyarlamalı kartlarla, Gönderimlerinizi daha açık, etkileşimli ve ilgi çekici hale getirmek için zengin biçimlendirme kullanabilirsiniz. Uyarlamalı kartlar görüntüler, grafikler, zengin biçimli metin ve daha fazlası gibi bileşenler içerebilir.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Bir takıma Uyarlamalı kartlar gönderen bir akış oluşturma

Strateji ve planlama ekibinizdeki genel kanala Uyarlamalı kart gönderen bir akış oluşturmak için bu adımları izleyin. Oluşturduğumuz akış, uyarlamalı kartın içeriğini kuruluşun kanalına haftalık olarak göndermek için **kendi Uyarlamalı kartınızı kanal (Önizleme) eyleminde akış bot 'ı olarak** kullanır.

1. Microsoft ekiplerinde oturum açın.
1. Sol taraftaki Gezinti çubuğunda **takımlar** simgesini seçin ve ardından **stratejiyi ve planlama** ekibini seçin.

    ![Takımları Seç](media/create-adaptive-cards-teams/select-teams-team.png)

1. Ekranın üst kısmındaki **akış** sekmesini seçin.
1. **+** (boş oluştur) simgesini seçin.
1. **Yinelenme**araması yapın ve sonra **yinelenme** tetikleyicisini seçin.

    ![Yinelenme kartı](media/create-adaptive-cards-teams/select-recurrence.png)

1. İstediğiniz zaman ve saat diliminde her hafta yinelemek için zamanlamayı aşağıdaki şekilde ayarlayın:
    
    ![Yinelenme kartı](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. **Yeni adım**' ı seçin.
1. **Uyarlamalı**arama yapın, **Microsoft ekipleri**' i seçin ve ardından **kendi Uyarlamalı kartınızı kanal (Önizleme) için akış bot olarak gönder** eylemini seçin.

   ![Uyarlamalı kart](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Uyarlamalı kart **iletisinin** nakledileceği ekibi ve kanalı göstermek için **kendi Uyarlamalı kartınızı kanal (Önizleme) kartına gönder** sayfasında bir **ekip**, **Kanal**ve **ileti** sağlayın.

   ![Uyarlamalı kart](media/create-adaptive-cards-teams/adaptive-card-message.png)

   **İleti**için bu örnek JSON içeriğini kullanabilirsiniz:

    ````
        {
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "speak": "Our team meeting is starting soon. Do you want to snooze  or do you want to send a late notification to the attendees?",
    "body": [
        {
        "type": "TextBlock",
        "text": "Strategy and Planning Weekly Team meeting",
        "size": "large",
        "weight": "bolder"
        },
        {
        "type": "TextBlock",
        "text": "Conf Room 112/3377 (10)",
        "isSubtle": true
        },
        {
        "type": "TextBlock",
        "text": "12:30 PM - 1:30 PM",
        "isSubtle": true,
        "spacing": "none"
        },
        {
        "type": "TextBlock",
        "text": "Snooze for"
        },
        {
        "type": "Input.ChoiceSet",
        "id": "snooze",
        "style": "compact",
        "value": "5",
        "choices": [
            {
            "title": "5 minutes",
            "value": "5",
            "isSelected": true
            },
            {
            "title": "15 minutes",
            "value": "15"
            },
            {
            "title": "30 minutes",
            "value": "30"
            }
        ]
        }
    ],
    "actions": [
        {
        "type": "Action.Submit",
        "title": "Snooze",
        "data": {
            "x": "snooze"
        }
        },
        {
        "type": "Action.Submit",
        "title": "I'll be late",
        "data": {
            "x": "late"
        }
        }
    ]
    }
    ````


1. Akışınıza bir ad verin ve kaydedin.


## <a name="run-the-flow"></a>Akışı çalıştırma

Yinelenme süresi dolduktan sonra akış, uyarlamalı kartın içeriğini tanımladığınız ekip kanalına gönderir.

![Akışı çalıştırma](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Daha fazla bilgi edinin

- [Uyarlamalı kart örnekleri](https://adaptivecards.io/samples/)ile çalışmaya başlayın.
- [Uyarlamalı kart içeriğini](https://adaptivecards.io) kolay bir şekilde oluşturun.



