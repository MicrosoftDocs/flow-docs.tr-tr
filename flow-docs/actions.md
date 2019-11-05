---
title: Eylemleri kullanma | MicrosoftDocs
description: Eylemlerle, oluşturma, güncelleştirme, silme, atama veya eylem gerçekleştirme gibi işlemleri gerçekleştirebilirsiniz. Dahili olarak, bir eylem özel bir ileti oluşturur
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: eb4fa4040611241dd2bd81706736738ad6774d38
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544596"
---
# <a name="use-actions"></a>Kullanım eylemleri
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Eylemler, iş mantığı oluşturmaya yönelik bir dizi olasılık açar. Eylemlerle, oluşturma, güncelleştirme, silme, atama veya eylem gerçekleştirme gibi işlemleri gerçekleştirebilirsiniz. Dahili olarak, bir eylem özel bir ileti oluşturur. Geliştiriciler bu eylemlere "iletiler" olarak başvurur. Bu mesajların her biri, bir varlık kaydında gerçekleştirilen eylemlere dayalıdır. Bir işlemin hedefi bir kayıt oluşturmak, sonra güncelleştirmek ve sonra atamak ise, üç ayrı adım vardır. Her adım, iş sürecinizi değil, varlığın özelliklerine göre tanımlanır.  
  
Eylemler, işiniz için gerçekleştirmeniz gereken bir işlemle eşleşen tek bir fiil (veya ileti) tanımlama olanağı sağlar. Bu yeni iletiler, bir varlıkla yapılabilecekleri yerine bir işlem veya davranışla çalıştırılır. Bu iletiler, ihtiyacınız olan her şey, Ilerleme, dönüştürme, zamanlama, yönlendirme veya onaylama gibi fiillere karşılık gelir. Bu fiillerin eklenmesi, iş süreçlerinizi akıcı bir şekilde tanımlayabilmeniz için daha zengin bir sözlük sağlanmasına yardımcı olur. Bu daha zengin bir sözlüğü, işlemleri istemcilere yazmak zorunda kalmadan, istemcilerden veya tümleştirmelerle uygulayabilirsiniz. Bu Ayrıca, tüm eylemin başarısını veya başarısızlığını tek bir birim olarak yönetip günlüğe kaydetmek için de daha kolay hale gelir.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Yapılandırılabilir iletiler  
 Bir eylem tanımlandıktan ve etkinleştirildikten sonra, geliştirici bu iletiyi platform tarafından sunulan diğer iletilerden herhangi biri gibi kullanabilir. Bununla birlikte, önemli bir farklılık, artık geliştirici olmayan birisinin, bu ileti kullanıldığında yapılması gereken değişiklikleri uygulayabilidir. İş işlemleriniz değiştikçe adımları değiştirmek için eylemi yapılandırabilirsiniz. Bu iletiyi kullanan özel kodların, işlem bağımsız değişkenleri değişmedikçe değiştirilmesi gerekmez.  
  
 İş akışı işlemleri ve eklentiler, Otomasyonu tanımlamaya yönelik benzer yetenekler sağlamaya devam eder. İş akışı işlemi, geliştirici olmayan değişikliklerin uygulanması için hala yetenek sağlar. Ancak fark, iş işlemlerinin nasıl oluşturulduğu ve bir geliştiricinin kendi kodlarını nasıl yazacağı ile aynıdır. Eylem, platformun sunduğu iletilerle aynı düzeyde çalışan bir iletidir. Geliştiriciler, eylemler için eklentileri kaydedebilir.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Genel iletiler 
 
 Common Data Service iş akışlarının veya [eklentilerin](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in)aksine, bir eylemin belirli bir varlıkla ilişkilendirilmesi gerekmez. Kendi kendilerine çağrılabilecek "genel" eylemleri tanımlayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[Özel eylem oluşturma](create-actions.md)  
  

