---
title: Çözüm kullanan akışlara genel bakış | Microsoft Docs
description: Çözümlerde akış oluşturmanın avantajlarını öğrenin.
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
ms.openlocfilehash: 19eb7d051c4d1438ec45305620e369b5499252a0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548553"
---
# <a name="overview"></a>Bakýþ
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Akışlarınızı bir [çözümde](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview)barındırdığınızda, taşınabilir hale gelir ve tüm bileşenlerini bir ortamdan diğerine taşımayı daha kolay hale getirir. Tipik kullanım durumu, bağımsız bir yazılım satıcısı (ISV) için bir korumalı alan ortamında akış geliştirme ve ardından bu akışları bir test ortamına taşıma içindir. Sınama sonrasında, ISV bu akışları satın alan istemciler için akışları bir üretim ortamına taşır. Bu süreç, çözümlerinde akışlarınızı oluşturduğunuzda ve ardından çözümleri ve bunların içeriğini taşırken çok daha kolay hale getirir.

Bir çözüm içinde oluşturduğunuz akışlar *çözüm kullanan* akışlar olarak bilinir. Tek bir çözümde birden çok akış ekleyebilirsiniz.

> [!NOTE] 
> Çözüme duyarlı olmayan akışları (bir çözümde oluşturulmamış akışlar) bir çözüme taşıyamazsınız.

## <a name="prerequisites"></a>Kaynakları

Çözümler oluşturmak ve çözüm kullanan akışlar için aşağıdaki bileşenlere sahip olmanız gerekir:

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Sürüm 9.1.0.267 veya üzerini içeren bir ortam.

  Sürümünüzü denetlemek için [Microsoft Flow Yönetim Merkezi](https://admin.flow.microsoft.com)' ne gidin, **ortamlar**' ı seçin, Ilgilendiğiniz ortamı seçin ve **Ayrıntılar** sekmesini seçin.

## <a name="create-a-solution"></a>Çözüm oluşturma

Çözüm oluşturmak için aşağıdaki adımları izleyin:

1. [Microsoft Flow](https://flow.microsoft.com)oturum açın.
1. Gezinti çubuğundan **çözümler** ' i seçin.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. **+ Yeni çözüm**' i seçin.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Yeni çözümünüz için, **görünen ad**, **Yayımcı**, **Sürüm**ve **ad**gibi tüm gerekli bilgileri sağlayın. Çözümünüz için bir açıklama sağlamak da iyi bir fikirdir.

   ![](./media/overview-solution-flows/new-solution.png)

1. Üstteki menüden **Kaydet ve Kapat ' ı** seçin.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   Yeni çözümünüz şu görüntü gibi görünebilir:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Yeni çözümünüz görünmezse çözüm listesini yenilemek için **çözümler** ' i seçin.

## <a name="learn-more"></a>Daha fazla bilgi edinin

- [Çözümde akış oluşturma](./create-flow-solution.md)
- [Bir çözümü dışarı aktarma](./export-flow-solution.md)
- [Bir çözümü içeri aktarma](./import-flow-solution.md)
- [Çözüm kullanan akışı düzenleme](./edit-solution-aware-flow.md)
- [Çözümle uyumlu akışı kaldırma](./remove-solution-aware-flow.md)
