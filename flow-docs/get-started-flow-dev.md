---
title: Özel Bağlayıcılar oluşturma ve akışları ekleme | Microsoft Docs
description: Özel bağlayıcı oluşturun, paylaşabilirsiniz, akış ekleyin ve çok daha fazlasını yapın.
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
ms.date: 11/22/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 80b1d17944d780a1800c91458ee674f5f2afe188
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548261"
---
# <a name="start-to-build-with-microsoft-flow"></a>Microsoft Flow ile oluşturmaya başlayın
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Uygulamanızı Microsoft Flow genişletebilmeniz için bazı yollar şunlardır:

* Özel bir bağlayıcı oluşturun ve bağlayın.
* Özel bağlayıcınızı tüm Microsoft Flow kullanıcılarla paylaşabilirsiniz.
* Flow deneyimini bir uygulama içine ekleyin.
* Kullanıcıların Microsoft Flow en iyi şekilde etkileşimde kullanılabilmesi için tüm özel bağlayıcıları vurgulayın.

## <a name="prerequisites"></a>Kaynakları

* [Microsoft Flow](https://flow.microsoft.com) hesabı.

## <a name="create-a-custom-connector"></a>Özel bağlayıcı oluşturma

Microsoft Flow bağlamak istediğiniz bir Web hizmetiniz varsa öncelikle bir özel bağlayıcı oluşturmanız gerekir. Özel bir bağlayıcıyı kaydettiğinizde, Web hizmetinizin özellikleri hakkında, gerekli kimlik doğrulaması, desteklediği Tetikleyiciler ve eylemler ile bu eylemlerin her biri için parametreler ve çıktılar dahil olmak üzere Microsoft Flow öğretirsiniz.

[Özel bağlayıcıları kaydetme ve kullanma](https://powerapps.microsoft.com/tutorials/register-custom-api/)hakkında bilgi edinmek için bu öğreticiyi izleyin. Özel bağlayıcınızı kaydettikten sonra, test etmek için kuruluşunuz dahilinde paylaşabilirsiniz.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Tüm Microsoft Flow kullanıcılarla özel bağlayıcı paylaşma

Özel bağlayıcınızı tam olarak test ettikten sonra, diğer tüm Microsoft Flow kullanıcılarla paylaşmak üzere Microsoft tarafından onaylanmak için [inceleme sürecini](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) başlatın.

İnceleme işlemi için gerekenler aşağıda verilmiştir:

* API 'nizi ve tüm kimlik doğrulama bilgilerini temsil eden bir Openapı dosyası.
* Bağlayıcınız için bir simge.
* Bağlayıcınızın açıklaması.
* Bağlayıcının diğer kullanıcılara şablonlar aracılığıyla nasıl yararlanabileceği hakkında yaklaşık 10 fikir.

Bu bilgileri gönderdikten sonra Microsoft, API 'nizin Microsoft Flow ve Microsoft PowerApps işlevselliğini değerlendirmeye başlar.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Akış deneyimini Web sitenize veya uygulamanıza ekleyin

Uygulamanız ile Microsoft Flow desteklediği diğer tüm hizmetler arasında derin ve bağlam içi tümleştirmeyi sağlamak [için Microsoft Flow uygulamanıza](developer/embed-flow-dev.md) ekleyebilirsiniz. Örneğin, şunları yapabilirsiniz:

* Hizmetinizle ilgili tüm şablonlara gözatıp kullanıcıların bir şablon seçmesini sağlayın.
* Kullanıcıların uygulamanızla ilgili akışlarını yönetin.

## <a name="next-steps"></a>Sonraki adımlar

Microsoft Flow uygulamanıza [ekleme](developer/embed-flow-dev.md) hakkında bilgi edinin.
