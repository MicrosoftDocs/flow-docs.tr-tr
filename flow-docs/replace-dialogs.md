---
title: Diyalogları iş süreci akışları veya tuval uygulamalarıyla değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 498efb98a4c89ca6c2a01e345f5593beae4dbcca
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64464605"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Diyalogları iş süreci akışları veya tuval uygulamalarıyla değiştirme

[Diyaloglar kullanım dışı bırakılmıştır](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated) ve iş süreci akışları veya tuval uygulamalarıyla değiştirilmelidir. Bu konu başlığında bu seçeneklerin farklı özelliklerinin yanı sıra model temelli bir formda eklenmiş olan iş süreci akışı veya tuval uygulamasının var olan bir diyaloğun yerine kullanılabileceği durumlar açıklanmaktadır.

## <a name="feature-capability-comparison"></a>Özellik işlevi karşılaştırması

Bu tabloda diyalog işlevleri ile iş süreci akışlarında ve tuval uygulamalarında bunlara karşılık gelen işlevler listelenmiştir.


|Diyalog işlevi  | İşlev, iş süreci akışlarında bulunuyor mu?  | İşlev, tuval uygulamalarında bulunuyor mu?  |
|---------|---------|---------|
|Sayfa     | Evet <br/> (iş süreci aşaması)    | Evet <br/> (uygulama ekranı)        |
|Yalnızca istem   |  Hayır    |  Evet <br/> (etiketler)        |
|İstem ve yanıt     |  Evet <br/> (yalnızca varlık öznitelikleri)    | Evet <br/> (etiketler ve giriş alanları)    |
|Giriş bağımsız değişkenleri     |  Sınırlı <br/> (iş süreci aşaması adımları)    | Evet <br/> (sorgu dizesi parametreleri)     |
|Değişkenler   |  Hayır     |  Evet       |
|Sorgu değişkenleri    |  Hayır     |  Evet     |
|Koşullu dallanma mantığı    |  Evet     | Evet <br/>  (uygulama içinde herhangi bir ekran gitme)    |
|Yeniden kullanma <br/> (alt diyalog olarak başlatma)   |  Hayır     | Evet <br/> (uygulama içinde herhangi bir ekran gitme, yeni pencerede farklı bir uygulama başlatma)     |
|Başlangıçta/bitişte iş akışı çalıştırma    |   Evet      |  Hayır <br/> (bunun yerine akış kullanın)  |
|Girişte iş akışı çalıştırma    | Evet    | Hayır <br/> (bunun yerine akış kullanın)   |
|Sayfa geçişinde iş akışı çalıştırma   |  Evet       | Hayır <br/> (bunun yerine akış kullanın)    |
|URL kullanmaya başlama  |   Hayır      |  Evet     |
|Oturumu günlüğe kaydetme    |  Evet       |  Hayır     |
|SDK desteği   |  Evet     |  Evet     |

### <a name="additional-capabilities-with-business-process-flows"></a>İş süreci akışlarındaki ek işlevler
- Süreç analizi (görünümler, grafikler ve belirli bir aşamada harcanan süre)
- Özel denetimler

### <a name="additional-capabilities-with-canvas-apps"></a>Tuval uygulamalarındaki ek işlevler
- Uygulama analizi (uygulama kullanımı ve performansı)
- Birden çok varlık sayfası oluşturma
- Akış çalıştırma
- Veri bağlayıcıları (standart veya özel)
- Tek başına uygulama olarak başlatma
- Yapılandırılabilir düzen

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>İş süreci akışı veya tuval uygulaması arasında seçim yapma
Diyaloğun yerine kullanacağınız sistemi seçerken sunmak istediğiniz kullanıcı deneyimini dikkate almanız gerekir. Ayrıca neredeyse tüm diyalogların tuval uygulaması kullanılarak modellenebileceğini aklınızda bulundurun.

İş süreci akışları, kullanıcı grupları arasında ve Dynamics 365 uygulaması bağlamında iş birliği gerektiren çalışma akışlarında rehberlik sağlayan süreçleri modelleyen diyalogların yerine kullanmak için idealdir. Bu süreçlere örnek olarak teklif gözden geçirme ve yeniden yönlendirme verilebilir. 

Alternatif olarak tuval uygulamaları müşteri adayı araştırmak için bir çağrı metni gibi kurallı görevleri modelleyen diyalogları değiştirmek veya bir fırsatı güncelleştirmek gibi diğer görevler için kullanıcı deneyimini basitleştirmek için kullanılabilir. Bu senaryolarda tek başına bir tuval uygulaması dahi kullanılabilir. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Diyalogları iş süreci akışlarıyla değiştirme senaryosu
Birkaç sayfada kullanıcıdan önemli bilgiler isteyen, teklif oluşturan ve müşteriye e-posta ile göndermeden önce gözden geçirenlere teklifi kabul etmeleri veya reddetmeleri için bir e-posta gönderen bir diyaloğunuz olduğunu düşünün. Bu süreç türü, iş süreci akışı kullanılarak daha verimli bir şekilde modellenebilir. 

Diyaloğu değiştirmeye başlamak için sürecin temel aşamalarını tanımlayın. Bu aşamalar tüm ürünlerin listelendiğinden ve indirimlerin uygulandığından emin olmak için kullanılan *İçerik Hazırlama* aşaması, teklifi oluşturmak ve biçim açısından gözden geçirmek için kullanılan *Teklif Oluşturma* aşaması, teklifi gözden geçirme ve onaya göndermek için kullanılan *Birincil Gözden Geçirme* aşaması, belirli durumlarda teklifi gözden geçirmek için kullanılan *İkincil Gözden Geçirme* aşaması ve son olarak teklifi müşteriye göndermek için kullanılan *Teklifi Gönderme* aşaması olabilir.

Ardından kullanıcıların süreçte izlemesi gereken temel adımları tanımlayın. Örneğin *İçerik Hazırlama* aşamasında kullanıcının teklif eklenecek ürünleri tekrar kontrol etmesi için basit bir doğru veya yanlış adımı, fiyat listesi seçmek için zorunlu bir arama adımı ve bir sonraki aşamaya geçmeden önce indirim tutarının girilmesi için bir sayısal adım bulunabilir. *Teklif Oluşturma* aşamasında, *İçerik Hazırlama* aşamasında alınmış olan tüm bilgileri ve ilgili Dynamics 365 kaydını kullanarak teklif oluşturan bir [eylem adımı](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) bulunabilir. *Birincil Gözden Geçirme* ve *İkincil Gözden Geçirme* aşamalarında teklifin gözden geçirilmesine yardımcı olacak birden fazla doğru veya yanlış adımı, onay durumunu almak ve onay alındıktan sonra sürecin bir sonraki aşamaya geçmesi için gerekli bir adım bulunabilir. Bu adımda [alan düzeyi güvenliği](/customer-engagement/admin/field-level-security), teklifi yalnızca yetkili gözden geçirenlerin onaylayabileceği şekilde yapılandırın.  Ayrıca *Birincil Gözden Geçirme* ve *İkincil Gözden Geçirme* aşamalarına girilmesi durumunda tüm gözden geçirenlere bir e-posta gönderilecek şekilde bir iş akışı ekleyebilirsiniz. 

Son olarak iş süreci akışı aşamalarına ve adımlarına ek olarak süreç akışına rehberlik yapacak koşullu mantığı yapılandırın. Bu örnekte *Birincil Gözden Geçirme* aşamasının sonrasında [koşullu dal](enhance-business-process-flows-branching.md) ekleyerek adımda ikinci bir gözden geçirmeye ihtiyaç duyulduğunun belirtilmesi durumunda süreçteki bir sonraki aşamanın *İkincil Gözden Geçirme* aşaması olmasını, aksi takdirde *Teklifi Gönderme* aşaması olmasını sağlayabilirsiniz.

Bu iş süreci akışını kullanıcılara açmak için kullanıcıların iş süreci akışında doğru ayrıcalıklara sahip olduğundan emin olun ve akışı etkinleştirin.

İş süreci akışı oluşturma hakkında daha fazla bilgi için bkz. [Öğretici: Süreçleri standart hale getirmek için bir iş süreci akışı oluşturma](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Diyalogları tuval uygulamalarıyla değiştirme senaryosu

Satış temsilcilerine müşteri adaylarını arama konusunda kılavuzluk yapan bir çağrı metnini takip eden bir diyaloğa sahip olduğunuzu düşünün. Bu süreç tuval uygulaması kullanılarak kolayca yakalanabilir.

Veri okumanız ve yazmanız gereken veri kaynaklarına bağlanarak başlayın. Bu örnekte müşteri adayı, hesap ve iletişim bilgileri için [Dynamics 365 bağlantısı](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) kullanılmıştır.

Gerekli ekran sayısını belirleyerek başlayın. Bu örnek için beş ekran kullanabilirsiniz. 
-   1. ekran. Listeden aranacak müşteri adayını seçmek için.
-   2. ekran. Giriş, görüşme için müsait olup olmadığını sorma ve başka bir tarihe ayarlama yapmak için. 
-   3. ekran. BANT (bütçe, yetki, ihtiyaç ve süre) belirlemek için. 
-   4. ekran. Sonraki adımları almak ve sonraki aramaları zamanlamak için. 
-   5. ekran. Müşteri adayına görüşmenin sonunda zaman ayırdığı için teşekkür etmek için.

Ardından ekranları oluşturmaya başlayın. İlk ekranda aranması gereken müşteri adaylarından oluşan bir [galeri oluşturun](/powerapps/maker/canvas-apps/customize-layout-sharepoint). İkincide ekranı adlandırmak için etiketler kullanın ve çağrı metnini girin. Adayın görüşme için uygun olup olmadığı gibi verileri almak için radyo düğmesi gibi denetimler kullanabilirsiniz. Aday uygunsa koşullu mantık kullanarak bir sonraki ekrana geçilmesini sağlayan bir düğmenin etkinleştirilmesini, uygun değilse aynı ekranda yeni bir arama zamanlamak için kullanılabilecek metnin gösterilmesini sağlayabilirsiniz. Sonraki ekranlarda çağrı metnini benzer şekilde tanımlayabilirsiniz.

Son olarak [ekranlar arasında gezinmeyi tanımlayın](/powerapps/maker/canvas-apps/functions/function-navigate). Bu örnekte ekranlar arasında sıralı olarak geçiş yapmak yerine müşteri adayının teklifle ilgilenmemesi durumunda kullanıcının ikinci ekrandan son ekrana (müşteri adayına zaman ayırdığı için teşekkür etmek üzere metnin sonuna) geçebilmesini istiyor olabilirsiniz.

Kullanıcılara sunmak için uygulamayı yayımlayın. Bu türdeki bir senaryonun çağrı metinleri sunan ve hızlı veri girişi yapılmasını sağlayan bir tek başına uygulamaya dönüştürülebileceği senaryo üzerinde düşünün.

Bu deneyimi Dynamics 365 for Sales hizmetine eklemek istediğinizi düşünün. Bunu yapmak için bir Dynamics 365 for Sales formunda iframe oluşturarak başlayın. Ardından PowerApps menüsünün **Uygulamalar** bölümüne gidin, yayımladığınız uygulamayı seçin, **Ayrıntılar** sekmesindeki web bağlantısını kopyalayın ve iframe URL'si olarak yapıştırın. 

Bunu bir adım ileri götürelim ve bu uygulamanın doğrudan müşteri adayı ana formundan kullanılabilmesini sağlamak istediğinizi ve müşteri adayı bağlamında olarak kullanıcının ilk ekranda müşteri adayı seçme gereksiniminin ortadan kaldırılmasını istediğinizi düşünün. Uygulamaya ilgili bilgileri iletmek için iframe URL'sini müşteri adayı veya hesap kimlikleri gibi bilgileri içeren bir sorgu dizesi ekleyerek değiştirmeniz ve form yüklenmesi gibi belirli olaylarda çalışan bir JavaScript betiği kullanmanız gerekir. Ardından uygulamayı güncelleştirerek ilk ekranı (müşteri adayı seçimi) kaldırmanız ve bunun yerine [Param işlevini](/powerapps/maker/canvas-apps/functions/function-param) kullanarak sorgu dizesi ile uygulamaya iletilmiş olan değerlere erişmeniz gerekir.

## <a name="dialog-replacement-faq"></a>Diyalogları değiştirme hakkında SSS

Tuval uygulamalarındaki bağımlılıklar izlenebilir mi? 
- Tuval uygulamalarındaki bağımlılıklar, Dynamics 365 müşteri etkileşimi bağımlılıkları gibi izlenebilir.

Tuval uygulamasını komut çubuğundaki bir düğmeyle başlatabilir miyim?
- Evet. Bunu yapmak için düğmenin hedef URL'sini yukarıda anlatılan şekilde tuval uygulamanızın **Ayrıntılar** bölümünden aldığınız uygulama URL'si olacak şekilde ayarlamanız gerekir.

Tuval uygulamasından iş akışı çağrılabilir mi?
- Bu özellik desteklenmez. Bunun yerine akış kullanmanızı öneririz. Daha fazla bilgi: [Kullanıcı girişli düğme akışları tanıtımı](button-flow-with-user-input-tokens.md)

Diyalogları otomatik olarak iş süreci akışlarına veya tuval uygulamalarına dönüştürebilir miyim?
- Diyalogları iş süreci akışlarına veya tuval uygulamalarına dönüştürmenin otomatikleştirilmiş bir yöntemi yoktur.


## <a name="see-also"></a>Ayrıca bkz.
[Öğretici: Süreçleri standart hale getirmek için bir iş süreci akışı oluşturma](create-business-process-flow.md) </br>
[PowerApps'te tuval uygulamaları nedir?](/powerapps/maker/canvas-apps/getting-started)


