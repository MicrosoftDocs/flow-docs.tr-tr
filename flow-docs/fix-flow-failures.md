---
title: Akışta sorun giderme | Microsoft Docs
description: Akışların başarısız olmasının en yaygın nedenlerinden bazılarını çözümleyin
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
ms.date: 05/01/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2981c125d722cb766a1cc840f404d84dfa57ac96
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547866"
---
# <a name="troubleshooting-a-flow"></a>Flow sorunlarını giderme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

## <a name="repair-tips-in-email"></a>E-postadaki onarma ipuçları

Bir akış başarısız olduğunda onarım ipuçları, akış sahiplerine e-posta yoluyla gönderilir. Bu onarım ipuçları e-postaları, belirli hatalar hakkında belirli ve eyleme dönüştürülebilir geri bildirimler içerir Örneğin, yaygın olarak karşılaşılan bir hata, Office 365 ' te bir kişinin yöneticisini almayı deneyen bir akış ayarlıyor, ancak Azure Active Directory (Azure AD) içinde yapılandırılmış bir yönetici yok. Bu veya birkaç başka koşul da akışın başarısız olmasına neden olursa aşağıdakine benzer bir onarım ipuçları e-postası alırsınız:

![Onarma ipuçları](media/fix-flow-failures/repair-tips-email.png)

Onarım İpuçları e-postası aşağıdaki bölümleri içerir:

Ada|Açıklaması
---|---
Işınızda|Akışın ilk başarısız olduğu zamanı görüntüler.
Ne oldu|Akıştaki hataya neden olan soruna ilişkin bir açıklama sağlar.
Nasıl yaparım? düzeltilmesi|Akışta hataya neden olan sorunu çözmek için ipuçları sağlar.
Sorun giderme Ipuçları|Akışın kaç kez başarısız olduğunu ve akışı aynı giriş verileriyle yeniden denemek için bir bağlantıyı içeren ayrıntıları sağlar.

Bildirilen hataları gidermek için **akışımı** Onar ' ı seçin ve onarım ipuçları e-postasında adımları izleyin.

Onarma ipuçları e-postaları isteğe bağlıdır. Bunları almak istemiyorsanız, söz konusu akışın Özellikler menüsünden devre dışı bırakın.

Akışınız başarısız olursa, doğrudan Microsoft Flow de sorun giderebilirsiniz.  Yaygın olarak karşılaşılan birkaç hata senaryosu ve bunların nasıl düzeltileceğini gösteren ipuçları aşağıda verilmiştir.

## <a name="identify-the-error"></a>Hatayı tanımla
Bir akışı çözebilmeniz için önce neden başarısız olduğunu belirlemeniz gerekir. Web portalının üst kısmındaki bildirimler simgesine tıklayın veya dokunun (veya mobil uygulamadaki **etkinlik** sekmesini açın) ve ardından görüntülenen listede akışınıza tıklayın veya dokunun.

![bildirimi](./media/fix-flow-failures/notifications-toolbar.png)

Akış hakkındaki ayrıntılar görünür ve en az bir adım kırmızı bir ünlem simgesi gösterir. Bu adımı açın ve hata iletisini gözden geçirin.

![Hata iletisi](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Kimlik doğrulama sorunları
Birçok durumda, akış bir kimlik doğrulama hatası nedeniyle başarısız olur. Bu tür bir hata varsa, hata iletisi **yetkisiz** veya **401** veya **403** hata kodu görüntülenir. Bağlantıyı güncelleştirerek bir kimlik doğrulama hatasını genellikle çözebilirsiniz:

1. Web portalının üst kısmındaki dişli simgesine tıklayarak veya dokunarak **Ayarlar** menüsünü açın ve **Bağlantılar**' a tıklayın veya dokunun.
2. **Yetkisiz** hata iletisini gördüğünüz bağlantıya ilerleyin.
3. Bağlantının yanında, kimlik doğrulamasından geçirilmediğinden, iletideki **Parolayı Doğrula** bağlantısına tıklayın veya dokunun.
4. Görüntülenen yönergeleri izleyerek kimlik bilgilerinizi doğrulayın, akış çalıştırma arızasına geri dönün ve ardından yeniden **Gönder**' e tıklayın veya dokunun.
   
    Akışın artık beklenen şekilde çalışması gerekir.

## <a name="action-configuration"></a>Eylem yapılandırması
Flow eyleminde bir ayar beklendiği gibi çalışmazsa akışlar da başarısız olur. Bu durumda, hata iletisi **Hatalı istek** içeriyor veya **bulunamadı**ya da **400** veya **404** hata kodu görünür.

Hata iletisinde hatanın nasıl düzeltiyapılacağı belirtilmelidir. **Düzenle** düğmesine tıklamanız veya dokunmanız ve ardından akış tanımındaki sorunu düzeltmeniz gerekir. Güncelleştirilmiş akışı kaydedin ve sonra yeniden **Gönder** ' e tıklayarak veya dokunarak güncelleştirilmiş yapılandırmayla tekrar çalıştırmayı deneyin.

## <a name="other-failures"></a>Diğer sorunlar
**500** veya **502** hata kodu görüntülenirse, hata geçicidir veya geçicidir. Akışı yeniden denemek için yeniden **Gönder** ' e tıklayın veya dokunun.

## <a name="getting-help-from-support-or-the-community"></a>Destek veya toplulukla yardım alma

Yardıma ihtiyacınız olduğunda **kendi kendine yardım** seçeneklerimizi kullanabilir veya diğerlerinin **yardımını isteyebilirsiniz** .

### <a name="self-help"></a>Kendi kendine yardım 

1. [Destek sitesine](https://flow.microsoft.com/support/)gidin.
1. **Kendi kendine yardım** kategorisine gidin ve kendi kendine yardım seçeneklerinden birini seçin.

    ![Yardım için sorun bölümüne bakın. Desteğe başvurun.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Başkalarından yardım isteyin

1. [Destek sitesine](https://flow.microsoft.com/support/)gidin.
1. **Yardım Için sor** bölümünde **desteğe başvurun** ' i seçin.
    
    ![Yardım için sorun bölümüne bakın. Desteğe başvurun.](media/fix-flow-failures/ask-for-help.png)

1. **Sorun türünü**, **kategorisini**doldurun ve alanlarla **ilgili yardıma ihtiyacınız olduğunu söyleyin** ve ardından **çözümleri göster**' i seçin. 

1. Çözümleri **göster**' i seçtikten sonra **çözüm** bölümünün görüntülendiğine dikkat edin. Bu, karşılaştığınız sorunu ele almak için kullanabileceğiniz sonuçların bir listesini içerir. 

    ![Tümleşik yardımcı Ayrıntılar](media/fix-flow-failures/integrated-helper-details.png)

Bir sorunla ilgili yardıma ihtiyacınız varsa [Community](https://go.microsoft.com/fwlink/?LinkID=787467) ve Microsoft 'tan yardım sağlanır. 

