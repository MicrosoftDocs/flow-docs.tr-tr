---
title: İletişim kutularını iş süreci akışlarıyla veya tuval uygulamalarıyla değiştirin | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- flow
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a7e8bac3c33fa5bb8cfb0501b981af65115036ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548809"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>İletişim kutularını iş süreci akışlarıyla veya tuval uygulamalarıyla değiştirin
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

[Iletişim kutuları kullanım dışıdır](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated)ve iş süreci akışları veya tuval uygulamaları tarafından değiştirilmelidir. Bu konu başlığı altında, bu seçeneklerin farklı özellikleri ve model temelli bir forma gömülü bir iş süreci veya tuval uygulamasının var olan bir iletişim kutusunun yerini almak için kullanılabileceği durumlar açıklanmaktadır.

## <a name="feature-capability-comparison"></a>Özellik yeteneği karşılaştırması

Bu tabloda, iletişim kutusu özellikleri ve iş süreci akışları ve tuval uygulamalarında eşdeğer yetenekler listelenmiştir.


|İletişim kutusu özelliği  | İş süreci akışlarında yetenek mı?  | Tuval uygulamalarında yetenek mi?  |
|---------|---------|---------|
|Sayfasında     | Yes <br/> (iş süreci aşaması)    | Yes <br/> (uygulama ekranı)        |
|Yalnızca istem   |  eşleşen    |  Yes <br/> etikete        |
|İstem ve yanıt     |  Yes <br/> (yalnızca varlık öznitelikleri)    | Yes <br/> (Etiketler ve giriş alanları)    |
|Giriş bağımsız değişkenleri     |  Az <br/> (iş süreci aşamasındaki adımlar)    | Yes <br/> (sorgu dizesi parametreleri)     |
|değişkenlerinin   |  eşleşen     |  Yes       |
|Sorgu değişkenleri    |  eşleşen     |  Yes     |
|Koşullu dallanma mantığı    |  Yes     | Yes <br/>  (uygulama içinde herhangi bir ekrana gidin)    |
|Pencereleri <br/> (alt öğe iletişim kutusu olarak Başlat)   |  eşleşen     | Yes <br/> (uygulama içindeki herhangi bir ekrana gidin, yeni bir pencerede farklı bir uygulama başlatın)     |
|Başlangıç/bitiş üzerinde iş akışlarını çalıştır    |   Yes      |  eşleşen <br/> (Bunun yerine bir akış kullanın)  |
|Girişte iş akışlarını çalıştır    | Yes    | eşleşen <br/> (Bunun yerine bir akış kullanın)   |
|Sayfa geçişte iş akışlarını çalıştır   |  Yes       | eşleşen <br/> (Bunun yerine bir akış kullanın)    |
|URL 'YI kullanmaya başlayın  |   eşleşen      |  Yes     |
|Oturum günlüğü    |  Yes       |  eşleşen     |
|SDK desteği   |  Yes     |  Yes     |

### <a name="additional-capabilities-with-business-process-flows"></a>İş süreci akışlarıyla ek yetenekler
- İşlem analizi (görünümler, grafikler ve bir aşamada harcanan zaman)
- Özel denetimler

### <a name="additional-capabilities-with-canvas-apps"></a>Tuval uygulamaları ile ek yetenekler
- Uygulama Analizi (uygulama kullanımı & performans)
- Çoklu varlık sayfa oluşturma
- Akışları Çalıştır
- Veri bağlayıcıları (Standart ve özel)
- Tek başına uygulama olarak başlatma
- Yapılandırılabilir düzen

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>İş süreci akışı veya tuval uygulaması arasında seçim yapma
İletişim kutusunun değiştirilmesini seçtiğinizde, teslim etmek istediğiniz kullanıcı deneyiminin hesaba göre dikkate almanız önemlidir. Ayrıca, neredeyse her iletişim kutusunun bir tuval uygulaması kullanılarak modellenebilir olduğunu göz önünde bulundurun.

İş süreci akışları, bireysel kişiler ve Dynamics 365 uygulama bağlamı arasında işbirliği gerektiren fazla çalışan bir iş akışı genelinde rehberlik sağlayan iletişim kutularını değiştirmek için en uygun seçenektir. Örneğin, teklif incelemesi ve yönlendirme. 

Alternatif olarak, tuval uygulamaları, müşteri adayı Prospecting için çağrı betiği veya bir fırsatı güncelleştirme gibi diğer görevlere yönelik kullanıcı deneyimini basitleştirmek için, bir veya daha fazla görev için bir çağrı betiği modeli oluşturan iletişim kutularını değiştirmek üzere kullanılabilir. Bu senaryoların, tek başına tuval uygulamasına sahip olmanın da avantajlarından faydalandığına dikkat edin. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>İş süreci akışı senaryosunu kullanarak iletişim kutusu değiştirme
Bir dizi sayfa üzerinde, kullanıcıdan gelen bilgilerin önemli parçalarını istediğinizi ve teklife göndermeden önce teklifi kabul etmek veya reddetmek üzere gözden geçirenlere bir e-posta gönderip almak için bir iletişim kutusu olduğunu düşünün. Bu tür bir işlem, iş süreci akışı kullanarak daha etkin şekilde modellenir. 

İletişim kutusunu değiştirmek için, işlemdeki anahtar aşamalarını tanımlayarak başlarsınız. Bunlar, tüm ürünlerin listelendiğinden ve indirimlerin uygulandığından emin olmak için bir *Içerik hazırlama* aşaması, teklifin oluşturulması için *bir teklif* oluşturma aşaması, teklifin gönderilmesi için bir *temel İnceleme* aşaması ve belirli koşullar altında teklifi gözden geçirmek için bir *Ikincil gözden geçirme* aşaması, son olarak teklifi müşteriye göndermek Için bir *teklif teklifi* aşaması olan gözden geçirme ve onaylama.

Ardından, kullanıcıların işlemde izlenmesi gereken önemli adımları belirleyebilirsiniz. Örneğin, *Içerik hazırlama* aşaması, kullanıcının teklif edilecek ürünleri, bir fiyat listesi seçmek için zorunlu bir arama adımını ve bir sonraki aşamaya geçmeden önce indirim girmek için bir sayısal adımı içeren basit bir doğru veya yanlış adımı içerebilir. *Teklif oluştur* aşaması, daha önce *hazırlama içerik* aşamasına ve ilgili Dynamics 365 kaydına göre yakalanan tüm bilgilere dayalı bir teklif oluşturmak için bir [eylem adımı](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) içerebilir. *Birincil İnceleme* ve *İkincil gözden geçirme* aşamaları, teklif gözden geçirmesi için gerekli bir adım ve onay durumunu yakalamak için gerekli bir adımla birlikte, teklifin incelenmesi için çeşitli doğru veya yanlış adımlara sahip olabilir ve işlemin yalnızca bir onay olduğunda bir sonraki aşamaya taşınabilmesini sağlayabilirsiniz. aldığınızı. Yalnızca yetkili gözden geçirenlerin teklifte onay sağlayaabileceği emin olmak için bu adımda [alan düzeyi güvenliğini](/customer-engagement/admin/field-level-security) yapılandırın.  Ayrıca, biri *birincil incelemeye* ve *İkincil gözden geçirme* aşamalarına, örneğin Enter 'a bir e-posta bildirimi ekleyerek tüm gözden geçirenler için bir iş akışı ekleyebilir. 

Son olarak, işlem akışına kılavuzluk etmek için, koşullu mantığla birlikte iş süreci akış aşamaları ve adımları yapılandırın. Bu örnekte, *birincil gözden geçirme* aşamasına sonra bir [koşullu dal](enhance-business-process-flows-branching.md) ekleyebilirsiniz, örneğin bir adım ikinci bir gözden geçirme gereksinimini gösteriyorsa, Işlemdeki sonraki aşama *İkincil gözden geçirme* aşaması, aksi *durumda Teklif aşaması sunun* .

Bu iş süreci akışının kullanıcılara kullanılabilmesini sağlamak için, doğru kullanıcıların iş süreci akışına yönelik ayrıcalıklara sahip olduğundan emin olun ve ardından etkinleştirin.

İş süreci akışı oluşturma hakkında daha fazla bilgi için bkz. [öğretici: işlemleri standartlaştırmak için iş süreci akışı oluşturma](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Tuval uygulaması senaryosunu kullanarak iletişim kutusu değiştirme

Satış temsilcilerine, soğuk arayan müşteri adayları aracılığıyla rehberlik eden bir çağrı betiğini izleyen bir iletişim kutusu olduğunu varsayalım. Bu işlem, tuval uygulaması kullanılarak kolayca yakalanır.

Verileri okuyup yazmanız gereken veri kaynaklarına bağlanma ile başlayın. Bu örnekte, müşteri adayı, hesap ve iletişim bilgileri için [Dynamics 365 bağlantısı](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) kullanılır.

Gerekli ekran sayısını tanımlayarak başlayın. Bu örnekte, beş ekran olduğuna karar verebilirsiniz. 
-   Ekran 1. Bir listeden çağırmak üzere bir müşteri adayı seçmek için.
-   Ekran 2. Tanıtımları için, bir konuşma için kullanılabilirliği kontrol edin ve daha sonraki bir tarihte geri arama yapın. 
-   Ekran 3. BANT (bütçe, yetkili, ihtiyaç ve zaman çizelgesi) belirlemek için. 
-   Ekran 4. Sonraki adımları yakalamak ve izleme çağrılarını zamanlamak için. 
-   Ekran 5. Çağrının sonundaki zaman için lider teşekkür ederiz.

Sonra, her ekranı derleyin. İlk ekranda, çağrılması gereken [bir müşteri adayı Galerisi oluşturun](/powerapps/maker/canvas-apps/customize-layout-sharepoint) . İkinci adımda, ekranı bağlamak için Etiketler ' i kullanın ve bir kişinin konuşmasıyla ilgili bir zaman olup olmadığını yakalamak için radyo düğmeleri gibi denetimler kullanın. Varsa, bir düğmenin bir sonraki ekrana gitmesini sağlamak için koşullu mantığı kullanın ve değilse, müşteriyle bir geri çağrı zamanlamayı denemek için aynı ekranda bir betiği açığa çıkar. Benzer şekilde, Sonraki ekranlarda çağrı betiğinizi tanımlayın.

Son olarak, [ekranlar arasında gezinme tanımlayın](/powerapps/maker/canvas-apps/functions/function-navigate). Bu örnekte, ekranda sırayla gezinmenin yanı sıra, bir konuşma ile ilgileniyorsa, kullanıcının ikinci ekrandan son ekrana gitmek isteyebilirsiniz (Bu, zaman içinde müşteri adayını en iyi durumda olan betiğin sonu).

Bu uygulamayı kullanıcılar için kullanılabilir hale getirmek üzere uygulamayı yayımlayın. Bu tür bir senaryonun çağrı betikleri sağlayan ve hızlı veri girişini destekleyen tek başına bir uygulamanın kullanılabilirliği aracılığıyla nasıl dönüştürülebileceğini göz önünde bulundurun.

Bu deneyimi Dynamics 365 Sales 'e eklemek istediğinizi düşünün. Bunu yapmak için, bir Dynamics 365 Sales formunda iframe oluşturmaya başlayın. Ardından, PowerApps menüsünde **uygulamalar** bölümüne gidin, yeni yayımladığınız uygulamayı seçin, **Ayrıntılar** sekmesinin altındaki web bağlantısını kopyalayın ve iframe 'nin URL 'si olarak yapıştırın. 

Bu adımı daha da gerçekleştirerek, bu uygulamanın müşteri adayı ana formu dahilinde kullanılabilir olmasını ve uygulamanın kullanıcının ilk ekranda bir müşteri adayı seçmesini gerektirmemesi için müşteri adayının bağlamında olduğunu varsayalım. İlgili bilgileri uygulamaya geçirmek için yalnızca iframe URL 'sini, belirli bir olay üzerinde çalışan JavaScript (örneğin, form yükü) kullanarak, müşteri adayı veya hesap kimlikleri gibi bu bilgileri içeren bir sorgu dizesi eklemek üzere değiştirirsiniz. Sonra, uygulamayı ilk ekranı kaldıracak şekilde güncelleştirin (müşteri adayı seçimi için) ve bunun yerine [param işlevini](/powerapps/maker/canvas-apps/functions/function-param)kullanarak sorgu dizesi aracılığıyla uygulamaya geçirilen değerlere erişin.

## <a name="dialog-replacement-faq"></a>İletişim kutusu değiştirme SSS

Tuval uygulamalarında bağımlılıklar izleniyor mu? 
- Tuval uygulamalarındaki bağımlılıklar, Dynamics 365 uygulamalarındaki bağımlılıklarla aynı şekilde izlenir.

Bir tuval uygulamasını Komut çubuğundaki bir düğmeden açılan pencere olarak başlatabilir miyim?
- Yes. Bunu yapmak için, daha önce açıklandığı gibi uygulamanın **Ayrıntılar** bölümünden elde EDILEN hedef URL 'yi tuval uygulamanızın adına ayarlamanız yeterlidir.

Bir tuval uygulamasından iş akışları çağrılabilir mi?
- Bu desteklenmez. Bunun yerine bir akış kullanmanızı öneririz. Daha fazla bilgi: [Kullanıcı girişiyle düğme akışlarını tanıtma](button-flow-with-user-input-tokens.md)

İletişim kutularını iş süreci akışlarına veya tuval uygulamalarına otomatik olarak dönüştürebilir miyim?
- İletişim kutularını iş süreci akışlarına veya tuval uygulamalarına dönüştürmenin otomatik bir yolu yoktur.


## <a name="see-also"></a>Ayrıca bkz.
[Öğretici: işlemleri standartlaştırmak için bir iş süreci akışı oluşturma](create-business-process-flow.md) </br>
[PowerApps 'te tuval uygulamaları nelerdir?](/powerapps/maker/canvas-apps/getting-started)


