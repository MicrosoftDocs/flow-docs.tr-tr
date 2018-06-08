---
title: Microsoft Flow’u web siteleri ve uygulamalarla tümleştirme | Microsoft Docs
description: Microsoft Flow deneyimlerini web sitenize veya uygulamanıza ekleyin.
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2017
ms.author: barathb
ms.openlocfilehash: af03ee70b09ba5ee1164a9a7ea5019b13c19eec6
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440055"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Microsoft Flow’u web siteleri ve uygulamalarla tümleştirme
Kullanıcılara, kişisel veya profesyonel görevlerini otomatik hale getirmeleri için kolay bir yol sunmak üzere, Microsoft Flow'u uygulamanıza veya web sitenize ekleyin.

Akış oluşturmak için, kullanıcıların bir **Microsoft Hesabına** veya **Azure Active Directory**'de bir iş ya da okul hesabına sahip olmaları gerekir. Microsoft Flow, sisteminizin kullandığı tüm kimlikleri destekleyen bir aracı çözümünü, Microsoft Hesapları veya AAD kullanmıyor olması durumunda desteklemez.

## <a name="prerequisites"></a>Önkoşullar
* Hizmetinizi Microsoft Flow'a bağlayan bir [özel bağlayıcı oluşturun](register-custom-api.md).
* API'nizi kullanan [bir veya daha fazla şablon oluşturun ve yayımlayın](publish-a-template.md).

## <a name="show-templates-for-your-scenarios"></a>Senaryolarınıza ilişkin şablonları gösterme
Başlangıç olarak, akış şablonlarını doğrudan web sitenizde göstermek için şu kodu ekleyin:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

**Not**: Kodun sayfada daha iyi görünmesi için bir satır sonu ekledik.

| Parametre | Açıklama |
| --- | --- |
| yerel ayar |Şablon görünümü için dört harfli dil ve bölge kodu. Örneğin, `en-us` Amerikan İngilizcesi'ni ve `de-de`, Almanca'yı temsil eder. |
| arama terimi |Görünümde göstermek istediğiniz şablonlara ilişkin arama terimi. Örneğin, Wunderlist şablonlarını göstermek için `wunderlist` öğesini arayın. |
| şablon sayısı |Görünümde göstermek istediğiniz şablon sayısı. |
| hedef |Kullanıcılar şablona tıklattığında açılan sayfa. Şablonla ilgili ayrıntıları göstermek için `details` öğesini belirtin veya Microsoft Flow tasarımcısını açmak için `new` öğesini belirtin. |
| parameters.{name} |Akışa geçirmek için ek bağlam. |

Hedef parametre `new` ise, kullanıcılar bir şablona tıkladığında Microsoft Flow açılır ve tasarımcıda akış oluşturabilirler. Uygulama ile ilgili eksiksiz deneyim edinmek istiyorsanız bir sonraki bölüme bakın.

### <a name="passing-additional-parameters-to-the-flow"></a>Akışa ek parametre geçirme
Kullanıcı, web sitenizde veya uygulamanızda belirli bir bağlamda ise bu bağlamı akışa geçirmek isteyebilirsiniz. Örneğin, bir kullanıcı Wunderlist'te belirli bir listeye bakarken *Notify me when an item is added to a list* (Listeye bir öğe eklendiğinde bana bildir) için bir şablon açabilir. Şu adımları izleyerek, liste kimliğini akışa bir *parametre* olarak geçirebilirsiniz:

1. Yayımlamadan önce, akış şablonunda parametreyi tanımlayın. Parametre şöyle görünür: `@{parameters('parameter_name')}`.
2. Parametreyi iframe src içine alın. Örneğin, **listName** adlı bir parametreniz varsa `&parameters.listName={the name of the list}` öğesini ekleyin.

### <a name="full-sample"></a>Tam örnek
Wunderlist ile ilgili ilk dört şablonu görüntülemek ve kullanıcıyı **myCoolList** ile başlatmak için:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="embed-the-management-of-flows"></a>Akış yönetimini ekleme
Kullanıcıların, (Microsoft Flow portalına gitmek yerine) doğrudan web sitenizden veya uygulamanızdan akış oluşturmasını ve yönetmesini sağlamak için, kimliği doğrulanmış Flow SDK'sını kullanın. Kullanıcının, kimliği doğrulanmış SDK'yı kullanmak için Microsoft Hesabı'nda veya Azure Active Directory'de oturum açması gerekir.

> [!NOTE]
> Uygulamanızda Microsoft Flow kullanan tüm kullanıcılar, Microsoft Flow kullanıcıları olacaktır. Microsoft Flow markasını gizlemenin hiçbir yolu yoktur.
> 
> 

### <a name="include-the-javascript-for-the-authenticated-sdk"></a>Kimliği doğrulanmış SDK için JavaScript ekleme
Bu örneği uygulayarak SDK'yı HTML kodunuza ekleyin. Ayrıca SDK'yı indirebilir, küçültebilir ve ürününüzle birlikte paket haline getirebilirsiniz.

```javascript
<script src="https://flow.microsoft.com/content/msflowsdk-1.1.js" async defer></script>
```

### <a name="create-a-container-to-contain-the-view"></a>Görünümü içerecek bir kapsayıcı oluşturma
HTML div'i ekleyin:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Bu kapsayıcıyı, deneyiminiz süresince uygun boyutlarda görünecek şekilde biçimlendirmenizi öneririz:

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

iframe'in 320 piksel genişliğin altında düzgün şekilde işlemeyeceğini ve 1200 piksel genişliğin üzerinde içerik doldurmayacağına dikkat edin. Herhangi bir yüksekliğe ayarlayabilirsiniz.

### <a name="authentication-against-the-sdk"></a>SDK'da kimlik doğrulaması
Kullanıcının önceden oluşturduğu akışları listelemek ve şablonlardan akış oluşturmak için AAD'den bir authToken sağlayın.

```javascript
<script>
    window.msFlowSdkLoaded = function() {
        var sdk = new MsFlowSdk({
            hostName:'https:/flow.microsoft.com'
        });
        var widget = sdk.renderWidget('flows', {
            container: 'flowDiv'
            environmentId: '[environmentId]'    // find environment id from browser URL when you 
                                                // click on 'my flows'
                                                //ex: https://flow.microsoft.com/manage/environments/[environmentId]/flows
        });
        widget.callbacks.GET_ACCESS_TOKEN = function(requestParam, widgetDoneCallback)
       {
            var authCallback = function(token) {
                widgetDoneCallback(null, {
                    token: token // Get AAD access token from your backend system
                });
            };
        }
    }
</script>
```

Kullanıcının erişimi olan ortamların listesini döndüren aşağıdaki API çağrısını yaparak, `environmentId` değerini bulabilirsiniz:

```http
GET https://management.azure.com/providers/Microsoft.ProcessSimple/environments
?api-version=2016-11-01 
```

Bu, ortamların listelendiği bir JSON yanıtı döndürür ve aralarından herhangi bir ortamı seçebilirsiniz. Varsayılan kullanıcı ortamını bulmak için `properties.isDefault=true` özelliğine bakabilirsiniz.

Bu örnekte, `requestParam` tanımı aşağıdaki gibi yapılmıştır:

```javascript
export interface IRpcRequestParam {
    callInfo: IRpcCallInfo,
    data?: any;
}
```

Daha sonraki `widgetDoneCallback`, konak belirteci aldığında çağrılması gereken bir geri çağırma işlevidir. Bu işlem, belirteç edinme işlemi muhtemelen zaman uyumsuz bir işlem olduğu için gerçekleştirilir. Bu işlev çağrılırken geçirilmesi gereken parametreler şunlardır: `(errorResult: any, successResult: any)`. successResult geri çağırma türüne bağlı olacaktır. `GetAccessToken` için tür şöyle olur:

```javascript
export interface IGetAccessTokenResult {
    token: string;
}
```
