---
title: "Microsoft Flow için bölgelere genel bakış | Microsoft Docs"
description: "Microsoft Flow’daki bölgelerle ilgili soru ve cevapları içeren genel bakış"
services: 
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: deonhe
ms.openlocfilehash: ec9b72e570c562c091aefd370f73d6862ff56f18
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="faq-for-regions-in-microsoft-flow"></a>Microsoft Flow'daki bölgelerle ilgili SSS
Bu belgede Microsoft Flow hakkında sık sorulan soruların bir listesi bulunur.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Akışımın dağıtıldığı yeri nasıl bulabilirim?
Akışınız [ortamı](environments-overview-admin.md) barındıran [bölgede](https://azure.microsoft.com/regions/) dağıtılır. Örneğin, ortamınız Avrupa bölgesinde oluşturulduysa akışınız da Avrupa'daki veri merkezlerinde dağıtılır.

Yöneticiler Microsoft Flow [yönetim merkezinde](https://admin.flow.microsoft.com) oturum açarak bölgeyi tanımlayabilir. **Ortamlar** sekmesinde, tüm mevcut ortamlarınız bölgeleriyle birlikte listelenir.

![ortamları görüntüleme](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Hangi bölgeler kullanılabilir?
* Amerika Birleşik Devletleri
* Avrupa
* Asya
* Avustralya
* Hindistan
* Japonya
* Kanada

## <a name="what-features-are-specific-to-a-given-region"></a>Hangi özellikler belirli bir bölgeye özeldir?
Ortamlar, farklı bölgelerde oluşturulabilir ve oluşturuldukları coğrafi konuma bağlı olur. Bir ortamda akış oluşturduğunuzda, bu akış o coğrafi konumdaki veri merkezlerinde dağıtılır. Bu durum, o ortamda oluşturduğunuz ortak veri modeli, akışlar, bağlantılar, ağ geçitleri, uygulamalar ve özel bağlayıcılar dahil tüm öğeler için geçerlidir.

En iyi performans için, ortamınızı kullanıcılarınıza en yakın bölgede oluşturun. Örneğin, kullanıcılarınız Avrupa’daysa ortamlarınızı Avrupa bölgesinde oluşturun. Kullanıcılarınız Birleşik Devletler'deyse ortamlarınızı Birleşik Devletler bölgesinde oluşturun.

## <a name="gateways"></a>Ağ geçitleri
Ağ geçitleri:

* Hindistan bölgesinde kullanılamaz.
* Yalnızca varsayılan ortamda desteklenir, özel ortamlarda desteklenmez.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>Microsoft Flow ulusal bulutlarda kullanılabilir mi?
Hayır, Microsoft Flow ulusal bulutlarda kullanılamaz. Ulusal bulutlara yönelik desteğin 2018’de sunulması planlanmaktadır.

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Hangi bölgede hangi giden IP adresleri kullanılır?
Bkz. [Limitler ve yapılandırma](limits-and-config.md).
