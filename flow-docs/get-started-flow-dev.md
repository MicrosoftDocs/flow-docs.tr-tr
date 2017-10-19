---
title: "Oluşturmaya başlama | Microsoft Docs"
description: "Özel bağlayıcıyı oluşturun, paylaşın, akış ekleyin ve çok daha fazlasını yapın."
services: 
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: barathb
ms.openlocfilehash: d22193ac40b6eb8f90abf2ae5ced91b39c2faad9
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="start-to-build-with-microsoft-flow"></a>Microsoft Flow ile oluşturmaya başlama
Diğer yolların yanı sıra şunları kullanarak Microsoft Flow ile uygulamanızı genişletin:

* özel bağlayıcı oluşturma ve bu bağlayıcıya bağlanma
* ilgili API'yi tüm Microsoft Flow kullanıcılarıyla paylaşma
* akış deneyimini uygulamaya ekleme
* kullanıcıların Microsoft Flow ile en iyi şekilde etkileşim kurması için tüm geliştirici API'lerinden faydalanma

## <a name="prerequisites"></a>Önkoşullar
* [flow.microsoft.com](https://flow.microsoft.com)'da bir hesap

## <a name="create-a-custom-connector"></a>Özel bağlayıcı oluşturma
Microsoft Flow ile otomatik hale getirebilmek istediğiniz bir web hizmetiniz olduğunda, öncelikle bir özel bağlayıcı oluşturmanız gerekir. Özel bağlayıcıyı kaydederek Microsoft Flow'a web API'nizin özelliklerini (API'niz için gereken kimlik doğrulaması, desteklenen tetikleyiciler ve eylemler ile bu eylemlerin her birine ilişkin parametreler ve çıkışlar da dahil olmak üzere) öğretirsiniz.

Özel bağlayıcıyı kaydetmek için bu [öğreticiye](https://powerapps.microsoft.com/tutorials/register-custom-api/) göz atın. Özel API'nizi kaydettikten sonra, başka kullanıcıların da test etmenize yardımcı olması için API'nizi kuruluşunuzun içinde paylaşabilirsiniz.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Özel bağlayıcıyı tüm Microsoft Flow kullanıcıları ile paylaşma
Özel bağlayıcınızı tamamen test ettikten sonra, [bu blog gönderisinde](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) belirtilen gözden geçirme sürecini başlatın:

* API'nizi ve tüm kimlik doğrulama bilgilerini içeren bir OpenAPI dosyası
* Bağlayıcınıza ilişkin bir simge
* API'nize ilişkin bir açıklama
* API'nizin şablonlar yoluyla diğer kullanıcılara ne gibi avantajlar sağlayabileceğiyle ilgili yaklaşık 10 fikir

Bu bilgileri gönderdikten sonra Microsoft, API'nizin Microsoft Flow ve Microsoft PowerApps'teki işlevini değerlendirmeye başlar.

## <a name="embed-the-flow-experience-in-your-website-or-app"></a>Akış deneyimini web sitenize veya uygulamanıza ekleme
Son olarak, uygulamanıza Microsoft Flow'u ekleyerek uygulamanız ile Microsoft Flow'un desteklediği tüm diğer hizmetler arasında derin ve bağlam içi bir tümleştirme sağlayabilirsiniz. Örneğin, şunları yapabilirsiniz:

* Hizmetinizle ilgili tüm şablonlara göz atma ve kullanıcıların şablon seçmesine izin verme
* Kullanıcıların uygulamanızla ilgili akışlarını yönetme

Microsoft Flow'un uygulamaya eklenmesi ile ilgili daha ayrıntılı bilgi edinmek için [bu öğreticiye](embed-flow-dev.md) göz atın.

