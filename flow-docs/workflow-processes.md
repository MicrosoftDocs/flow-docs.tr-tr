---
title: Klasik Uygulamalar için Common Data Service (CDS) iş akışları | MicrosoftDocs
ms.custom: ''
ms.date: 08/06/2018
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
ms.openlocfilehash: 5f3e2145741c96d20f73ff74f5fd6cc6c1cbb52e
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462922"
---
# <a name="classic-common-data-service-cds-for-apps-workflows"></a>Klasik Uygulamalar için Common Data Service (CDS) iş akışları 

İş akışları, bir kullanıcı arabirimi olmadan iş süreçlerini otomatikleştirir. Kişiler genellikle herhangi bir kullanıcı etkileşimi gerektirmeyen otomasyonu başlatmak için iş akışı işlemlerini kullanır.  
  
 Her iş akışı işlemi, tek bir varlık ile ilişkilidir. İş akışları yapılandırılırken dikkate alınması gereken başlıca dört alan vardır:  
  
-   Ne zaman başlatılmalıdır?  
  
-   Gerçek zamanlı iş akışı olarak mı yoksa arka plan iş akışı olarak mı çalıştırılmalıdır?  
  
-   Hangi eylemleri gerçekleştirmelidir?  
  
-   Hangi koşullar altında eylemler gerçekleştirilmelidir?  
  
 Bu konu, iş akışı işlemlerinin nasıl bulunacağını tanıtır ve ne zaman başlatılacağını ve gerçek zamanlı olarak mı yoksa arka plan olarak mı çalıştırılması gerektiğini açıklamaktadır. Gerçekleştirmeleri gereken eylemler ve koşullar hakkında bilgi için bkz. [İş Akışı İşlemlerini Yapılandırma](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>İş akışı işlemlerini nereden özelleştirirsiniz?  
 **Varsayılan Çözüm** bölümünde **İşlemler** düğümünü görüntüleyip, **Kategori** **İş Akışı** içeren işlemleri filtreleyerek kuruluşunuzdaki iş akışlarını görebilirsiniz.  
  
 ![Dynamics 365’te iş akışına göre filtrelenmiş işlemler](media/workflow-processes-filtered.PNG "Dynamics 365’te iş akışına göre filtrelenmiş işlemler")  
  
 Kullanıcılar, uygulamanın nasıl derlendiğine bağlı olarak uygulamada iş akışları oluşturabilir veya uygulamadaki iş akışlarını değiştirebilir. 
 
Geliştiriciler, [Dynamics 365 Müşteri Etkileşimi Geliştirici Kılavuzu](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-guide)’ndaki bilgileri kullanarak iş akışları oluşturabilir ve satın aldığınız çözümler, değiştirebileceğiniz iş akışlarını içerebilir.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>İş akışı özellikleri  
 Çözüm gezgininde **İşlemler**’i seçin ve **Yeni**’ye tıklayın.  
  
 Bir iş akışı oluşturduğunuzda **İşlem Oluştur** iletişim kutusu, tüm işlemlerin sahip olacağı üç özelliği ayarlamanızı gerektirir:  
  
 ![Dynamics 365’te iş akışı oluşturma](media/create-workflow.PNG "Dynamics 365’te iş akışı oluşturma")  
  
 **İşlem Adı**  
 İş akışı işleminin adının benzersiz olması gerekmez, ancak çok sayıda iş akışınız olmasını planlıyorsanız, işlemlerinizi net şekilde ayırt etmek için bir adlandırma kuralı kullanmak isteyebilirsiniz. İş akışının adına standart önekler uygulamak isteyebilirsiniz. Önek, iş akışının veya şirket içindeki departmanın işlevini açıklayabilir. Böylece, iş akışları listesinde benzer öğeleri gruplandırabilirsiniz.  
  
 **Kategori**  
 Bu özellik, bunun bir iş akışı işlemi olduğunu belirler.  
  
 **Varlık**  
 Her iş akışı işlemi, tek bir varlığa ayarlanmalıdır. İş akışı işlemi oluşturulduktan sonra varlığı değiştiremezsiniz.  
  
 **Bu iş akışını arka planda çalıştır (önerilen)**  
 Kategori olarak iş akışını seçtiğinizde bu seçenek görüntülenir. Bu ayar, iş akışının gerçek zamanlı mı yoksa arka plan iş akışı mı olduğunu belirler. Gerçek zamanlı iş akışları hemen çalıştırılır (zaman uyumlu) ve arka plan iş akışları zaman uyumsuz şekilde çalıştırılır. Kullanılabilir yapılandırma seçenekleri, bu ayar için yaptığınız tercihe bağlıdır. Arka plan iş akışları, gerçek zamanlı iş akışları için kullanılabilir olmayan bekleme koşullarına izin verir. Bu bekleme koşullarını kullanmadığınız sürece, daha sonra arka plan iş akışlarını gerçek zamanlı iş akışlarına ve gerçek zamanlı iş akışlarını da arka plan iş akışlarına dönüştürebilirsiniz. Bekleme koşulları hakkında daha fazla bilgi için bkz. [İş akışı eylemleri için koşulları ayarlama](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 Ayrıca sıfırdan yeni bir iş akışı mı oluşturulacağını yoksa mevcut bir şablondan mı işlemi başlatacağınızı seçmek için **Tür** seçeneğiniz de vardır. **Mevcut bir şablondan yeni işlem (listeden seçin)** seçeneğini belirlediğinizde, önceden işlem şablonu olarak kaydedilmiş olan kullanılabilir İş Akışları işlemleri arasından seçim yapabilirsiniz.  
  
 İş Akışını oluşturduktan sonra veya mevcut bir iş akışını düzenlerseniz aşağıdaki ek özelliklere sahip olursunuz:  
  
 ![Bir iş akışındaki genel sekmesi](media/create-workflow-general-tab.PNG "Bir iş akışındaki genel sekmesi")  
  
 **Farklı Etkinleştir**  
 Diğer şablonlara yönelik gelişmiş bir başlangıç noktası oluşturmak için **İşlem şablonu**’nu seçebilirsiniz. Bu seçeneği belirtirseniz, iş akışını etkinleştirmenizin ardından iş akışı uygulanmaz; bunun yerine iş akışının **İşlem Oluştur** iletişim kutusunda seçilebilir duruma gelmesi için **Tür**: **Mevcut bir şablondan yeni işlem (listeden seçin)** öğesini seçersiniz  
  
 İşlem şablonları, bir dizi iş akışı işleminiz olduğunda ve aynı mantığı yinelemeden bunları tanımlamak istediğinizde kullanışlıdır.  
  
> [!NOTE]
>  Bir işlem şablonu düzenlendiğinde, bu işlem şablonu kullanılarak önceden oluşturulan diğer tüm iş akışı işlemlerinin davranışı değişmez. Şablon kullanılarak oluşturulan yeni bir iş akışı, şablondaki içeriğin bir kopyasıdır.  
  
 **Çalıştırmak İçin Kullanılabilen**  
 Bu bölüm, iş akışının nasıl çalıştırılmaya hazır olduğunu açıklayan seçenekleri içerir.  
  
 **Bu İş Akışını arka planda çalıştır (önerilen)**  
 Bu onay kutusu, iş akışını oluştururken belirlediğiniz seçeneği yansıtır. Bu seçenek devre dışı bırakılır, ancak **Gerçek zamanlı iş akışına dönüştür** veya **Arka plan iş akışına dönüştür** seçeneğini belirleyerek **Eylemler** menüsünden bunu değiştirebilirsiniz.  
  
 **İsteğe bağlı işlem olarak**  
 Kullanıcıların, **İş Akışını Çalıştır** komutundan bu iş akışını çalıştırmasına olanak sağlamak istiyorsanız bu seçeneği belirleyin.  
  
 **Alt işlem olarak**  
 İş akışının başka bir iş akışından başlatılabilmesine olanak sağlamak istiyorsanız bu seçeneği belirleyin.  
  
 **İş Akışı İş Bekletme**  
 Bu bölüm, iş akışı yürütmesi tamamlandıktan sonra iş akışını silme seçeneğini içerir.  
  
 **Tamamlanan iş akışı işlerini otomatik olarak sil (disk alanında yer açmak için)**  
 Tamamlanan bir iş akışı işinin otomatik olarak silinmesini istiyorsanız bu seçeneği belirleyin.  
  
> [!NOTE]
>  İş akışı işleri tamamlandıktan hemen sonra silinmez, ancak kısa bir süre sonra toplu iş işlemiyle silinir.  
  
 **Kapsam**  
 Kullanıcıya ait varlıklar için seçenekler **Kuruluş**, **Üst Öğe: Alt Departmanlar**, **Departman** ve **Kullanıcı**'dır. Kuruluşa ait varlıklar tek seçenek **Kuruluş**’tur.  
  
 Kapsam **Kuruluş** ise iş akışı mantığı, kuruluştaki herhangi bir kayda uygulanabilir. Aksi takdirde iş akışı yalnızca kapsam dahilindeki bir kayıt alt kümesine uygulanabilir.  
  
> [!NOTE]
>  Varsayılan kapsam değeri **Kullanıcı**’dır. İş akışını etkinleştirmeden önce kapsam değerinin uygun olduğunu doğruladığınızdan emin olun.  
  
 **Başlangıç Zamanı**  
 Bir iş akışının otomatik olarak ne zaman başlayacağını belirtmek için bu bölümdeki seçenekleri kullanın. Gerçek zamanlı bir iş akışını belirli olaylardan önce çalıştırılacak şekilde yapılandırabilirsiniz. İş akışı, gerçekleşmeden önce eylemi durdurabileceğinden bu çok güçlü bir özelliktir. Daha fazla bilgi: [Gerçek Zamanlı İş Akışları Kullanma](configure-workflow-steps.md#BKMK_SynchronousWorkflows). Seçenekler şunlardır:  
  
- **Kayıt oluşturuldu**  
  
- **Kayıt durumu değişikliği**  
  
- **Kayıt atandı**  
  
- **Kayıt alanı değişikliği**  
  
- **Kayıt silindi**  
  
> [!NOTE]
>  İş akışı için tanımladığınız eylemlerin ve koşulların, iş akışının ne zaman çalıştırılacağıyla uyumlu olmadığını unutmayın. Örneğin, kaydı güncelleştirmek için bir iş akışı tanımlarsanız, kayıt oluşturulmadan önce gerçek zamanlı bir iş akışı tarafından bu eylem gerçekleştirilemez. Mevcut olmayan bir kayıt güncelleştirilemez. Benzer şekilde, iş akışı için bu eylemi tanımlamış olsanız da bir arka plan iş süreci, silinmiş olan bir kaydı güncelleştiremez. Bir iş akışını, gerçekleştirilemeyecek bir eylemi gerçekleştirecek şekilde yapılandırırsanız iş akışının tamamı başarısız olur.  
  
 **Farklı Yürüt**  
 Bu seçenek yalnızca, iş akışını oluştururken **Bu iş akışını arka planda çalıştır (önerilen)** seçeneğinin işaretini kaldırdıysanız veya daha sonra bir arka plan iş akışını gerçek zamanlı iş akışına dönüştürdüyseniz kullanılabilir.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>İş akışı işlemlerinin güvenlik bağlamı  
 Bir arka plan iş akışı, isteğe bağlı işlem olarak yapılandırıldığında ve **İş Akışını Çalıştır** komutu kullanılarak bir kullanıcı tarafından başlatıldığında, iş akışının gerçekleştirebileceği eylemler, kullanıcının kullanıcı hesabı için ayarlanan güvenlik rolleri tarafından tanımlanan ayrıcalıklara ve erişim düzeylerine göre gerçekleştirebildikleriyle sınırlıdır.  
  
 Bir arka plan iş akışı bir olaya göre başlatıldığında iş akışı ona sahip olan kişinin (bu kişi genellikle iş akışını oluşturan kişidir) bağlamında çalışır.  
  
 Gerçek zamanlı iş akışları için **Farklı Yürüt** seçeneğiniz vardır ve iş akışının, iş akışı sahibinin mi yoksa kayıt üzerinde değişiklik yapan kullanıcının mı güvenlik bağlamını uygulaması gerektiğini seçebilirsiniz. İş akışınız, güvenlik kısıtlamalarına göre tüm kullanıcıların gerçekleştiremeyeceği eylemleri içeriyorsa, iş akışı sahibi olarak iş akışının çalıştırılmasını sağlamayı seçmeniz gerekir.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>İş akışını etkinleştirme  
 İş akışları yalnızca devre dışı bırakıldığında düzenlenebilir. Bir iş akışını kendinizin kullanabilmesi veya olaylar nedeniyle bir iş akışının uygulanabilmesi için iş akışının etkinleştirilmesi gerekir. Bir iş akışının etkinleştirilebilmesi için en az bir adım içermesi gerekir. Adımları yapılandırma hakkında bilgi için bkz. [İş akışı süreçlerini yapılandırma](configure-workflow-steps.md)  
  
 Bir iş akışı yalnızca iş akışı sahibi tarafından veya sistem yöneticisi gibi **Başka Bir Kullanıcı Adına Hareket Etme** ayrıcalığına sahip birisi tarafından etkinleştirilebilir ya da devre dışı bırakılabilir.  Bunun nedeni, kötü niyetli bir kullanıcının değişikliği bilmeden birisinin iş akışını değiştirebilecek olmasıdır. Sahibi değiştirerek sahip olduğunuz bir iş akışını yeniden atayabilirsiniz. Bu alan, **Yönetim** sekmesindedir. Sistem yöneticisi değilseniz ve başka bir kullanıcıya ait bir iş akışını düzenlemeniz gerekiyorsa söz konusu kişinin iş akışını devre dışı bırakıp size ataması gerekir. İş akışını düzenleme işlemini bitirdikten sonra sistem yöneticisine veya ilgili kullanıcıya iş akışını etkinleştirmesi için geri atayabilirsiniz.  
  
 Gerçek zamanlı iş akışları, kullanıcının **Gerçek Zamanlı İşlemleri Etkinleştirme** ayrıcalığına sahip olmasını gerektirir. Gerçek zamanlı iş akışları, sistem performansını etkileme konusunda yüksek risk taşıdığından yalnızca olası riski değerlendirebilecek kişilere bu ayrıcalık verilmelidir.  
  
 İş akışları etkinleştirildiğinde kaydedilir, bu nedenle etkinleştirilmeden önce kaydedilmesi gerekmez.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 [İş akışı işlemlerini yapılandırma](configure-workflow-steps.md)  <br/>
[İş süreci akışına isteğe bağlı iş akışı ekleme](bpf-add-on-demand-workflow.md) 

