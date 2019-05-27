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
ms.openlocfilehash: 007caa66731870f359e8cb33ba0919390d3196cd
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64465807"
---
# <a name="monitor-and-manage-workflow-processes"></a>İş akışı süreçlerini izleme ve yönetme

İşlemleri izlemek ve yönetmek için, işlemi bulmanız, durumunu değerlendirmeniz ve sorunları gidermek için gerekli eylemleri gerçekleştirmeniz gerekir.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Arka plan iş akışlarını izleme  
 Arka plan iş akışları, durumlarını izlemek için Sistem İş kayıtları oluşturur. Uygulama içinde çeşitli yerlerde bu sistem işleri hakkındaki bilgilere erişebilirsiniz:  
  
 **[Ayarlar](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Sistem İşleri**  
 Bu tüm sistem işi türlerini içerir. Kayıtları **Sistem İşi Türü** **İş Akışı** olanlara filtrelemeniz gerekir.  
  
 **İş Akışı İşleminden**  
 Arka plan iş akışı tanımını açın ve **İşlem Oturumu** sekmesine gidin. Bu yalnızca bu arka plan iş akışı için sistem işlerini gösterir.  
  
 **Kayıttan**  
 Varlık formunu gezinti **Arka Plan İşlemleri** ilişkisini içerecek şekilde düzenleyebilirsiniz. Bu, kayıt bağlamında başlatılan tüm sistem işlerini gösterir.  
  
> [!NOTE]
>  Zaman uyumsuz bir sistem işi (iş akışı) birkaç kez art arda başarısız olursa, yönetici veya uygulama oluşturucusunun sorunu belirleyip çözebilmesi için sistem bu işin yürütülmesini giderek artan aralıklarla erteler. İş yeniden başarılı olmaya başladıktan sonra normal olarak yürütülmeye devam eder.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Çalışan arka plan iş akışları üzerinde gerçekleştirilen eylemler  
 Bir arka plan iş akışı çalışırken, iş akışı için **İptal**, **Duraklat** veya **Ertele** seçeneklerini kullanabilirsiniz. Daha önce bir iş akışını duraklattıysanız, bunu **Sürdürebilirsiniz**.  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Gerçek zamanlı iş akışlarını ve eylemleri izleme  
 Gerçek zamanlı iş akışları ve eylemleri hemen gerçekleştirildiği için Sistem İşi kayıtlarını kullanmaz. Oluşan herhangi bir hata uygulama içinde **İş süreci Hatası** başlığıyla kullanıcıya gösterilir.  
  
 Başarılı işlemler için günlük yoktur. İşlem için **Yönetim** sekmesinin altında **İş Akışı Günlüğü Bekletme** alanında **Hatalarla karşılaşılan iş akışı işleri için Günlükleri sakla** seçeneğini işaretleyerek hatalar için günlüğe kaydetmeyi etkinleştirebilirsiniz.  
  
 Belirli bir işlem için hata günlüğünü görüntülemek için, gerçek zamanlı iş akışı veya eylem tanımını açın ve **İşlem Oturumu** sekmesine gidin. Bu, yalnızca bu işlem için günlüğe kaydedilmiş olan hataları gösterir.  
  
 Herhangi bir işlem için tüm hataların bir görünümünü istiyorsanız, **Gelişmiş Bulma**’ya giderek işlem oturumu varlığında hataları gösteren bir görünüm oluşturun.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>İş akışı işlemlerinin durumu  
 İş akışı işlemlerinin listesini görüntülediğinizde, herhangi bir işlem aşağıdaki **Durum** ve **Durum Nedeni** değerlerinden birine sahip olabilir:  
  
|Eyalet|Durum Nedeni|  
|-----------|-------------------|  
|Hazır|Kaynaklar Bekleniyor|  
|Askıya Alındı|Bekleniyor|  
|Kilitli|Sürüyor<br /><br /> Duraklatılıyor<br /><br /> İptal Ediliyor|  
|Tamamlandı|Başarılı Oldu<br /><br /> Başarısız<br /><br /> İptal Edildi|  

## <a name="deleting-process-log-records"></a>İşlem günlüğü kayıtlarını silme

Kuruluşunuz sık sık çalıştırılan arka plan iş akışları veya iş süreci akışları kullanıyorsa, işlem kaydı günlüklerinin miktarı performans sorunlarına yol açabilecek ve önemli miktarda alan kullanabilecek kadar büyük olabilir. Standart toplu kayıt silme işlerinden biri tarafından yeterli bir şekilde kaldırılmayan işlem günlüğü kayıtlarını silmek üzere özel bir toplu kayıt silme işi oluşturmak için sistem işlerini toplu silme özelliğini kullanabilirsiniz.

1. **Ayarlar** > **Veri Yönetimi** > **Toplu Kayıt Silme** seçeneğine gidin.
2. **Toplu Kayıt Silme** alanında **Yeni** seçeneğini belirleyin. 
3. **Toplu Silme Sihirbazı** başlangıç sayfasında, **Sonraki** seçeneğini belirleyin.
4. **Ara** listesinde **Sistem İşleri** seçeneğini belirleyin.
5. İşlem kaydı günlüklerini silmek üzere bir toplu kayıt silme işi oluşturmak için aşağıdaki koşullar kullanılır. 
 - **Sistem İş Türü Eşittir İş Akışı**. Bu iş akışı kayıtlarını hedefler. 
 - **Durum Eşittir Tamamlandı**. İş yalnızca tamamlanan iş akışlarına karşı çalıştırılabilir.
 - **Durum Nedeni Eşittir Başarılı**. Başarılı, iptal edilen ve başarısız olan işleri silin.
 - **X 30 Günden Daha Eski Tamamlanma Zamanı**. Yalnızca 30 günden daha eski iş akışı işlem günlüğü kayıtlarını silmek için Tamamlanma alanını kullanın.
 ![custom-bulk-record-deletion.png](media/custom-bulk-record-deletion.png)
6. **Sonraki** seçeneğine tıklayın.
7. Toplu silme işinizin çalıştırılacağı sıklığı ayarlayın. İşinizi belirlenen aralıklarla çalıştırmak için zamanlayabilir veya [Hemen seçeneğini kullanarak](#using-the-immediately-option) tek seferlik bir toplu silme işi oluşturabilirsiniz. Bu örnekte, yinelenen bir iş 21 Mayıs 2018 tarihinde ve bundan sonra 30 günde bir çalışacak şekilde ayarlanmış. 
![Toplu kayıt silme seçenekleri](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Hemen seçeneğini kullanma

**Hemen** seçeneğini belirleyerek kayıtları zaman uyumlu toplu silme işlemini hemen gerçekleştirme seçeneğiniz olduğunu fark edeceksiniz. Bu silme işlemi, her bir kaydı ortamı işlem hattından geçirmek yerine doğrudan SQL Server yürütmesi ile gerçekleştirilir ve sistem performansına etkiyi azaltabilir. İşleme için zaman uyumsuz kuyrukta bekleyen toplu silme işlemi yerine fazla iş akışı kayıtlarını hızlı bir şekilde temizlemek istiyorsanız bu iyi bir seçenektir. 

**Hemen** seçeneği aşağıdaki koşullar doğru olduğunda etkinleştirilir: 
- Toplu silme işlemi, Sistem İşleri varlığı içindir.
- Arama ölçütlerinde sistem iş türü eşittir iş akışı koşulu vardır. 
- Toplu silme işini oluşturan kullanıcı AsyncOperation varlığında silme ayrıcalığı için genel derinliğe sahiptir. Sistem yöneticisi güvenlik rolü bu ayrıcalığa sahiptir.  

Zaman uyumlu toplu silme yalnızca tamamlanmış durumdaki AsyncOperation kayıtlarını siler. Her çağrı için en fazla bir milyon kayıt işlenir. Ortamınızda kaldırılması gereken bir milyondan fazla kayıt varsa, işin birden çok kez yürütülmesi gerekir.  
  
## <a name="next-steps"></a>Sonraki adımlar   
 [İş akışı süreçleri için en iyi uygulamalar](best-practices-workflow-processes.md) <br />

