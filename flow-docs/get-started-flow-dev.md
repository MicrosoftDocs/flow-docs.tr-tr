---
title: Özel bağlayıcılar oluşturma ve akışlar ekleme | Microsoft Docs
description: Özel bağlayıcıyı oluşturun, paylaşın, akış ekleyin ve çok daha fazlasını yapın.
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: barathb
ms.openlocfilehash: a3f1e21cfbf00749a0ef09c0363da162f0419f42
ms.sourcegitcommit: aee927ab32b5e28ee9b1880b4a292f9c15025f88
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/03/2018
---
# <a name="start-to-build-with-microsoft-flow"></a>Microsoft Flow ile oluşturmaya başlama

Microsoft Flow ile uygulamanızı genişletebileceğiniz yollardan bazıları şunlardır:

* Özel bağlayıcı oluşturun ve bu bağlayıcıya bağlanın.
* Özel bağlayıcınızı tüm Microsoft Flow kullanıcıları ile paylaşın.
* Akış deneyimini uygulamaya ekleyin.
* Kullanıcıların Microsoft Flow ile en iyi şekilde etkileşim kurması için tüm özel bağlayıcıları vurgulayın.

## <a name="prerequisites"></a>Önkoşullar

* Bir [Microsoft Flow](https://flow.microsoft.com) hesabı.

## <a name="create-a-custom-connector"></a>Özel bağlayıcı oluşturma

Microsoft Flow’dan bağlanmak istediğiniz bir web hizmetiniz olduğunda, öncelikle bir özel bağlayıcı oluşturmanız gerekir. Özel bağlayıcıyı kaydederek Microsoft Flow'a web hizmetinizin özelliklerini (hizmetiniz için gereken kimlik doğrulaması, hizmetinizin desteklediği tetikleyiciler ve eylemler ile bu eylemlerin her birine ilişkin parametreler ve çıkışlar da dahil olmak üzere) öğretirsiniz.

[Özel bağlayıcıları kaydetmeyi ve kullanmayı](https://powerapps.microsoft.com/tutorials/register-custom-api/) öğrenmek için bu öğreticiyi takip edin. Özel bağlayıcınızı kaydettikten sonra, test etmek üzere kuruluşunuzda paylaşabilirsiniz.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Özel bağlayıcıyı tüm Microsoft Flow kullanıcıları ile paylaşma

Özel bağlayıcınızı tam olarak test ettikten sonra, diğer tüm Microsoft Flow kullanıcılarıyla paylaşılması için Microsoft tarafından onaylanmak üzere [inceleme işlemini](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) başlatın.

İnceleme işlemi için gerekenler:

* API’nizi ve tüm kimlik doğrulama bilgilerini temsil eden bir OpenAPI dosyası.
* Bağlayıcınıza ilişkin bir simge.
* Bağlayıcınıza ilişkin bir açıklama.
* Bağlayıcınızın şablonlar yoluyla diğer kullanıcılara ne gibi avantajlar sağlayabileceğiyle ilgili yaklaşık 10 fikir.

Bu bilgileri gönderdikten sonra Microsoft, API’nizin Microsoft Flow ve Microsoft PowerApps’teki işlevini değerlendirmeye başlar.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Akış deneyimini web sitenize veya uygulamanıza ekleme

Uygulamanıza Microsoft Flow’u [ekleyerek](embed-flow-dev.md) uygulamanız ile Microsoft Flow’un desteklediği tüm diğer hizmetler arasında derin ve bağlam içi bir tümleştirme sağlayabilirsiniz. Örneğin, şunları yapabilirsiniz:

* Hizmetinizle ilgili tüm şablonlara göz atın ve kullanıcıların şablon seçmesine izin verin.
* Kullanıcıların uygulamanızla ilgili akışlarını yönetin.

## <a name="next-steps"></a>Sonraki adımlar

Microsoft Flow’u uygulamanıza nasıl [ekleyeceğinizi](embed-flow-dev.md) öğrenin.
