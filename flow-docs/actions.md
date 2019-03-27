---
title: Eylem kullanma | MicrosoftDocs
description: Eylemler ile; Oluşturma, Güncelleştirme, Silme, Atama veya Eylem Gerçekleştirme gibi işlemleri uygulayabilirsiniz. İçsel olarak bir eylem özel bir ileti oluşturur
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cf5c0e488f1d01c514f509b9d2a8afae265cf487
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58352884"
---
# <a name="use-actions"></a>Eylemler kullanma

Eylemler, iş mantığı kurmak için bir dizi olanak sunar. Eylemler ile; Oluşturma, Güncelleştirme, Silme, Atama veya Eylem Gerçekleştirme gibi işlemleri uygulayabilirsiniz. İçsel olarak bir eylem özel bir ileti oluşturur. Geliştiriciler bu eylemleri "ileti" olarak adlandırır. Bu iletilerin her biri bir varlık kaydı üzerinde gerçekleştirilen eylemleri temel alır. Bir işlemin amacı bir kayıt oluşturmak, sonra bu kaydı güncelleştirmek ve daha sonra da atamak ise, bu, üç ayrı adımdan oluşur. Her adım zorunlu olarak iş süreçlerinizle değil varlığın yapabilecekleriyle tanımlanır.  
  
Eylemler, işletmeniz için yapmanız gereken bir işlemle eşleşen tek bir fiil (yani ileti) tanımlama olanağı sunar. Bu yeni iletiler, bir varlıkla yapılabilecek şeylerden çok bir süreç veya davranış tarafından yönlendirilir. Bu iletiler Yükselt, Dönüştür, Zamanla, Yönlendir veya Onayla veya ihtiyacınız olan başka bir şey gibi fiillere karşılık gelir. Bu fiillerin eklenmesi, işletme süreçlerinizi akıcı bir şekilde tanımlamanız için daha zengin bir kavram dağarcığı sunmaya yardımcı olur. Bu daha zengin kavram dağarcığını, eylemi istemciler içinde yazmak zorunda kalmak yerine istemcilerden veya tümleştirmelerden uygulayabilirsiniz. Bu, tüm eylemin tek bir birimdeki başarısını ya da başarısızlığını yönetip günlüğe kaydedebileceğiniz için kolaylık sağlar.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Yapılandırılabilir iletiler  
 Bir eylem bir kez tanımlanıp etkinleştirildikten sonra bir geliştirici bu iletiyi platformun sunduğu diğer iletiler gibi kullanabilir. Burada önemli bir fark, artık geliştirici olmayan birisinin de bir ileti kullanılırken yapılması gerekenlerde değişiklik yapabilmesidir. İşletme süreciniz değiştikçe eylemi adımları değiştirmek üzere yapılandırabilirsiniz. Süreç bağımsız değişkenleri değişmediği sürece iletiyi kullanan herhangi bir özel kodda değişiklik yapılması gerekmez.  
  
 İş akışı süreçleri ve eklentiler de otomasyon tanımlamak için benzer olanaklar sunmaya devam eder. İş akışı süreçleri hala geliştirici olmayan birisinin de değişiklik yapabilmesi olanağını sunmaktadır. Ancak buradaki fark, işletme süreçlerinin nasıl birleştirildiği ve bir geliştiricinin kodunu nasıl yazabileceğidir. Bir eylem, platform tarafından sunulan herhangi bir ileti ile aynı düzeyde işlem gören bir iletidir. Geliştiriciler Eylemler için eklentiler kaydedebilir.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Genel iletiler 
 
 Bir eylem, Common Data Service iş akışlarından ya da [eklentilerden](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in) farklı olarak belirli bir varlıkla ilişkilendirilmek zorunda değildir. Kendi başlarına çağrılabilen "genel" eylemler tanımlayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[Özel eylem oluşturma](create-actions.md)  
  

