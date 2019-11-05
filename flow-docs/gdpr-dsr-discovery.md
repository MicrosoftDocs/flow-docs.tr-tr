---
title: Microsoft Flow GDPR veri konu Isteği bulma | Microsoft Docs
description: GUZ veri konu bulma Isteklerini yanıtlamak için Microsoft Flow nasıl kullanacağınızı öğrenin.
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
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 197d9ebfc38fc4f5b52bf674aef61d419530f439
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548119"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Microsoft Flow için GDPR veri konu bulma Isteklerini yanıtlama
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

DSR 'e yanıt vermeye yönelik ilk adım, isteğin konusu olan kişisel verileri buluyor. Bu ilk adım, bir DSR 'nin bir DSR isteğini değerlendirmek veya reddetmeyi sağlamak için kuruluşunuzun gereksinimlerini karşılayıp karşılamadığını belirlemenize yardımcı olur. Örneğin, sorunun kişisel verilerini bulduktan ve gözden geçirdikten sonra, isteğin kuruluşunuzun gereksinimlerini karşılamadığını tespit edebilir, çünkü bunun yapılması başkalarının haklarını ve serbest sürümlerini olumsuz etkileyebilir.

Aşağıda belirli bir kullanıcı için kişisel verileri içeren Microsoft Flow kaynak türlerinin bir özeti verilmiştir.

|**Kişisel verileri içeren kaynaklar**|**Amaçla**|
|-----|-----|
|Sistem tarafından oluşturulan Günlükler|Sistem olaylarını ve geçmişini yakalayan telemetri.|
|çalıştırma geçmişi|Son 28 gün boyunca her bir akış yürütmenin geçmişi. Bu veriler, Flow için başlangıç zamanı, bitiş zamanı, durum ve tüm giriş/çıkış bilgilerini içerir. [Daha fazla bilgi edinin](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Etkinlik akışı| Çalışma durumu, başarısızlık ve bildirimler dahil olmak üzere akış etkinliklerinin bir üst sınırını sağlar.|
|Kullanıcı işleri|Kullanıcıya görülmeyen, akışların yürütülmesi için Kullanıcı adına çalışan sistem işleri.|
|Var|Bir akış için mevcut iş akışı mantığı. [Daha fazla bilgi edinin](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Akış izinleri|Akışlar, diğer kullanıcılara paylaşılabilir ve yeniden atanabilir. Tüm akışlar için izin listeleri mevcuttur. [Daha fazla bilgi edinin](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Kullanıcı ayrıntıları|Akış yürütmeyi destekleyen Kullanıcı tarafından görülmeyen ayrıntılar.|
|Bağlantının|Bağlayıcılar tarafından kullanılır ve API 'Ler, sistemler, veritabanları vb. bağlantılara izin verir. [Daha fazla bilgi edinin](https://docs.microsoft.com/flow/add-manage-connections)|
|Bağlantı izinleri|Belirli bir bağlantı için izinler. [Daha fazla bilgi edinin](https://docs.microsoft.com/flow/add-manage-connections)|
|Özel Bağlayıcılar|Bir kullanıcının oluşturduğu ve yayımlamakta olduğu özel bağlayıcılar, özel veya üçüncü taraf sistemlere bağlantı sağlar. [Daha fazla bilgi edinin](https://docs.microsoft.com/connectors/custom-connectors/)|
|Özel bağlayıcı izinleri|Özel bağlayıcılar için izin listeleri. [Daha fazla bilgi edinin](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Geçidinde|Ağ geçitleri, Microsoft Flow ve bulutta olmayan bir veri kaynağı arasında verileri hızlı ve güvenli bir şekilde aktarmak için bir kullanıcı tarafından yüklenebilen şirket içi veri hizmetlerdir. [Daha fazla bilgi edinin](https://docs.microsoft.com/flow/gateway-manage)|
|Ağ Geçidi izinleri|Ağ geçitleri, bir kuruluştaki kullanıcılarla paylaşılabilir. [Daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=872249)|
