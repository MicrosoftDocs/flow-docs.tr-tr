---
title: İş akışı süreçlerini yönetmeye yönelik en iyi uygulamalar | MicrosoftDocs
description: İş akışlarını kullanmak için önerilen yolları anlayın
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
- powerapps
author: Mattp123
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ad9935b171568b62376232f450a62dbda4752cac
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546029"
---
# <a name="best-practices-for-workflow-processes"></a>İş akışı işlemleri için en iyi uygulamalar
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bu konu, iş akışı işlemleri oluşturmak ve yönetmek için en iyi yöntemleri içerir.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Sonsuz döngüden kaçının  
 Sunucu kaynaklarını tüketen ve performansı etkileyen sonsuz bir döngü Başlatan bir iş akışında mantık oluşturmak mümkündür. Bir sonsuz döngünün gerçekleşebileceği tipik durum, bir öznitelik güncelleştirildiğinde başlatılacak şekilde yapılandırılmış bir iş akışınız varsa ve sonra iş akışının mantığındaki bu özniteliği güncelleştirdiyse olur. Güncelleştirme eylemi, kaydı güncelleştiren aynı iş akışını tetikler ve iş akışını yeniden tetikler.  
  
 Oluşturduğunuz iş akışları sonsuz döngüleri algılayıp durdurma mantığını içerir. Bir iş akışı işlemi, kısa bir süre içinde belirli bir kayıt üzerinde belirli sayıda kez çalışıyorsa, işlem aşağıdaki hatayla başarısız olur: Bu iş akışı **, başlatılan iş akışı sonsuz bir döngüye dahil edildiğinden iptal edildi. İş akışı mantığını düzeltip yeniden deneyin**. Zaman sınırı 16 ' dır.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>İş akışı şablonlarını kullanma  
 Benzer iş akışlarınız varsa ve aynı kalıbı izleyen daha fazla iş akışı oluşturmayı düşünüyorsanız, iş akışınızı iş akışı şablonu olarak kaydedin. Bu şekilde, bir dahaki sefer benzer bir iş akışı oluşturmanız gerektiğinde, şablonu kullanarak iş akışını oluşturmanız ve tüm koşulların ve eylemlerin sıfırdan girmekten kaçının.  
  
 **Işlem oluştur** iletişim kutusunda, **varolan bir şablondan yeni işlem ' ı seçin (listeden seçin)** .  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Alt iş akışlarını kullanma  
 Aynı mantığı farklı iş akışlarıyla veya koşullu dallarda uygularsanız, bu mantığı alt iş akışı olarak tanımlayın, böylece bu mantığı her iş akışında veya koşullu dalda el ile çoğaltmanız gerekmez. Bu, İş akışlarınızın bakımını daha kolay hale getirmeye yardımcı olur. Aynı mantığı uygulayabilen birçok iş akışını incelemek yerine yalnızca bir iş akışını güncelleştirebilirsiniz.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Tamamlanan iş akışı işlerini otomatik olarak sil
Arka plan (zaman uyumsuz) iş akışları için, iş akışı tanımındaki **tamamlanan iş akışı işlerinin (disk alanını kaydetmek için) otomatik olarak silinmesini** tercih ederiz. Bu kutunun işaretlenmesi, sistemin başarılı yürütmeler için alan kazanmak için iş akışı günlüklerini silmesine izin verir. Başarısız iş akışı yürütmelerinin günlüklerinin, sorun giderme için her zaman kaydedilip kaydedilmediğini görürsünüz.  

![İş akışı işi bekletme](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Hatalarla karşılaşan iş akışı işleri için günlükleri tut  
Arka planda (zaman uyumlu) çalıştırmayan iş akışları için, iş akışı tanımında **hatalarla karşılaşan iş akışı işleri için günlükleri tut** seçeneğini seçmenizi öneririz. Bu seçeneğin belirlenmesi, başarısız iş akışı yürütmelerinin sorun giderme için kaydedilmesine izin verir. Başarılı zaman uyumlu iş akışı yürütmelerinin günlükleri, alanı kazanmak için her zaman silinir.   

![Başarısız iş akışları için günlükleri tut seçeneği](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Aynı varlığı güncelleştiren iş akışlarının sayısını sınırlayın
Aynı varlığı güncelleştiren birden fazla iş akışı çalıştırmak kaynak kilidi sorunlarına neden olabilir. Her fırsat güncelleştirmesinin ilişkili hesapta bir güncelleştirmeyi tetiklediği birkaç iş akışını düşünün. Bu iş akışlarının birden fazla örneği çalışıyor ve aynı anda aynı hesap kaydını güncelleştirmeye çalışıyor, kaynak kilitleme sorunlarına yol açabilir. İş akışı hataları oluşur ve **SQL zaman aşımı: kaynak _kaynak adında_kilit alınamıyor**, kaydedilir. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Değişiklikleri izlemek için notları kullanın  
 İş akışlarını düzenlerken Notlar sekmesini kullanmanız ve ne istediğinizi ve ne yaptığımız olduğunu yazmanız gerekir. Bu, başka birinin yaptığınız değişiklikleri anlamasına olanak sağlar.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 [Iş akışı işlemlerine genel bakış](workflow-processes.md)   
 [İş akışı süreçlerini yapılandırma](configure-workflow-steps.md)   
 [İş akışı süreçlerini izleme ve yönetme](monitor-manage-processes.md)
   
