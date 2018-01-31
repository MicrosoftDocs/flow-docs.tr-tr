---
title: "API bağlayıcısı geliştirme | Microsoft Docs"
description: "API’nizi açıklayın, kimlik doğrulama türünü belirtin, tetikleyicilerle eylemleri oluşturun ve test edin."
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
ms.openlocfilehash: 8731e8a90a62bac4a05068386d23d2449952860b
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="develop-an-api-connector-microsoft-flow"></a>API bağlayıcısı oluşturma (Microsoft Flow)
Bağlayıcı oluşturma işlemi çeşitli adımlar içerir. Başlamak için, [Microsoft Flow](https://flow.microsoft.com/)’da sayfanın sağ üst kısmındaki **Ayarlar** düğmesine (dişli simgesi) tıklayın veya dokunun. Ardından **Özel Bağlayıcılar**’a tıklayın veya dokunun.

![API bağlayıcılarını bulma](./media/api-connectors-dev/finding-custom-apis.png)

## <a name="describe-your-api"></a>API'nizi açıklama
API bağlayıcıları, HTTP API’sinin arabirimini tanımlamaya yönelik [OpenAPI standardı](https://swagger.io/) kullanılarak açıklanır. Oluşturmaya başlarken mevcut OpenAPI dosyasını kullanabilir veya sizin için OpenAPI dosyasını otomatik olarak oluşturan bir [Postman Collection](https://www.getpostman.com/docs/collections) dosyasını içeri aktarabilirsiniz. 

![API’nizi tanımlama diyagramı](./media/api-connectors-dev/build-your-api-updated.png)

Bu API açıklamalarının birinden başlarsanız, sihirbazdaki meta veri alanları otomatik olarak doldurulur. Bunları istediğiniz zaman düzenleyebilirsiniz.  

## <a name="build-security"></a>Güvenliği oluşturma
Hizmetinizde desteklenen kimlik doğrulama türünü seçin ve kimliğin hizmetinizle istemciler arasında düzgün bir şekilde akıtılmasına olanak tanımak için ek ayrıntıları sağlayın. 

![Güvenlik Diyagramı](./media/api-connectors-dev/security.png)

Bağlayıcı güvenliği hakkında [daha fazla bilgi edinin](register-custom-api.md).

## <a name="build-triggers-and-actions"></a>Tetikleyicileri ve eylemleri oluşturma
1. Bağlayıcınızın tetikleyicilerini ve eylemlerini oluşturmak için, **Tanım** sekmesine geçin. 
   
    ![Tanım Diyagramı](./media/api-connectors-dev/definition.png)
2. Sihirbazı kullanarak yeni işlemler ekleyebilir veya var olan işlemlerin şemasını ve yanıtını düzenleyebilirsiniz. Her işlemin **Genel** özellikleri, bağlayıcınızın son kullanıcı deneyimini denetlemenize olanak tanır. Aşağıdaki bağlantıları kullanarak farklı işlem türleri hakkında daha fazla bilgi edinin:
   
   * [Tetikleyiciler](customapi-webhooks.md) (PowerApps’te görünmez)
   * [Eylemler](register-custom-api.md)
     
     Microsoft Flow’da gelişmiş işlevsellik uygulamak için, [API bağlayıcıları için OpenAPI uzantıları](https://flow.microsoft.com/documentation/customapi-how-to-swagger/) konusunu gözden geçirin. 
3. Son olarak, **Bağlayıcı oluştur**’a tıklayarak veya dokunarak API bağlayıcısını kaydedin.

Sihirbazda sağlanmayan ek özellikler için lütfen [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com) adresine başvurun.

## <a name="test-the-connector"></a>Bağlayıcıyı test etme
Göndermeden önce API bağlayıcınızı bir veya birden çok yöntemle test edin: 

* API bağlayıcısı [Test sihirbazını](https://flow.microsoft.com/blog/new-updates-custom-api/) kullanarak, işlevselliğini ve yanıt şemasını doğrulamak üzere her işlemi çağırabilirsiniz.
* Microsoft Flow’un tasarımcısında, API bağlayıcınızı kullanıp görsel olarak akışlar oluşturabilirsiniz. Bu test yöntemi, kullanıcı arabirimi işlevselliğini ve bağlayıcınızın özelliklerini görebilmenizi sağlar.
* PowerApps Studio’da, formül çubuğunu kullanıp her işlemi çağırabilir ve yanıtı ekranınızdaki denetimlere bağlayabilirsiniz.

Bu konu başlığı altında bir genel bakış sağlanır; daha fazla bilgi için bkz. [Özel bağlayıcıyı kaydetme ve kullanma](register-custom-api.md).

