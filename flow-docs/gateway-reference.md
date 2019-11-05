---
title: Şirket içi veri ağ geçidi | Microsoft Docs
description: Bu makale, Microsoft Flow için şirket içi veri ağ geçidine bir genel bakıştır.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8349361b7ee543c19635dc5899726d69adaa917a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544648"
---
# <a name="what-is-an-on-premises-data-gateway"></a>Şirket içi veri ağ geçidi nedir?
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Şirket içi veri ağ geçidi, şirket içi veriler (bulutta olmayan veriler) ve birkaç Microsoft bulut hizmeti arasında hızlı ve güvenli veri aktarımı sağlamak için bir köprü görevi görür. Bu bulut hizmetlerinde Power BI, PowerApps, Microsoft Flow, Azure Analysis Services ve Azure Logic Apps bulunur. Kuruluşlar, bir ağ geçidi kullanarak veritabanlarını ve diğer veri kaynaklarını şirket içi ağlarında tutabilir, ancak bulut hizmetlerinde bu şirket içi verileri güvenli bir şekilde kullanabilir.

## <a name="how-the-gateway-works"></a>Ağ geçidinin çalışması

![Ağ geçidine genel bakış](media/gateway-reference/on-premises-data-gateway.png)

Ağ geçidinin nasıl çalıştığı hakkında daha fazla bilgi için bkz. Şirket [içi veri ağ geçidi mimarisi](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Ağ geçidi türleri

Her biri farklı bir senaryo için iki farklı ağ geçidi türü vardır:

- Şirket **içi veri ağ geçidi** , birden çok kullanıcının birden çok şirket içi veri kaynağına bağlanmasına izin verir. Tek bir ağ geçidi yüklemesiyle desteklenen tüm hizmetlerle şirket içi veri ağ geçidi kullanabilirsiniz. Bu ağ geçidi, birden çok veri kaynağına erişen çok sayıda kişinin karmaşık senaryolarına uygundur.

- **Şirket içi veri ağ geçidi (kişisel mod)** , bir kullanıcının kaynaklara bağlanmasına ve başkalarıyla paylaşılabilmesi için izin verir. Şirket içi veri ağ geçidi (kişisel mod) yalnızca Power BI ile kullanılabilir. Bu ağ geçidi, rapor oluşturan tek kişi olduğunuz senaryolar için uygundur ve herhangi bir veri kaynağını başkalarıyla paylaşmak zorunda kalmazsınız.

## <a name="use-a-gateway"></a>Ağ geçidi kullanma

Ağ Geçidi kullanmanın dört ana adımı vardır.

1. [Ağ geçidini](/data-integration/gateway/service-gateway-install) yerel bir bilgisayara indirip yükleyin.
2. Ağ geçidini güvenlik duvarınız ve diğer ağ gereksinimlerinize göre [yapılandırın](/data-integration/gateway/service-gateway-app) .
3. Diğer ağ gereksinimlerini yönetebilen ve yönetebilen [ağ geçidi yöneticileri ekleyin](/data-integration/gateway/service-gateway-manage) .
4. Hata durumunda ağ geçidinde [sorun giderin](/data-integration/gateway/service-gateway-tshoot) .

## <a name="next-steps"></a>Sonraki adımlar

- [Şirket içi veri ağ geçidini yükler](/data-integration/gateway/service-gateway-install)
