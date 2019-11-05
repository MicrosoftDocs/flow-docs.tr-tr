---
title: Microsoft Flow için bölgelere genel bakış | Microsoft Docs
description: Microsoft Flow bölgeler hakkında soru ve cevap ile genel bakış
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 33c5a1c331d9874f6b794e8fd2ea92b541024ec6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548480"
---
# <a name="faq-for-regions-in-microsoft-flow"></a>Microsoft Flow bölgeler için SSS
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Bu belge Microsoft Flow hakkında sık sorulan soruların bir listesini sağlar.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Akışımın dağıtıldığı yeri öğrenmek Nasıl yaparım? mı?
Akışınız [ortamı](environments-overview-admin.md)barındıran [bölgede](https://azure.microsoft.com/regions/) dağıtılır. Örneğin, ortamınız Avrupa bölgesinde oluşturulduysa, akışınız Avrupa veri merkezlerinde dağıtılır.

Yöneticiler, Microsoft Flow [Yönetim merkezinde](https://admin.flow.microsoft.com)oturum açtıklarında bölge tanımlayabilir. **Ortamlar** sekmesi, mevcut tüm ortamları ve bunların bölgelerini listeler.

![ortamları görüntüle](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Hangi bölgeler kullanılabilir?
* Amerika Birleşik Devletleri
* 'Ya
* Noktası
* Avustralya
* Hindistan
* Japonya
* Kanada
* Güney Amerika
* Birleşik Krallık
* ABD kamu (GCC)
* Fransa

## <a name="what-features-are-specific-to-a-given-region"></a>Hangi özellikler belirli bir bölgeye özeldir?
Ortamlar, farklı bölgelerde oluşturulabilir ve bu coğrafi konuma bağlanır. Bir ortamda akış oluşturduğunuzda, bu akış o coğrafi konumdaki veri merkezlerinde dağıtılır. Bu, ortak veri modeli, akışlar, bağlantılar, ağ geçitleri, uygulamalar ve özel bağlayıcılar dahil olmak üzere o ortamda oluşturduğunuz tüm öğeler için geçerlidir.

En iyi performans için, ortamınızı kullanıcılarınıza en yakın bölgede oluşturun. Örneğin, kullanıcılarınız Avrupa 'daysa ortamlarınızı Avrupa bölgesinde oluşturun. Kullanıcılarınız Birleşik Devletler, ortamlarınızı Birleşik Devletler bölgesinde oluşturun.

## <a name="gateways"></a>geçidinin
Ağ geçitleri:

* Hindistan bölgesinde kullanılamaz.
* Yalnızca varsayılan ortamda desteklenir, özel ortamlarda desteklenmez.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>Microsoft Flow Ulusal bulutlarda kullanılabilir mi?
Yes. [Daha fazla bilgi edinin](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Her bölgede hangi giden IP adresleri kullanılır?
[Sınırlara ve yapılandırmaya](limits-and-config.md)bakın.

