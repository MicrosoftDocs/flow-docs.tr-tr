---
title: PowerApps 'teki iş akışı aşamalarını ve adımlarını yapılandırma | MicrosoftDocs
description: İş akışı adımlarını yapılandırmayı öğrenin
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 0b47dfd5-76db-464f-90c0-c64a0173dcdd
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4239e939f9522b4b3a22e56dfc69275482b017a7
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547063"
---
# <a name="configure-workflow-stages-and-steps"></a>İş akışı aşamalarını ve adımları yapılandırın
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

İş akışları tasarladığınızda, aşamalar ve adımlarda gerçekleştirmek istediğiniz mantığı içeren seçeneğiniz vardır.  
  
 **Verisi**  
 Aşamalar, iş akışı mantığını daha kolay okunabilir hale getirir ve iş akışı mantığını açıklar. Ancak aşamalar, iş akışlarının mantığını veya davranışını etkilemez. Bir işlemde aşamalar varsa, işlemdeki tüm adımlar bir aşama ile birlikte bulunmalıdır.  
  
 **Olanları**  
 Adımlar, iş akışı içindeki bir iş mantığı birimidir. Adımlar koşulları, eylemleri, diğer adımları veya bu öğelerin birleşimini içerebilir.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>İş akışı işlemlerinin gerçekleştirebileceği eylemler  

 İş akışı işlemleri, aşağıdaki tabloda listelenen eylemleri gerçekleştirebilir.  
  
|Ön|Açıklaması|  
|------------|-----------------|  
|**Kayıt oluştur**|Bir varlık için yeni bir kayıt oluşturur ve öznitelikleri seçtiğiniz değerleri atar.|  
|**Kaydı güncelleştir**|İş akışının üzerinde çalıştığı kaydı, bir N:1 ilişkilerde bu kayıtla bağlantılı kayıtlardan herhangi birini veya önceki adımlarla oluşturulan kayıtları güncelleştirebilirsiniz.|  
|**Kayıt ata**|İş akışının üzerinde çalıştığı kaydı, bir N:1 ilişkisi ile ilgili kayda bağlı kayıtlardan herhangi birini veya önceki adımlarla oluşturulmuş kayıtları atayabilirsiniz.|  
|**E-posta gönder**|Bir e-posta gönderir. Yeni bir e-posta iletisi oluşturmayı veya iş akışının üzerinde çalıştığı kaydın varlığı için yapılandırılmış bir e-posta şablonunu ya da varlıkla bir N:1 ilişkisine sahip olan herhangi bir varlık ya da önceki adımlarla oluşturulan tüm kayıtlar için varlığı kullanmayı seçebilirsiniz.|  
|**Alt Iş akışını Başlat**|Alt iş akışı olarak yapılandırılmış bir iş akışı işlemini başlatır.|  
|**Değişiklik durumu**|İşlemin üzerinde çalıştığı kaydın durumunu, bir N:1 ilişkisiyle ilgili kayıtla bağlantılı kayıtlardan herhangi birini veya önceki adımlarla oluşturulmuş kayıtları değiştirir.|  
|**Iş akışını durdur**|Geçerli iş akışını sonlandırır. **Başarılı** ya da **iptal edildi** durumunu ayarlayabilir ve bir durum iletisi belirtebilirsiniz.<br /><br /> Bir olay için gerçek zamanlı iş akışları yapılandırıldığında, durumu iptal edildi olan bir iş akışını durdurmak olay eyleminin tamamlanmasını önler. Daha fazla bilgi için bkz. [gerçek zamanlı iş akışları kullanma](configure-workflow-steps.md#BKMK_SynchronousWorkflows) .|  
|**Özel adım**|Geliştiriciler, eylemleri tanımlayan özel iş akışı adımları oluşturabilir. Varsayılan olarak kullanılabilir özel bir adım yoktur.|  
  
### <a name="setting-record-values"></a>Kayıt değerlerini ayarlama  

 Bir kayıt oluşturduğunuzda kayıt değerlerini ayarlayabilirsiniz. Bir kaydı güncelleştirdiğinizde, değerleri ayarlayabilir, ekleyebilir, arttırıp azaltacak, çarpmanız veya temizleyemezsiniz.  
  
 **Özellikleri ayarla**' yı seçtiğinizde, varlık için varsayılan formu gösteren bir iletişim kutusu açılır.  
  
 İletişim kutusunun alt kısmında, formda bulunmayan ek alanların bir listesini görebilirsiniz.  
  
 Herhangi bir alan için, bir statik değer ayarlayabilirsiniz ve bu, iş akışı tarafından ayarlanır.  
  
 İletişim kutusunun sağ tarafında **Form Yardımcısı** , geçerli kayıt bağlamından dinamik değerler ayarlama veya ekleme olanağı sunar. Bu, varlığa yönelik N:1 (çoktan bire) ilişkilerinden erişilebilen ilgili kayıtlardan değerler içerir.  
  
 **Form Yardımcısı** 'nda bulunan seçenekler, formda seçtiğiniz alana göre değişir. Dinamik bir değer ayarladığınızda, dinamik verilerin nereye ekleneceğini gösteren bir ' başlık ' olarak bilinen sarı bir yer tutucu görürsünüz. Değeri kaldırmak istiyorsanız, yalnızca başlık ' ı seçin ve silin. Metin alanları için statik ve dinamik verilerin bir bileşimini kullanabilirsiniz.  
  
 Dinamik değerlerle, bir alanın veya ilgili varlığın ayarlamak istediğiniz değere sahip olduğunu bilemezsiniz. Gerçekten denemek için bir dizi alan ayarlayabilir ve değeri ayarlayabilir ve yeşil okları kullanarak bunları sırayla sıralayabilirsiniz. İlk alan veri içermiyorsa ikinci alan denenir ve bu şekilde devam eder. Alanların hiçbirinde veri yoksa, kullanılacak varsayılan bir değer belirtebilirsiniz.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>İş akışı eylemleri için koşulları ayarlama  

 Uyguladığınız eylemler genellikle koşullara bağlıdır. İş akışı işlemi, istediğiniz sonuçları almak için koşullar ayarlamak ve dallanma mantığı oluşturmak için çeşitli yollar sağlar. İş akışı işleminin çalıştırıldığı kaydın değerlerini, bir N:1 ilişkisiyle ilgili kayda bağlı kayıtlardan herhangi birini veya işlemin kendisi içindeki değerleri kontrol edebilirsiniz  
  
|Koşul türü|Açıklaması|  
|--------------------|-----------------|  
|**Koşulu denetle**|Mantıksal bir "if-\<koşulu > then" deyimidir.<br /><br /> İş akışının üzerinde çalıştığı kayıt için geçerli değerleri, N:1 ilişkilerde bu kayıtla bağlantılı kayıtlardan herhangi birini veya önceki adımlarla oluşturulmuş kayıtları kontrol edebilirsiniz. Bu değerlere bağlı olarak, koşul doğru olduğunda ek adımlar tanımlayabilirsiniz.<br /><br /> "If-\<Condition > then" ifadesinde, şu işleçleri kullanabilirsiniz: **eşittir**, **eşit değildir**, **veri Içerir** **, altında** **değil**, **veri içermez**. **Note:**  Altında **ve** **altında değil** hiyerarşik işleçlerdir. Bunlar yalnızca tanımlanmış hiyerarşik bir ilişkiye sahip olan varlıklarda kullanılabilir. Hiyerarşik ilişkiye sahip olmayan varlıklarda bu işleçleri kullanmaya çalışıyorsanız, "hiyerarşik bir ilişkiye sahip olmayan bir varlık üzerinde hiyerarşik bir operatör kullanıyorsunuz" hata iletisini görürsünüz. Varlığı hiyerarşik yapın (bir ilişkiyi hiyerarşik olarak işaretleyerek) veya farklı bir işleç kullanın. " Hiyerarşik ilişkiler hakkında daha fazla bilgi için bkz. [hiyerarşik olarak ilgili verileri tanımlama ve sorgulama](/powerapps/maker/common-data-service/define-query-hierarchical-data). Tablo takip eden bir ekran görüntüsü, hiyerarşik işleçler **altında değil** **, öğesini** kullanan iş akışı işleminin tanımına bir örnektir.|  
|**Koşullu dal**|"Else-if-then" ifadesinde, düzenleyici "Aksi takdirde, \<koşulu >"<br /><br /> Daha önce tanımladığınız bir denetim koşulunu seçin ve denetim koşulu false değerini döndürdüğünde ek adımlar tanımlamak için koşullu bir dal ekleyebilirsiniz.|  
|**Varsayılan eylem**|Mantıksal bir "Else" deyimidir. Düzenleyici "Aksi takdirde:" metnini kullanır<br /><br /> Daha önce tanımladığınız bir denetim koşulu, koşullu dal, bekleme koşulu veya paralel bekleme dalı seçin ve koşul veya dal öğelerinde tanımlanan ölçütlerle eşleşmeyen tüm durumlar için adımları tanımlamak üzere varsayılan bir eylem kullanabilirsiniz.|  
|**Bekleme koşulu**|Koşul tarafından tanımlanan kriterler karşılanana kadar arka plan iş akışının kendisini duraklatmasını sağlar. Bekleme koşulunda ölçüt karşılandığında iş akışı otomatik olarak yeniden başlar.<br /><br /> Gerçek zamanlı iş akışları bekleme koşullarını kullanamaz.|  
|**Paralel bekleme dalı**|Yalnızca ilk ölçüt karşılandığında gerçekleştirilen ilgili ek adımlar kümesine sahip bir arka plan iş akışı için alternatif bir bekleme koşulu tanımlar. İş akışı mantığınızdaki zaman sınırlarını oluşturmak için paralel bekleme dallarını kullanabilirsiniz. Bir bekleme koşulunda tanımlanan kriterler karşılanana kadar, iş akışının süresiz olarak beklemesini önlemeye yardımcı olurlar.|  
|**Özel adım**|Geliştiriciler, koşulları tanımlayan özel iş akışı adımları oluşturabilir. Varsayılan olarak kullanılabilir özel bir adım yoktur.|  
  
 Aşağıdaki ekran görüntüsünde, hiyerarşik işleçler **altında değil** , **altında** olan iş akışı işlemi tanımının bir örneği bulunur. Bizim örneğimizde, iki hesap grubuna iki farklı indirim uygulayacağız. **Ekle adımında** **, işleç** **altında değil** işlecini içeren **If-Then** koşulunu belirtmek için **Denetim koşulunu** seçtik. İlk **if-then** koşulu, Alp kayak House hesabı **altındaki** tüm hesaplar için geçerlidir. Bu hesaplar satın alınan iyi ve hizmetlere ilişkin %10 indirim alır. İkinci **if-then** koşulu, Alp kayak House hesabı **altında olmayan** tüm hesaplara uygulanır ve %5 indirim alırlar. Ardından, koşula göre gerçekleştirilecek eylemi tanımlamak için **kaydı güncelleştir** ' i seçtik.  
  
 ![İşleçleri altında değil altında&#47;olan iş akışı işlemi](media/wfp-under-not-under.PNG "İşleci altında/değil, iş akışı işlemi")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Gerçek zamanlı iş akışlarını kullanma  

 Gerçek zamanlı iş akışlarını yapılandırabilirsiniz, ancak bunları dikkatli bir şekilde kullanmanız gerekir. Arka plan iş akışları genellikle önerilir çünkü sunucu üzerindeki kaynaklar kullanılabilir. Bu, sunucunun yapması için sahip olduğu işi düzgünleştirmenize ve sistemi kullanan herkes için en iyi performansı korumanıza yardımcı olur. Dezavantajı, arka plan iş akışları tarafından tanımlanan eylemlerin anında değil. Ne zaman uygulanacağını tahmin edemeyecektir, ancak bu işlem genellikle birkaç dakika sürer. İş süreçlerinin çoğu otomasyonu için, sistemin kullandığı kişilerin işlemin çalıştığını consciously farkında olması gerekmez.  
  
 Bir iş süreci, birisinin işlem sonuçlarını hemen görmesini gerektirdiğinde veya bir işlemi iptal etmek istiyorsanız gerçek zamanlı iş akışları kullanın. Örneğin, bir kayıt için belirli varsayılan değerleri ilk kaydedildiğinde ayarlamak veya bazı kayıtların silinmediğinden emin olmak isteyebilirsiniz.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Gerçek zamanlı ve arka plan iş akışları arasında dönüştürme  

 Araç çubuğundaki **bir arka plan iş akışına dönüştür** ' i seçerek gerçek zamanlı bir iş akışını arka plan iş akışında değiştirebilirsiniz.  
  
 Araç çubuğunda **gerçek zamanlı bir iş akışına dönüştür** ' ü seçerek arka plan iş akışını gerçek zamanlı bir iş akışına değiştirebilirsiniz. Arka plan iş akışı bekleme koşullarını kullanıyorsa, geçersiz hale gelir ve bekleme koşulunu kaldırana kadar etkinleştiremeyeceksiniz.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Durum değişikliklerinden önce veya sonra gerçek zamanlı iş akışları başlatma  

 Gerçek zamanlı iş akışları için **Otomatik işlemlere yönelik seçenekleri** yapılandırdığınızda, durum değişiklikleri olayı için seçenekler, durum değiştiğinde **Başlangıç** **veya daha** **önce** seçmenizi sağlar. Varsayılan seçenek daha **sonra**olur.  
  
 ' İ seçtiğinizde, durumu **değiştirmeden önce iş** akışındaki mantığın uygulanmasını istediğinizi söyleyerek. Bu, işlemden sonra diğer mantığdan önce değerleri denetleyebilme ve daha fazla mantık gerçekleştirilmesini önlemeye olanak sağlar. Örneğin, bir eklenti veya özel iş akışı eyleminde, başka bir sistem üzerinde eylemler başlatabilecek ek mantığa sahip olabilirsiniz. Daha fazla işleme durdurulduğunda, dış sistemlerin etkilenmesinden kaçınabilirsiniz. Bu olaydan önce gerçek zamanlı iş akışları uygulamak, işlem iptal edildiğinde, verileri kaydetmiş olabilecek diğer iş akışı veya eklenti eylemlerinin "geri alındı" olması gerekmediği anlamına da gelir.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Gerçek zamanlı iş akışlarıyla Iş akışını durdur eylemini kullanma  

 Bir iş akışı içinde bir iş **akışını durdur** eylemini uyguladığınızda, **başarılı** veya **iptal**edilebilir bir durum koşulu belirtme seçeneğiniz vardır. Durumu iptal edildi olarak ayarladığınızda, işlemi önleyin. Durdurma eylemi durum iletisindeki metni içeren bir hata iletisi, **Iş süreci hatası**başlığına sahip kullanıcıya görüntülenecektir.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 [İşlemlerle özel iş mantığı oluşturun](guide-staff-through-common-tasks-processes.md)   
 [Iş akışı işlemlerine genel bakış](workflow-processes.md)   
 [İş akışı süreçlerini izleme ve yönetme](monitor-manage-processes.md)   
 [İş akışı işlemleri için en iyi uygulamalar](best-practices-workflow-processes.md)
