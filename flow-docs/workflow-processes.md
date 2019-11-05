---
title: Klasik Common Data Service iş akışları | MicrosoftDocs
ms.custom: ''
ms.date: 08/27/2019
ms.reviewer: matp
ms.service: flow
ms.topic: article
ms.assetid: 1f3c9780-26ad-49ec-a3fb-fc226def19c5
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 42ac7bd75268010a8d7e2bf88a600621504dda39
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548328"
---
# <a name="classic-common-data-service-workflows"></a>Klasik Common Data Service iş akışları 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

İş akışları, Kullanıcı arabirimi olmadan iş süreçlerini otomatik hale getirir. İnsanlar, genellikle herhangi bir kullanıcı etkileşimi gerektirmeyen Otomasyonu başlatmak için iş akışı süreçlerini kullanır.

> [!IMPORTANT]
> İş işlemlerinizi otomatikleştirmek için klasik iş akışları yerine akışları kullanın. Daha fazla bilgi: [klasik Common Data Service iş akışlarını akışlarla değiştirme](replace-workflows-with-flows.md)  
  
 Her iş akışı işlemi tek bir varlıkla ilişkilendirilir. İş akışlarını yapılandırırken göz önünde bulundurmanız gereken dört ana alan vardır:  
  
-   Ne zaman başlatılacağını?  
  
-   Bunların gerçek zamanlı bir iş akışı veya bir arka plan iş akışı olarak çalıştırılmaları gerekir mi?  
  
-   Hangi eylemler gerçekleştirmeleri gerekir?  
  
-   Eylemler hangi koşullarda gerçekleştirilmelidir?  
  
 Bu konu, iş akışı işlemlerinin nasıl bulunacağını tanıtır ve ne zaman başlatılacağını ve gerçek zamanlı ya da arka plan olarak çalışacağını açıklar. Gerçekleştirdikleri eylemler ve koşullar hakkında daha fazla bilgi için bkz. [Iş akışı Işlemlerini yapılandırma](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>İş akışı süreçlerini nerede özelleştireceğiniz?  
 **Varsayılan çözümde** **süreçler** düğümünü görüntüleyerek ve **Kategori** **iş akışına**sahip işlemlere filtre uygulayarak kuruluşunuzdaki iş akışlarını görebilirsiniz.  
  
 ![Dynamics 365 ' de iş akışına göre filtrelenen süreçler](media/workflow-processes-filtered.PNG "Dynamics 365 ' de iş akışına göre filtrelenen süreçler")  
  
 Uygulamanın nasıl oluşturulduğuna bağlı olarak, kullanıcılar uygulamada iş akışlarını oluşturabilir veya değiştirebilir. 
 
Geliştiriciler, [Common Data Service geliştirici kılavuzundaki](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions) bilgileri kullanarak iş akışları oluşturabilir ve satın aldığınız çözümlerin değiştiremeyeceğiniz iş akışlarını içerebilirler.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>İş akışı özellikleri  
 Çözüm Gezgini 'nde, **süreçler** ' ı seçin ve **Yeni**' ye tıklayın.  
  
 Bir iş akışı oluşturduğunuzda, **Işlem oluştur** iletişim kutusu tüm işlemlerin sahip olduğu üç özelliği ayarlamanızı gerektirir:  
  
 ![Dynamics 365 ' de iş akışı oluşturma](media/create-workflow.PNG "Dynamics 365 ' de iş akışı oluşturma")  
  
 **İşlem adı**  
 İş akışı işleminin adının benzersiz olması gerekmez, ancak çok sayıda iş akışınız olacağını düşünüyorsanız işlemlerinizi açıkça ayırt etmek için bir adlandırma kuralı kullanmak isteyebilirsiniz. İş akışının adına standart önekleri uygulamak isteyebilirsiniz. Ön ek, iş akışının işlevini veya Şirket içindeki departmanı tanımlayabilir. Bu, iş akışları listesinde benzer öğeleri gruplandırgetirmenize yardımcı olur.  
  
 **Alan**  
 Bu özellik bunun bir iş akışı işlemi olduğunu belirler.  
  
 **Varlığının**  
 Her iş akışı işleminin tek bir varlığa ayarlanması gerekir. İş akışı işlemi oluşturulduktan sonra varlığı değiştiremezsiniz.  
  
 **Bu iş akışını arka planda çalıştır (önerilir)**  
 Kategori olarak iş akışı ' nı seçtiğinizde bu seçenek görüntülenir. Bu ayar iş akışının gerçek zamanlı veya arka plan iş akışı olup olmadığını belirler. Gerçek zamanlı iş akışları hemen çalışır (eşzamanlı) ve arka plan iş akışları zaman uyumsuz olarak çalışır. Kullanılabilir yapılandırma seçenekleri, bu ayar için seçtiğiniz seçeneğe bağlıdır. Arka plan iş akışları, gerçek zamanlı iş akışları için kullanılamayan bekleme koşullarına izin verir. Bu bekleme koşullarını kullanmamaları koşuluyla, daha sonra arka plan iş akışlarını gerçek zamanlı iş akışlarına ve gerçek zamanlı iş akışlarına arka plan iş akışlarına dönüştürebilirsiniz. Bekleme koşulları hakkında daha fazla bilgi için bkz. [iş akışı eylemleri için koşulları ayarlama](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 Ayrıca, sıfırdan yeni bir iş akışı oluşturulup oluşturulmayacağını veya mevcut bir şablondan başlatmayı istediğinizi belirtmek için de **tür** seçeneğiniz vardır. **Varolan bir şablondan yeni işlem ' ı seçtiğinizde (listeden seçin)** , daha önce bir işlem şablonu olarak kaydedilmiş olan iş akışı işlemlerinden seçim yapabilirsiniz.  
  
 Iş akışını oluşturduktan sonra veya var olanı düzenledikten sonra, aşağıdaki ek özelliklere sahip olursunuz:  
  
 ![Bir iş akışındaki Genel sekmesi](media/create-workflow-general-tab.PNG "Bir iş akışındaki Genel sekmesi")  
  
 **Farklı etkinleştir**  
 Diğer şablonlar için gelişmiş bir başlangıç noktası oluşturmak üzere **işlem şablonu** ' nu seçebilirsiniz. Bu seçeneği belirlerseniz, iş akışını etkinleştirdikten sonra bu, uygulanmaz, ancak **mevcut bir şablondan yeni işlem (listeden seç)** seçeneğini belirlerseniz, **işlem oluştur** iletişim **kutusunda seçim yapmak**için kullanılabilir olacaktır.  
  
 İşlem şablonları, benzer bir dizi iş akışı işlemleriniz olduğunda ve bunları aynı mantığı çoğaltmadan tanımlamak istediğinizde kullanışlıdır.  
  
> [!NOTE]
>  Bir işlem şablonunun düzenlenmesiyle, daha önce oluşturulmuş diğer iş akışı işlemlerinin davranışları bir şablon olarak kullanılarak değişmez. Şablon kullanılarak oluşturulan yeni bir iş akışı, şablondaki içeriğin bir kopyasıdır.  
  
 **Çalıştırmak için kullanılabilir**  
 Bu bölüm, iş akışının nasıl çalıştırılabileceğini betimleyen seçenekleri içerir.  
  
 **Bu Iş akışını arka planda çalıştır (önerilir)**  
 Bu onay kutusu, iş akışını oluştururken seçtiğiniz seçeneği yansıtır. Bu seçenek devre dışıdır, ancak **gerçek zamanlı bir iş akışına dönüştür** ' ü seçerek veya **bir arka plan iş akışına dönüştürürseniz**, **Eylemler** menüsünden değiştirebilirsiniz.  
  
 **İsteğe bağlı işlem olarak**  
 Kullanıcıların **iş akışını Çalıştır** komutundan bu iş akışını çalıştırmasına izin vermek istiyorsanız bu seçeneği belirleyin.  
  
 **Alt işlem olarak**  
 İş akışının başka bir iş akışından çalışmaya izin vermek istiyorsanız bu seçeneği belirleyin.  
  
 **İş akışı Işi bekletme**  
 Bu bölüm, iş akışı yürütme tamamlandıktan sonra bir iş akışını silme seçeneği içerir.  
  
 **Tamamlanan iş akışı işlerini otomatik olarak sil (disk alanını kaydetmek için)**  
 Tamamlanmış bir iş akışı işinin otomatik olarak silinmesini istiyorsanız bu seçeneği belirleyin.  
  
> [!NOTE]
>  İş akışı işleri tamamlanma sonrasında hemen silinir, ancak yakında bir toplu işlem aracılığıyla silinmez.  
  
 **Kapsam**  
 Kullanıcıya ait varlıklar için, Seçenekler **kuruluş**, **üst öğe: alt iş birimleri**, **iş birimi**veya **Kullanıcı**. Kuruluşa ait varlıklar için tek seçenek **kuruluştur**.  
  
 Kapsam **kuruluş**ise, iş akışı mantığı kuruluştaki herhangi bir kayda uygulanabilir. Aksi takdirde, iş akışı yalnızca kapsam içinde yer alan bir kayıt alt kümesine uygulanabilir.  
  
> [!NOTE]
>  Varsayılan kapsam değeri **Kullanıcı**' dır. İş akışını etkinleştirmeden önce kapsam değerinin uygun olduğundan emin olun.  
  
 **Başlangıç**  
 Bir iş akışının ne zaman otomatik olarak başlaması gerektiğini belirtmek için bu bölümdeki seçenekleri kullanın. Belirli olaylardan önce çalıştırılacak gerçek zamanlı bir iş akışı yapılandırabilirsiniz. İş akışı eylemi gerçekleşmeden önce durdurabileceğinden bu çok güçlü bir özelliktir. Daha fazla bilgi: [gerçek zamanlı Iş akışları kullanma](configure-workflow-steps.md#BKMK_SynchronousWorkflows). Seçenekler şunlardır:  
  
- **Kayıt oluşturuldu**  
  
- **Durum değişikliklerini kaydet**  
  
- **Kayıt atandı**  
  
- **Kayıt alanları değişikliği**  
  
- **Kayıt silindi**  
  
> [!NOTE]
>  İş akışı için tanımladığınız eylemlerin ve koşulların, iş akışının ne zaman çalıştırıldığının farkında olduğunu aklınızda bulundurun. Örneğin, kaydı güncelleştirmek için bir iş akışı tanımlarsanız, bu eylem kayıt oluşturulmadan önce gerçek zamanlı bir iş akışı tarafından gerçekleştirilemez. Mevcut olmayan bir kayıt güncelleştirilemez. Benzer şekilde, bir arka plan iş akışı silinmiş olan bir kaydı güncelleştiremez, ancak iş akışı için bu eylemi tanımlayabilseniz bile. Gerçekleştirilemeyebilir bir eylem gerçekleştirmek için bir iş akışı yapılandırırsanız, başarısız olur ve iş akışının tamamı başarısız olur.  
  
 **Farklı Çalıştır**  
 Bu seçenek yalnızca, iş akışını oluştururken **Bu iş akışını arka planda çalıştır (önerilir)** seçeneğinde veya daha sonra bir arka plan iş akışını gerçek zamanlı bir iş akışı olacak şekilde dönüştürdüyseniz kullanılabilir.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>İş akışı işlemlerinin güvenlik bağlamı  
 Arka plan iş akışı, isteğe bağlı bir işlem olarak yapılandırıldığında ve bir kullanıcı tarafından **Iş akışını Çalıştır** komutu kullanılarak başlatıldığında, iş akışının gerçekleştirebileceği işlemler, Kullanıcı tarafından tanımlanan ayrıcalıklar ve erişim düzeylerine göre gerçekleştirilebilenlerle sınırlıdır Kullanıcı hesapları için ayarlanan güvenlik rolleri.  
  
 Bir arka plan iş akışı, bir olaya göre başladığında, genellikle iş akışını oluşturan kişi, bu kişiye sahip olan kişi bağlamında çalışır.  
  
 Gerçek zamanlı iş akışları için **Farklı Çalıştır** seçeneğine sahip olursunuz ve iş akışının, iş akışının sahibinin güvenlik bağlamını veya kayıtta değişiklik yapan kullanıcıyı uygulayıp uygulamamayacağını seçebilirsiniz. İş akışınız, tüm kullanıcıların güvenlik kısıtlamalarına göre gerçekleştiremeyecek eylemleri içeriyorsa, iş akışının sahibi olarak iş akışının çalışmasını tercih etmeniz gerekir.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Bir iş akışını etkinleştirme  
 İş akışları, yalnızca devre dışı bırakıldıklarında düzenlenebilir. Bir iş akışı, el ile veya etkinleştirilmesi gereken olaylar nedeniyle uygulanmadan önce. Bir iş akışı etkinleştirilmeden önce, en az bir adım içermesi gerekir. Adımları yapılandırma hakkında daha fazla bilgi için bkz. [iş akışı süreçlerini yapılandırma](configure-workflow-steps.md)  
  
 Bir iş akışı yalnızca iş akışı sahibi tarafından etkinleştirilebilir veya devre dışı bırakılabilir ya da bir kişi tarafından sistem yöneticisi gibi **başka bir kullanıcı ayrıcalığı adına hareket** edebilir.  Bunun nedeni, kötü niyetli bir kullanıcının değişikliğin farkında olmadan iş akışını değiştirebilidir. Sahibi değiştirerek sahip olduğunuz bir iş akışını yeniden atayabilirsiniz. Bu alan, **Yönetim** sekmesindedir. Sistem yöneticisi değilseniz ve başka bir kullanıcının sahip olduğu bir iş akışını düzenlemeniz gerekiyorsa, devre dışı bırakmanız ve size atamanız gerekir. İş akışını düzenledikten sonra, uygulamayı etkinleştirebilmeleri için geri atayabilirsiniz.  
  
 Gerçek zamanlı iş akışları, kullanıcının **gerçek zamanlı süreçler etkinleştirme** ayrıcalığına sahip olmasını gerektirir. Gerçek zamanlı iş akışlarının sistem performansını etkileyerek daha büyük bir riski olduğundan, yalnızca olası riski değerlendirebilen kişilere bu ayrıcalık verilmelidir.  
  
 İş akışları etkinleştirildiklerinde kaydedilir, bu nedenle bunları etkinleştirmeden önce kaydetmek gerekli değildir.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 [İş akışı süreçlerini yapılandırma](configure-workflow-steps.md)  <br/>
[İş süreci akışına isteğe bağlı iş akışı ekleme](bpf-add-on-demand-workflow.md) 

