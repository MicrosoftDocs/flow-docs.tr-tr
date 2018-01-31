---
title: "API bağlayıcısına genel bakış  | Microsoft Docs"
description: "ISS’ler ve SaaS hizmet sahipleri bağlayıcılar oluşturabilir ve bunların Microsoft tarafından onaylanmasını sağlayabilir."
services: 
suite: flow
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: 62f8f8d0af72292a61324d75bd46f53d559b46a3
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="api-connector-overview-microsoft-flow"></a>API bağlayıcısına genel bakış (Microsoft Flow)
**API bağlayıcısı**, REST API’nin etrafında bir OpenAPI (Swagger) tabanlı sağlayıcıdır ve temelini oluşturan hizmetin [Microsoft Flow](https://flow.microsoft.com), [PowerApps](https://powerapps.microsoft.com), ve [Logic Apps](https://docs.microsoft.com/azure/logic-apps/) ile iletişim kurmasına olanak tanır. Kullanıcıların hesaplarını bağlamaları ve uygulamalarıyla iş yüklerini oluştururken önceden oluşturulmuş bir dizi **tetikleyici** ve **eylemden** yararlanmaları için bir yol sağlar.

**Bağımsız yazılım satıcısı (ISS)** veya **SaaS hizmet sahibi** olarak, kullanıcılarınıza geniş bir yelpazede iş ve üretkenlik senaryoları sunmak için bağlayıcılar oluşturabilirsiniz. Bağlayıcı, tanımlı bir tümleştirme kümesinin ötesine geçmenize ve hizmetinizin kapsama alanını, keşfedilebilirliğini ve kullanımını artırmanıza yardımcı olur.

## <a name="requirements"></a>Gereksinimler
Bağlayıcı oluşturmak ve göndermek için, hizmetiniz aşağıdaki gereksinimleri karşılamalıdır:

* Microsoft Flow, PowerApps ve Logic Apps’e gayet uygun olan iş kullanıcısı senaryosu
* Kararlı REST API’leriyle genel kullanıma açık bir hizmet

## <a name="build-your-connector"></a>Bağlayıcınızı oluşturma
API Bağlayıcısı oluşturmanın ilk adımı, tümüyle işlevsel bir özel bağlayıcı oluşturmaktır. Özel bağlayıcı aynı API bağlayıcısı gibi çalışır, ama kullanılabilirliği yazarıyla ve yazarın kiracısı içindeki belirli kullanıcılarla sınırlıdır.

Bağlayıcı oluşturma işlemi çeşitli adımlar içerir:

![API bağlayıcısı yazma adımları](./media/api-connectors-overview/authoring-steps.png)

API bağlayıcısını geliştirme hakkında [daha fazla bilgi edinin](api-connector-dev.md).

## <a name="submit-for-certification"></a>Sertifika için gönderme
Bağlayıcıyı oluşturduktan sonra, sertifika için gönderirsiniz. Üçüncü taraf sertifika sürecimiz kapsamında, Microsoft yayımlama öncesinde bağlayıcıyı gözden geçirir.

Bu süreçte bağlayıcınızın Microsoft Flow ve PowerApps’teki işlevselliği doğrulanır; teknik ve içerik uyumluluğu açısından denetlenir.

Bağlayıcınızı sertifika ve yayımlama için gönderme süreci hakkında [daha fazla bilgi edinin](api-connector-submission.md).

## <a name="get-support"></a>Destek alma
Başlangıç yapma ve geliştirme desteği için lütfen[condevhelp@microsoft.com](mailto:condevhelp@microsoft.com) adresine e-posta gönderin. Bu hesap etkin bir şekilde izlenmekte ve yönetilmektedir. Geliştiricilerin sorguları ve olayları kısa süre içinde uygun takıma ulaştırılır.

