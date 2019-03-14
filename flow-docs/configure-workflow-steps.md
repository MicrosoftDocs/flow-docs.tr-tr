---
title: PowerApps’te iş akışı aşamalarını ve adımlarını yapılandırma | MicrosoftDocs
description: İş akışı adımlarının nasıl yapılandırılacağını öğrenin
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
ms.openlocfilehash: 9ebdb1eddaea1f2fd7918c968879f5da37c287fe
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462867"
---
# <a name="configure-workflow-stages-and-steps"></a>İş akışı aşamalarını ve adımlarını yapılandırma

İş akışlarını tasarlarken, aşamalarda ve adımlarda gerçekleştirmek istediğiniz mantığı dahil etme seçeneğiniz vardır.  
  
 **Aşamalar**  
 Aşamalar, iş akışı mantığının okunmasını kolaylaştırır ve iş akışı mantığını açıklar. Ancak aşamalar, iş akışlarının mantığını veya davranışını etkilemez. Bir işlemin aşamaları varsa, işlemdeki tüm adımlar bir aşamada yer almalıdır.  
  
 **Adımlar**  
 Adımlar, bir iş akışındaki iş mantığı birimidir. Adımlar, koşulları, eylemleri, diğer adımları veya bu öğelerin birleşimini içerebilir.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>İş akışı işlemlerinin gerçekleştirebileceği eylemler  

 İş akışı işlemleri, aşağıdaki tabloda listelenen eylemleri gerçekleştirebilir.  
  
|Eylem|Açıklama|  
|------------|-----------------|  
|**Kayıt Oluştur**|Bir varlık için yeni bir kayıt oluşturur ve özniteliklere seçtiğiniz değerleri atar.|  
|**Kaydı Güncelleştir**|İş akışının çalışmakta olduğu kaydı, N:1 ilişkilerinde bu kayıtla bağlantılı herhangi bir kaydı veya önceki adımlar tarafından oluşturulan tüm kayıtları güncelleştirebilirsiniz.|  
|**Kaydı Ata**|İş akışının çalışmakta olduğu kaydı, N:1 ilişkisinde bu kayıtla bağlantılı herhangi bir kaydı veya önceki adımlar tarafından oluşturulan tüm kayıtları atayabilirsiniz.|  
|**E-posta Gönder**|Bir e-posta gönderir. Yeni bir e-posta iletisi oluşturmayı veya iş akışının çalışmakta olduğu kaydın varlığı ya da varlık ile N:1 ilişkisi olan varlıklar veya önceki adımlar tarafından oluşturulan kayıtların varlığı için yapılandırılmış bir e-posta şablonunu kullanmayı seçebilirsiniz.|  
|**Alt İş Akışını Başlat**|Alt iş akışı olarak yapılandırılmış bir iş akışı işlemi başlatır.|  
|**Durumu Değiştir**|İşlemin çalışmakta olduğu kaydın, N:1 ilişkisinde bu kayıtla bağlantılı herhangi bir kaydın veya önceki adımlar tarafından oluşturulan tüm kayıtların durumunu değiştirir.|  
|**İş Akışını Durdur**|Geçerli iş akışını durdurur. **Başarılı Oldu** veya **İptal Edildi** durumunu ayarlayabilir ve bir durum iletisi belirtebilirsiniz.<br /><br /> Bir olay için gerçek zamanlı iş akışları yapılandırıldığında, iptal edildi durumundaki bir iş akışı durdurulduğunda olay eyleminin tamamlanması engellenir. Daha fazla bilgi için bkz. [Gerçek zamanlı iş akışlarını kullanma](configure-workflow-steps.md#BKMK_SynchronousWorkflows).|  
|**Özel Adım**|Geliştiriciler, eylemleri tanımlayan özel iş akışı adımları oluşturabilir. Varsayılan olarak, kullanılabilir bir özel adım yoktur.|  
  
### <a name="setting-record-values"></a>Kayıt değerlerini ayarlama  

 Bir kayıt oluşturduğunuzda, kayıt için değerler ayarlayabilirsiniz. Bir kaydı güncelleştirdiğinizde, değerleri ayarlayabilir, ekleyebilir, artırabilir, azaltabilir, çarpabilir veya temizleyebilirsiniz.  
  
 **Özellikleri Ayarla** seçeneğini belirlediğinizde, size varlık için varsayılan formu gösteren bir iletişim kutusu açılır.  
  
 İletişim kutusunun alt kısmında, formda yer almayan ek alanların bir listesini görebilirsiniz.  
  
 Tüm alanlar için bir statik değer ayarlayabilirsiniz; bu, iş akışı tarafından ayarlanacaktır.  
  
 İletişim kutusunun sağ tarafındaki **Form Yardımcısı**, size geçerli kaydın bağlamından dinamik değerler ayarlama veya ekleme yeteneği sunar. Bu, varlık için N:1 (çok-bir) ilişkilerinden erişilebilen ilgili kayıtlardaki değerleri içerir.  
  
 **Form Yardımcısı**’nda kullanılabilir olan seçenekler, formda seçtiğiniz alana bağlıdır. Bir dinamik değer ayarladığınızda, dinamik verilerin nereye dahil edileceğini gösteren, ‘dinamik veri alanı’ olarak da bilinen sarı bir yer tutucu görürsünüz. Değeri kaldırmak istiyorsanız, tek yapmanız gereken dinamik veri alanını seçip silmektir. Metin alanları için, statik ve dinamik verilerin bileşimini kullanabilirsiniz.  
  
 Dinamik değerler olduğunda, bir alanın veya ilgili varlığın ayarlamak istediğiniz değeri içerdiğinden emin olamazsınız. Aslında denemelik birkaç alan ayarlayabilir ve değeri ayarlayıp yeşil okları kullanarak bunları sıralayabilirsiniz. İlk alan veri içermiyorsa ikinci alan denenir ve bu şekilde devam eder. Alanlardan herhangi bir veri içermiyorsa, kullanılacak varsayılan bir değer belirtebilirsiniz.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>İş akışı eylemleri için koşulları ayarlama  

 Uygulayacağınız eylemler çoğu zaman koşullara bağlıdır. İş akışı işlemleri, koşulları ayarlamanın ve istediğiniz sonuçları almak için dallanma mantığı oluşturmanın birçok yolunu sağlar. İş akışı işleminin çalıştırıldığı kaydın, N:1 ilişkisi olan bu kayıtla bağlantı herhangi bir kaydın değerlerini veya işlemin içindeki değerleri denetleyebilirsiniz  
  
|Koşul Türü|Açıklama|  
|--------------------|-----------------|  
|**Denetim Koşulu**|Mantıksal bir "if-\<condition> then" deyimi.<br /><br /> İş akışının çalışmakta olduğu kayıt, N:1 ilişkilerinde bu kayıtla bağlantılı herhangi bir kayıt veya önceki adımlar tarafından oluşturulan tüm kayıtlar için geçerli değerleri denetleyebilirsiniz. Bu değerlere göre, koşul true olduğunda ek adımlar tanımlayabilirsiniz.<br /><br /> "if-\<condition> then" deyiminde aşağıdaki işleçleri kullanabilirsiniz: **Eşittir**, **Eşit Değildir**, **Veri İçerir**, **Veri İçermez**, **Altındadır** ve **Altında Değildir**. **Not:**  **Altındadır** ve **Altında Değildir**, hiyerarşik işleçlerdir. Yalnızca bir hiyerarşik ilişki tanımlanmış olan varlıklarda kullanılabilir. Tanımlı hiyerarşik ilişkisi olmayan varlıklarda bu işleçleri kullanmayı denerseniz şu hata iletisini görürsünüz: “Tanımlı bir hiyerarşik ilişkisi bulunmayan bir varlıkta hiyerarşik işleç kullanıyorsunuz. Varlığı hiyerarşik yapın (bir ilişkiyi hiyerarşik olarak işaretleyerek) veya farklı bir işleç kullanın.” Hiyerarşik ilişkiler hakkında daha fazla bilgi için bkz. [Hiyerarşik olarak ilgili verileri tanımlama ve sorgulama](/powerapps/maker/common-data-service/define-query-hierarchical-data). Tablonun altındaki ekran görüntüsü, **Altındadır** ve **Altında Değildir** hiyerarşik işleçlerini kullanan iş akışı işleminin tanımına bir örnektir.|  
|**Koşullu Dal**|Mantıksal bir "else-if-then" deyimi, düzenleyici, “Otherwise, if \<condition> then:” metnini kullanır.<br /><br /> Önceden tanımladığınız bir denetim koşulu seçin; böylece denetim koşulu false değerini döndürdüğünde ek adımlar tanımlamak için bir koşullu dal ekleyebilirsiniz.|  
|**Varsayılan Eylem**|Mantıksal bir "else" deyimi. düzenleyici “Otherwise:” metnini kullanır.<br /><br /> Önceden tanımladığınız bir denetim koşulu, koşullu dal, bekleme koşulu veya paralel bekleme dalı seçin; böylece koşul veya dal öğelerinde tanımlanan ölçütlerle eşleşmeyen tüm durumlara yönelik adımlar tanımlamak için varsayılan bir eylem kullanabilirsiniz.|  
|**Bekleme Koşulu**|Arka plan iş akışının, koşul tarafından tanımlanan ölçütler yerine getirilinceye kadar kendisini duraklatmasını sağlar. Bekleme koşulundaki ölçütler karşılandığında iş akışı otomatik olarak yeniden başlar.<br /><br /> Gerçek zamanlı iş akışları, bekleme koşullarını kullanamaz.|  
|**Paralel Bekleme Dalı**|Yalnızca ilk ölçüt karşılandığında gerçekleştirilen ilgili bir dizi ek adım ile bir arka plan iş akışı için alternatif bir bekleme koşulu tanımlar. İş akışı mantığınızda zaman sınırları oluşturmak için paralel bekleme dalları kullanabilirsiniz. Bunlar, iş akışının bir bekleme koşulunda tanımlanan ölçütler karşılanıncaya kadar süresiz olarak beklemesinin engellenmesine yardımcı olur.|  
|**Özel Adım**|Geliştiriciler, koşulları tanımlayan özel iş akışı adımları oluşturabilir. Varsayılan olarak, kullanılabilir bir özel adım yoktur.|  
  
 Aşağıdaki ekran görüntüsü, **Altındadır** ve **Altında Değildir** hiyerarşik işleçlerini içeren iş akışı işlemi tanımının bir örneğini içerir. Bizim örneğimizde, iki hesap grubuna iki farklı indirim uygularız. **Adım Ekle** bölümünde, **Altındadır** veya **Altında Değildir** işleçlerini içeren **if-then** koşulunu belirtmek için **Denetim Koşulu** seçeneğini belirledik. Birinci **if-then** koşulu, Alpine Ski House hesabı **Altında** olan tüm hesaplar için geçerlidir. Bu hesaplar, satın alınan mal ve hizmetlerde %10 indirim kazanır. İkinci **if-then** koşulu, Alpine Ski House hesabı **Altında Olmayan** tüm hesaplar için geçerlidir ve %5 indirim kazanır. Daha sonra koşula dayalı olarak gerçekleştirilecek eylemi tanımlamak için **Kaydı Güncelleştir** seçeneğini belirledik.  
  
 ![Altındadır&#47;Altında Değildir işleçleri ile iş akışı işlemi](media/wfp-under-not-under.PNG "Altındadır/Altında Değildir işleçleri ile iş akışı işlemi")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Gerçek zamanlı iş akışları kullanma  

 Gerçek zamanlı iş akışları yapılandırabilirsiniz, ancak bunları dikkatli kullanmanız gerekir. Sunucuda kaynaklar kullanılabilir oldukça sistemin bunları uygulamasına izin verdiğinden, arka plan iş akışları genellikle önerilir. Bu, sunucunun yapması gereken işi sorunsuz hale getirir ve sistemi kullanan herkes için en iyi performansın korunmasına yardımcı olur. Dezavantajı, arka plan iş akışları tarafından tanımlanan eylemlerin hemen olmamasıdır. Ne zaman uygulanacağını tahmin edemezsiniz, ancak genellikle birkaç dakika sürer. Sistemi kullanan kişilerin, işlemin çalıştığını bilinçli olarak bilmesi gerekmediğinden, İş süreçlerinin çoğu otomasyonu için bu iyidir.  
  
 Bir iş süreci, birisinin işlemin sonuçlarını hemen görmesini gerektirdiğinde veya bir işlemi iptal etme yeteneğini istiyorsanız gerçek zamanlı iş akışlarını kullanın. Örneğin, ilk kez kaydedildiğinde bir kayıt için belirli varsayılan değerleri ayarlamak isteyebilir veya bazı kayıtların silinmediğinden emin olmak isteyebilirsiniz.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Gerçek zamanlı iş akışları ve arka plan iş akışları arasında dönüştürme  

 Araç çubuğundaki **Arka plan iş akışına dönüştür** seçeneğini belirleyerek gerçek zamanlı iş akışını bir arka plan iş akışına dönüştürebilirsiniz.  
  
 Araç çubuğundaki **Gerçek zamanlı iş akışına dönüştür** seçeneğini belirleyerek arka plan iş akışını bir gerçek zamanlı iş akışına dönüştürebilirsiniz. Arka plan iş akışı bir bekleme koşulu kullanıyorsa geçersiz olur ve siz bekleme koşulunu kaldırıncaya kadar arka plan iş akışını etkinleştiremezsiniz.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Durum değişmeden önce veya durum değiştikten sonra gerçek zamanlı iş akışları başlatma  

 Gerçek zamanlı iş akışları için **Otomatik İşlemler için Seçenekler**’i yapılandırdığınızda, durum değişiklikleri olayı için **Başlangıç Zamanı** seçenekleri, durum değiştiğinde **Sonra** veya **Önce** seçeneğini belirlemenize olanak sağlar. Varsayılan seçenek **Sonra**’dır.  
  
 **Önce**’yi seçtiğinizde, durumu değiştiren verilerden önce uygulanacak iş akışındaki mantığın kaydedilmesini istediğinizi belirtmiş olursunuz. Bu size işlemden sonra diğer mantık uygulanmadan önceki değerleri denetleme ve daha fazla mantığın gerçekleştirilmesini engelleme yeteneği sağlar. Örneğin, başka bir sistemde eylemler başlatabilecek bir eklenti veya özel iş akışı eyleminde ek mantığınız olabilir. Daha fazla işlemi durdurarak, harici sistemlerin etkilenmesi durumunu önleyebilirsiniz. Bu olaydan önce gerçek zamanlı iş akışları uygulanması, işlem iptal edildiğinde, verileri kaydetmiş olabilecek diğer iş akışı veya eklenti eylemlerinin “geri alınması” gerekmediği anlamına gelir.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Gerçek zamanlı iş akışlarıyla İş Akışını Durdur eylemini kullanma  

 Bir iş akışında **İş Akışını Durdur** eylemini uyguladığınızda, **Başarılı Oldu** veya **İptal Edildi** şeklinde bir durum koşulu belirtme seçeneğiniz vardır. İptal edilecek durumu ayarladığınızda, işlemi engellemiş olursunuz. Kullanıcıya, **İş Süreci Hatası** başlığıyla birlikte durdurma eylemi durum iletisindeki metni içeren bir hata iletisi görüntülenir.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 [İşlemler ile özel iş mantığı oluşturma](guide-staff-through-common-tasks-processes.md)   
 [İş akışı süreçlerine genel bakış](workflow-processes.md)   
 [İş akışı süreçlerini izleme ve yönetme](monitor-manage-processes.md)   
 [İş akışı süreçleri için en iyi uygulamalar](best-practices-workflow-processes.md)
