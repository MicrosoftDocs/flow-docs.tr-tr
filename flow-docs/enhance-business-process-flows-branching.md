---
title: PowerApps kullanarak dallanma ile iş süreci akışlarını geliştirme | MicrosoftDocs
description: İş süreci akışında dallanmanın nasıl kullanılacağını öğrenin
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8911c828b216d8f65210b4c54603fd8838e848b
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65054098"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Öğretici: Dal oluşturma ile iş süreci akışlarını geliştirme

İş süreci akışları; satış, pazarlama veya hizmet süreçlerinin çeşitli aşamalarından tamamlanma aşamasına kadar size yol gösterir. Basit durumlarda, doğrusal bir iş süreci akışı iyi bir seçenektir. Ancak daha karmaşık senaryolarda, dallanma ile bir iş sürecini geliştirebilirsiniz. İş süreci akışlarında oluşturma izinlerine sahipseniz, `If-Else` mantığını kullanarak birden çok dal ile iş süreci akışı oluşturabilirsiniz. Dallanma koşulu, `AND` veya `OR` işleç birleşimini kullanan birden çok mantıksal ifadeden oluşabilir. Dal seçimi, işlem tanımı sırasında tanımlanan kurallara göre gerçek zamanlı olarak otomatik şekilde gerçekleşir. Örneğin, araba satışında, tek bir iş süreci akışı yapılandırabilirsiniz; bu iş süreci akışından sonra genel bir nitelendirme aşaması, bir kurala (Müşteri yeni bir araba mı, ikinci el bir araba mı tercih ediyor, bütçesi 20.000 $’ın üstünde mi altında mı vb.) dayanarak iki ayrı dala bölünür. bir dal, yeni arabaların satışı için; başka bir dal da ikinci el arabaların satışı içindir. İş süreci akışları hakkında daha fazla bilgi için bkz. [İş süreci akışlarına genel bakış](business-process-flows-overview.md).  
  
 Aşağıdaki diyagramda, dallar içeren bir iş süreci akışı gösterilmektedir.  
  
 ![Araba satışı işlemindeki adımları gösteren akış çizelgesi](media/example-car-sales-flow-chart.png "Araba satışı işlemindeki adımları gösteren akış çizelgesi")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Dallar içeren iş süreci akışları tasarlarken bilmeniz gerekenler  
 Dallar içeren iş süreci akışını tasarlarken aşağıdaki bilgilere dikkat edin:  
  
-   Bir işlem en fazla 5 benzersiz varlığa yayılabilir.  
  
-   İşlem başına en fazla 30 aşama ve aşama başına en fazla 30 adım kullanabilirsiniz.  
  
-   Her dal en fazla 5 düzey derinliğinde olabilir.  
  
-   Dallanma kuralı, kendisinden hemen önceki aşamadaki adımları temel almalıdır.  
  
-   Her iki işleci birden değil, ya `AND` işlecini ya da `OR` işlecini kullanarak bir kuralda birden fazla koşulu birleştirebilirsiniz.  
  
-   Bir işlem akışını tanımladığınızda, isteğe bağlı olarak bir varlık ilişkisi seçebilirsiniz. Bu ilişki, 1:N (Bir-Çok) varlık ilişkisi olmalıdır.  
  
-   Aynı veri kaydında birden fazla etkin işlem eş zamanlı olarak çalıştırılabilir.  
  
-   Sürükleyip bırakma işlevini kullanarak işlem akışında kutucukları (Aşamalar, Adımlar, Koşullar vb.) yeniden düzenleyebilirsiniz.  
  
-   Dallar birleştirilirken tüm eş dallar tek bir aşamada birleştirilmelidir. Eş dalların tümü tek bir aşamada birleştirilmeli veya her eş dal, işlemi sonlandırmalıdır. Bir eş dal, diğer dallarla birleştirilemez ve aynı anda işlemi sonlandıramaz.  
  
> [!NOTE]
> - İşlemde kullanılan bir varlık birçok kez yeniden ziyaret edilebilir (birden çok kapalı varlık döngüsü).  
> - Bir işlem, varlık türüne bakılmaksızın önceki aşamaya geri dönebilir. Örneğin, bir teklif kaydında etkin aşama **Teklif Ver** ise, işlem kullanıcıları etkin aşamayı bir fırsat kaydında **Öner** aşamasına geri taşıyabilir.  
>   
>   Bir diğer örnek olarak, süreç akışınızda bir sürecin şu anda **Teklif Sun** aşamasında olduğunu varsayalım: **Müşteri Adayını Uygun Kabul Et** > **Gereksinimleri Belirle** > **Öneri Oluştur** > **Teklif Sun** > **Kapat**. Müşteriye sunulan öneri, müşteri gereksinimlerini tanımlamak için daha fazla araştırma yapılmasını gerektiriyorsa, kullanıcılar işleminizin **Gereksinimleri Tanımla** aşamasını seçip **Etkin Olarak Ayarla** seçeneğini belirleyebilir.  
  
<a name="CarSelling365"></a>   
## <a name="dynamics-365-customer-engagement-example-car-selling-process-flow-with-two-branches"></a>Dynamics 365 müşteri katılımı örneği: İki dalı olan araba satışı süreç akışı
 
Yeni ve ikinci el araba satışı için iki dal içeren iş süreci akışı örneğine göz atalım.  
  
 İlk olarak **Araba Satışı İşlemi** adlı yeni bir işlem oluşturacağız.  
  
1.  [Çözüm gezginini açın](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) ve sonra sol gezinti bölmesinde **İşlemler**’i seçin.  
  
2.  Yeni bir işlem oluşturmak için **Yeni**’yi seçin.  
  
3.  **İş Süreci Akışı** olarak **Kategori**’yi belirtin ve birincil **Varlık** için **Müşteri Adayı** seçeneğini belirleyin.  
  
4.  **Uygun Kabul Et** adlı işleme birinci aşamayı ekleyin ve **Satın Alma Zaman dilimi** ve **Araba Tercihi** adımlarını ekleyin.  
  
5.  Genel **Uygun Kabul Et** aşamasından sonra, **Koşul** kutucuğunu kullanarak işlemi iki ayrı dala böleriz.  
  
    1.  Koşul kutucuğunu, iş gereksinimlerinizi karşılayan kurallarla yapılandırma  
  
    2.  Bir aşamaya yönelik birinci dalı eklemek için, koşul dosyasının “Evet” yoluna bir Aşama kutucuğu ekleyin  
  
    3.  Koşul karşılanmadığında yürütülecek ikinci dalı eklemek için, koşul kutucuğunun “Hayır” yoluna başka bir Aşama kutucuğu ekleyin  
  
> [!TIP]
>  Daha karmaşık dallanma oluşturmak için mevcut bir koşul kutucuğunun “hayır” yoluna başka bir koşul ekleyebilirsiniz.  
  
 ![Oluşturulan Uygun Kabul Et aşamasını gösteren görüntü](media/example-car-sales-qualify-stage.JPG "Oluşturulan Uygun Kabul Et aşamasını gösteren görüntü")  
  
 **Araba tercihi** = **Yeni** olursa işlem, **Yeni Araba Satışı** aşamasına dallanır, aksi takdirde, aşağıda gösterildiği gibi ikinci dalda **İkinci El Araba Satışı** aşamasına atlar.  
  
 ![Yeni Araba Satışı aşamasını gösteren görüntü](media/example-car-sales-new-stage-1.JPG "Yeni Araba Satışı aşamasını gösteren görüntü")  
  
 ![İkinci el araba satışı aşaması](media/example-car-sales-pre-owned-stage.JPG "İkinci el araba satışı aşaması")  
  
 **Yeni Araba Satışı** aşamasındaki veya **İkinci El Araba Satışı** aşamasındaki tüm adımlar tamamlandıktan sonra işlem, **Teklif Ver** aşaması ile ana akışa geri döner.  
  
 ![Teklif Ver aşaması](media/example-car-sales-deliver-quote-stage.JPG "Teklif Ver aşaması")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Bilgilerin açığa çıkmasını önleme  
 Aşağıda gösterildiği gibi, bir bankadaki kredi isteğini işlemeye yönelik dallar içeren bir iş süreci akışını düşünün. Aşamalarda kullanılan özel varlıklar, parantez içinde gösterilmektedir.  
  
 ![Bilgilerin açığa çıkmasını önlemek için örnek bir işlemdeki adımları gösteren akış çizelgesi](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Bilgilerin açığa çıkmasını önlemek için örnek bir işlemdeki adımları gösteren akış çizelgesi")  
  
 Bu senaryoda, banka kredi yetkilisinin İstek kaydına erişmesi gerekir, ancak bu yetkilinin istek araştırmasını görmemesi gerekir. İlk bakışta, kredi yetkilisine, araştırma varlığına erişim belirtmeyen bir güvenlik rolü atayarak kolayca bunu yapabilirsiniz gibi görünüyor. Ancak örneğe daha ayrıntılı şekilde bakalım ve bu durumun doğru olup olmadığını görelim.  
  
 Bir müşterinin bankaya 60.000 $ üzerinde kredi isteğinde bulunduğunu varsayalım. Kredi yetkilisi ilk aşamada isteği gözden geçirir. Bankaya borçlanılan tutarın 50.000 $’ı aşıp aşmadığını denetleyen dallanma kuralı karşılanırsa, işlemdeki sonraki aşama, isteğin sahtekarlık amaçlı olup olmadığının araştırılmasıdır. Bunun gerçekten sahtekarlık durumu olduğu belirlenirse, işlem, istekte bulunana karşı hukuki işlem yapılması aşamasına ilerler. Kredi yetkilisinin Araştırma varlığına erişimi olmadığından iki araştırma aşamasını görmemesi gerekir.  
  
 Ancak kredi yetkilisi İstek kaydını açarsa herkes uçtan uca işlemin tamamını görebilir. Kredi yetkilisi yalnızca sahtekarlık araştırması aşamasını görebilmekle kalmaz, aynı zamanda işlemdeki Hukuki İşlem aşamasını görebilir ve araştırmanın sonucunu da belirleyebilir. Ayrıca aşamayı seçerek araştırma aşamalarındaki adımların önizlemesini de görüntüleyebilir. Kredi yetkilisi verileri veya adımın tamamlanma durumunu göremese de, araştırma ve hukuki işlem aşamalarında isteği gönderene karşı uygulanan olası eylemleri belirleyebilir.  
  
 Bu işlem akışında kredi yetkilisi, uygunsuz şekilde bilgilerin açığa çıkmasına neden olan Sahtekarlık Araştırması ve Hukuki İşlem aşamalarını görebilir. Dallanma nedeniyle açığa çıkabilecek bilgilere özellikle dikkat edilmesini öneririz. Bizim örneğimizde, bilgilerin açığa çıkmasını önlemek için işlemi iki ayrı işleme bölüyoruz; biri istek işleme için, diğeri ise sahtekarlık araştırması içindir. Kredi yetkilisi için işlem şöyle görünür:  
  
 ![Bilgilerin açığa çıkmasını önleme işlemindeki ek adımları gösteren akış çizelgesi](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Bilgilerin açığa çıkmasını önleme işlemindeki ek adımları gösteren akış çizelgesi")  
  
 Araştırma işlemi kendi içindedir ve aşağıdaki aşamaları içerir:  
  
 ![Bilgilerin açığa çıkması durumları için araştırma işlemine ilişkin adımları gösteren akış çizelgesi](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Bilgilerin açığa çıkması durumları için araştırma işlemine ilişkin adımları gösteren akış çizelgesi")  
  
 Araştırma kaydından İstek kaydına Onaylama/Reddetme kararını eşitlemek için bir iş akışı sağlamanız gerekir.  
  
### <a name="next-steps"></a>Sonraki adımlar  
 [İş süreci akışı oluşturma](create-business-process-flow.md)   
 [İşlemler ile özel iş mantığı oluşturma](guide-staff-through-common-tasks-processes.md)   
 
