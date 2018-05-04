---
title: Microsoft Flow GDPR Veri Sahibi İstekleri Keşfi | Microsoft Docs
description: Microsoft Flow’u kullanarak GDPR Veri Sahibi Keşif İstekleri’ni yanıtlamayı öğrenin.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: 9f950da1b62eac66b35a667f307917f704eb9133
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Microsoft Flow için GDPR Veri Sahibi Keşif İstekleri’ni yanıtlama

Bir DSR’yi yanıtlamadaki ilk adım, isteğin konusu olan kişisel verileri bulmaktır. Bu ilk adım, DSR’nin kuruluşunuzun bir DSR isteğini yerine getirme veya reddetme gereksinimlerini karşılayıp karşılamadığını belirlemenize yardımcı olur. Örneğin, söz konusu kişisel verileri bulup inceledikten sonra, aksi takdirde başkalarının haklarını ve özgürlüklerini olumsuz yönde etkileyebileceğinden isteğin kuruluşunuzun gereksinimlerini karşılamadığını belirleyebilirsiniz.

Aşağıda belirli bir kullanıcının kişisel verilerini kapsayan Microsoft Flow kaynakları türlerinin bir özeti yer almaktadır.

|**Kişisel verileri kapsayan kaynaklar**|**Amaç**|
|-----|-----|
|Sistem tarafından oluşturulan günlükler|Sistem olaylarını ve geçmişini yakalayan telemetri.|
|Çalıştırma geçmişi|Son 28 gün içindeki her akış yürütmesinin geçmişi. Bu veriler, akışın başlangıç zamanı, bitiş zamanı, durum ve tüm giriş/çıkış bilgilerini içerir. [Daha fazla bilgi](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Etkinlik akışı| Çalışma durumunu, hataları ve bildirimleri içeren akış etkinliklerinin bir özetini sağlar.|
|Kullanıcı işleri|Akışların yürütülmesi için bir kullanıcı adına çalıştırılan ve kullanıcıya görülmeyen sistem işleri.|
|Akışlar|Bir akış için mevcut olan iş akışı mantığı. [Daha fazla bilgi](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Akış izinleri|Akışlar diğer kullanıcılarla paylaşılabilir ve bu kullanıcılara yeniden atanabilir. Tüm akışlar için mevcut olan izinler listeleri. [Daha fazla bilgi](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Kullanıcı ayrıntıları|Kullanıcı tarafından görülmeyen ve akış yürütmeyi destekleyen ayrıntılar.|
|Bağlantılar|Bağlayıcılar tarafından kullanılır ve API’lere, sistemlere, veritabanlarına vb. bağlantı olanağı sağlar. [Daha fazla bilgi](https://docs.microsoft.com/flow/add-manage-connections)|
|Bağlantı izinleri|Belirli bir bağlantı için izinler. [Daha fazla bilgi](https://docs.microsoft.com/flow/add-manage-connections)|
|Özel bağlayıcılar|Özel veya üçüncü taraf sistemlere bağlantı olanağı sağlayan, bir kullanıcının oluşturduğu ve yayımladığı özel bağlayıcılar. [Daha fazla bilgi](https://docs.microsoft.com/connectors/custom-connectors/)|
|Özel bağlayıcı izinleri|Özel bağlayıcılar için izin listeleri. [Daha fazla bilgi](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Ağ geçidi|Ağ geçitleri, Microsoft Flow ile bulutta olmayan bir veri kaynağı arasında hızlı ve güvenli bir şekilde veri aktarmak için bir kullanıcı tarafından yüklenebilen şirket içi veri hizmetleridir. [Daha fazla bilgi](https://docs.microsoft.com/flow/gateway-manage)|
|Ağ geçidi izinleri|Ağ geçitleri bir kuruluş içinde kullanıcılarla paylaşılabilir. [Daha fazla bilgi](https://go.microsoft.com/fwlink/?linkid=872249)|
