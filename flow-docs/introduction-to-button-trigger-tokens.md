---
title: Düğme tetikleyici belirteçlerine giriş | Microsoft Docs
description: Microsoft düğme akışları için düğme tetikleyici belirteçlerine giriş.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/12/2016
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1b439a972393f800ea550480b883945664e17e53
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547474"
---
# <a name="get-started-with-button-trigger-tokens"></a>Düğme tetikleyici belirteçleriyle çalışmaya başlama
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-trigger-tokens"></a>Düğme tetikleyici belirteçleri nedir?
Düğme tetikleyici belirteçleri, bir [düğme akışının](introduction-to-button-flows.md) çalıştığı cihaz tarafından bilinen ve kullanılabilir olan veri noktalardır. Bu belirteçler, belirli bir anda cihazın geçerli saati veya coğrafi konumu gibi etkenlere bağlı olarak değişir.  

Örneğin, akıllı telefonda bir düğme akışı çalıştırıyorsanız, telefonun geçerli konumunuzdaki saati, tarihi ve geçerli adresinizi **biliyor** olması olasıdır. Bu bağlamda, telefonun bulunduğu saat, tarih ve adres, düğme akışının çalıştırıldığı zamanda belirlenir. Bunlar, cihazda yürütülen herhangi bir düğme akışı için otomatik olarak kullanılabilir. Bu tetikleyici belirteçlerini, konumunuzu bir kişiye sağlamak ya da belirli bir iş/hizmet çağrısında ne kadar zaman harcadığınızı izlemek gibi yinelenen görevleri en aza indirecek yararlı akışlar oluşturmak için kullanabilirsiniz.

### <a name="list-of-button-trigger-tokens"></a>Düğme tetikleyici belirteçlerinin listesi
Düğme akışlarınızı oluştururken kullanabileceğiniz düğme tetikleyici belirteçlerinin listesi aşağıda verilmiştir.

| parametresinin | Açıklaması |
| --- | --- |
| Baş |Akışı çalıştıran cihazın bulunduğu şehir. |
| Ülke/bölge |Akışı çalıştıran cihazın bulunduğu ülke/bölge. |
| Tam adres |Akışı çalıştıran cihazın bulunduğu tam adres. |
| En |Akışı çalıştıran cihazın bulunduğu enlem. |
| MIN |Akışı çalıştıran cihazın bulunduğu boylam. |
| PostalCode |Akışı çalıştıran cihazın bulunduğu posta kodu. |
| Durumunda |Akışı çalıştıran cihazın bulunduğu durum. |
| Caddesi |Akışı çalıştıran cihazın bulunduğu cadde. |
| ilişkin |Akışı çalıştıran cihazın bulunduğu alanda geçen süre. |
| Güncel |Akışı çalıştıran cihazın bulunduğu alandaki tarih. |
| Kullanıcı adı |Akışı çalıştıran cihazda oturum açan kişinin Kullanıcı adı. |
| Kullanıcı e-postası |Akışı çalıştıran cihazda oturum açan kişinin e-posta adresi. |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>Tetikleyici belirteçleri kullanan bir düğme akışı oluşturma
Bir düğme oluşturduğunuzda, düğmenize zengin işlevsellik eklemek için tetikleyici belirteçlerini kullanabilirsiniz.

Bu kılavuzda, Android cihazında bir düğme akışı oluşturacağız. Düğme akışı, tarihi ve tam adresinizi "**evden çalışma**" e-postası olarak patronuma göndermek için tetikleyici belirteçlerini kullanır.

Bu kılavuzda, bir Android cihazından ekran görüntülerini görürsünüz, ancak bu deneyim iOS ve Windows Phone cihazlarında de benzerdir.

### <a name="prerequisites"></a>Kaynakları
* Microsoft Flow erişimi olan bir iş veya okul e-posta adresi veya [Microsoft hesabı](https://account.microsoft.com/about?refd=www.microsoft.com) .
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows)için mobil uygulama Microsoft Flow.

Haydi başlayalım:

1. Akışı başlatın ve  **görüntüle** ' yi seçin  
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/1.png)  
2. **Düğme** kategorisi altındaki **yönetici hizmetinize ' Bugün evden çalışma ' e-postası gönder '** i seçin   
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/2.png)  
3. **Bu şablonu kullan** ' ı seçin  
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/3.png)  
4. **E-posta gönder** kartında **Düzenle** ' yi seçin  
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/3-5.png)  
5. **Konu** metin kutusuna dokunun ve "WFH" metinden sonra metin kutusuna " **bugün-** " yazın. Metin kutusuna dokunduktan sonra bir parametre/belirteç listesinin de açıldığını unutmayın. Bir sonraki adımda bu belirteçlerden birini, tarihi e-postanın konusuna eklemek için kullanacağız.  
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/4.png)  
6. İmleç hala konu metin kutusunda, **el ile** parametre listesine kaydırın ve **Tarih**' e dokunun. Date parametresinin şimdi **Konu** metin kutusunda olduğunu fark edin:  
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/6.png)  
7. **Gövde** metin kutusuna ilerleyin ve varsayılan iletiden sonra, ek belirteçlerin dahil edilmesini sağlamak için dokunun.  
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/7.png)  
8. **Tam adres** parametresine dokunun, ardından **Oluştur** ' a dokunun.  
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/8.png)  
9. **Bitti**' ye dokunun. Düğme akışınız artık oluşturuldu.  
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/9.png)  

## <a name="run-the-button-flow"></a>Düğme akışını çalıştırma
**Note**: Bu düğme akışı, geçerli konumunuzu e-posta ile gönderir.  

1. Ekranın alt kısmındaki **düğmeler** kategorisine dokunun. Kullanma izninizin olduğu düğmelerin listesini görürsünüz. Yeni oluşturduğunuz düğme akışını temsil eden düğmeye dokunun:  
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/10.png)  
2. Düğme akışının cihazınızın konum bilgilerine erişmesi için Tamam olduğunu göstermek için **Izin ver** ' e dokunun:  
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/11.png)  
3. Birkaç dakika içinde, e-postanın patronuma gönderildiğine dikkat edin:  
   ![düğme tetikleyici belirteci](./media/introduction-to-button-trigger-tokens/12.png)  

Tebrikler, hem tarih hem de tam adres tetikleyici belirteçleri kullanan bir düğme akışı oluşturdunuz. 

## <a name="next-steps"></a>Sonraki adımlar
* [Düğme akışlarını paylaşma](share-buttons.md)
* [Düğme akışları hakkında bilgi edinin](introduction-to-button-flows.md)
