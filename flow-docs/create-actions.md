---
title: Özel eylem Oluştur | MicrosoftDocs
description: Sistemde bir dizi komutu otomatikleştirmek istediğinizde özel eylemleri kullanın. Eylemler, geliştiricilerin iş süreçlerini ifade etmek için kullanılabilir olan sözlüğü genişletir.
ms.custom: ''
ms.date: 08/06/2018
ms.reviewer: matp
ms.service: flow
ms.topic: article
author: msftman
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8b00e6e0b3ca2da357eb98d1b6de7756ff5cc75
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546814"
---
# <a name="create-a-custom-action"></a>Özel eylem oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Sistemde bir dizi komutu otomatikleştirmek istediğinizde özel eylemleri kullanın. Eylemler, geliştiricilerin iş süreçlerini ifade etmek için kullanılabilir olan sözlüğü genişletir. Sistem tarafından sunulan oluşturma, güncelleştirme, silme ve atama gibi temel yüklemler sayesinde, bir eylem onaylama, Ilerleme, yönlendirme veya zamanlama gibi daha açıklayıcı fiiller oluşturmak için bu temel fiilleri kullanır. Bir iş işleminin tanımı değişirse, geliştirici olmayan birisi özel eylemi düzenleyerek kodun değiştirilmesine gerek kalmaz.  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Eylem oluşturma  
  
> [!IMPORTANT]
>  Dağıtılacak bir çözümün parçası olarak dahil etmek için bir eylem oluşturuyorsanız, çözümü bağlamında oluşturun. **[Ayarlar](/powerapps/maker/model-driven-apps/advanced-navigation#settings)**  > **çözümler** ' e gidin ve bu eylemin parçası olacak yönetilmeyen çözümü bulun. Ardından, menü çubuğunda **yeni** > **işlem**' i seçin. Bu, eylemin adı ile ilişkili özelleştirme ön ekinin çözümdeki diğer bileşenlerle tutarlı olmasını sağlar. Eylemi oluşturduktan sonra, öneki değiştiremezsiniz.  
  
 İş akışı işlemleri gibi eylemler, **Işlem oluştur** iletişim kutusunda aşağıdaki özelliklere sahiptir.  
  
 **İşlem adı**  
 İşlem için bir ad girdikten sonra, işlem adından herhangi bir boşluk veya özel karakter kaldırılarak benzersiz bir ad oluşturulur.  
  
 **Alan**  
 Bu özellik bu bir eylem işlemi olduğunu belirler. İşlemi kaydettikten sonra bunu değiştiremezsiniz.  
  
 **Varlığının**  
 Eylem işlemleriyle, diğer işlem türleri gibi iş akışı için bağlam sağlamak üzere bir varlık seçebilirsiniz, ancak **hiçbiri (genel)** seçeneğini de belirleyebilirsiniz. Eyleminiz belirli bir varlığın bağlamını gerektirmiyorsa bunu kullanın. İşlemi kaydettikten sonra bunu değiştiremezsiniz.  
  
 **Türüyle**  
 Sıfırdan yeni bir eylem oluşturulup oluşturulmayacağını veya var olan bir şablondan başlatmayı seçmek için bu özelliği kullanın.  
 
İş akışı işlemlerinden farklı olarak, aşağıdaki seçenekleri ayarlamanız gerekmez:  
  
- **Başlama zaman**: kod, bunlar için oluşturulan iletiyi çağırdığında eylemler başlar.  
  
- **Kapsam**: eylemler her zaman çağıran kullanıcı bağlamında çalıştırılır.  
  
- **Arka planda çalıştır**: eylemler her zaman gerçek zamanlı iş akışlarıdır.  
  
Eylemler, iş akışı işlemlerinin değil, giriş ve çıkış bağımsız değişkenleri olan bir şeyi de vardır.

> [!NOTE]
> Kod yazmadan bir iş akışından özel bir eylemi etkinleştirebilirsiniz. Daha fazla bilgi: [bir iş akışından özel eylemler çağırma](invoke-custom-actions-workflow-dialog.md).
 
<a name="edit"></a>   
## <a name="edit-an-action"></a>Bir eylemi düzenleme  
 Öğeleri düzenleyebilmeniz için önce devre dışı bırakmanız gerekir.  
  
 Yönetilmeyen bir çözümün parçası olarak oluşturulmuş veya kuruluşunuzda yüklü bir çözüme dahil olan bir eylemi düzenleyebilirsiniz. Çözüm yönetilen bir çözümse, onu düzenleyemeyebilirsiniz. Çözüm yayımcısı, yönetilen bir çözümle yüklenen eylemin düzenlenememesi için yönetilen özellikleri düzenleme seçeneğine sahiptir.  
  
 Bir eylem kaydedildiğinde, işlem adına göre benzersiz bir ad oluşturulur. Bu benzersiz ad, çözüm yayımcısından eklenen özelleştirme ön ekine sahiptir. Bu, bir geliştiricinin kodda kullanacağı iletinin adıdır.  
  
 Bir eylem düzenlenirken aşağıdaki seçeneklere sahip olursunuz:  
  
 **İşlem adı**  
 İşlem oluşturulduktan ve işlem adından benzersiz ad oluşturulduktan sonra, işlem adını düzenleyebilirsiniz. Belirli işlemlerin yerini daha kolay bulabilmek için bir adlandırma kuralı uygulamak isteyebilirsiniz.  
  
 **Benzersiz ad**  
 Bir eylem kaydedildiğinde, işlem adına göre benzersiz bir ad oluşturulur. Bu benzersiz ad, çözüm yayımcısından eklenen özelleştirme ön ekine sahiptir. Bu, bir geliştiricinin kodda kullanacağı iletinin adıdır. İşlem etkinleştirildiyse bu benzersiz adı değiştirmeyin ve bu adı kullanarak eylemi çağırmak beklenirken kod yerinde olur.  
  
> [!IMPORTANT]
>  Eylem etkinleştirildikten ve kod benzersiz bir ad kullanacak şekilde yazıldıktan sonra, benzersiz adın buna başvuran kodu değiştirmeden değiştirilmemelidir.  
  
 **Geri almayı etkinleştir**  
 Genellikle, işlemleri destekleyen işlemler, herhangi bir parçası başarısız olursa tüm işlemi "geri alır" veya geri alır. Bunun için bazı özel durumlar vardır. Geliştiriciler tarafından başlatılan kodda olabilecek bazı eylemler işlemleri desteklemeyebilir. Örneğin, kod, işlem kapsamının ötesinde diğer sistemlerde eylemler gerçekleştirir. Bunlar bir uygulamada çalışan eylem tarafından geri alınamaz. Platformdaki bazı iletiler işlemleri desteklemez. Ancak yalnızca eylemin Kullanıcı arabirimiyle yapabileceğiniz her şey işlemleri destekleyecektir. Gerçek zamanlı bir iş akışının parçası olan tüm eylemler işlemde kabul edilir, ancak eylemlerle bunu devre dışı bırakmak için seçeneğiniz vardır.  
  
 İşlem içinde olup olmadığını öğrenmek için bu iletiyi kullanacak geliştiriciye danışmanız gerekir. Genellikle, iş süreci tarafından gerçekleştirilen eylemler, hepsi başarıyla tamamlanmamışsa mantıklı bir işlem olmalıdır. Klasik örnek, fonları iki banka hesabı arasında aktarıyordu. Bir hesaptan gelen fonları geri alırsanız, bunları diğer hesaba yatırmalısınız. Her ikisi de başarısız olursa, her ikisi de başarısız olmalıdır.  
  
> [!NOTE]
>  Özel bir eylem doğrudan bir iş akışı içinden çağrılırsa geri alma işlemini etkinleştiremezsiniz. PowerApps Web Hizmetleri iletisi tarafından bir eylem tetiklendiğinde geri almayı etkinleştirebilirsiniz.  
  
 **Farklı etkinleştir**  
 Tüm işlemler gibi, işlemi bir şablon olarak etkinleştirebilir ve benzer bir kalıbı izleyen işlemler için onu gelişmiş bir başlangıç noktası olarak kullanabilirsiniz.  
  
 **Işlem bağımsız değişkenlerini tanımlama**  
 Bu alanda, eylemin başlamasını beklediği tüm verileri ve eylemden hangi verilerin geçirileceğini belirtin. Daha fazla bilgi: [işlem bağımsız değişkenlerini tanımlama](#define-process-arguments)  
  
 **Aşama ve adım ekleme**  
 Diğer işlemler gibi, gerçekleştirilecek eylemleri ve ne zaman gerçekleştirileceğini belirtirsiniz. Daha fazla bilgi: [aşama ve adım ekleme](#add-stages-and-steps)

<a name="BKMK_DefineProcessArgs"></a>   
## <a name="define-process-arguments"></a>İşlem bağımsız değişkenlerini tanımlama  
 Bir geliştirici bir ileti kullandığında, iletiye geçebilecekleri bazı veriler ile başlayabilirler. Örneğin, yeni bir durum kaydı oluşturmak için, giriş bağımsız değişkeni olarak geçirilen Case başlık değeri olabilir.  
  
 İleti tamamlandığında, geliştiricinin kod tarafından değiştirilmiş veya oluşturulmuş bazı verileri kodlarında başka bir işleme geçmesi gerekebilir. Bu veri çıktı bağımsız değişkenidir.  
  
 Hem giriş hem de çıkış bağımsız değişkenlerinin adı, türü ve bağımsız değişkeninin her zaman gerekli olup olmadığı hakkında bazı bilgiler olmalıdır. Ayrıca bir açıklama da sağlayabilirsiniz.  
  
 İletinin adı ve tüm işlem bağımsız değişkenleriyle ilgili bilgiler iletinin "imzasını" temsil eder. Bir eylem etkinleştirildikten ve kodda kullanıldıktan sonra imza değişmemelidir. Bu imza değişirse, iletiyi kullanan tüm kodlar başarısız olur. Bu durumun tek istisnası, her zaman gerekli olmaması için parametrelerden birini değiştiriyor olabilir.  
  
 Bağımsız değişkenler sıralama tarafından değil ad ile tanımlandığından, bunları sıralayarak veya yukarı veya aşağı taşıyarak bağımsız değişkenlerin sırasını değiştirebilirsiniz. Ayrıca, açıklamayı değiştirmek iletiyi kullanarak kodu bozmayacaktır.  
  
### <a name="action-process-argument-types"></a>Eylem işlemi bağımsız değişken türleri  
 Aşağıdaki tabloda eylem işlemi bağımsız değişken türleri açıklanmaktadır.  
  
|Türüyle|Açıklaması|  
|----------|-----------------|  
|Boolean|Bir `true` veya `false` değeri.|  
|Hem|Tarih ve saat bilgilerini depolayan bir değer.|  
|Kategori|Ondalık duyarlığa sahip bir sayı değeri. Duyarlık son derece önemli olduğunda kullanılır.|  
|Varlığının|Belirtilen varlık için bir kayıt. Varlık ' ı seçtiğinizde, açılan liste etkinleştirilir ve varlık türünü seçmenizi sağlar.|  
|EntityCollection|Varlık kayıtları koleksiyonu.|  
|EntityReference|Benzersiz bir şekilde tanımlayan bir varlık kaydının adını, KIMLIĞINI ve türünü içeren bir nesne. EntityReference ' ı seçtiğinizde, açılan liste etkinleştirilir ve varlık türünü seçmenizi sağlar.|  
|Float|Ondalık duyarlığa sahip bir sayı değeri. Verilerin kesinlikle kesin olmayan bir ölçüden geldiği durumlarda kullanılır.|  
|gir|Tam sayı.|  
|etmenize|Bir miktar para hakkında veri depolayan bir değer.|  
|Seçim listesi|Bir OptionSet özniteliği için bir seçeneği temsil eden bir değer.|  
|dizisinde|Bir metin değeri.|  
  
> [!NOTE]
> Kullanıcı arabiriminde, koşullar veya eylemler için **EntityCollection** bağımsız değişken değerleri ayarlanamıyor. Bunlar, geliştiriciler tarafından özel kodda kullanılmak üzere sağlanır. Daha fazla bilgi: [kendi eylemlerinizi oluşturma](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Aşama ve adım ekleme  
 Eylemler, gerçek zamanlı iş akışlarına çok benzeyen bir işlem türüdür. Gerçek zamanlı iş akışlarında kullanılabilen tüm adımlar eylemlerde kullanılabilir. Gerçek zamanlı iş akışları ve eylemler için kullanılabilen adımlar hakkında daha fazla bilgi için bkz. [Iş akışı aşamaları ve adımları](configure-workflow-steps.md).  
  
 Gerçek zamanlı iş akışları için kullanılabilen adımlara ek olarak, eylemler **değer ata** adımı da vardır.  Eylemler ' de, bunlar yalnızca çıkış bağımsız değişkenlerini ayarlamak için kullanılabilir. Çıktı bağımsız değişkenlerini belirli değerlere veya daha büyük olasılıkla, eylemin çalıştığı kayıttaki değerlere göre ayarlamak için form yardımcısını, çoktan bire bir ilişkiye, daha önceki bir adımda oluşturulan kayıtlara veya bir dizi değere sahip işlemin bir parçasıdır.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 [Bir iş akışından özel eylemleri çağırma](invoke-custom-actions-workflow-dialog.md)   

 
 
