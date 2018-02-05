---
title: "API bağlayıcısı hakkında SSS | Microsoft Docs"
description: "Gereksinimler, tetikleyiciler ve diğer alanlar hakkındaki soruların yanıtlarını bulun."
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
ms.date: 09/19/2017
ms.author: astay
ms.openlocfilehash: 1715700fa6a94bb35733865556a2c9be0ba3ce9f
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="api-connector-faq-microsoft-flow"></a>API bağlayıcısı hakkında SSS (Microsoft Flow)
## <a name="requirements"></a>Gereksinimler
**S:** REST API’leri olmadan bağlayıcı oluşturabilir miyim? </br>
**C:** Hayır, bağlayıcı oluşturmak için, hizmetinizde kararlı HTTP REST API’lerini desteklemeniz gerekir. 

**S:** Bağlayıcı oluşturmak için hangi araçları kullanabilirim? </br>
**C:** Azure’da, herhangi bir hizmeti API olarak açığa çıkarmak için kullanabileceğiniz özellikler ve hizmetler (örneğin, barındırma için Azure App Service, API Management ve diğerleri) bulunur.

**S:** Hangi kimlik doğrulaması türleri desteklenir? </br>
**C:** Aşağıdaki desteklenen kimlik doğrulaması standartlarını kullanabilirsiniz:

* [Azure Active Directory](https://azure.microsoft.com/develop/identity/) dahil olmak üzere [OAuth 2.0](https://oauth.net/2/) veya Dropbox, GitHub ve SalesForce gibi belirli hizmetler
* Genel OAuth 2.0
* [Temel kimlik doğrulaması](https://swagger.io/docs/specification/authentication/basic-authentication/)
* [API Anahtarı](https://swagger.io/docs/specification/authentication/api-keys/)

## <a name="triggers"></a>Tetikleyiciler
**S:** Web kancaları olmadan tetikleyiciler oluşturabilir miyim? </br>
**C:** Hayır, Azure Logic Apps ve Microsoft Flow için özel bağlayıcılar, yalnızca web kancası tabanlı tetikleyicileri destekler. Uygulama için diğer desenlere yönelik istekte bulunmak için, API’niz hakkında daha fazla ayrıntı ile [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com) adresinden bizimle iletişime geçin.

## <a name="certification"></a>Sertifika
**S**: Bir Microsoft iş ortağı veya Bağımsız Yazılım Satıcısı (ISV) değilim. Yine de bağlayıcı oluşturabilir miyim? </br>
**C**: Evet, bu bağlayıcıları kuruluşunuz içinde kullanmak için kaydedebilirsiniz ancak bir bağlayıcıyı doğrulamak ve genel olarak yayınlamak istiyorsanız, temel alınan hizmetin sahibi olmanız veya API’yi kullanmak için açık hakları sunmanız gerekir.

## <a name="other"></a>Diğer
**S:** API’lerimde dinamik ana bilgisayar kullanılıyor. Bunları OpenAPI’de nasıl uygulayabilirim? </br>
**C:** Özel bağlayıcılar dinamik konakları desteklemez. Bunun yerine, geliştirme ve test amaçlarıyla statik ana bilgisayar kullanın. Bağlayıcınızı doğrulamak istiyorsanız, Microsoft temsilcinizden dinamik uygulama hakkında daha fazla bilgi alabilirsiniz.

**S:** Postman Collection V2’yi destekliyor musunuz? </br>
**C:** Hayır, şu anda yalnızca Postman Collection V1 desteklenmektedir.

**S:** OpenAPI 3.0’ı destekliyor musunuz? </br>
**C:** Hayır, şu anda yalnızca OpenAPI 2.0 desteklenmektedir.

