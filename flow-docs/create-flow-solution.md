---
title: Çözüm kullanan akışlar oluşturmayı öğrenin | Microsoft Docs
description: Çözüm kullanan akışlar oluşturmayı öğrenin.
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
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6cbd1ee543cfe5f54b61486eefbacbd5bb837f33
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546484"
---
# <a name="create-a-flow-in-a-solution"></a>Çözümde akış oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bir çözümde oluşturduğunuz akışlar *çözüm kullanan* akışlar olarak bilinir. Çözüm kullanan bir akış oluşturmak için bu adımları izleyin.

## <a name="prerequisites"></a>Kaynakları

Çözüm kullanan bir akış oluşturabilmeniz için en az bir çözümünüz olması gerekir.

## <a name="create-the-flow"></a>Akışı oluşturma 

1. [Microsoft Flow](https://flow.microsoft.com)oturum açın.
1. Gezinti çubuğundan **çözümler** ' i seçin.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Akışınızı oluşturacağınız çözümü seçin.

   ![](./media/create-flow-solution/new-solution-created.png)

1. **+ Yeni**' yi seçin ve ardından **akış**' ı seçin.

   ![](./media/create-flow-solution/select-new-flow.png)

   Microsoft Flow açılır.

1. Akışınızı derlemek için kullanılabilir bağlayıcıları ve Tetikleyicileri kullanın.

   Bu örnekte, gelen kutunuza e-posta geldiğinde bildirim gönderen basit bir akış oluşturacağız.
1. **Office 365 Outlook**için arama yapın ve seçin.
1. **Yeni bir e-posta geldiğinde** tetikleyiciyi seçin.
1. **+ Yeni adım**' ı seçin.
1. **Bana mobil bildirim gönder** eylemini seçin.
1. **Konu** dinamik belirtecini **bana mobil bildirim gönder** kutusunun **metin** alanına ekleyin.
1. Akışınıza bir ad verin ve ardından akışı kaydedin.

   Akışınız şöyle görünmelidir:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Çözümünüzde akışınızı görmek için **çözümler** ' i seçin:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Daha fazla bilgi edinin

* [Çözüm oluşturma](./overview-solution-flows.md)
* [Bir çözümü dışarı aktarma](./export-flow-solution.md)
* [Bir çözümü içeri aktarma](./import-flow-solution.md)
* [Çözüm kullanan akışı düzenleme](./edit-solution-aware-flow.md)
* [Çözümle uyumlu akışı kaldırma](./remove-solution-aware-flow.md)
