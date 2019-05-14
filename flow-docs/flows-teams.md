---
title: Microsoft Teams'de akışları oluşturmayı ve yönetmeyi öğrenme | Microsoft Docs
description: İsteğe bağlı iletiler gönderme, kullanıcılardan ve kanallardan @mention, yanıt seçenekleriyle kartlar gönderme ve benzeri işlemler için akışlar oluşturun ve bunları yönetin.
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
ms.openlocfilehash: 4987d1f4fb504c0279540eb86dcb6ad1b983ff4a
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65061860"
---
# <a name="microsoft-flow-in-teams"></a>Teams'de Microsoft Flow

### <a name="prerequisites"></a>Önkoşullar

1. Microsoft Teams erişimi.
1. Microsoft Flow erişimi.

## <a name="install-the-microsoft-flow-app-in-teams"></a>Teams'de Microsoft Flow uygulamasını yükleme

Microsoft Teams'de Microsoft Flow uygulamasını yüklemek için aşağıdaki adımları izleyin.

1. Microsoft Teams'de oturum açın.

1. Teams gezinti çubuğunun sağ alt tarafındaki **Uygulamalar** simgesine dokunun.

    ![Uygulamaları seçme](media/flows-teams/apps.png)

1. **Flow** uygulamasını seçin. Uygulamayı görmüyorsanız **Flow** için arama yapmanız gerekebilir.

    ![Flow uygulamasını seçme](media/flows-teams/select-flow-app.png)

1. **Yükle**’yi seçin.

    ![Yükle düğmesi](media/flows-teams/select-install.png)

1. Microsoft Flow artık yüklenmiştir.

    ![Yüklendi](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Teams’de akış oluşturma

1. Microsoft Teams'de oturum açın.

1. Gezinti çubuğunda **Diğer eklenen uygulamalar** bağlantısını (...) seçin ve sonra da **Flow** uygulamasını seçin.

    ![Eklenen uygulamalar simgesi](media/flows-teams/added-apps-icon.png)

1. Daha önce yapmadıysanız oturum açmanız ve izinler vermeniz gerekebilir.

    ![Oturum açma](media/flows-teams/grant-permissions-sign-in.png)


    Aşağıdaki sekmelere dikkat edin:

    ![Akış açılış sayfası](media/flows-teams/flow-landing-page.png)

    Ad|Amaç
    ----|-----|
    Konuşma|Akış botuyla etkileşim kurar.
    Akışlar|Akışları oluşturur ve yönetir.
    Onaylar|Alınan ve gönderilen onay isteklerini listeler.
    Hakkında|Microsoft Flow'un sürümünü ve diğer bilgilerini görüntüler.


    Şimdi Microsoft Flow tasarımcısında oluşturduğunuz (varsa) tüm akışları görürsünüz. 

    Aynı Microsoft Flow tasarımcısından yaptığınız gibi özel şablondan veya boş şablondan da akış oluşturabilirsiniz. 

## <a name="manage-approvals"></a>Onayları yönetme

Aynı Microsoft Flow'da yaptığınız gibi Microsoft Teams'de de [onayları](modern-approvals.md) yönetebilirsiniz. Onaylarınızı yönetmek için aşağıdaki adımları izleyin:

1. Microsoft Teams'de oturum açın.
1. **Onaylar** sekmesini seçin.

    ![Onaylar sekmesi](media/flows-teams/approvals-tab.png)

    Aşağıdaki alt sekmeleri fark edeceksiniz:

    Sekme|Amaç
    ----|-----|
    Alınan|Aldığınız ve sizden eylem bekleyen onay isteklerini listeler.
    Gönderilen|Gönderdiğiniz ve diğer kişilerden eylem bekleyen onay isteklerini listeler.
    Geçmiş|Alınan ve gönderilen onay isteklerini listeler.
    Onay akışı oluşturma|Onay akışları oluşturun.

1. Daha fazla bilgi edinmek için **Alınan**, **Gönderilen** veya **Geçmiş** sekmelerini seçin.

    ![Onaylar sekmesi](media/flows-teams/approvals-tab-2.png)

1. Onay akışı oluşturmak için **Onay akışı oluştur**'u seçin.

    ![Onaylar sekmesi](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Akışlarla bot kullanma

### <a name="list-and-launch-flows-with-the-bot"></a>Botla akışları listeleme ve başlatma

> [!TIP]
> Bot bir zamanlamaya göre veya kullanıcı girişi olmadan elle tetiklenen akışları listeler ve çalıştırır.

1. Microsoft Teams'de oturum açın.
1. Gezinti çubuğunda **Diğer eklenen uygulamalar** bağlantısını (...) seçin ve sonra da **Flow** uygulamasını seçin.

    ![Eklenen uygulamalar simgesi](media/flows-teams/added-apps-icon.png)
    
1. **Konuşma** sekmesini seçin.

    ![Konuşma sekmesi](media/flows-teams/conversations-tab.png)

**Konuşma** sekmesinde bota komutlar gönderebilirsiniz ve bot size komutta istediğiniz eylemleri gerçekleştirerek yanıt verir. Örneğin akışlarınızı listelemek ve 1 dizin numaralı akışı çalıştırmak için şu komutları çalıştırın:

- ```List flows``` - Bot, akışlarınızın listesini önünde bir dizin numarasıyla görüntüler.
- ```Run flow 1``` - 1 numaralı akışı çalıştırır. Burada *1*, çalıştırmak istediğiniz akışın dizin numarasıdır.

   ![Bot komutları](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Akışların açıklamasını alma

Akış listenizden dizin numarası 1 olan akışın açıklamasını almak için ```describe flow 1``` komutunu çalıştırın. Botun yanıtı aşağıdaki resme benzer olacaktır:

   ![Akışı açıklama](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Bot için komut listesini alma

Botun işlediği komutların listesini almak için, şu komutla listeyi isteyin: ```learn more``` 

Botun yanıtı aşağıdaki resme benzer olacaktır:

![Akışı açıklama](media/flows-teams/bot-learn-more.png) 
