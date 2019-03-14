---
title: PowerApps ile işlemler aracılığıyla özel iş mantığı oluşturma | MicrosoftDocs
description: Uygulamanızda kullanabileceğiniz farklı iş mantığı türleri hakkında bilgi edinin
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5e123fa2abc8955d90fad2c9b09da76e449bf4b1
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462959"
---
# <a name="create-custom-business-logic-through-processes"></a>İşlemler aracılığıyla özel iş mantığı oluşturma

Kişilerin model tabanlı uygulamaları kullanmasının asıl nedenlerinden biri, tutarlı iş süreçleri tanımlamak ve uygulamaktır. Tutarlı işlemler, sistemi kullanan kişilerin kendisinin gerçekleştireceği bir dizi adımı hatırlamak yerine işlerine odaklanabildiklerinden emin olunmasını sağlar. İşlemler basit veya karmaşık olabilir ve zaman içinde değişebilir.  
  
PowerApps, her biri farklı bir amaç için tasarlanmış olan birçok işlem türünü içerir:  
  
-   İş süreci akışları  
  
-   Mobil görev akışları  
  
-   İş Akışları  
  
-   Eylemler  
  
 İşlemlere benzer şekilde, iş kuralları ve öneriler de oluşturabilirsiniz. Daha fazla bilgi için bkz. [Bir forma mantık uygulamak için iş kuralları ve öneriler oluşturma](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
>  İşlemlerin kullanılması, PowerApps ve akışlar için lisans gereksinimlerini etkileyebilir. Daha fazla bilgi için bkz. [Varlık lisansı gereksinimleri](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>İş süreci akışları ne zaman kullanılır?  
 Personelinizin aynı aşamalar boyunca hareket etmesini ve bir müşteriyle etkileşim kurmak için aynı adımları izlemesini istediğinizde bir iş süreci akışı kullanın. Örneğin, herkesin müşteri hizmetleri isteklerini aynı şekilde ele almasını veya personelin bir siparişi göndermeden önce fatura için onay almasını zorunlu tutmak istiyorsanız bir iş süreci akışı kullanın.  
  
 Ortamınız, çok az değişiklikle veya hiç değişiklik olmadan kullanabileceğiniz genel satış, hizmet ve pazarlama görevleri için kullanıma hazır birçok iş süreci akışı içerir. Veya kendiniz de oluşturabilirsiniz. İş süreci akışları hakkında daha fazla bilgi için aşağıdaki konuya bakın:  
  
-   [İş süreci akışı oluşturma](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>İş akışları ne zaman kullanılır?  
 Arka planda iş süreçlerini otomatikleştirmek için iş akışlarını kullanın. İş akışları genellikle sistem olayları tarafından başlatılır, bu nedenle kullanıcının söz konusu iş akışlarının ne zaman çalışıyor olduğunu bilmesi gerekmez. Arka planda çalışan iş akışları "zaman uyumsuzdur". İş akışları, bu iş akışlarını kendisi başlatan kişiler için de yapılandırılabilir. Bir sipariş sevk edildiğinde otomatik olarak müşteriye onay e-postası gönderme gibi genel görevleri otomatikleştirmek istediğinizde. Gerçek zamanlı olarak çalışan iş akışları "zaman uyumludur". İş akışları hakkında daha fazla bilgi için bkz. [İş akışı işlemleri](workflow-processes.md)  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Eylemler ne zaman kullanılır?  
 Sistemde bir dizi komutu otomatikleştirmek istediğinizde Eylemleri kullanın. Eylemler, geliştiricilerin iş süreçlerini ifade etmek için kullandığı sözlüğü genişletir. Sistem tarafından sağlanan Oluştur, Güncelleştir, Sil ve Ata gibi temel fiillerle Eylem; Onayla, İlerlet, Yönlendir veya Zamanla gibi daha ifadesel fiiller oluşturmak için bu temel filleri kullanır. Bir iş sürecinin tanımı değişirse, geliştirici olmayan birisi Eylemi düzenleyebilir ve böylece kodun değiştirilmesi gerekmez.  Eylemler hakkında daha fazla bilgi için bkz. [Eylemler](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-microsoft-flow"></a>Microsoft Flow ne zaman kullanılır?  
 Ortamınız ve Dynamics 365, Twitter, Dropbox, Google hizmetleri, Office 365 ve SharePoint gibi sık kullandığınız uygulama veya hizmet arasında eylemler gerçekleştiren otomatik iş akışları oluşturmanız gerektiğinde Microsoft Flow’u kullanın. Belirli bir eyleme göre bir akış tetikleyebilir veya uygulamanızın içinden çağırabilirsiniz. Daha fazla bilgi: [Hizmetler genelinde işlemleri otomatikleştirmek için Microsoft Flow’u kullanma](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>İşlemler oluşturmak için nereye gitmeliyim?  
 İşlemlere gitmenin iki yolu vardır:  
  
- [Çözüm gezgini](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer)’ni açın ve **Bileşenler > İşlemler** bölümüne gidin. Bu yol, özelleştirme araçlarında başka özelleştirme çalışmaları yaparken rahat erişim sağlar.  

- **[Ayarlar](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > İşlemler.** Bu yol, özel görünümler de dahil olmak üzere İşlem varlığı için tanımlanan görünümleri kullanmanıza olanak sağlar.  
  
 İş süreci akışının etkin olduğu form için komut çubuğunda **İşlemi Düzenle** düğmesi kullanılarak da tek tek iş süreci akışları düzenlenebilir.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Kimler işlem oluşturabilir?  
 Yalnızca Sistem Yöneticisi, Sistem Özelleştirici ve CEO-İşletme Yöneticisi güvenlik rolüne sahip kişiler, tüm ortam için geçerli olan işlemler oluşturabilir. Başka rollere sahip kişiler, sınırlı erişim düzeyi ile işlemler oluşturabilir. Örneğin, Kullanıcı erişim düzeyine sahip kişiler, sahibi oldukları kayıtlarla kendi kullanımları için iş akışları oluşturabilir.  
  
 Aşağıdaki tabloda, varsayılan güvenlik rollerine göre işlemlerin erişim düzeyi gösterilmektedir.  
  
|||  
|-|-|  
|**Güvenlik rolü**|**Erişim düzeyi**|  
|CEO-İşletme Yöneticisi|Kuruluş|  
|Sistem Yöneticisi|Kuruluş|  
|Sistem Özelleştirici|Kuruluş|  
|Pazarlamadan Sorumlu Başkan Yardımcısı|Üst Öğe: Alt Departmanlar|  
|Satıştan Sorumlu Başkan Yardımcısı|Üst Öğe: Alt Departmanlar|  
|Service Manager|Departman|  
|Pazarlama Yöneticisi|Departman|  
|Satış Yöneticisi|Departman|  
|Zamanlama Yöneticisi|Departman|  
|Müşteri Hizmetleri Temsilcisi|Kullanıcı|  
|Pazarlama Uzmanı|Kullanıcı|  
|Satış Temsilcisi|Kullanıcı|  
|Zamanlayıcı|Kullanıcı|  
  
> [!NOTE]
>  Kullanıcılar, iş süreci akışı, gerçek zamanlı iş akışı veya eylem süreçleri oluşturabilse de, bunları etkinleştirmek için **İş Süreci Akışlarını Etkinleştir** veya **Gerçek Zamanlı İşlemleri Etkinleştir** ayrıcalıklarına sahip olması gerekir.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>İş akışları ve Eylemler hakkında daha fazla bilgi  
 İşlemler, koşulları denetleyebilir, dallanma mantığı uygulayabilir ve eylemler gerçekleştirebilir. Bir dizi adımda bu eylemleri gerçekleştirir. Aşağıdaki tabloda, eylem süreçleri ve iş akışındaki kullanılabilir adımlar açıklanmaktadır. Daha fazla ayrıntı için her bir işlem türüne ilişkin konulara bakın.  
  
|Adım|İşlem türü|Açıklama|  
|----------|------------------|-----------------|  
|**Aşama**|İş Akışı, Eylem|Aşamalar, iş akışı mantığının okunmasını kolaylaştırır ve iş akışı mantığını açıklar. Ancak aşamalar, iş akışlarının mantığını veya davranışını etkilemez. Bir işlemin aşamaları varsa, işlemdeki tüm adımlar bir aşamada yer almalıdır.|  
|**Denetim Koşulu**|İş Akışı, Eylem|Mantıksal bir "if-\<condition> then" deyimi.<br /><br /> İş akışının çalışmakta olduğu kayıt, N:1 ilişkisinde bu kayıtla bağlantılı herhangi bir kayıt veya önceki adımlar tarafından oluşturulan tüm kayıtlar için değerleri denetleyebilirsiniz. Bu değerlere göre, koşul `true` olduğunda ek adımlar tanımlayabilirsiniz.|  
|**Koşullu Dal**|İş Akışı, Eylem|Mantıksal bir "else-if-then" deyimi, düzenleyici, “Otherwise, if \<condition> then:” metnini kullanır.<br /><br /> Önceden tanımladığınız bir denetim koşulu seçin; böylece denetim koşulu `false` değerini döndürdüğünde ek adımlar tanımlamak için bir koşullu dal ekleyebilirsiniz.|  
|**Varsayılan Eylem**|İş Akışı, Eylem|Mantıksal bir "else" deyimi. düzenleyici “Otherwise:” metnini kullanır.<br /><br /> Önceden tanımladığınız bir denetim koşulu, koşullu dal, bekleme koşulu veya paralel bekleme dalı seçin; böylece koşul veya dal öğelerinde tanımlanan ölçütlerle eşleşmeyen tüm durumlara yönelik adımlar tanımlamak için varsayılan bir eylem kullanabilirsiniz.|  
|**Bekleme Koşulu**|Yalnızca Arka Plan İş Akışı|Arka plan iş akışının, koşul tarafından tanımlanan ölçütler yerine getirilinceye kadar kendisini duraklatmasını sağlar. Bekleme koşulundaki ölçütler karşılandığında iş akışı otomatik olarak yeniden başlar.|  
|**Paralel Bekleme Dalı**|Yalnızca Arka Plan İş Akışı|Yalnızca ilk ölçüt karşılandığında gerçekleştirilen ilgili bir dizi ek adım ile bir arka plan iş akışı için alternatif bir bekleme koşulu tanımlar. İş akışı mantığınızda zaman sınırları oluşturmak için paralel bekleme dalları kullanabilirsiniz. Bunlar, iş akışının bir bekleme koşulunda tanımlanan ölçütler karşılanıncaya kadar süresiz olarak beklemesinin engellenmesine yardımcı olur.|  
|**Değer Ata**|Eylem|İşlemde bir değişkene veya çıkış parametresine bir değer ayarlar.|  
|**Kayıt Oluştur**|İş Akışı, Eylem|Bir varlık için yeni bir kayıt oluşturur ve özniteliklere değerler atar.|  
|**Kaydı Güncelleştir**|İş Akışı, Eylem|İş akışının çalışmakta olduğu kaydı, N:1 ilişkisinde bu kayıtla bağlantılı herhangi bir kaydı veya önceki adımlar tarafından oluşturulan tüm kayıtları güncelleştirebilirsiniz.|  
|**Kaydı Ata**|İş Akışı, Eylem|İş akışının çalışmakta olduğu kaydı, N:1 ilişkisinde bu kayıtla bağlantılı herhangi bir kaydı veya önceki adımlar tarafından oluşturulan tüm kayıtları atayabilirsiniz.|  
|**E-posta Gönder**|İş Akışı, Eylem|Bir e-posta gönderir. Yeni bir e-posta iletisi oluşturmayı veya iş akışının çalışmakta olduğu kaydın varlığı ya da varlık ile N:1 ilişkisi olan varlıklar veya önceki adımlar tarafından oluşturulan kayıtların varlığı için yapılandırılmış bir e-posta şablonunu kullanmayı seçebilirsiniz.|  
|**Alt İş Akışını Başlat**|İş Akışı, Eylem|Alt iş akışı olarak yapılandırılmış bir iş akışı işlemi başlatır.|  
|**Durumu Değiştir**|İş Akışı, Eylem|İşlemin çalışmakta olduğu kaydın, N:1 ilişkisinde bu kayıtla bağlantılı herhangi bir kaydın veya önceki adımlar tarafından oluşturulan tüm kayıtların durumunu değiştirir.|  
|**İş Akışını Durdur**|İş Akışı, Eylem|Geçerli iş akışını veya eylemi durdurur. **Başarılı Oldu** veya **İptal Edildi** durumunu ayarlayabilir ve bir durum iletisi belirtebilirsiniz.|  
|**Özel Adım**|İş Akışı, Eylem|Varsayılan olarak kullanılabilir mantıksal öğelere yönelik uzantılar sağlar. Adımlar, koşulları, eylemleri, diğer adımları veya bu öğelerin birleşimini içerebilir. Geliştiriciler özel iş akışı adımları oluşturabilir. Varsayılan olarak, kullanılabilir bir özel adım yoktur.|

Geliştiriciler hakkında daha fazla bilgi için [Kullanıcı Etkileşiminde iş süreçlerinizi otomatikleştirme](https://docs.microsoft.com/dynamics365/customer-engagement/developer/automate-business-processes-customer-engagement
) başlıklı Geliştirici Kılavuzu konusuna bakın.
  

