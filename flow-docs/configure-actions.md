---
title: PowerApps’te iş akışları için eylemler yapılandırma | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
author: Mattp123
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
caps.latest.revision: 19
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c1b8686000b7723f2d942f3c6c5ebe685d98429d
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462936"
---
# <a name="configure-custom-actions-from-a-workflow"></a>Bir iş akışından özel eylemler yapılandırma

Kod yazmadan bir iş akışından özel eylemi etkinleştirebilirsiniz. Daha fazla bilgi: [Bir iş akışından özel eylemler çağırma](invoke-custom-actions-workflow-dialog.md).  
  
 Bir geliştiricinin kod içinde kullanabilmesi için de bir eylem oluşturabilirsiniz veya önceden tanımlanmış olan bir eylemi düzenlemeniz gerekebilir. İş akışı işlemlerine benzer şekilde aşağıdakileri göz önünde bulundurun:  
  
-   Eylem ne yapmalıdır?  
  
-   Hangi koşullar altında eylem gerçekleştirilmelidir?  
  
 
İş akışı işlemlerinden farklı şekilde, aşağıdaki seçenekleri ayarlamanız gerekmez:  
  
- **Başlangıç Zamanı**: Kod, kendisi için oluşturulan iletiyi çağırdığında eylemler başlar.  
  
- **Kapsam**: Eylemler her zaman çağıran kullanıcı bağlamında çalıştırılır.  
  
- **Arka planda çalıştır**: Eylemler her zaman gerçek zamanlı iş akışlarıdır.  
  
Eylemler, iş akışı işlemlerinde olmayan bir şeye de sahiptir; giriş ve çıkış bağımsız değişkenleri. Daha fazla bilgi: [İşlem bağımsız değişkenlerini tanımlama](configure-actions.md#BKMK_DefineProcessArgs)  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Eylem oluşturma  
  
> [!IMPORTANT]
>  Dağıtılacak bir çözümün parçası olarak bir eylem oluşturuyorsanız, bunu çözüm bağlamında oluşturun. **[Ayarlar](/powerapps/maker/model-driven-apps/advanced-navigation#settings)** > **Çözümler** bölümüne gidin ve bu eylemin parçası olacağı yönetilmeyen çözümü bulun. Daha sonra menü çubuğunda **Yeni** > **İşlem** seçeneğini belirleyin. Böylece, eylemin adıyla ilişkili özelleştirme önekinin, çözümdeki diğer bileşenlerle tutarlı olması sağlanır. Eylemi oluşturduktan sonra öneki değiştiremezsiniz.  
  
 İş akışı işlemlerine benzer şekilde eylemler, **İşlem Oluştur** iletişim kutusunda aşağıdaki özelliklere sahiptir.  
  
 **İşlem adı**  
 İşlem için bir ad girmenizin ardından, işlem adından boşluklar veya özel karakterler kaldırılarak işlem için benzersiz bir ad oluşturulur.  
  
 **Kategori**  
 Bu özellik, bunun bir eylem işlemi olduğunu belirler. İşlemi kaydettikten sonra bunu değiştiremezsiniz.  
  
 **Varlık**  
 Eylemler işlemleri ile, diğer işlem türleri gibi iş akışının bağlamını sağlamak için bir varlık seçebilirsiniz, ancak **Hiçbiri (global)** seçeneğini tercih etme seçeneğiniz de vardır. Eyleminiz belirli bir varlığın bağlamını gerektirmiyorsa bunu kullanın. İşlemi kaydettikten sonra bunu değiştiremezsiniz.  
  
 **Tür**  
 Sıfırdan yeni bir eylem oluşturma veya mevcut bir şablondan başlama arasında seçim yapmak için bu özelliği kullanın.  
  
<a name="edit"></a>   
## <a name="edit-an-action"></a>Eylemi düzenleme  
 İşlemleri düzenleyebilmeniz için önce devre dışı bırakmanız gerekir.  
  
 Yönetilmeyen çözümün parçası olarak oluşturulan veya kuruluşunuzda yüklenmiş olan bir çözüme dahil edilen bir eylemi düzenleyebilirsiniz. Çözüm, yönetilen bir çözümse onu düzenleyemeyebilirsiniz. Çözüm yayımcısı, yönetilen çözüm ile yüklenen eylem düzenlenemeyecek şekilde, yönetilen özellikleri düzenleme seçeneğine sahiptir.  
  
 Bir eylem kaydedilirken, işlem adını temel alan benzersiz bir ad oluşturulur. Bu benzersiz ad, çözüm yayımcısından eklenen özelleştirme önekini içerir. Bu, bir geliştiricinin kodunda kullanacağı iletinin adıdır.  
  
 Bir eylemi düzenlerken aşağıdaki seçenekleriniz vardır:  
  
 **İşlem Adı**  
 İşlem oluşturulduktan ve işlem adından benzersiz ad oluşturulduktan sonra işlem adını düzenleyebilirsiniz. Belirli işlemlerin bulunmasını kolaylaştırmak için bir adlandırma kuralı da uygulamak isteyebilirsiniz.  
  
 **Benzersiz Ad**  
 Bir eylem kaydedilirken, işlem adını temel alan benzersiz bir ad oluşturulur. Bu benzersiz ad, çözüm yayımcısından eklenen özelleştirme önekini içerir. Bu, bir geliştiricinin kodunda kullanacağı iletinin adıdır. İşlem etkinleştirildiyse ve bu adı kullanan eylemin çağrılmasını bekleyen kod mevcutsa bu benzersiz adı değiştirmeyin.  
  
> [!IMPORTANT]
>  Eylem etkinleştirildikten ve benzersiz bir ad kullanmak üzere kod yazıldıktan sonra kendisine başvuran kod da değiştirilmeden benzersiz kod değiştirilmemelidir.  
  
 **Geri almayı etkinleştir**  
 Genellikle, işlem hareketlerini destekleyen işlemler, herhangi bir kısmının başarısız olması durumunda işlemin tamamını “geri alır”. Bu durumun bazı istisnaları vardır. Geliştiricilerin, eylem tarafından başlatılan kodda yapabileceği bazı eylemler, işlem hareketlerini desteklemeyebilir. Örneğin, kod, işlem hareketi kapsamının ötesindeki diğer sistemlerde eylemler gerçekleştiriyorsa. Bunlar, bir uygulamada çalıştırılan eylem tarafından geri alınamaz. Platformdaki bazı iletiler, işlem hareketlerini desteklemez. Ancak eylemin kullanıcı arabirimi ile yapabileceğiniz her şey, işlem hareketlerini destekler. Gerçek zamanlı bir iş akışının parçası olan tüm eylemlerin işlem hareketi içinde olduğu düşünülür, ancak eylemler ile, bunu iptal etme seçeneğine sahip olursunuz.  
  
 İşlem hareketi içinde olup olmaması gerektiğini belirlemek için bu iletiyi kullanacak geliştiriciye danışmanız gerekir. Genellikle, tümü başarıyla tamamlanmadığı sürece iş süreci tarafından gerçekleştirilen eylemler mantıklı değilse eylem, işlem hareketi içinde olmalıdır. İki banka hesabı arasında para transferi buna klasik bir örnektir. Bir hesaptan para çekerseniz, diğerine parayı yatırmanız gerekir. Herhangi biri başarısız olursa, her ikisi de başarısız olmuş olur.  
  
> [!NOTE]
>  Doğrudan bir iş akışının içinden bir özel eylem çağrılırsa geri almayı etkinleştiremezsiniz. Bir PowerApps web hizmetleri iletisi tarafından bir eylem tetiklenirse geri almayı etkinleştirebilirsiniz.  
  
 **Farklı Etkinleştir**  
 Tüm işlemlere benzer şekilde, bir şablon olarak işlemi etkinleştirebilir ve benzer bir deseni izleyen işlemler için gelişmiş bir başlangıç noktası olarak bunu kullanabilirsiniz.  
  
 **İşlem Bağımsız Değişkenlerini Tanımla**  
 Bu alanda, eylemin başlatması beklenen verileri ve eylemden hangi verilerin geçirileceğini belirteceksiniz. Daha fazla bilgi: [İşlem bağımsız değişkenlerini tanımlama](configure-actions.md#BKMK_DefineProcessArgs)  
  
 **Aşamalar, Koşullar ve Eylemler Ekle**  
 Diğer işlemlere benzer şekilde, hangi eylemlerin ne zaman gerçekleştirileceğini belirtirsiniz. Daha fazla bilgi: [Aşamalar, koşullar ve eylemler ekleme](configure-actions.md#BKMK_AddStagesConditionsAndActions)

<a name="BKMK_DefineProcessArgs"></a>   
### <a name="define-process-arguments"></a>İşlem bağımsız değişkenlerini tanımlama  
 Bir geliştirici bir ileti kullandığında, iletiye geçirebileceği bazı verilerle başlayabilir. Örneğin, yeni bir durum kaydı oluşturmak için, giriş bağımsız değişkeni olarak geçirilen durum başlığı değeri olabilir.  
  
 İleti tamamlandığında geliştiricinin, ileti tarafından oluşturulan bazı verileri, kodundaki başka bir işleme geçirmesi gerekebilir. Bu veriler, çıkış bağımsız değişkenidir.  
  
 Hem giriş hem de çıkış bağımsız değişkenlerinin bir adı, türü ve bağımsız değişkenin her zaman gerekli olup olmadığına dair bazı bilgileri olması gerekir. Bir açıklama da sağlayabilirsiniz.  
  
 İletinin adı ve tüm işlem bağımsız değişkenleriyle ilgili bilgiler, iletinin “imzasını” temsil eder. Bir eylem etkinleştirilip kodda kullanıldıktan sonra imza değişmemelidir. Bu imza değişirse, iletiyi kullanan tüm kodlar başarısız olur. Buna tek istisna, parametrelerden birinin her zaman gerekli olmayacak şekilde değiştirilmesi olabilir.  
  
 Bağımsız değişkenler sıralamaya göre değil, ada göre belirlendiğinden, bağımsız değişkenleri sıralayarak veya yukarı ya da aşağı taşıyarak bağımsız değişkenlerin sırasını değiştirebilirsiniz. Ayrıca açıklama değiştirildiğinde, iletiyi kullanan kod bozulmaz.  
  
#### <a name="action-process-argument-types"></a>Eylem işlemi bağımsız değişken türleri  
 Aşağıdaki tabloda, eylem işlemi bağımsız değişken türleri açıklanmaktadır.  
  
|Tür|Açıklama|  
|----------|-----------------|  
|Boole|Bir `true` veya `false` değeri.|  
|DateTime|Tarih ve saat bilgilerini depolayan bir değerdir.|  
|Ondalık|Ondalık duyarlığa sahip bir sayı değeridir. Duyarlık son derece önemli olduğunda kullanılır.|  
|Varlık|Belirtilen varlık için bir kayıttır. Varlığı seçtiğinizde açılır liste etkinleştirilir ve varlık türünü seçmenize olanak sağlar.|  
|EntityCollection|Varlık kayıtlarının koleksiyonudur.|  
|EntityReference|Kendisini benzersiz olarak tanımlayan ad, kimlik ve varlık kaydı türünü içeren bir nesnedir. EntityReference seçtiğinizde açılır liste etkinleştirilir ve varlık türünü seçmenize olanak sağlar.|  
|Kayan|Ondalık duyarlığa sahip bir sayı değeridir. Veriler, mutlak kesin olmayan bir ölçümden geldiğinde kullanılır.|  
|Tamsayı|Bir tamsayıdır.|  
|Para|Para tutarıyla ilgili verileri depolayan bir değerdir.|  
|Seçim Listesi|Bir OptionSet özniteliği için seçeneği temsil eden bir değerdir.|  
|Dize|Bir metin değeridir.|  
  
> [!NOTE]
> **EntityCollection** bağımsız değişken değerleri, koşullar veya eylemler için kullanıcı arabiriminde ayarlanamaz. Bunlar geliştiriciler tarafından özel kodda kullanılmak üzere sağlanır. Daha fazla bilgi: [Kendi eylemlerinizi oluşturma](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Aşamalar ve adımlar ekleme  
 Eylemler, gerçek zamanlı iş akışlarına çok benzer bir işlem türüdür. Gerçek zamanlı iş akışlarında kullanılabilen tüm adımlar, eylemlerde kullanılabilir. Hem gerçek zamanlı iş akışları hem de eylemler için kullanılabilen adımlar hakkında bilgi için bkz. [İş akışı aşamaları ve adımları](configure-workflow-steps.md).  
  
 Eylemler, gerçek zamanlı iş akışları için kullanılabilen adımlara ek olarak **Değer Ata** adımını da içerir.  Eylemlerde bunlar yalnızca çıkış bağımsız değişkenlerini ayarlamak için kullanılabilir. Çıkış değişkenlerini belirli değerlere veya büyük ihtimalle, eylemin çalıştırıldığı kayıttaki, çok-bir ilişkisi olan bu kayıtla ilgili kayıttaki, önceki bir adımda oluşturulan kayıtlardaki değerlere veya işlemin parçası olan değerlere ayarlamak için form yardımcısını kullanabilirsiniz.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 [Eylemler](actions.md)  

 [Bir iş akışından özel eylemler çağırma](invoke-custom-actions-workflow-dialog.md) .  
 [Gerçek zamanlı iş akışlarını ve eylemleri izleme](monitor-manage-processes.md#BKMK_MonitorSyncWorkflows)
 
 
