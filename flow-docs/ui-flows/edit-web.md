---
title: Web Kullanıcı arabirimi akışlarını nasıl düzenleyeceğinizi öğrenin | Microsoft Docs
description: Web UI akışlarını nasıl düzenleyeceğinizi öğrenin.
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 263f8634b2435217fba436e68ab7e744dd3b52b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549588"
---
# <a name="edit-web-ui-flows"></a>Web Kullanıcı arabirimi akışlarını düzenleme

[Bu konu ön sürüm belgesidir ve değişikliğe tabidir.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Web Kullanıcı arabirimi akışları, Microsoft Edge veya Google Chrome ['un bir sonraki sürümünde](https://www.microsoftedgeinsider.com/) çalışan Web sitelerini otomatik hale getirir. [Bir Web Kullanıcı arabirimi akışı](create-web.md)oluşturduktan sonra, onu düzenlemeniz gerekebilir. Web UI akışlarınızı nasıl düzenleyeceğinizi öğrenmek için bu belgedeki adımları izleyin.

## <a name="edit-in-selenium-ide"></a>Selenium IDE 'de Düzenle

Web UI akışlarınızı düzenlemek için Selenium IDE 'yi kullanın.

>[!NOTE]
>Selenium IDE 'de düzenlemenin, gelişmiş kullanıcılar ve geliştiricilerle bir hedef vardır.

Komut dosyasını nasıl düzenleyeceğinizi öğrenmek için [Selenium komutlarına](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) başvurabilirsiniz.

Selenium IDE, bir kullanıcı arabirimi öğesini hedeflerken farklı seçiciler ve varsayılan bir tane önerir. Önerilen seçicilerin hiçbiri uygun değilse yeni bir seçici de tanımlayabilirsiniz. Bu genellikle Web sitesinin HTML yapısı yüksek oranda dinamik olduğunda gerçekleşir.

Aşağıda Selenium IDE 'nin tanımladığı olası seçicilerin bir örneği verilmiştir:

![Olası seçiciler](../media/edit-web/possible-selectors.png "Olası seçiciler")

## <a name="accessing-a-property-of-an-object-variable-or-item-of-an-array-variable"></a>Bir nesne değişkeninin özelliğine veya bir dizi değişkeninin öğesine erişme * *

Bu gelişmiş özellik, foo nesnesinin Bar özelliğine erişmek için \${foo. bar} gibi bir sözdizimi kullanmanıza olanak sağlar. Ayrıca, bir Store komutunda değer özelliği olarak foo. Bar ' i kullanarak foo 'ın Bar özelliğine de yazabilirsiniz. Foo dizisinde 0 dizinindeki öğeye erişmek için \${foo [0]} gibi bir sözdizimi de kullanabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Web UI akışları oluşturma](create-web.md)
- [UI akışlarını çalıştırma](run-ui-flow.md)
