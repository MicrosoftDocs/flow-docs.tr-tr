---
title: Microsoft hesapları için GDPR veri konu Isteği Özeti (MSA) | Microsoft Docs
description: Microsoft Flow için GMBU veri konu taleplerini nasıl yanıtleyeceğinizi öğrenin.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: bff3e050db40c60622496202a092f94cc1d36fca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548174"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>GDPR veri konu hakları (DSRs) isteklerini yanıtlama
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bu makalede, Avrupa Birliği 'nin Genel Veri Koruma Yönetmeliği (GDPR) açıklanır ve Microsoft hesaplarıyla (MSA) kimlik doğrulayan Microsoft Flow kullanıcılar için GDPR uyumluluğunu desteklemek üzere uygulayabileceğiniz adımlar sağlanmaktadır.

## <a name="prerequisites"></a>Kaynakları

Bu makaledeki adımları gerçekleştirmek için [ücretsiz bir Microsoft Flow lisansa](https://flow.microsoft.com/pricing/) sahıp bir MSA gerekir.

>[!TIP]
> GDPR uyumluluk bilgileri, [Azure Active Directory hesaplarıyla](gdpr-dsr-summary.md)kimlik doğrulayan kullanıcılar için de kullanılabilir.
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>Microsoft Flow müşteri verileri için DSRs 'ye yanıt verme

Veri konusunun kişisel verilerinde bir işlem yapması için bir denetleyiciye yönelik resmi istek, veri konu hakları (DSR) isteği olarak adlandırılır. GDPR, kişisel verileri **tanımlanan veya tanımlanabilen doğal bir kişiyle ilgili herhangi bir veri**olarak tanımlar. GDPR, bir işveren, kurum veya kuruluş tarafından toplanan kişisel verileri (veri denetleyicisi veya denetleyici olarak bilinir) yönetmek için kişiler (veri konuları olarak bilinir) hakları sağlar. Bu haklar şunları içerir:

* Kişisel verilerin kopyalarını alma.
* Kişisel verilerde düzeltmeler isteme.
* Kişisel verilerin işlenmesini sınırlandırma.
* Kişisel verileri silme.
* Kişisel verileri başka bir denetleyiciye taşınabilmesi için elektronik biçimde alma.

Microsoft, denetleyicilerin bulutta bulunan veriler için DSRs isteklerine yanıt verme sırasında kişisel verileri bulmasına ve üzerinde işlem yapması için ürünleri, hizmetleri ve araçları sağlar.

Bu kılavuzda özetlenen işlemlere genel bakış aşağıda verilmiştir:

1. **Keşfet**: bir DSR isteğinin konusu olabilecek müşteri verilerini kolayca bulmak için arama ve bulma araçlarını kullanın. Topladığınız belgelerin işlem yapmak için denetleyici kılavuzlarınızı karşıladığını belirlerseniz, aşağıdaki adımlarda açıklanan DSR eylemlerinden birini veya birkaçını gerçekleştirebilirsiniz. [Microsoft hesapları için MICROSOFT Flow DSR bulma belgeleri](gdpr-dsr-discovery-msa.md)hakkında daha fazla bilgi edinin. Alternatif olarak, isteğin DSR isteklerine yanıt vermek için denetleyici kılavuzlarınızı karşılamadığını belirleyebilirsiniz.

1. **Erişim**: Microsoft bulutunda bulunan kişisel verileri alın ve istenirse, veri konusunun kullanabilmesi için bir kopyasını oluşturun.

1. **Rectify**: uygun olduğunda, kişisel veriler üzerinde değişiklikler yapın veya istenen diğer eylemleri uygulayın.

1. **Kısıtla**: çeşitli çevrimiçi hizmetler lisanslarını kaldırarak veya mümkün olduğunca istenen Hizmetleri kapatarak kişisel verilerin işlenmesini kısıtlayın. Ayrıca Microsoft bulutundaki verileri kaldırabilir ve şirket içinde veya başka bir konumda saklayabilirsiniz.

1. **Sil**: Microsoft 'un bulutunda bulunan kişisel verileri kalıcı olarak kaldırın. [Microsoft hesapları için kişisel verileri silme](gdpr-dsr-delete-msa.md)hakkında daha fazla bilgi edinin. [Bir Microsoft hesabı kapatma](gdpr-dsr-accountclose-msa.md)hakkında daha fazla bilgi edinin.

1. **Dışarı aktar**: kişisel verilerin elektronik bir kopyasını (makine tarafından okunabilen bir biçimde) sağlayın. [Microsoft hesapları için kişisel verileri dışarı aktarma hakkında daha fazla bilgi edinin](gdpr-dsr-export-msa.md).
