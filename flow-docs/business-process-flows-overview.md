---
title: İş süreci akışlarına genel bakış | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: baefae21e605b0e54e32b09dfaee8f2980d73c13
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690339"
---
# <a name="business-process-flows-overview"></a>İş süreci akışlarına genel bakış

Bir iş süreci akışı oluşturarak, kişilerin sürekli veri girmelerine ve bir müşteri ile her çalıştıklarında aynı adımları izlemelerine yardım olursunuz. Örneğin, herkesin müşteri hizmetleri isteklerini aynı şekilde ele alması veya kişilerin bir sipariş göndermeden önce fatura onayı istemesini zorunlu hale getirmek için bir iş süreci akışı oluşturmak isteyebilirsiniz. İş süreci akışları diğer süreçlerle aynı temel teknolojiyi kullanır, ancak sağladıkları yetenekler, süreçleri kullanan diğer özelliklerden çok farklıdır. Bir iş süreci akışı oluşturmayı veya düzenlemeyi öğrenmek için, bkz. [Bir iş süreci akışı oluşturma](create-business-process-flow.md).  
  
 [İş süreci akışları hakkında kısa bir video (4:49) izleyin.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>İş süreci akışları neden kullanılır?  
İş süreci akışları, insanların işlerini yapmaları için bir kılavuz sağlar. Kullanıcılara, kuruluşlarının bir sonuca ulaşmak için ihtiyaç duyduğu etkileşimler için tanımladığı süreçler içinde öncülük eden, kolaylaştırılmış bir kullanıcı deneyimi sağlar. Bu kullanıcı deneyimi, farklı güvenlik rollerine sahip kişilerin, yaptıkları işe en iyi uyan deneyime sahip olabilmeleri için uygun hale getirilebilir.  
  
 Kişilerin, kendilerini istenen sonuca götürmek için takip edecekleri bir adım kümesi tanımlamak için iş süreci akışlarını kullanın. Bu adımlar, insanlara iş sürecinde nerede olduklarını söyleyen görsel bir gösterge sağlar. Yeni kullanıcılar hangi varlığı kullanacaklarına odaklanmak zorunda olmadığı için, iş süreci akışları eğitime olan ihtiyacı azaltır. Sürecin kendilerine kılavuzluk etmesine izin verebilirler. Satış gruplarınızın daha iyi sonuçlar elde etmesine yardımcı olabilecek genel satış yöntemlerini desteklemek için iş süreci akışlarını yapılandırabilirsiniz. Hizmet grupları için, iş süreci akışları yeni personelin gelişmelerden daha çabuk haberdar olmasına yardımcı olabilir ve memnuniyetsiz müşterilere yol açabilecek hatalardan kaçınabilir.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>İş süreci akışları neler yapabilir?  
 İş süreci akışları ile, daha sonra formun en üstünde yer alan bir denetimde görüntülenecek bir *aşama* ve *adım* kümesi tanımlarsınız.  
  
 ![Aşamalı iş süreçleri](media/business-process-stages.png "Aşamalı iş süreçleri")  
  
 Her aşama bir adım grubu içerir. Her adım verilerin girilebileceği bir alanı temsil eder. Kişiler, **Sonraki Aşama** düğmesini kullanarak bir sonraki aşamaya ilerler. İnsanların bir sonraki aşamaya geçmeden önce ilgili alana veri girmesi için gerekli bir adım atabilirsiniz. Buna genellikle “aşama geçişi” adı verilir.  
  
 İş süreci akışları diğer veri türlerine kıyasla nispeten basit görünürler, çünkü veri girişi ve aşamalara girişin denetlenmesi için kolaylaştırılmış bir deneyim sağlamanın ötesinde, herhangi bir koşullu iş mantığı veya otomasyonu sağlamazlar. Ancak, bunları diğer süreçler ve özelleştirmelerle birleştirdiğinizde insanlara zaman kazandırma, eğitim maliyetlerini azaltma ve kullanıcı benimsemesini artırmada önemli bir rol oynayabilirler.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Diğer özelleştirmelerle tümleşik iş süreci akışları  
 Siz veya kullanıcınız iş süreci akışlarını kullanarak veriye girdiğinizde, veri değişimleri, iş kuralları veya form betikleri tarafından sağlanan herhangi bir otomasyonun hemen uygulanabilmesi için alanlar oluşturmak için de uygulanır. Formda bulunmayan alanların değerlerini ayarlayan adımlar eklenebilir ve bu alanlar form betikleri için kullanılan `Xrm.Page` nesne modeline eklenir. Bir iş süreci akışına dahil edilen alanlarda yapılan değişikliklerle başlatılan tüm iş akışları, formdaki veriler kaydedildiğinde uygulanır. Otomasyon gerçek zamanlı bir iş akışı tarafından uygulanırsa, formdaki veriler kayıt kaydedildikten sonra yenilendiğinde, kullanıcıya hemen görünür.  
  
 Formdaki iş süreci akış denetimi herhangi bir doğrudan istemci tarafı programlanabilirliği sağlamamasına rağmen, iş kuralları veya form betikleri tarafından uygulanan değişiklikler, iş süreci akış denetimlerine otomatik olarak uygulanır. Bir formdaki bir alanı gizlerseniz, bu alan iş süreci akış denetiminde de gizlenir. İş kuralları veya form betikleri kullanarak bir değer ayarlarsanız, bu değer iş süreci akışında ayarlanır.  
  
### <a name="concurrent-process-flows"></a>Eş zamanlı süreç akışları  
 Eş zamanlı iş süreci akışları, özelleştiricilerin birden çok iş süreci yapılandırmasını sağlar ve bunları aynı başlangıç kaydıyla ilişkilendirir. Kullanıcılar eş zamanlı çalışan birden çok iş süreci arasında geçiş yapabilir ve çalışmalarını devam ettikleri süreçteki aşamada devam ettirebilir.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Sistem iş süreci akışları  
 Aşağıdaki iş süreci akışları dahildir. İş süreci akışlarının nasıl işlediğini anlamak için, şu sistem iş süreci akışlarını inceleyin:  
  
-   Fırsat Satış Sürecine Yol Açma  
  
-   Fırsat Satış Süreci  
  
-   Servis Talebi İşleme Telefonu  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>İş süreci akışlarında birden çok varlık  
 Tek bir varlık için bir iş süreci akışı kullanabilir veya birden çok varlığa yayabilirsiniz. Örneğin; bir fırsatla başlayan, ardından teklifi kapatmak için geri dönmeden önce teklif, sipariş ve faturaya devam eden bir sürece sahip olabilirsiniz.  
  
 Uygulamayı kullanan kişilerin, üzerinde çalışmakta oldukları varlık yerine kendi süreçlerinin akışına odaklanabilmesi için, en fazla beş farklı varlığın kayıtlarını varlığa tek bir süreçle birleştiren iş süreci akışları tasarlayabilirsiniz. İlgili varlık kayıtları arasında daha kolay gezinebilirler.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Varlık başına birden çok iş süreci akışı bulunur  
 Bir kuruluştaki her kullanıcı aynı süreci takip edemez ve farklı koşullar farklı bir sürecin uygulanmasını gerektirebilir. Farklı durumlar için uygun süreçleri sağlamak üzere, varlık başına en fazla 10 aktif iş süreci akışına sahip olabilirsiniz.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Hangi iş süreci akışının uygulanacağını denetleyin  
 Yalnızca o güvenlik rollerine sahip kişilerin görebilmesi veya kullanabilmesi için, iş süreci akışlarını güvenlik rolleriyle ilişkilendirebilirsiniz. Hangi iş süreci akışının varsayılan olarak ayarlanacağını denetleyebilmek için, iş süreci akışlarının sırasını da ayarlayabilirsiniz. Bu, bir varlık için birden çok formun tanımlandığı gibi işler.  
  
 Biri yeni bir varlık kaydı oluşturduğunda, kullanılabilir etkin iş süreci tanımı listesi kullanıcının güvenlik rolüyle filtrelenir. İşlem sırası listesine göre kullanıcının güvenlik rolü için kullanabilir olan, etkinleştirilmiş ilk iş süreci tanımı varsayılan olarak uygulanır. Birden fazla etkin iş süreci tanımlaması bulunuyorsa, kullanıcılar Süreci Değiştir iletişim kutusundan başka bir tane yükleyebilir. Süreçler her değiştirildiğinde, o anda işlenmiş süreç arka plana gider ve seçili olanla değiştirilir, ancak durumunu korur ve tekrar değiştirilebilir. Her kaydın birden çok ilişkili süreç örneği olabilir (her biri farklı bir iş süreci akış tanımlaması için, en fazla 10 tane). Form yüklemede yalnızca bir iş süreci akışı işlenir. Herhangi bir kullanıcı farklı bir süreç uyguladığında, o süreç yalnızca o kullanıcı için varsayılan olarak yüklenebilir.  
  
 Bir iş sürecinin tüm kullanıcılar için varsayılan olarak yüklendiğinden emin olmak için (süreci “sabitlemeye” eşdeğer davranış) form yüklemede, özellikle iş süreci tanımı kimliğini temel alan mevcut bir iş süreci örneğini yükleyen özel bir İstemci API komut dosyası (web kaynağı) eklenebilir. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>İş süreci akışında dikkat edilmesi gerekenler  
 İş süreci akışlarını yalnızca kendilerini destekleyen varlıklar için tanımlayabilirsiniz. Eklenebilecek süreç, aşama ve adım sayısı sınırlarının da farkında olmanız gerekir.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Bir iş akışını çağıran iş süreci akışları  
 İsteğe bağlı iş akışlarını bir iş süreci akışının içinden çağırabilirsiniz. Bunu, bir iş akışı bileşenini bir süreç aşamasına veya Genel İş Akışları bölümüne sürükleyerek yeni iş süreci akış tasarımcısından yapılandırabilirsiniz. İş süreci akışı akışlarında iş akışlarını kullanma hakkında daha fazla bilgi için, bkz. [Blog: Dynamics 365’te iş süreci akış otomasyonu](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 İş süreci akışınıza, bir aşamanın Aşama Çıkışı'nda tetiklemek istediğiniz bir iş akışı dahil etiğinizde ve bu aşama akıştaki son aşama olduğunda, tasarımcı o aşama tamamlandığında iş akışının tetikleneceği izlenimini verir. Ancak, bir aşama geçişi gerçekleşmediği için iş akışı tetiklenmez. İş akışını aşamaya dahil etmenizi engelleyen bir uyarı veya hata almazsınız. Bir kullanıcı iş süreci akışıyla etkileşime girdiğinde, işlemi bitirmek veya bırakmak aşama geçişiyle sonuçlanmaz ve bu nedenle iş akışı tetiklenmez. Aşağıdaki örnekleri dikkate alın:  
  
-   İki aşamalı bir iş süreci akışı oluşturursunuz, S1, S2 aşamasındaki bir iş akışıyla S2’ye bağlanır ve tetiği **Aşama Çıkışı**’na ayarlarsınız.  
  
-   Üç aşamalı bir iş süreci akışı oluşturursunuz, S1, S2’ye bağlanır, ardından S2, S3’e dal oluşturur. S2’ye bir iş akışı dahil edersiniz ve tetiği **Aşama Çıkışı**’na ayarlarsınız.  
  
 İş akışı, her iki durumda da tetiklenmez. Bu sorunu geçici olarak çözmek için Genel İş Akışı ekleyebilir ve iş akışının, sürecin bir aşaması yerine iş süreci için tetiklenmesi için, tetiklemek istediğiniz iş akışını buna ekleyebilirsiniz. Bir kullanıcı iş sürecini bıraktığında veya tamamladığında, Bırakılan Sürecin veya Tamamlanan Sürecin iş akışının tetiklenmesine yol açması için Genel iş akışının tetiklenmesini ayarlayabilirsiniz.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>İş süreci akışlarını kullanabilen varlıklar  
 Tüm özel varlıklar iş süreci akışlarını kullanabilir. Aşağıdaki standart varlıklar da iş süreci akışlarını kullanabilir:  
  
-   Hesap  
-   Randevu  
-   Kampanya  
-   Kampanya Etkinliği  
-   Kampanya Yanıtı  
-   Rakip  
-   İletişim  
-   E-posta  
-   Destek Hakkı  
-   Faks  
-   Servis Talebi  
-   Fatura  
-   Müşteri Adayı  
-   Mektup  
-   Pazarlama Listesi  
-   Fırsat  
-   Telefon Araması  
-   Ürün  
-   Fiyat Listesi Kalemi  
-   Teklif  
-   Yinelenen Randevu  
-   Satış Belgesi  
-   Sosyal Etkinlik  
-   Sıra  
-   Kullanıcı  
-   Görev  
-   Takım  
  
 İş süreci akışları için özel bir varlık etkinleştirmek için, varlık tanımındaki **İş süreci akışları (alanlar oluşturulacak)** onay kutusunu seçin. Bu eylemi geri alamayacağınızı unutmayın.  
  
> [!NOTE]
>  `Social Activity` varlığı içeren iş süreci akış aşamasına gidip **Sonraki Aşama** düğmesini seçerseniz **Oluştur** seçeneğini görürsünüz. **Oluştur**’u seçtiğinizde, **Sosyal Etkinlik** formu yüklenir. Ancak `Social Activity`, uygulama kullanıcısı arabiriminden `Create` için geçerli olmadığından, formu kaydedemezsiniz ve şu hata iletisini görürsünüz: “Beklenmeyen hata”.  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Süreç, aşama ve adım sayısı üst sınırı  
 Kabul edilebilir performans ve kullanıcı arabiriminin kullanılabilirliğini sağlamak için, iş süreci akışlarını kullanmayı planladığınızda dikkat etmeniz gereken bazı sınırlamalar vardır:  
  
-   Varlık başına 10’dan fazla etkinleştirilmiş iş akış süreci olamaz.  
  
-   Her süreç en fazla 30 aşama içerebilir.  
  
-   Çoklu varlık süreçleri en fazla beş varlık içerebilir.
  
## <a name="business-process-flow-entity-customization-support"></a>İş süreci akış varlığı özelleştirme desteği 

Varlık kaydı verileri kılavuzlarda, görünümlerde, grafiklerde ve panolarda kullanılabilmesi için, Dynamics 365 (çevrimiçi) sürüm 9.0 güncelleştirmesinde sunulan iş süreci akış varlıkları sistemde görünebilir. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>İş süreci akış varlığı kayıtlarını kılavuzlar, görünümler, grafikler ve panolarla kullanma

İş süreci akışlarının bir varlık olarak kullanılabilir olmasıyla, bir müşteri adayı veya fırsat gibi belli bir varlığın iş süreci akış verilerinden kaynaklanan gelişmiş aramalar, görünümler, grafikler ve panolar kullanabilirsiniz. Sistem yöneticileri ve özelleştiriciler, başka bir varlık ile oluşturulanlara benzeyen özel iş süreci akış kılavuzları, görünümler, grafikler ve panolar oluşturabilir.

**Müşteri Adayından Fırsat Satışına Geçiş Süreci** gibi iş süreci akışları, çözüm gezgininde özelleştirilebilir bir varlık olarak görünür.

![Müşteri adayından fırsat satışına geçiş sürecine sahip Çözüm Gezgini](media/bpf-lead-solution-explorer.png)

Varsayılan bir iş süreci akış görünümüne erişmek için, çözüm gezginini açın, **Varlıklar**’ı genişletin > **Müşteri Adayından Fırsat Satışına Geçiş Süreci** gibi istediğiniz süreci genişletin,  **Görünümler**’i seçin ve ardından istediğiniz görünümü seçin.

**Etkin Fırsat Satışı Süreci** görünümü gibi bir grafik olarak görüntüleyebileceğiniz bazı varsayılan görünümler bulunmaktadır. 

![Etkin Fırsat Satışı Süreci görünümü](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Bir iş akışından, iş süreci akış varlığıyla etkileşime girme
Bir iş akışından, iş süreci akış varlıklarıyla da etkileşime girebilirsiniz. Örneğin, Fırsat varlığı kaydındaki bir alan güncelleştirildiğinde, Etkin Aşama'yı değiştirmek için İş Süreci Akışı varlık kaydı için bir iş akışı oluşturabilirsiniz. Bunun nasıl yapılacağı hakkında daha fazla bilgi için, bkz. [İş akışlarını kullanarak iş süreci akış aşamalarını otomatikleştirme](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows).


### <a name="limitations-of-using-business-process-flow-entities"></a>İş süreci akış varlıklarını kullanma sınırlamaları

- Şu anda bir iş süreci akışını temel alan varlıklar için özel formlar oluşturamazsınız.
- Bir çözüm, bir iş süreci akış varlığı içeriyorsa, dışarı aktarmadan önce, iş süreci akış varlığını çözüme el ile eklemeniz gerekir. Tersi durumda, iş süreci akış varlığı çözüm paketine dahil edilmez. Daha fazla bilgi: [Çözüm bileşenleri ekleme](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)

### <a name="next-steps"></a>Sonraki adımlar  
 [İş süreci akışları hakkında kısa bir video (4:49) izleyin](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [İş süreci akışı oluşturma](create-business-process-flow.md)   
 [Dal oluşturma ile iş süreci akışlarını geliştirme](enhance-business-process-flows-branching.md) <br/>
 [Teknik İnceleme: Dynamics 365 ile İşlem Etkinleştirme](http://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
