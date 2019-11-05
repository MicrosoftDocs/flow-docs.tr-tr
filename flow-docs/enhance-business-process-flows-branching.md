---
title: PowerApps ile Dalla iş süreci akışlarını geliştirin | MicrosoftDocs
description: Bir iş süreci akışında dallanmayı kullanmayı öğrenin
ms.custom: ''
ms.date: 06/27/2018
ms.tgt_pltfrm: ''
ms.topic: article
ms.service: flow
author: MSFTMAN
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: Deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c3a03cefcb3e808bb7900b79b05e6c2b3f8ef7f5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544775"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Öğretici: Dalla iş süreci akışlarını geliştirin
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

İş süreci akışları, çeşitli satış, pazarlama veya hizmet işlemlerinin tamamlanmasına yönelik çeşitli aşamalarda size rehberlik sağlar. Basit durumlarda, doğrusal bir iş süreci akışı iyi bir seçenektir. Ancak, daha karmaşık senaryolarda, dalla bir iş süreci akışını geliştirebilirsiniz. İş süreci akışlarında oluşturma izinleriniz varsa, `If-Else` mantığını kullanarak birden çok dalı olan iş süreci akışı oluşturabilirsiniz. Dallanma koşulu, `AND` veya `OR` işleçlerinin birleşimini kullanan birden çok mantıksal ifadenin oluşturulabilir. Dal seçimi, işlem tanımı sırasında tanımlanan kurallara göre otomatik olarak gerçek zamanlı olarak yapılır. Örneğin, otomobillerin satılırken, ortak bir sektör aşaması bir kural temelinde iki ayrı dala bölündüğünü (müşteri yeni bir otomobil veya önceden sahip bir otomobil tercih ettiği, $20.000 vb. ), bir dalı, yeni otomobilleri ve başka bir dalı satmaya yönelik, önceden sahip olan otomobilleri satmaya yönelik Iş süreci akışları hakkında daha fazla bilgi için bkz. [iş işleme akışlarına genel bakış](business-process-flows-overview.md).  
  
 Aşağıdaki diyagramda dallarla bir iş süreci akışı gösterilmektedir.  
  
 ![Araba satışları işlemindeki adımları gösteren akış çizelgesi](media/example-car-sales-flow-chart.png "Araba satışları işlemindeki adımları gösteren akış çizelgesi")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Dallarla iş süreci akışlarını tasarlarken bilmeniz gerekenler  
 Şubelerle iş süreci akışını tasarlarken aşağıdaki bilgileri görebilirsiniz:  
  
-   Bir işlem, en fazla 5 benzersiz varlık arasında yayılabilir.  
  
-   İşlem başına en fazla 30 aşama ve her aşama için en fazla 30 adım kullanabilirsiniz.  
  
-   Her dal, 5 düzeyden daha derin olamaz.  
  
-   Dallanma kuralı, aşamadaki hemen önce gelen adımlara dayalı olmalıdır.  
  
-   Bir kuralda birden çok koşulu, `AND` işlecini veya `OR` işlecini (her iki işleçle değil) kullanarak birleştirebilirsiniz.  
  
-   Bir işlem akışı tanımladığınızda, isteğe bağlı olarak bir varlık ilişkisi seçebilirsiniz. Bu ilişki 1: N (bire çok) varlık ilişkisine sahip olmalıdır.  
  
-   Aynı veri kaydında birden fazla etkin işlem aynı anda çalışabilir.  
  
-   Sürükle ve bırak ile işlem akışındaki kutucukları (aşamalar, adımlar, koşullar vb.) yeniden düzenleyebilirsiniz.  
  
-   Dallar birleştirilirken tüm eş dalların tek bir aşamaya birleştirilmesi gerekir. Eş dalların hepsi tek bir aşamada birleştirilmelidir, ya da her eş dalı işlemi sonlandırmalıdır. Bir eş dal, diğer dallarla birleştirilemez ve aynı anda işlemi sonlandırın.  
  
> [!NOTE]
> - İşlemde kullanılan bir varlık birden çok kez yeniden ziyaret edilebilir (birden çok kapalı varlık döngüsü).  
> - Bir işlem, bir varlık türünden bağımsız olarak önceki aşamaya geri dönebilir. Örneğin, etkin aşama teklif kaydında **teklif sunduğunuzda** , işlem kullanıcıları etkin aşamayı bir fırsat kaydındaki **teklif aşamasına geri** taşıyabilirler.  
>   
>   Başka bir örnekte, şu anda işlem akışındaki **mevcut teklif** aşamasında bir işlem olduğunu varsayalım: **müşteri adayını nitelendir** > **Ihtiyaçları belirlemek** >  teklif > **sunma teklifi** oluştur >  **Kapatın**. Müşteriye sunulan teklif, müşteri ihtiyaçlarını belirlemek için daha fazla araştırma gerektiriyorsa, kullanıcılar yalnızca işleminizin **Ihtiyaçlarını belirle** aşamasını seçebilir ve **etkin ayarla**' yı seçebilirler.  
  
<a name="CarSelling365"></a>   
## <a name="example-car-selling-process-flow-with-two-branches"></a>Örnek: iki Dalla işlem akışını satan otomobil
 
Yeni ve önceden sahip olan otomobilleri satmaya yönelik olarak iki Dalla iş süreci akışı örneğine bakalım.  
  
 İlk olarak, **otomobil Sales Process**adlı yeni bir işlem oluşturacağız.  
  
1.  [Çözüm Gezgini](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) ' ni açın ve ardından sol gezinti bölmesinde **süreçler**' ı seçin.  
  
2.  Yeni bir işlem oluşturmak için **Yeni** ' yi seçin.  
  
3.  **Kategoriyi** **iş süreci akışı** olarak belirtin ve birincil **varlık** için **müşteri adayı**' nı seçin.  
  
4.  Hazırlama ve adım **satın alma zamanı çerçevesi** ve **otomobil tercihi** **adlı işleme** ilk aşamayı ekleyin.  
  
5.  Ortak **niteleme** aşamasından sonra, **koşul** kutucuğunu kullanarak işlemi iki ayrı dala böyoruz.  
  
    1.  Koşul kutucuğunu iş gereksinimlerinizi karşılayan kurallarla yapılandırın  
  
    2.  Bir aşamanın ilk dalını eklemek için koşul kutucuğunun "Evet" yoluna bir aşama kutucuğu ekleyin  
  
    3.  Koşul karşılanmadığı zaman yürütülen ikinci dalı eklemek için koşul kutucuğunun "Hayır" yoluna başka bir aşama kutucuğu ekleyin  
  
> [!TIP]
>  Daha karmaşık dallandırma oluşturmak için var olan koşul kutucuğunun "Hayır" yoluna başka bir koşul ekleyebilirsiniz.  
  
 ![Oluşturulan uygun bulma aşamasını gösteren resim](media/example-car-sales-qualify-stage.JPG "Oluşturulan uygun bulma aşamasını gösteren resim")  
  
 **Araba tercihi** **Yeni** = , işlem **Yeni araba satışları** aşamasına dallandırır, aksi takdirde, Ikinci dalda aşağıda gösterildiği gibi, **önceden sahip olan araba satış** aşamasına atlar.  
  
 ![Yeni araba satışı aşamasını gösteren resim](media/example-car-sales-new-stage-1.JPG "Yeni araba satışı aşamasını gösteren resim")  
  
 ![Ön&#45;sahip olan araba satış aşaması](media/example-car-sales-pre-owned-stage.JPG "Önceden sahip olan otomobil satış aşaması")  
  
 **Yeni araba satış** aşamasındaki veya **önceden sahip olan araba satışları** aşamasındaki tüm adımları tamamladıktan sonra, işlem **teklif teklifi** aşamasına sahip ana akışa geri döner.  
  
 ![Teklif aşaması sunma](media/example-car-sales-deliver-quote-stage.JPG "Teklif aşaması sunma")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Bilgilerin açığa çıkmasına engel  
 Aşağıda gösterildiği gibi, bir bankadaki kredi isteğini işlemeye yönelik dallarla bir iş süreci akışını göz önünde bulundurun. Aşamalarda kullanılan özel varlıklar parantez içinde gösterilir.  
  
 ![Bilgilerin açığa çıkmasını önleyen örnek bir işlemin adımlarını gösteren akış grafiği](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Bilgilerin açığa çıkmasını önleyen örnek bir işlemin adımlarını gösteren akış grafiği")  
  
 Bu senaryoda, banka kredisi Müdürü, Istek kaydına erişmesi gerekir, ancak kredi Müdürü istek araştırmasına ilişkin görünürlüğe sahip olmamalıdır. İlk bakışta, kredi kurumunun araştırma varlığına erişimi olmadığını belirten bir güvenlik rolü atayarak bunu kolayca yapabiliriz. Ancak, daha ayrıntılı bir şekilde örneğe bakalım ve bunun gerçekten doğru olup olmadığına bakın.  
  
 Bir müşterinin krediden $60.000 ' e kadar kredi isteğini iade edelim. Kredi Müdürü, isteği ilk aşamada inceler. Bankaya borçlu olunan tutarın $50.000 ' i aşıp aşmadığını kontrol eden dallanma kuralı karşılanmazsa, sürecin bir sonraki aşaması isteğin sahte olup olmadığını araştırmaktır. Bunun gerçekten sahtekarlık durumunda olduğunu tespit ediyorsanız, işlem istek sahibine karşı yasal bir eylem gerçekleştirmek için hareket eder. Kurumun araştırma varlığına erişimi olmadığından, kredi Müdürü iki araştırma aşamasına yönelik görünürlüğe sahip olmamalıdır.  
  
 Ancak, kredi Müdürü Istek kaydını açarsa, tümü uçtan uca işlemin tamamını görebilir. Yalnızca, kredi Müdürü sahtekarlık araştırma aşamasını göremez, ancak işlemdeki yasal eylem aşamasını görebilerek araştırmanın sonucunu da tanımlayabilecektir. Ayrıca, müdürü, aşamayı seçerek araştırma aşamalardaki adımların önizlemesini yapabilir. Kredi Müdürü verileri veya adım tamamlanma durumunu göremeyecek olsa da, araştırma ve yasal eylem aşamaları sırasında isteğin gönderenine karşı alınan olası eylemleri tanımlayabilecektir.  
  
 Bu işlem akışında, kredi Müdürü, yanlış bir bilginin açığa çıkmasına neden olan sahtekarlık araştırmasını ve yasal eylem aşamalarını görebilir. Dallandırma nedeniyle açıklanabilir olabilecek bilgilere özel bir dikkat ödemenizi öneririz. Bizim örneğimizde, bir tane, istek işleme için bir diğeri ve sahtekarlık araştırması için başka bir tane olmak üzere, bilgilerin açığa çıkmasını önlemek için işlemi iki ayrı işleme ayırın. Kredi Müdürü süreci şöyle görünür:  
  
 ![Bilgilerin açığa çıkmasına engel olmak için işlemdeki ek adımları gösteren akış grafiği](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Bilgilerin açığa çıkmasına engel olmak için işlemdeki ek adımları gösteren akış grafiği")  
  
 Araştırma süreci, kendi içinde olacaktır ve aşağıdaki aşamaları içerir:  
  
 ![Bilgi açıklama durumları için araştırma işleminin adımlarını gösteren akış grafiği](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Bilgi açıklama durumları için araştırma işleminin adımlarını gösteren akış grafiği")  
  
 Araştırma kaydından Istek kaydına onay/reddetme kararı eşitlenmesi için bir iş akışı sağlamanız gerekir.  
  
### <a name="next-steps"></a>Sonraki adımlar  
 [İş süreci akışı oluşturma](create-business-process-flow.md)   
 [İşlemlerle özel iş mantığı oluşturma](guide-staff-through-common-tasks-processes.md)   
 
