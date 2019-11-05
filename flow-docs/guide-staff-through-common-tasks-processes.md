---
title: PowerApps ile süreçler aracılığıyla özel iş mantığı oluşturma | MicrosoftDocs
description: Uygulamanızda kullanabileceğiniz farklı iş mantığı türleri hakkında bilgi edinin
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
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
ms.openlocfilehash: b3072cc5897b8a2ef5a2a92ec3a07a0e31b57898
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545343"
---
# <a name="create-custom-business-logic-through-processes"></a>Süreçler aracılığıyla özel iş mantığı oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Tutarlı iş süreçlerini tanımlama ve zorlama, insanların model temelli uygulamaları kullanmasının başlıca nedenlerinden biridir. Tutarlı işlemler, sistemi kullanan kişilerin kendi işlerine odaklanmasına ve el ile yapılan adımların bir kümesini gerçekleştirmesine yardımcı olmasına yardımcı olur. Süreçler basit veya karmaşık olabilir ve zaman içinde değişebilir.  
  
PowerApps, her biri farklı bir amaçla tasarlanan çeşitli türlerde süreçler içerir:  
  
-   İş süreci akışları  
  
-   Mobil görev akışları  
  
-   sürdürülen  
  
-   Eylem  
  
 İşlemlere benzer şekilde, iş kuralları ve öneriler de oluşturabilirsiniz. Daha fazla bilgi için bkz. [bir formdaki mantığı uygulamak için iş kuralları ve öneriler oluşturma](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
>  İşlemlerin kullanılması PowerApps ve akışlar için lisans gereksinimlerini etkileyebilir. Daha fazla bilgi için bkz. [varlık lisansı gereksinimleri](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>İş süreci akışları ne zaman kullanılır?  
 Personelin aynı aşamada hareket etmek istediğinizde bir iş süreci akışı kullanın ve müşteriyle etkileşime geçmek için aynı adımları izleyin. Örneğin, herkesin müşteri hizmetleri taleplerini aynı şekilde işlemesini istiyorsanız veya bir siparişi göndermeden önce personelin bir faturaya onay sağlamasını gerektirmek için bir iş süreci akışı kullanın.  
  
 Ortamınız, çok az değişiklikle veya hiçbir değişiklik gerekmeden kullanabileceğiniz ortak satış, hizmet ve pazarlama görevlerine yönelik kullanıma yönelik birkaç ücretsiz iş süreci içerir. Veya kendi kendinize de oluşturabilirsiniz. İş süreci akışları hakkında daha fazla bilgi için aşağıdaki konuya bakın:  
  
-   [İş süreci akışı oluşturma](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>İş akışları ne zaman kullanılır?  
 Arka planda iş süreçlerini otomatikleştirmek için iş akışlarını kullanın. İş akışları genellikle sistem olayları tarafından başlatılır, böylece kullanıcının çalıştırdıkları farkında olması gerekmez. Arka planda çalışan iş akışları "zaman uyumsuz" dir. İş akışları, kullanıcıların bunları el ile başlatması için de yapılandırılabilir. bir sipariş sevk edildiğinde müşteriye otomatik olarak onay e-postası göndermek gibi genel görevleri otomatikleştirmek istediğinizde. Gerçek zamanlı olarak çalışan iş akışları "zaman uyumludur." İş akışları hakkında daha fazla bilgi için bkz. [Iş akışı işleme](workflow-processes.md)  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Eylemler ne zaman kullanılır?  
 Sistemde bir dizi komutu otomatikleştirmek istediğinizde eylemleri kullanın. Eylemler, geliştiricilerin iş süreçlerini ifade etmek için kullanılabilir olan sözlüğü genişletir. Sistem tarafından sunulan oluşturma, güncelleştirme, silme ve atama gibi temel yüklemler sayesinde, bir eylem onaylama, Ilerleme, yönlendirme veya zamanlama gibi daha açıklayıcı fiiller oluşturmak için bu temel fiilleri kullanır. Bir iş işleminin tanımı değişirse, geliştirici olmayan birisi eylemi düzenleyerek kodun değiştirilmesine gerek kalmaz.  Eylemler hakkında daha fazla bilgi için bkz. [Eylemler](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-microsoft-flow"></a>Ne zaman kullanılacağı Microsoft Flow  
 Ortamınız ile en sevdiğiniz uygulama veya hizmet arasında (Dynamics 365, Twitter, Dropbox, Google Hizmetleri, Office 365 ve SharePoint gibi) eylemler gerçekleştiren otomatik iş akışları oluşturmanız gerektiğinde Microsoft Flow kullanın. Bir akışı belirli bir eyleme göre tetikleyip uygulamanız içinden Invoke yapabilirsiniz. Daha fazla bilgi: [Hizmetler genelinde işlemleri otomatikleştirmek için Microsoft Flow kullanma](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>İşlem oluşturmak için nereye gidebilirim?  
 İşlemlere gitmek için iki yol vardır:  
  
- [Çözüm Gezgini](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) 'ni açın ve **Bileşenler > işlemlere gidin.** Bu yol, özelleştirme araçlarında başka özelleştirme işleri yaparken kullanışlı erişim sağlar.  

- **Işlem > [ayarları](/powerapps/maker/model-driven-apps/advanced-navigation#settings) .** Bu yol, özel görünümler de dahil olmak üzere, Işlem varlığı için tanımlanan görünümleri kullanmanıza olanak sağlar.  
  
 Bireysel iş süreci akışları, iş süreci akışının etkin olduğu form için Komut çubuğundaki **Işlem Düzenle** düğmesi kullanılarak da düzenlenebilir.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>İşlem kimin tarafından oluşturulabilir?  
 Yalnızca Sistem Yöneticisi, Sistem Özelleştirici veya CEO-Iş Yöneticisi güvenlik rolüne sahip kişiler tüm ortama uygulanan süreçler oluşturabilir. Diğer rollere sahip kişiler, sınırlı erişim düzeyine sahip süreçler oluşturabilir. Örneğin, Kullanıcı erişim düzeyine sahip kişiler sahip oldukları kayıtlarla kendi kullanımları için iş akışları oluşturabilir.  
  
 Aşağıdaki tabloda, varsayılan güvenlik rollerine göre işlem erişim düzeyi gösterilmektedir.  
  
|||  
|-|-|  
|**Güvenlik rolü**|**Erişim düzeyi**|  
|CEO-Iş Yöneticisi|Kuruluşunuzun|  
|Sistem Yöneticisi|Kuruluşunuzun|  
|Sistem Özelleştirici|Kuruluşunuzun|  
|Pazarlama Başkan Yardımcısı|Üst öğe: alt Iş birimleri|  
|Satış Başkan Yardımcısı|Üst öğe: alt Iş birimleri|  
|Service Manager|İş birimi|  
|Pazarlama Yöneticisi|İş birimi|  
|Satış Yöneticisi|İş birimi|  
|Zamanlama Yöneticisi|İş birimi|  
|Müşteri hizmetleri temsilcisi|Kullanıcısını|  
|Pazarlama uzmanı|Kullanıcısını|  
|İsiyseniz|Kullanıcısını|  
|leyiciyi|Kullanıcısını|  
  
> [!NOTE]
>  İnsanlar iş süreci akışı, gerçek zamanlı iş akışı veya eylem işlemleri oluşturabiliyor olsa da, bunları etkinleştirmek için **Iş sürecini etkinleştir** veya **gerçek zamanlı işlemleri etkinleştir** ayrıcalıklarına sahip olmaları gerekir.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>İş akışları ve eylemler hakkında daha fazla bilgi  
 İşlemler koşulları denetleyebilir, dallanma mantığını uygulayabilir ve eylemler gerçekleştirebilir. Bu eylemleri bir dizi adımda gerçekleştirirler. Aşağıdaki tabloda iş akışı ve eylem işlemlerinde kullanılabilen adımlar açıklanmaktadır. Daha fazla ayrıntı için her işlem türü için konulara bakın.  
  
|Indan|İşlem türü|Açıklaması|  
|----------|------------------|-----------------|  
|**Aşama**|İş akışı, eylem|Aşamalar, iş akışı mantığını daha kolay okunabilir hale getirir ve iş akışı mantığını açıklar. Ancak aşamalar, iş akışlarının mantığını veya davranışını etkilemez. Bir işlemde aşamalar varsa, işlemdeki tüm adımların bir aşama ile bulunması gerekir.|  
|**Koşulu denetle**|İş akışı, eylem|Mantıksal bir "if-\<koşulu > then" deyimidir.<br /><br /> İş akışının üzerinde çalıştığı kaydın değerlerini, bir N:1 ilişkisinde bu kayıtla bağlantılı kayıtlardan herhangi birini veya önceki adımlarla oluşturulmuş kayıtları kontrol edebilirsiniz. Bu değerlere bağlı olarak, koşul `true`ek adımlar tanımlayabilirsiniz.|  
|**Koşullu dal**|İş akışı, eylem|"Else-if-then" ifadesinde, düzenleyici "Aksi takdirde, \<koşulu >"<br /><br /> Daha önce tanımladığınız bir denetim koşulunu seçin ve denetim koşulu `false`döndürdüğünde ek adımlar tanımlamak için bir koşullu dal ekleyebilirsiniz.|  
|**Varsayılan eylem**|İş akışı, eylem|Mantıksal bir "Else" deyimidir. Düzenleyici "Aksi takdirde:" metnini kullanır<br /><br /> Daha önce tanımladığınız bir denetim koşulu, koşullu dal, bekleme koşulu veya paralel bekleme dalı seçin ve koşul veya dal öğelerinde tanımlanan ölçütlerle eşleşmeyen tüm durumlar için adımları tanımlamak üzere varsayılan bir eylem kullanabilirsiniz.|  
|**Bekleme koşulu**|Yalnızca arka plan Iş akışı|Koşul tarafından tanımlanan kriterler karşılanana kadar arka plan iş akışının kendisini duraklatmasını sağlar. Bekleme koşulunda ölçüt karşılandığında iş akışı otomatik olarak yeniden başlar.|  
|**Paralel bekleme dalı**|Yalnızca arka plan Iş akışı|Yalnızca ilk ölçüt karşılandığında gerçekleştirilen ilgili ek adımlar kümesine sahip bir arka plan iş akışı için alternatif bir bekleme koşulu tanımlar. İş akışı mantığınızdaki zaman sınırlarını oluşturmak için paralel bekleme dallarını kullanabilirsiniz. Bir bekleme koşulunda tanımlanan kriterler karşılanana kadar, iş akışının süresiz olarak beklemesini önlemeye yardımcı olurlar.|  
|**Değer ata**|Ön|İşlemdeki bir değişkene veya çıkış parametresine bir değer ayarlar.|  
|**Kayıt oluştur**|İş akışı, eylem|Bir varlık için yeni bir kayıt oluşturur ve öznitelikleri değerlere atar.|  
|**Kaydı güncelleştir**|İş akışı, eylem|İş akışının üzerinde çalıştığı kaydı, bir N:1 ilişkisinde bu kayıtla bağlantılı kayıtları veya önceki adımlarla oluşturulmuş kayıtları güncelleştirebilirsiniz.|  
|**Kayıt ata**|İş akışı, eylem|İş akışının üzerinde çalıştığı kaydı, bir N:1 ilişkisi ile ilgili kayda bağlı kayıtlardan herhangi birini veya önceki adımlarla oluşturulmuş kayıtları atayabilirsiniz.|  
|**E-posta gönder**|İş akışı, eylem|Bir e-posta gönderir. Yeni bir e-posta iletisi oluşturmayı veya iş akışının üzerinde çalıştığı kaydın varlığı için yapılandırılmış bir e-posta şablonunu ya da varlıkla bir N:1 ilişkisine sahip olan herhangi bir varlık ya da önceki adımlarla oluşturulan tüm kayıtlar için varlığı kullanmayı seçebilirsiniz.|  
|**Alt Iş akışını Başlat**|İş akışı, eylem|Alt iş akışı olarak yapılandırılmış bir iş akışı işlemini başlatır.|  
|**Değişiklik durumu**|İş akışı, eylem|İşlemin üzerinde çalıştığı kaydın durumunu, bir N:1 ilişkisiyle ilgili kayıtla bağlantılı kayıtlardan herhangi birini veya önceki adımlarla oluşturulmuş kayıtları değiştirir.|  
|**Iş akışını durdur**|İş akışı, eylem|Geçerli iş akışını veya eylemi sonlandırır. **Başarılı** ya da **iptal edildi** durumunu ayarlayabilir ve bir durum iletisi belirtebilirsiniz.|  
|**Özel adım**|İş akışı, eylem|Varsayılan olarak kullanılabilen mantıksal öğelere uzantılar sağlar. Adımlar koşulları, eylemleri, diğer adımları veya bu öğelerin birleşimini içerebilir. Geliştiriciler, özel iş akışı adımları oluşturabilir. Varsayılan olarak, kullanılabilir özel bir adım yoktur.|

  

