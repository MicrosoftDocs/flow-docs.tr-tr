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
ms.date: 05/01/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0e151f3c5cd69fe07263e5fa36d46eb3b8be19f5
ms.sourcegitcommit: edc0f625914b7dc8f0dd7f05e7b9c05346282064
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/02/2019
ms.locfileid: "64992697"
---
# <a name="troubleshooting-a-flow"></a>Bir akışla ilgili sorunları giderme

## <a name="repair-tips-in-email"></a>E-postada onarım ipuçları

Akış başarısız olduğunda onarım ipuçları akış sahiplerine e-postayla gönderilir. Bu onarım ipucu e-postaları bazı hatalarla ilgili belirli, eyleme dönüştürülebilir geri bildirimler içerir. Örneğin, Office 365'te bir kişinin yöneticisini almaya çalışan bir akış oluşturulması ama Azure Active Directory'de (Azure AD) yapılandırılmış bir yönetici olmaması yaygın hatalardan biridir. Bu veya başka bazı koşullar akışınızın başarısız olmasına neden olursa, aşağıdaki gibi bir onarım ipuçları e-postası alırsınız:

![Onarım ipuçları](media/fix-flow-failures/repair-tips-email.png)

Onarım ipuçları e-postasında aşağıdaki bölümler bulunur:

Ad|Açıklama
---|---
Saat|Akışın ilk başarısız olduğu saati görüntüler.
Olanlar|Akışta hataya neden olan sorunun açıklamasını sağlar.
Nasıl düzeltebilirim?|Akışta hataya neden olan sorunu çözmeye yönelik ipuçları sağlar.
Sorun Giderme İpuçları|Akışın kaç kez başarısız olduğu gibi ayrıntılar ve aynı giriş verileriyle akışı yeniden deneme bağlantısı sağlar.

Raporlanan hataları düzeltmek için **Akışımı düzelt**'i seçin ve onarım ipuçları e-postasında verilen adımları izleyin.

Onarım ipuçları e-postaları isteğe bağlıdır. Bunları almak istemiyorsanız, belirli bir akışın özellikler menüsünden bu özelliği kapatmanız yeterli olur.

Akışınız başarısız olursa sorun giderme işlemlerini doğrudan Microsoft Flow'dan da yapabilirsiniz.  Burada birkaç yaygın hata senaryosu ve bunları düzeltme ipuçları verilmiştir.

## <a name="identify-the-error"></a>Hatayı belirleme
Bir akışı düzeltebilmek için önce akışın neden başarısız olduğunu belirlemeniz gerekir. Web portalının üst kısmındaki bildirimler simgesine dokunun veya tıklayın (veya mobil uygulamadaki **Etkinlik** sekmesini açın) ve açılan listeden akışınıza tıklayın veya dokunun.

![Bildirimler](./media/fix-flow-failures/notifications-toolbar.png)

Akışla ilgili ayrıntılara ek olarak, en az bir adımda kırmızı bir ünlem işareti gösterilir. Bu adımı açıp hata iletisini gözden geçirin.

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

## <a name="getting-help-from-support-or-the-community"></a>Destekten veya topluluktan yardım alma

Yardıma ihtiyacınız olduğunda **Kendi Kendine Yardım** seçeneklerimizi kullanabilir veya diğer kişilerden **Yardım isteyebilirsiniz**.

### <a name="self-help"></a>Kendi kendine yardım 

1. [Destek sitesine](https://flow.microsoft.com/support/) gidin.
1. **Kendi Kendine Yardım** kategorisine gidin ve kendi kendine yardım seçeneklerinden birini belirtin.

    ![Yardım isteyin bölümü. Desteğe başvurun.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Diğer kişilerden yardım isteme

1. [Destek sitesine](https://flow.microsoft.com/support/) gidin.
1. **Yardım isteyin** bölümünde **Desteğe Başvurun** seçeneğini belirtin.
    
    ![Yardım isteyin bölümü. Desteğe başvurun.](media/fix-flow-failures/ask-for-help.png)

1. **Sorun türü**, **Kategori** ve **Hangi konuda yardıma ihtiyacınız olduğunu bize bildirin**  alanlarını doldurun ve **Çözümlere bakın**'ı seçin. 

1. **Çözümler** bölümünün siz **Çözümlere bakın**'ı seçtikten sonra görüntülendiğine dikkat edin. Bu bölümde karşılaştığınız sorunun çözümünde size yardımcı olacak bir sonuç listesi yer alır. 

    ![Tümleşik yardımcı ayrıntıları](media/fix-flow-failures/integrated-helper-details.png)

Bir sorunla ilgili yardıma ihtiyacınız varsa, [topluluğumuzdan](https://go.microsoft.com/fwlink/?LinkID=787467) ve Microsoft'tan yardım sağlanır. 

