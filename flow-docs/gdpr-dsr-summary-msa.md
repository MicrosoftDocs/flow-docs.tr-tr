---
title: Microsoft Hesapları (MSA) için GDPR Veri Sahibi İstekleri Özeti| Microsoft Docs
description: Microsoft Flow için GDPR Veri Sahibi İstekleri’ni yanıtlamayı öğrenin.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/16/2018
ms.author: keweare
ms.openlocfilehash: b6fdcd33fd657086a5d37919858eceefabd18934
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34563291"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>GDPR Veri Sahibi Hakları (DSR) isteklerine yanıt verme

Bu makalede, Avrupa Birliği’nin Genel Veri Koruma Yönetmeliği (GDPR) açıklanmakta ve Microsoft Hesapları (MSA) ile kimlik doğrulaması yapan Microsoft Flow kullanıcıları için GDPR uyumluluğunu desteklemek amacıyla uygulayabileceğiniz adımlar sağlanmaktadır.

## <a name="prerequisites"></a>Önkoşullar

Bu makaledeki adımları gerçekleştirmek için [ücretsiz Microsoft Flow lisansı](https://flow.microsoft.com/pricing/) ile bir MSA gerekir.

>[!TIP]
> GDPR uyumluluk bilgileri, [Azure Active Directory hesapları](gdpr-dsr-summary.md) ile kimlik doğrulaması yapan kullanıcılar için de kullanılabilir.
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>Microsoft Flow müşteri verileri için DSR’leri yanıtlama

Bir veri sahibinin bir sorumludan kişisel verileri üzerinde bir işlem yapmak üzere resmi istekte bulunmasına Veri Sahibi Hakları (DSR) isteği adı verilir. GDPR, kişisel verileri, **tanımlı veya tanımlanabilir bir gerçek kişiyle ilişkili tüm veriler** olarak tanımlar. GDPR, kişilere (veri sahipleri olarak bilinir) bir işveren, acente veya kuruluş (veri sorumlusu ya da yalnızca sorumlu olarak bilinir) tarafından toplanan kişisel verileri yönetme hakkı verir. Bu haklar şunları kapsar:

* Kişisel verilerin kopyalarını alma.
* Kişisel veriler üzerinde düzeltme isteme.
* Kişisel verilerin işlenmesini kısıtlama.
* Kişisel verileri silme.
* Başka bir sorumluya taşınabilmesi için kişisel verileri elektronik biçimde alma.

Microsoft, sorumluların bulutta bulunan veriler için DSR isteklerini yanıtlarken kişisel verileri bulup bu veriler üzerinde işlem yapmasına yardımcı olmak için ürünler, hizmetler ve araçlar sağlar.

Bu kılavuzda gösterilen işlemlerin genel bakışını burada bulabilirsiniz:

1. **Keşfedin**: Arama ve bulma araçlarını kullanarak bir DSR isteğinin konusu olabilecek müşteri verilerini kolayca bulun. Topladığınız belgelerin, işlem uygulamaya yönelik denetleyici yönergelerini karşıladığını belirlerseniz, aşağıdaki adımlarda açıklanan DSR eylemlerinden birini veya daha fazlasını gerçekleştirebilirsiniz. [Microsoft Hesapları için Microsoft Flow DSR Bulma belgelerinden](gdpr-dsr-discovery-msa.md) daha fazla bilgi edinebilirsiniz. Alternatif olarak, isteğin sorumlunuzun DSR isteklerini yanıtlama yönergelerini karşılamadığını belirleyebilirsiniz.

1. **Erişin**: Microsoft bulutunda yer alan kişisel verileri alın ve istenirse veri sahibinin kullanabileceği bir kopyasını oluşturun.

1. **Düzeltin**: Uygunsa kişisel veriler üzerinde değişiklikler yapın veya istenen diğer eylemleri uygulayın.

1. **Kısıtlayın**: Mümkün olduğunca çeşitli çevrimiçi hizmetlerin lisanslarını kaldırarak veya istenen hizmetleri kapatarak kişisel verilerin işlenmesini kısıtlayın. Ayrıca verileri Microsoft bulutundan kaldırabilir ve şirket içinde ya da başka bir konumda saklayabilirsiniz.

1. **Silin**: Microsoft’un bulutunda yer alan kişisel verileri kalıcı olarak kaldırın. [Microsoft Hesapları için kişisel verileri silme](gdpr-dsr-delete-msa.md) hakkında daha fazla bilgi edinin. [Microsoft Hesabını kapatma](gdpr-dsr-accountclose-msa.md) hakkında daha fazla bilgi edinin.

1. **Dışarı aktarın**: Kişisel verilerin bir elektronik kopyasını (makine tarafından okunabilir bir biçimde) sağlayın. [Microsoft Hesapları için kişisel verileri dışarı aktarma hakkında daha fazla bilgi edinin](gdpr-dsr-export-msa.md).