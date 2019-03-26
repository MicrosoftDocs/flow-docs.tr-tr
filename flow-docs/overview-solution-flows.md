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
ms.openlocfilehash: 8b0e64317b868dc32ede173329fa2f88ed53de76
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58353021"
---
# <a name="overview"></a>Genel bakış

Bir [çözümde](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview) barındırdığınız akışlar taşınabilir hale gelir, böylece akışlarınızı ve tüm bileşenlerini zahmetsizce bir ortamdan diğerine taşıyabilirsiniz. Bir bağımsız yazılım satıcısı (ISV) için genel bir kullanım örneği, akışları korumalı alan ortamında geliştirip daha sonra test ortamına taşımaktır. Test edildikten sonra, ISV bu akışları satın alan müşteriler için bir üretim ortamına taşır. Bu işlem, akışları çözümlerin içinde oluşturup daha sonra çözümleri ve içeriklerini taşıdığınızda çok daha kolaydır.

Bir çözümün içinde oluşturduğunuz akışlar *çözüm kullanan* akışlar olarak bilinir. Tek bir çözüme birden fazla akış ekleyebilirsiniz.

> [!NOTE] 
> Çözüm kullanmayan akışları (bir çözümün içinde oluşturulmamış akışları) bir çözüme taşıyamazsınız.

## <a name="prerequisites"></a>Önkoşullar

Çözümler ve çözüm kullanan akışlar oluşturmak için aşağıdaki bileşenlere sahip olmanız gerekir.

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- 9.1.0.267 veya sonraki sürüme sahip bir ortam.

  Sürümünüzü denetlemek için, [Microsoft Flow Yönetim merkezine](https://admin.flow.microsoft.com) gidin, **Ortamlar**’ı seçin, ilgilendiğiniz ortamı seçin ve ardından **Ayrıntılar** sekmesini seçin.

## <a name="create-a-solution"></a>Çözüm oluşturma

Çözüm oluşturmak için aşağıdaki adımları izleyin:

1. [Microsoft Flow](https://flow.microsoft.com)’da oturum açın.
1. Gezinti çubuğundan **Çözümler**’i seçin.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. **+ Yeni çözüm**’ü seçin.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Yeni çözümünüz için **Görünen Ad**, **Yayımcı**, **Sürüm** ve **Ad** dahil olmak üzere tüm gerekli bilgileri sağlayın. Çözümünüze bir açıklama eklemek de iyi bir fikirdir.

   ![](./media/overview-solution-flows/new-solution.png)

1. Üstteki menüden **Kaydet ve Kapat**’ı seçin.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   Yeni çözümünüz bu resimdeki gibi görünebilir:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Yeni çözümünüz görüntülenmezse çözüm listesini yenilemek için **Çözümler**’i seçin.

## <a name="learn-more"></a>Daha fazla bilgi

- [Çözümde akış oluşturma](./create-flow-solution.md)
- [Çözümü dışarı aktarma](./export-flow-solution.md)
- [Çözümü içeri aktarma](./import-flow-solution.md)
- [Çözüm kullanan bir akışı düzenleme](./edit-solution-aware-flow.md)
- [Çözüm kullanan bir akışı kaldırma](./remove-solution-aware-flow.md)
