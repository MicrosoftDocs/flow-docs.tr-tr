---
title: Bir akışla ilgili sorunları giderme | Microsoft Docs
description: Akışların başarısız olmasına yol açan en yaygın sorunları çözümleyin
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/17/2017
ms.author: stepsic
ms.openlocfilehash: 7f4e41437fa19f58c08e2ecd1fb65a3a30092ef8
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23439551"
---
# <a name="troubleshooting-a-flow"></a>Bir akışla ilgili sorunları giderme
## <a name="identify-the-error"></a>Hatayı belirleme
Bir akışı düzeltebilmek için önce akışın neden başarısız olduğunu belirlemeniz gerekir. Web portalının üst kısmındaki bildirimler simgesine dokunun veya tıklayın (veya mobil uygulamadaki **Etkinlik** sekmesini açın) ve açılan listeden akışınıza tıklayın veya dokunun.

![Bildirimler](./media/fix-flow-failures/notifications-toolbar.png)

Akışla ilgili ayrıntılara ek olarak, en az bir adımda kırmızı bir ünlem işareti gösterilir. Bu adımı açıp hata iletisini inceleyin.

![Hata iletisi](./media/fix-flow-failures/flow-run-failure.png)

## <a name="authentication-failures"></a>Kimlik doğrulama hataları
Çoğu durumda, akışların başarısız olmasının nedeni bir kimlik doğrulama hatasıdır. Bu tür bir hata aldıysanız, hata iletisi **Yetkisiz** ifadesini içerir veya **401** ya da **403** hata kodu görüntülenir. Kimlik doğrulama hatalarını genellikle bağlantıyı güncelleştirerek düzeltebilirsiniz.

1. Web portalının üst kısmından dişli simgesine tıklayarak veya dokunarak **Ayarlar** menüsünü açın ve **Bağlantılar**’a tıklayın.
2. **Yetkisiz** hata iletisinin görüntülendiği bağlantıya gidin.
3. Bağlantının yanında bulunan ve bağlantı kimliğinin doğrulanmadığıyla ilgili olan iletideki **Parolayı doğrula** bağlantısına tıklayın.
4. Görüntülenen yönergeleri izleyerek kimlik bilgilerinizi doğrulayın, akış çalıştırma hatasına dönün ve **Yeniden gönder**’e tıklayın veya dokunun.
   
    Akışın beklendiği şekilde çalışması gerekir.

## <a name="action-configuration"></a>Eylem yapılandırma
Akış eylemlerinin ayarlardan birinin beklendiği şekilde çalışmaması da akışların başarısız olmasına yol açabilir. Böyle bir durumda, hata iletisi **Hatalı istek** veya **Bulunamadı** ifadesini içerir ya da **400** veya **404** hata kodu görüntülenir.

Hata iletisi, hatanın nasıl düzeltileceğini belirtmelidir. **Düzenle** düğmesine tıklamanız veya dokunmanız ve ardından akış tanımındaki sorunu düzeltmeniz gerekir. Güncelleştirilen akışı kaydedin ve sonra **Yeniden gönder**’e tıklayarak veya dokunarak güncel yapılandırmayla yeniden çalıştırmayı deneyin.

## <a name="other-failures"></a>Diğer hatalar
**500** veya **502** hata kodu görüntüleniyorsa hata geçicidir. Akışı yeniden denemek için **Yeniden gönder**’e tıklayın veya dokunun.

Başka bir sorun yaşarsanız, [topluluğumuza danışarak](https://go.microsoft.com/fwlink/?LinkID=787467) aynı sorunla daha önce karşılaşan kullanıcılar olup olmadığını öğrenebilirsiniz.

