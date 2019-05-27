---
title: İş akışı işlemlerini yönetmek için en iyi yöntemler | Microsoft Docs
description: İş akışlarını kullanmak için önerilen yöntemleri anlayın
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
ms.openlocfilehash: c0a59a625f4d43d125bde6ddf6edd5da5b6f6430
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460582"
---
# <a name="best-practices-for-workflow-processes"></a>İş akışı işlemleri için en iyi yöntemler

Bu konuda iş akışı işlemi oluşturmak ve yönetmek için en iyi yöntemler anlatılmaktadır.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Sonsuz döngülerden kaçının  
 Bir iş akışında sunucu kaynaklarını kullanan ve performansı kötü yönde etkileyen bir sonsuz döngü başlatan mantık oluşturmak mümkündür. Sonsuz döngünün sık görüldüğü durumlardan biri, bir öznitelik güncelleştirildiğinde başlatılacak şekilde yapılandırılmış bir iş akışının aynı iş akışının mantığındaki bir özniteliği güncelleştirmesidir. Güncelleştirme eylemi kaydı güncelleştiren iş akışını tetikler ve bunun sonucunda iş akışı tekrar tekrar tetiklenir.  
  
 Oluşturduğunuz iş akışları, sonsuz döngüleri tespit edip durduracak mantığa sahiptir. Bir iş akışı işleminin kısa bir süre içinde belirli bir kayıt üzerinde belirli bir sayının üzerinde çalıştırılması durumunda işlem şu hatayla başarısız olur: **Bu iş akışı işi, onu başlatan iş akışı sonsuz döngü içeriğinden iptal edildi. İş akışı mantığını düzeltip yeniden deneyin**. Çalıştırma sayısı üst sınırı 16 olarak belirlenmiştir.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>İş akışı şablonlarını kullanın  
 Benzer iş akışlarınız varsa ve aynı deseni kullanacak daha fazla iş akışı oluşturmayı planlıyorsanız iş akışınızı iş akışı şablonu olarak kaydedebilirsiniz. Bu sayede benzer bir iş akışı oluşturmanız gerektiğinde iş akışını şablonu kullanarak oluşturabilir ve tüm koşullarla eylemleri sıfırdan girmek zorunda kalmazsınız.  
  
 **İşlem Oluştur** iletişim kutusunda **Mevcut bir şablondan yeni işlem (listeden seçin)** öğesini seçin.  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Alt iş akışlarını kullanın  
 Aynı mantığı farklı iş akışlarına veya koşullu dallara uyguluyorsanız bu mantığı bir alt iş akışı olarak tanımlayabilir, böylece bu mantığı her iş akışında veya koşullu dalda çoğaltmaktan kaçınabilirsiniz. Bu sayede iş akışlarınızın bakımını daha kolay yapabilirsiniz. Aynı mantığı uygulayabilecek birden fazla iş akışını incelemek yerine yalnızca bir iş akışını güncelleştirmeniz yeterli olacaktır.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Tamamlanan iş akışı işlerini otomatik olarak silin
Arka plan (zaman uyumsuz) iş akışlarının tanımında **Tamamlanan iş akışı işlerini otomatik olarak sil (disk alanında yer açmak için)** seçeneğini belirlemenizi öneririz. Bu onay kutusunu işaretlediğinizde sistem yer açmak için başarılı yürütme işlemlerinin iş akışı günlüklerini silebilir. Başarısız iş akışı yürütme işlemlerinin günlükleri sorun giderme amacıyla kullanmak üzere her zaman kaydedilecektir.  

![İş akışı iş bekletme](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Hatalarla karşılaşan iş akışı işlerinizin günlüklerini saklayın  
Arka planda çalışmayan (zaman uyumlu) iş akışlarının tanımında**Hatalarla karşılaşan iş akışı işlerinizin günlüklerini saklayın** seçeneğini belirlemenizi öneririz. Bu seçeneği belirlediğinizde başarısız olan iş akışı yürütme işlemlerinin günlükleri sorun giderme amacıyla kaydedilir. Başarılı zaman uyumlu iş akışı yürütme işlemlerinin günlükleri yer açmak için silinecektir.   

![Başarısız iş akışları için günlükleri saklama seçeneği](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Aynı varlığı güncelleştiren iş akışı sayısını sınırlayın
Aynı varlığı güncelleştiren birden fazla iş akışının çalıştırılması kaynak kilitleme sorunlarına neden olabilir. Her fırsat güncelleştirmesinin ilgili hesapta bir güncelleştirmeyi tetiklediği birden fazla iş akışına sahip olduğunuzu düşünün. Bu iş akışlarının birden fazla örneğinin aynı anda çalışarak aynı hesap kaydını güncelleştirmeye çalışması kaynak kilitleme sorunlarına yol açabilir. İş akışı hataları oluşur ve **SQL Zaman Aşımı: _Kaynak adı_ kaynağında kilit alınamıyor** gibi bir hata iletisi kaydedilir. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Değişiklikleri izlemek için Notlar sekmesini kullanın  
 İş akışlarınızı düzenlediğinizde Notlar sekmesini kullanarak yaptığınız değişiklikleri ve nedenini yazmanız önerilir. Bu sayede diğer kullanıcılar bu değişikliklerin nedenini anlayabilir.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 [İş akışı süreçlerine genel bakış](workflow-processes.md)   
 [İş akışı işlemlerini yapılandırma](configure-workflow-steps.md)   
 [İş akışı süreçlerini izleme ve yönetme](monitor-manage-processes.md)
   
