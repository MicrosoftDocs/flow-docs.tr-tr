---
title: Microsoft Teams'e uyarlamalı kartlar gönderen akışlar oluşturmayı öğrenme | Microsoft Docs
description: Microsoft Teams'e uyarlamalı kartlarla zengin biçimlendirmeli içerik gönderen akışlar oluşturmayı öğrenin.
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
ms.openlocfilehash: d6bb4bb55fe876db1d8b64c157d3b4967e5d067f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65061584"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Microsoft Teams'de uyarlamalı kartları kullanma

Microsoft Teams kanalına [uyarlamalı kartlar](https://adaptivecards.io) gönderen bir akış oluşturabilirsiniz. Uyarlamalı kartlarla, gönderilerinizi daha net, etkileşimli ve cazip hale getirecek zengin biçimlendirme kullanabilirsiniz. Uyarlamalı kartlar resim, grafik ve zengin biçimlendirmeli metin gibi bileşenler içerebilir.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Ekibe uyarlamalı kartlar gönderen bir akış oluşturma

Strategy and Planning takımında genel kanala uyarlamalı bir kart gönderen bir akış oluşturmak için aşağıdaki adımları izleyin. Oluşturduğumuz akış, uyarlamalı kartın içeriğini her hafta takımın kanalına göndermek için **Kendi uyarlamalı kartınızı Flow botu olarak bir kanala gönderin (önizleme)** eylemini kullanır.

1. Microsoft Teams'de oturum açın.
1. Sol taraftaki gezinti çubuğunda **Takımlar** simgesini seçin ve sonra da **Strategy and Planning** takımını seçin.

    ![Takımlar'ı seçin](media/create-adaptive-cards-teams/select-teams-team.png)

1. Ekranın en üstündeki **Akış** sekmesini seçin.
1. **+** (Boş akış oluştur) simgesini seçin.
1. **Yinelenme** için arama yapın ve **Yinelenme** tetikleyicisini seçin.

    ![Yinelenme kartı](media/create-adaptive-cards-teams/select-recurrence.png)

1. Tercih ettiğiniz saatte ve saat diliminde her hafta tekrarlamak için zamanlamayı aşağıdaki gibi ayarlayın:
    
    ![Yinelenme kartı](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. **Yeni adım**’ı seçin.
1. **Uyarlamalı** için arama yapın, **Microsoft Teams**'i seçin ve sonra da **Kendi uyarlamalı kartınızı Flow botu olarak bir kanala gönderin (önizleme)** eylemini seçin.

   ![Uyarlamalı kart](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. **Kendi uyarlamalı kartınızı Flow botu olarak bir kanala gönderin (Önizleme)** kartında bir **Takım**, **Kanal** ve **İleti** seçerek uyarlamalı kart **iletisinin** gönderileceği takımı ve kanalı belirtin.

   ![Uyarlamalı kart](media/create-adaptive-cards-teams/adaptive-card-message.png)

   **İletiniz** için şu örnek JSON içeriğini kullanabilirsiniz:

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


1. Akışınıza bir ad verip akışı kaydedin.


## <a name="run-the-flow"></a>Akışı çalıştırma

Yineleme saati geçtikten sonra akışın uyarlamalı kart içeriğini sizin tanımladığınız takım kanalına gönderdiğine dikkat edin.

![Akışı çalıştırma](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Daha fazla bilgi

- [Uyarlamalı kart örneklerini](https://adaptivecards.io/samples/) kullanmaya başlayın.
- Kolay yoldan [uyarlamalı kart içeriği](https://adaptivecards.io) oluşturun.



