---
title: İş işleme akışlarına genel bakış | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 230c35947c4e499c5e26fc37bb87828ec787a469
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545511"
---
# <a name="business-process-flows-overview"></a>İş işleme akışlarına genel bakış
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Kişilerin verileri sürekli olarak girmelerini ve bir iş süreci akışı oluşturarak müşteriyle çalıştıkları her seferinde aynı adımları izlemesini sağlamaya yardımcı olabilirsiniz. Örneğin, herkesin müşteri hizmet taleplerini aynı şekilde işlemesini sağlamak ya da bir siparişi göndermeden önce kişilerin bir faturaya onay almasını istemek için bir iş süreci akışı oluşturmak isteyebilirsiniz. İş süreci akışları diğer işlemlerle aynı temel teknolojinin aynısını kullanır, ancak sağladıkları yetenekler, işlemleri kullanan diğer özelliklerden çok farklıdır. İş süreci akışını oluşturma veya düzenleme hakkında bilgi edinmek için bkz. [iş süreci akışı oluşturma](create-business-process-flow.md).  
  
 [İş süreci akışları hakkında kısa bir video (4:49) izleyin.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>İş süreci akışları neden kullanılmalıdır?  
İş süreci akışları, kullanıcıların işleri almasını sağlayan bir kılavuz sağlar. Bu kişiler, kendilerine ait oldukları işlemlerin bir süre sonunda ileri düzey olması gereken etkileşimler için tanımladığı, kolaylaştırılmış bir kullanıcı deneyimi sağlar. Bu Kullanıcı deneyimi, farklı güvenlik rollerine sahip kişilerin yaptıkları işi en iyi şekilde sunan bir deneyimle karşılaşabilmesi için uyarlanabilir.  
  
 Kişilerin istedikleri sonuca gelmesi için takip etmek üzere bir adım kümesi tanımlamak için iş süreci akışlarını kullanın. Bu adımlar, kullanıcılara iş sürecinde oldukları yerleri söyleyen bir görsel gösterge sağlar. İş süreci akışları, yeni kullanıcıların kullanılması gereken varlığa odaklanmaları gerekmiyorsa eğitim gereksinimini azaltır. Bu işlemler, işlem kılavuzuna izin verebilir. İş süreci akışlarını, satış gruplarınızı daha iyi sonuçlar elde etmenize yardımcı olabilecek ortak satış yöntemlerini destekleyecek şekilde yapılandırabilirsiniz. İş süreci akışları, hizmet grupları için yeni personelin daha hızlı bir şekilde daha hızlı ulaşmasını ve memnun olmayan müşterilere neden olabilecek hatalardan kaçınmanıza yardımcı olabilir.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>İş süreci akışları ne yapabilir?  
 İş süreci akışlarıyla, daha sonra formun en üstündeki bir denetimde görüntülenen bir dizi *aşama* ve *adım* tanımlarsınız.  
  
 ![Aşamalarla iş süreci](media/business-process-stages.png "Aşamalarla iş süreci")  
  
 Her aşama bir adım grubunu içerir. Her adım, verilerin girilebileceği bir alanı temsil eder. Kullanıcılar **sonraki aşama** düğmesini kullanarak sonraki aşamaya geçer. Kullanıcıların bir sonraki aşamaya geçebilmesi için ilgili alana veri girmesi gereken bir adım yapabilirsiniz. Bu genellikle "aşama geçişi" olarak adlandırılır.  
  
 İş süreci akışları, veri girişi için kolaylaştırılmış deneyim sağlamaktan daha fazla koşullu iş mantığı veya Otomasyonu sağlamadıklarından, diğer işlem türleri görece şekilde oldukça basit görünür. Bununla birlikte, bunları diğer işlemlerle ve özelleştirmelerle birleştirdiğinizde, kişi zaman kaydederek önemli bir rol oynatabilir, eğitim maliyetlerini azaltabilir ve Kullanıcı benimseme işlemini artırır.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Diğer özelleştirmelerle tümleştirilmiş iş süreci akışları  
 Siz veya kullanıcınız iş süreci akışlarını kullanarak veri girdiğinde, iş kuralları veya form betikleri tarafından sunulan tüm otomasyon hemen uygulanabilmesi için veri değişiklikleri form alanlarına da uygulanır. Formda mevcut olmayan alanlar için değerler ayarlanan adımlar eklenebilir ve bu alanlar, form betikleri için kullanılan `Xrm.Page` nesne modeline eklenecektir. Bir iş süreci akışına dahil edilen alanlarda yapılan değişiklikler tarafından başlatılan tüm iş akışları, formdaki veriler kaydedildiğinde uygulanır. Otomasyon gerçek zamanlı bir iş akışı tarafından uygulanırsa, form verileri kayıt kaydedildikten sonra yenilendiğinde, değişiklikler kullanıcıya anında görünür olur.  
  
 Form içindeki iş süreci akışı denetimi doğrudan istemci tarafı programlamasına sahip olmasa da, iş kuralları veya form betikleri tarafından uygulanan değişiklikler otomatik olarak iş süreci akış denetimlerine uygulanır. Formdaki bir alanı gizlerseniz, bu alan aynı zamanda iş süreci akış denetiminde de gizlenir. İş kuralları veya form betikleri kullanarak bir değer ayarlarsanız, bu değer iş süreci akışı içinde ayarlanır.  
  
### <a name="concurrent-process-flows"></a>Eşzamanlı işlem akışları  
 Eşzamanlı iş süreci akışları, özelleştiricilerin birden çok iş işlemini yapılandırmalarına ve aynı başlangıç kaydıyla ilişkilendirilmesine izin verir. Kullanıcılar, eşzamanlı olarak çalışan birden fazla iş işlemi arasında geçiş yapabilir ve işlerini açık oldukları işlemde aşamada sürdürür.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Sistem iş süreci akışları  
 Aşağıdaki iş süreci akışları dahildir. İş süreci akışlarının nasıl çalıştığını anlamak için, bu sistem iş süreci akışlarını gözden geçirin:  
  
-   Fırsat satışı sürecine lider  
  
-   Fırsat satışı süreci  
  
-   Telefonla servis talebi Işleme  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>İş süreci akışlarında birden çok varlık  
 Bir iş süreci akışını tek bir varlık için veya birden çok varlığı yayan kullanabilirsiniz. Örneğin, bir fırsatla başlayan bir işleminiz olabilir, ardından bir teklife, siparişe ve sonra bir faturaya devam etmeden önce, fırsatı kapatmak üzere döndürmeden önce bir işlem yapabilirsiniz.  
  
 En fazla beş farklı varlık için kayıtları tek bir işlem halinde bağlayan iş süreci akışları tasarlayabilmeniz için, uygulamayı kullanan kişilerin üzerinde çalıştıkları varlık yerine kendi işlem akışına odaklanabilmesi adına. İlgili varlık kayıtları arasında daha kolay gezinebilirler.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Varlık başına birden çok iş süreci akışı kullanılabilir  
 Bir kuruluştaki her kullanıcı aynı işlemi takip edebilir ve farklı koşullar farklı bir işlemin uygulanmasını gerektirebilir. Farklı durumlara uygun işlemler sağlamak için varlık başına en fazla 10 etkin iş süreci olabilir.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Hangi iş süreci akışının uygulanacağını denetleme  
 İş süreci akışlarını güvenlik rolleriyle ilişkilendirebilmeniz için, yalnızca bu güvenlik rollerine sahip kişilerin bunları görmesini veya kullanmasını sağlayabilirsiniz. Ayrıca, iş süreci akışlarının sırasını, varsayılan olarak hangi iş süreci akışının ayarlanacağını denetleyebilmeniz için de ayarlayabilirsiniz. Bu, bir varlık için birden çok form tanımlananla aynı şekilde kullanılır.  
  
 Birisi yeni bir varlık kaydı oluşturduğunda, kullanılabilir etkin iş süreci tanımının listesi kullanıcının güvenlik rolüne göre filtrelenir. Kullanıcının güvenlik rolü için, işlem sırası listesine göre kullanılabilir olan ilk etkinleştirilen iş süreci tanımı, varsayılan olarak uygulanan bir işlemdir. Birden fazla etkin iş süreci tanımı varsa, kullanıcılar, Işlemi Değiştir iletişim kutusundan bir tane yükleyebilir. Her geçen işlem, şu anda işlenmiş olan arka plana gider ve seçili bir şekilde değişir, ancak durumunu korur ve geri dönebilir. Her kayıt için birden çok işlem örneği (her biri farklı bir iş işlemi akış tanımı için, toplam 10 ' a kadar) olabilir. Form yükleme sırasında yalnızca bir iş süreci akışı işlenir. Herhangi bir kullanıcı farklı bir işlem uygularsa, bu işlem yalnızca söz konusu Kullanıcı için varsayılan olarak yüklenebilir.  
  
 Bir iş sürecinin tüm kullanıcılar için varsayılan olarak yüklendiğinden emin olmak için (işlemi "sabitleme" davranışı ile eşdeğer), bir özel Istemci API betiği (Web kaynağı), işletmeden, mevcut bir iş süreci örneğini özel olarak yükleyen form yüküne eklenebilir işlem tanımı KIMLIĞI. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>İş süreci akışı konuları  
 İş süreci akışlarını yalnızca bunları destekleyen varlıklar için tanımlayabilirsiniz. Ayrıca, eklenebilecek işlem, aşama ve adımların sayısı için sınırlara dikkat etmeniz gerekir.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>İş akışını çağıran iş süreci akışları  
 İsteğe bağlı iş akışlarını iş süreci akışının içinden çağırabilirsiniz. Bunu yeni iş süreci akış Tasarımcısı 'ndan bir iş akışı bileşenini bir işlem aşamasına veya küresel Iş akışları bölümüne sürükleyerek yapılandırabilirsiniz. İş süreci akışlarında iş akışlarını kullanma hakkında daha fazla bilgi için, bkz. [Blog: Dynamics 365 ' de iş süreci akışı Otomasyonu](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 İş süreci akışınızda bir aşamanın aşamasına çıkmak istediğiniz bir iş akışını dahil ettiğinizde ve bu aşama akıştaki son aşamayken, tasarımcı iş akışının bu aşama tamamlandığında tetikleyeceği izlenimi verir. Ancak, bir aşama geçişi gerçekleşmediğinden iş akışı tetiklenmeyecektir. İş akışını aşamasına dahil etmek için bir uyarı veya hata almazsınız. Bir kullanıcı iş süreci akışıyla etkileşime geçtiğinde, işlemin tamamlanması veya geri olmaması bir aşama geçişine neden olmaz ve bu nedenle iş akışı tetiklenmez. Aşağıdaki örnekleri göz önünde bulundurun:  
  
-   İki aşamaya sahip bir iş süreci akışı oluşturursunuz. S1, S2 ' de bir iş akışı ile S2 'ye bağlanır ve tetikleyiciyi **aşama çıkış**olarak ayarlar.  
  
-   Üç aşamadan oluşan bir iş süreci akışı oluşturursunuz, S1, S2 'ye bağlanır ve S2, S3 'e dallandırır. S2 'ye bir iş akışı ekleyin ve tetikleyiciyi **aşama çıkış**olarak ayarlayın.  
  
 İş akışı her iki durumda da tetiklemez. Bu sorunu geçici olarak çözmek için, genel bir Iş akışı ekleyebilir ve tetiklemeyi istediğiniz iş akışını, iş akışının işlemin bir aşaması yerine iş süreci için tetiklenmesi için ekleyebilirsiniz. Bir kullanıcı iş sürecini tamamladıktan veya tamamlandığında iş akışının tetiklenmesine neden olmak için, bir genel iş akışı için tetikleyiciyi durdurulmuş veya Işlem tamamlandı olarak ayarlayabilirsiniz.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>İş süreci akışlarını kullanan varlıklar  
 Tüm özel varlıklar, iş süreci akışlarını kullanabilir. Aşağıdaki standart varlıklar iş süreci akışlarını da kullanabilir:  
  
-   Hesabı  
-   Randevusundaki  
-   Kampanyadan  
-   Kampanya etkinliği  
-   Kampanya yanıtı  
-   Oluşturma  
-   İrtibata  
-   E-posta  
-   Verme  
-   Faks  
-   Harflerini  
-   Faturalayabilirsiniz  
-   Neden  
-   Harfin  
-   Pazarlama listesi  
-   Fırsatta  
-   Telefon araması  
-   Ürünüyle  
-   Fiyat listesi öğesi  
-   Tırnak  
-   Yinelenen randevu  
-   Satış belgeleri  
-   Sosyal etkinlik  
-   Siparişi  
-   Kullanıcısını  
-   Görevinin  
-   Takım  
  
 İş süreci akışları için özel bir varlığı etkinleştirmek üzere varlık tanımında **iş süreci akışlarını (alanları oluşturulacak alanlar)** onay kutusunu seçin. Bu eylemi geri alamazsınız.  
  
> [!NOTE]
>  `Social Activity` varlığını içeren iş süreci akış aşamasına gidebilir ve **sonraki aşama** düğmesini seçtiğinizde, **Oluştur** seçeneğini görürsünüz. **Oluştur**' u seçtiğinizde **sosyal etkinlik** formu yüklenir. Ancak, uygulama kullanıcı arabiriminden `Create` için `Social Activity` geçerli olmadığından, formu kaydedemeyeceksiniz ve şu hata iletisini görürsünüz: "beklenmeyen hata".  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>En fazla işlem, aşama ve adım sayısı  
 Kullanıcı arabiriminin kabul edilebilir performansını ve kullanılabilirliğini sağlamak için, iş süreci akışlarını kullanmayı planlarken dikkat etmeniz gereken bazı sınırlamalar vardır:  
  
-   Varlık başına en fazla 10 etkin iş süreci akışı işlemi olabilir.  
  
-   Her işlem 30 ' dan fazla aşama içerebilir.  
  
-   Çoklu varlık işlemlerinde en fazla beş varlık bulunabilir.
  
## <a name="business-process-flow-entity-customization-support"></a>İş süreci akışı varlık özelleştirme desteği 

Dynamics 365 (çevrimiçi), sürüm 9,0 güncelleştirmesinde tanıtılan iş süreci akış varlıkları sistemde görünebilir, böylece varlık kaydı verileri kılavuzlar, görünümler, grafikler ve panolarda kullanılabilir hale getirilebilir. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Kılavuzlar, görünümler, grafikler ve panolar ile iş süreci akışı varlık kayıtlarını kullanma

Bir varlık olarak kullanılabilen iş süreçleriyle birlikte, bir müşteri adayı veya fırsat gibi belirli bir varlık için iş süreci akış verilerinden kaynaklanan gelişmiş bulma, görünümler, grafikler ve panoları kullanabilirsiniz. Sistem yöneticileri ve özelleştiriciler, başka bir varlıkla oluşturulanlara benzer özel iş süreci akış kılavuzları, görünümler, grafikler ve panolar oluşturabilir.

**Fırsat satışları Için müşteri adayı süreci**gibi iş süreci akışları, Çözüm Gezgini 'nde özelleştirilebilir bir varlık olarak görünür.

![Müşteri adayı-fırsat işlem varlığıyla Çözüm Gezgini](media/bpf-lead-solution-explorer.png)

Varsayılan bir iş süreci akışı görünümüne erişmek için Çözüm Gezgini ' ni açın, **varlıklar** ' ı genişletin > istediğiniz işlemi genişletin, örneğin **fırsat satışları süreci**, **Görünümler**' i seçin ve ardından istediğiniz görünümü seçin.

**Etkin fırsat satış süreci** görünümü gibi bir grafik olarak görüntüleyebileceğiniz çeşitli varsayılan görünümler vardır. 

![Etkin fırsat satışları Işlem görünümü](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Bir iş akışından iş süreci akışı varlığıyla etkileşim kurma
İş süreci akışı varlıklarıyla bir iş akışından de etkileşim kurabilirsiniz. Örneğin, fırsat varlık kaydındaki bir alan güncelleştirilirken etkin aşamayı değiştirmek üzere Iş süreci akışı varlık kaydı için bir iş akışı oluşturabilirsiniz. Bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz. iş [akışlarını kullanarak iş süreci akışı aşamalarını otomatikleştirme](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows).


### <a name="limitations-of-using-business-process-flow-entities"></a>İş süreci akışı varlıklarını kullanma sınırlamaları

- Şu anda, iş süreci akışına göre varlıklar için özel formlar oluşturamazsınız.
- Bir çözüm iş süreci akışı varlığı içeriyorsa, iş süreci akış varlığının dışarı aktarmadan önce çözüme el ile eklenmesi gerekir. Aksi takdirde, iş süreci akış varlığı çözüm paketine dahil edilmez. Daha fazla bilgi: [çözüm bileşenleri ekleme](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)

### <a name="next-steps"></a>Sonraki adımlar  
 [İş süreci akışları hakkında kısa bir video (4:49) izleyin](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [İş süreci akışı oluşturma](create-business-process-flow.md)   
 [Dalla iş süreci akışlarını geliştirin](enhance-business-process-flows-branching.md) <br/>
 [Teknik İnceleme: Dynamics 365 ile Işlem etkinleştirme](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
