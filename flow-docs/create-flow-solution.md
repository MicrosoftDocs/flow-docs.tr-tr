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
ms.openlocfilehash: cbc6e3a8ffe50eb7ad27e80eba044957647a1da3
ms.sourcegitcommit: b41b45f6fa29a22e9a9a4d3c726a2321b2ff3cbf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51026011"
---
# <a name="create-a-flow-in-a-solution"></a>Çözümde akış oluşturma

Bir çözümde oluşturduğunuz akışlar *çözüm kullanan* akışlar olarak bilinir. Çözüm kullanan bir akış oluşturmak için aşağıdaki adımları izleyin.

## <a name="prerequisites"></a>Önkoşullar

Çözüm kullanan bir akış oluşturmak için en az bir çözümünüzün olması gerekir.

## <a name="create-the-flow"></a>Akışı oluşturma 

1. [Microsoft Flow](https://flow.microsoft.com)’da oturum açın.
1. Gezinti çubuğundan **Çözümler**’i seçin.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Akışınızı oluşturacağınız çözümü seçin.

   ![](./media/create-flow-solution/new-solution-created.png)

1. **+ Yeni** seçeneğini ve ardından **Akış** seçeneğini belirleyin.

   ![](./media/create-flow-solution/select-new-flow.png)

   Microsoft Flow açılır.

1. Akışınızı oluşturmak için uygun bağlayıcıları ve tetikleyicileri kullanın.

   Bu örnekte, gelen kutunuza e-posta geldiğinde bildirim gönderen basit bir akış oluşturacağız.
1. **Office 365 Outlook** öğesini arayıp seçin.
1. **Yeni bir e-posta geldiğinde** tetikleyicisini seçin.
1. **+ Yeni adım**’ı seçin.
1. **Bana mobil bildirim gönder** eylemini seçin.
1. **Konu** dinamik belirtecini **Bana mobil bildirim gönder** kutusunun **Metin** alanına ekleyin.
1. Akışınıza bir ad verin ve akışı kaydedin.

   Akışınız şu şekilde görünmelidir:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Akışınızı çözümde görmek için **Çözümler**’i seçin:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Daha fazla bilgi

* [Çözüm oluşturma](./overview-solution-flows.md)
* [Çözümü dışarı aktarma](./export-flow-solution.md)
* [Çözümü içeri aktarma](./import-flow-solution.md)
* [Çözüm kullanan bir akışı düzenleme](./edit-solution-aware-flow.md)
* [Çözüm kullanan bir akışı kaldırma](./remove-solution-aware-flow.md)
