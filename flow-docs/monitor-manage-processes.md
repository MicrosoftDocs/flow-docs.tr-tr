---
title: PowerApps ile iş akışı süreçlerini izleme ve yönetme | MicrosoftDocs
ms.custom: ''
ms.date: 05/06/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: a987a803-4674-4eb0-87de-caefa003b1eb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 00d20d361dd7b3db9f55d6b975c472bea0c4160e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549002"
---
# <a name="monitor-and-manage-workflow-processes"></a>İş akışı süreçlerini izleme ve yönetme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

İşlemleri izlemek ve yönetmek için, işlemi bulmanız, durumu değerlendirmeniz ve sorunları gidermek için gereken tüm eylemleri gerçekleştirmeniz gerekir.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Arka plan iş akışlarını izleme  
 Arka plan iş akışları, durumlarını izlemek için sistem Işi kayıtları oluşturur. Bu sistem işleriyle ilgili bilgilere uygulamanın içindeki çeşitli konumlarda erişebilirsiniz:  
  
 **Sistem Işlerinin [ayarları](/powerapps/maker/model-driven-apps/advanced-navigation#settings) >**  
 Bu, tüm sistem işleri türlerini içerir. Kayıtları, **sistem Işi türünün** **iş akışı**olduğu yere filtrelemeniz gerekir.  
  
 **Iş akışı Işleminden**  
 Arka plan iş akışı tanımını açın ve **Işlem oturumu** sekmesine gidin. Bu, yalnızca bu arka plan iş akışı için sistem işlerini gösterir.  
  
 **Kayıttan**  
 Varlık formunu, gezintinin **arka plan işlemi** ilişkisini içerecek şekilde düzenleyebilirsiniz. Bu, kayıt bağlamında başlatılan tüm sistem işlerini gösterir.  
  
> [!NOTE]
>  Zaman uyumsuz bir sistem işi (iş akışı) birkaç kez art arda başarısız olursa, sistem, yöneticinin veya uygulama Oluşturucu sorunu araştırıp çözebilmesi için o işin yürütülmesini daha uzun ve daha uzun zaman aralıklarıyla erteleyecek şekilde başlatılır. İş yeniden başarılı bir şekilde başladıktan sonra normal yürütmeyi sürdürür.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Arka plan iş akışları çalıştırma eylemleri  
 Arka plan iş akışı çalışırken, iş akışını **Iptal etme**, **duraklatma**veya **erteleme** seçenekleriniz vardır. Daha önce bir iş akışını durakladıysanız, bunu **sürdürebilirsiniz** .  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Gerçek zamanlı iş akışlarını ve eylemleri izleme  
 Gerçek zamanlı iş akışları ve eylemler hemen gerçekleştiğinden sistem Işi kayıtlarını kullanmaz. Oluşan herhangi bir hata, uygulamada **Iş süreci hatası**başlıklı Kullanıcı tarafından görüntülenir.  
  
 Başarılı işlemler için günlük yok. İşlem için **Yönetim** sekmesinin alt kısmındaki **Iş akışı günlüğü tutma** alanında **hatalarla karşılaşan Iş akışı işleri için günlükleri tut** seçeneğini işaretleyerek hatalara yönelik günlük kaydını etkinleştirebilirsiniz.  
  
 Belirli bir işlemin hata günlüğünü görüntülemek için gerçek zamanlı iş akışını veya eylem tanımını açın ve **Işlem oturumu** sekmesine gidin. Bu, yalnızca bu işlem için günlüğe kaydedilen hataları gösterir.  
  
 Herhangi bir işlem için tüm hataların bir görünümünü istiyorsanız **Gelişmiş bul** ' a gidin ve işlem oturumu varlığındaki hataları gösteren bir görünüm oluşturun.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>İş akışı işlemlerinin durumu  
 İş akışı işlemlerinin bir listesini görüntülediğinizde, her bir işlem aşağıdaki **durum** ve **durum nedeni** değerlerinden birine sahip olabilir:  
  
|Durumunda|Durum nedeni|  
|-----------|-------------------|  
|Geldiğinizde|Kaynak bekleniyor|  
|Alın|Bekleniyor|  
|Kilitlenecek|Devam ediyor<br /><br /> Duraklatılıyor<br /><br /> İptali|  
|dım|Baarı<br /><br /> başaramadı<br /><br /> Edilmesi|  

## <a name="deleting-process-log-records"></a>İşlem günlüğü kayıtlarını silme

Kuruluşunuz sık çalıştırılan arka plan iş akışlarını veya iş süreci akışlarını kullanıyorsa, işlem günlüğü kayıtlarının miktarı performans sorunlarına neden olacak kadar büyük olabilir ve önemli miktarda depolama alanı tüketir. Standart toplu kayıt silme işlerinin bir üyesi tarafından yeterince kaldırılmayan işlem günlüğü kayıtlarını silmek için, özel bir toplu kayıt silme işi oluşturmak üzere sistem işlerini toplu silme özelliğini kullanabilirsiniz.

1. **Toplu kayıt silme** > **veri yönetimi** > **Ayarlar** ' a gidin.
2. **Toplu kayıt silme** alanından **Yeni**' yi seçin. 
3. **Toplu Silme Sihirbazı** başlangıç sayfasında **İleri**' yi seçin.
4. **Ara** listesinde **Sistem işleri**' ni seçin.
5. İşlem günlüğü kayıtlarını silmek için bir toplu kayıt silme işi oluşturmak için aşağıdaki koşullar kullanılır. 
 - **Sistem Işi türü Iş akışına eşittir**. Bu, iş akışı kayıtlarını hedefler. 
 - **Durum eşittir tamamlandı**. İşi çalıştırmak için yalnızca tamamlanan iş akışları geçerlidir.
 - **Durum açıklaması başarılı oldu**. Başarılı, iptal edilmiş ve başarısız işleri silin.
 - **X gün 30 ' dan daha eski bir süre Içinde tamamlandı**. Yalnızca 30 günden eski olan iş akışı işlem günlüğü kayıtlarını silmek için tamamlandı alanını kullanın.
 ![Custom-Bulk-Record-Deletion. png](media/custom-bulk-record-deletion.png)
6. **İleri**' ye tıklayın.
7. Toplu silme işinizin çalışacağı sıklığı ayarlayın. İşinizi ayarlanan aralıklarda çalışacak şekilde zamanlayabilir veya [anında seçeneği kullanarak](#using-the-immediately-option)bir kerelik toplu silme işi oluşturabilirsiniz. Bu örnekte, yinelenen bir iş 21 Mayıs 2018 tarihinde ve sonrasında 30 günde bir çalışacak şekilde ayarlanır. 
Toplu kayıt silme seçeneklerini ![](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Hemen seçeneğini kullanma

**Hemen** seçeneğini belirleyerek kayıtların anında zaman uyumlu toplu silme işlemini gerçekleştirme seçeneğiniz olduğuna dikkat edin. Bu silme işlemi, her bir kaydı silme olayı ardışık düzeni aracılığıyla geçirmek yerine, sistem performansının etkilerini azaltan doğrudan SQL Server yürütme ile gerçekleştirilir. İşlem için zaman uyumsuz Kuyrukta bekleyen toplu silme işi yerine ek iş akışı kayıtlarını hızlıca temizlemek istiyorsanız bu iyi bir seçenektir. 

Aşağıdaki koşullar doğru olduğunda **hemen** seçenek etkinleştirilir: 
- Toplu silme işi, sistem Işleri varlığına yöneliktir.
- Arama ölçütlerinde, sistem işi türü iş akışına eşit bir durum vardır. 
- Toplu silme işini oluşturan kullanıcı, zaman uyumsuz coperation varlığındaki silme ayrıcalığının genel derinliğine sahiptir. Sistem Yöneticisi güvenlik rolünde bu ayrıcalık vardır.  

Zaman uyumlu toplu silme işlemi, yalnızca zaman uyumsuz coperation kayıtlarını tamamlanmış durumunda siler. Her çağırma için en fazla 1.000.000 kayıt işlenir. Ortamınızda kaldırmak üzere 1.000.000 'den fazla kayıt varsa, işi birden çok kez yürütmeniz gerekecektir.  
  
## <a name="next-steps"></a>Sonraki adımlar   
 [İş akışı işlemleri için en iyi uygulamalar](best-practices-workflow-processes.md) <br />

