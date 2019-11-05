---
title: Microsoft Visio ile akış tasarlama | Microsoft Docs
description: Akış oluşturmak için başlangıç noktası olarak ortak modeller oluşturmak üzere kuruluşunuzun Visio uzmanlığından yararlanın.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0ffe9fbf8c29682bbcb941dbb48f9986f3c7144d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548777"
---
# <a name="design-flows-in-microsoft-visio"></a>Microsoft Visio 'da akış tasarlama
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Microsoft Flow Tasarımcısı, mantığınızın her ayrıntısını yapılandırabileceğiniz zengin bir araçtır. Ancak, bazen akışınızı oluşturmaya başlamadan önce Flow mantığınızı taslağı yapmak isteyebilirsiniz. Bunu yapmak için doğrudan Microsoft Flow içinden Microsoft Visio kullanın.

>[!TIP]
> Birçok işlem ortak bir modeli paylaşır, ancak kuruluş genelinde küçük çeşitlemeler vardır. Daha sonra özel parametrelerle ayarlayacağı bir ana iş akışı modeli oluşturmak için, Visio kullanarak kuruluşunuzda zaman kazanabilirsiniz.

## <a name="prerequisites"></a>Kaynakları

- Microsoft Flow hesabı.
- Microsoft Visio masaüstü uygulaması (Ingilizce sürüm).
- Microsoft Visio kullanan uzmanlık.

## <a name="design-a-workflow-in-visio"></a>Visio 'da iş akışı tasarlama

1. [Microsoft Flow](https://flow.microsoft.com)oturum açın.
1. Sol taraftaki panelden **Şablonlar** ' ı seçin.

     ![Sol paneldeki Şablonlar ' ı seçin](./media/visio-flows/templates-from-left-panel.png)

1. Listeden **Visio** ' yı seçin.

     ![Visio şablonlarına Filtre Uygula](./media/visio-flows/select-visio.png) 

1. Görüntülenen **Visio** şablonları listesinden **temel Flow BPMN diyagramı** şablonunu seçin.

     ![Bir Visio şablonu seçin](./media/visio-flows/visio-templates.png) 

     >[!IMPORTANT]
     >Visio, Internet 'teki dosyaların cihazınıza zarar verebileceği konusunda sizi uyarır. Rahat olduğunuzda uyarı iletisinde **Evet** ' i seçin.

     ![Internet 'ten gelen dosyalar hakkında uyarı](./media/visio-flows/visio-warning.png)

1. Visio Tasarımcısı başlatılır.

     ![Visio Tasarımcısı 'nın görünümü](./media/visio-flows/visio-designer.png)


1. [İş akışınızı tasarlamak](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a)için BPMN temel şekillerini kullanın.

   ![BPMN temel şekilleri](./media/visio-flows/bpmn-basic-shapes.png)

## <a name="prepare-to-export-your-workflow-to-microsoft-flow"></a>İş akışınızı Microsoft Flow dışarı aktarmaya hazırlanın

Microsoft Flow dışarı aktarmak için iş akışınızı hazırlamak üzere aşağıdaki adımları izleyin.

1. **İşlem** sekmesini seçin.
1. **Microsoft Flow** simgeler grubundan **dışarı aktarmaya hazırlanın** ' i seçin.

   ![Dışarı aktarmaya hazırla simgesini seçin](./media/visio-flows/prepare-export-icon.png)
   
   **Dışarı aktarmaya hazırlanma** grubu açılır.

   ![Dışarı aktarma grubunu hazırla](./media/visio-flows/prepare-export-group.png)

1. **Dışarı aktarmaya hazırlama** grubunun **akış eşleme** sekmesinde, BPMN diyagramınızı Microsoft Flow denetimlerine eşleyin. 

1. **Dışarı aktarmaya hazırlama** grubunun **Tetikleyiciler ve eylemler** sekmesinde, her bir şekli seçerek ve ardından bu Microsoft Flow şekli göstermek için bir tetikleyici veya eylem seçerek, BPMN diyagramınızı Microsoft Flow Tetikleyiciler ve eylemlerle eşleyin.

**Dışarı aktarmaya hazırlanma** denetiminde herhangi bir sorun kalmadığında iş akışınız dışarı aktarmaya hazırız.

![Sorun yok](./media/visio-flows/prepare-export-no-issues.png) 

## <a name="export-your-workflow"></a>İş akışınızı dışarı aktarma
1. İş akışı diyagramınızı Microsoft Flow dışarı aktarmak için **akışa dışarı aktar** düğmesini seçin.
1. Akışınızı adlandırın ve ardından **akış oluştur** düğmesini seçin.
   
   ![Akışı oluşturma](./media/visio-flows/export-create-flow.png)

1. Buna benzer bir başarı raporu görmeniz gerekir.

    ![Başarılı](./media/visio-flows/export-create-flow-success.png)

Artık, Microsoft Flow tasarımcısından başka herhangi bir akışta olduğu gibi, akışınızdan de düzenleme yapabilirsiniz.

>[!TIP]
> Birden çok paydaşda işbirliği yapmak ve hızlıca bir iş akışı oluşturmak için Visio 'nun paylaşım ve yorum oluşturma yeteneklerini kullanın.

## <a name="learn-more"></a>Daha fazla bilgi edinin

- [Microsoft Flow kullanmaya başlayın](getting-started.md) 
- [Çok adımlı akışlar oluşturun](multi-step-logic-flow.md)
- [Microsoft Visio ile akış tasarlama](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a)

     
