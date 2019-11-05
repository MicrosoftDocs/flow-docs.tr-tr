---
title: Microsoft ekiplerinde akış oluşturmayı ve yönetmeyi öğrenin | Microsoft Docs
description: İletileri isteğe bağlı olarak, kullanıcılar ve kanallar @mention, yanıt seçenekleriyle ve daha fazlasını göndermek için akışlar oluşturun ve yönetin.
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
ms.openlocfilehash: 34cb8577d57d70686fd9811db9146443b56a07b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547990"
---
# <a name="microsoft-flow-in-teams"></a>Ekiplerde Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

### <a name="prerequisites"></a>Kaynakları

1. Microsoft ekiplerine erişin.
1. Microsoft Flow erişim.

## <a name="install-the-microsoft-flow-app-in-teams"></a>Microsoft Flow uygulamasını takımlara yükler

Microsoft ekiplerine Microsoft Flow uygulamasını yüklemek için bu adımları izleyin.

1. Microsoft ekiplerinde oturum açın.

1. Takımlar gezinti çubuğunun sol alt kısmındaki **uygulamalar** simgesine dokunun.

    ![Uygulama seçin](media/flows-teams/apps.png)

1. **Flow** uygulamasını seçin. Bunu görmüyorsanız **akış** araması yapmanız gerekebilir.

    ![Flow uygulaması Seç](media/flows-teams/select-flow-app.png)

1. **Yüklemeyi**seçin.

    ![Install düğmesi](media/flows-teams/select-install.png)

1. Microsoft Flow şimdi yüklendi.

    ![Yüklendiyse](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Ekiplerde akış oluşturma

1. Microsoft ekiplerinde oturum açın.

1. Gezinti çubuğunda **daha fazla eklenen uygulamalar** bağlantısı (...) seçin ve ardından **Flow** uygulamasını seçin.

    ![Eklenen uygulamalar simgesi](media/flows-teams/added-apps-icon.png)

1. Daha önce yapmadıysanız, oturum açmanız ve izin vermeniz gerekebilir.

    ![Oturum Aç](media/flows-teams/grant-permissions-sign-in.png)


    Aşağıdaki sekmelere dikkat edin:

    ![Akış giriş sayfası](media/flows-teams/flow-landing-page.png)

    Ada|Amaçla
    ----|-----|
    Görül|Flow bot ile etkileşim kurun.
    Var|Akışlar oluşturun ve yönetin.
    Filtreleyebilirsiniz|Alınan ve gönderilen onay isteklerini listeler.
    bilgi|Microsoft Flow hakkındaki sürümü ve diğer bilgileri görüntüler.


    Artık Microsoft Flow tasarımcısından oluşturduğunuz tüm akışları görürsünüz (varsa). 

    Ayrıca, Microsoft Flow tasarımcıdan yaptığınız gibi, özel bir şablondan veya boş bir şablondan akış oluşturabilirsiniz. 

## <a name="manage-approvals"></a>Onayları Yönet

Microsoft Flow yaptığınız gibi, Microsoft ekiplerinde [onayları](modern-approvals.md) yönetebilirsiniz. Onayları yönetmek için aşağıdaki adımları izleyin:

1. Microsoft ekiplerinde oturum açın.
1. **Onaylar** sekmesini seçin.

    ![Onaylar sekmesi](media/flows-teams/approvals-tab.png)

    Aşağıdaki alt sekmeleri görürsünüz:

    Sekmesinde|Amaçla
    ----|-----|
    Aldığınızı|Aldığınız onay isteklerini listeler ve sizin için bekleyen bir işlemdir.
    Gönderilip|Gönderdiğiniz onay isteklerini listeler ve diğerleri için bekleyen bir işlemdir.
    Geçmişi|Alınan ve gönderilen onay isteklerini listeler.
    Onay akışı oluştur|Onay akışları oluşturun.

1. Daha fazla bilgi için **alınan**, **gönderilen**veya **Geçmiş** sekmelerini seçin.

    ![Onaylar sekmesi](media/flows-teams/approvals-tab-2.png)

1. Onay akışı oluşturmak için onay **akışı oluştur** ' u seçin.

    ![Onaylar sekmesi](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Botu akışlarla kullanma

### <a name="list-and-launch-flows-with-the-bot"></a>Bot ile akışları listeleme ve başlatma

> [!TIP]
> Bot, bir zamanlama tarafından tetiklenen veya Kullanıcı girişi olmadan el ile tetiklenen akışları listeler ve çalıştırır.

1. Microsoft ekiplerinde oturum açın.
1. Gezinti çubuğunda **daha fazla eklenen uygulamalar** bağlantısı (...) seçin ve ardından **Flow** uygulamasını seçin.

    ![Eklenen uygulamalar simgesi](media/flows-teams/added-apps-icon.png)
    
1. **Konuşma** sekmesini seçin.

    ![Konuşma sekmesi](media/flows-teams/conversations-tab.png)

**Konuşma** sekmesinde, çalıştırmak istediğiniz eylemleri gerçekleştirerek yanıt veren, bot 'a komut gönderebilirsiniz. Örneğin, akışlarınızı listelemek ve akışı Dizin 1 ile çalıştırmak için aşağıdaki komutları çalıştırın:

- ```List flows```-bot, akışlarınızın bir listesini bir dizin numarası tarafından ön eki olarak görüntüler.
- ```Run flow 1```-akış numarası 1 ' i çalıştırır. Burada *1* , çalıştırmak istediğiniz akışın dizin numarasıdır.

   ![Bot komutları](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Akışlar için açıklama alın

Akışlarınızın listesinden Dizin 1 olan akışın açıklamasını almak için ```describe flow 1```çalıştırın. Bot yanıtı bu görüntüye benzer olacaktır:

   ![Akışları açıkla](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Bot için komutların listesini al

Bot 'ın işleyeceği komutların listesini almak için şu komutla sorun: ```learn more``` 

Bot yanıtı bu görüntüye benzer olacaktır:

![Akışları açıkla](media/flows-teams/bot-learn-more.png) 
