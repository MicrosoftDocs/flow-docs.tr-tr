---
title: İş süreci akışı varlık özniteliklerini kullanmaya yönelik en iyi uygulamalar | MicrosoftDocs
description: İş süreci akışı varlık özniteliklerini kullanmaya yönelik en iyi uygulamaları öğrenin.
ms.custom: ''
ms.date: 04/23/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Business Process Flows
helpviewer_keywords:
- flow
- process flow
- business process flow
- process
- workflow
author: msftman
ms.author: deonhe
manager: kvivek
ms.openlocfilehash: b46eac7317db8f5b63ebcd7b8b1fe8c79109bc11
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545276"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>İş süreci akış özniteliklerini kullanmanın en iyi yöntemleri
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]


Varlıklardaki işle ilgili eski öznitelikler kullanım dışıdır. İşte iş süreci akışı varlığında *etkin aşama* (activestageid) özniteliğini kullanmaya yönelik bazı en iyi yöntemler aşağıda verilmiştir. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>İş süreci akışının etkin aşamasında raporlama

**Fırsat satışı işleminin** açık olduğu etkin aşamada raporlama yaparak satış işlem hattınızın bir görünümünü almak istediğinizi varsayalım.

Daha önce, iş süreçlerini aşamasına göre raporlamak için, birisi iş süreci akışının ilgili her varlığında bir görünüm tanımlayabilir ve ardından *etkin aşama* (activestageid) alanına rapor verebilir.

İlgili varlıklarda *etkin aşama* (activestageid) alanının kullanımdan kaldırılması sayesinde, iş süreci akışlarını raporlamak için iki yol vardır.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Seçenek 1: iş süreci akış varlığındaki görünümler ve grafikler **(önerilir)**

9,0 ve üzeri sürümlerde her iş süreci akışı, genellikle iş süreci akışıyla aynı ada sahip kendi Common Data Service varlığını oluşturur. İş süreci akışını raporlamak için, raporlamak istediğiniz iş süreci akışının varlığını seçin ve ardından, daha önce yaptığınız gibi görünümler ve grafikler oluşturun.

Bizim örneğimizde, **fırsat satış süreci varlığına müşteri adayı** 'na gitmek için aşağıdaki adımları izleyin:
1. https://web.powerapps.comgidin.
1. **Verileri**seçin.
1. **Varlıkları**seçin.
1. Filtreyi **Tümü**olarak ayarlayın.
1. ' İ arayın ve ardından **fırsat satışları işlem** varlığı ' nı seçin.

   ![fırsat satış süreci varlığına lider](media/best-practices-entity-attributes/lead-opportunity-process.png)

Burada, diğer varlıklar üzerinde yaptığınız gibi görünümleri ve grafikleri de tanımlayabilirsiniz.

![Çeviri işlemi varlık ayrıntıları](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

Bu yaklaşımın avantajı, birden çok varlığı kapsayan iş süreci akışlarını raporlamak için tek bir görünüm veya grafik kullanmanıza olanak sağlar.

Ayrıca, iş süreci akışı varlığı Common Data Service başka bir özel varlıktan farklı olmadığından, ihtiyacınız olan ek bilgileri izlemek için varlığa özel alanlar ekleyebilirsiniz.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Seçenek 2: etkin aşamayı ilgili varlığa kopyalama

Alternatif olarak, ilgili varlığı raporlamaya devam etmek için, iş süreci akışı varlığındaki *etkin aşama* (activestageid) alanını ilgili Common Data Service varlıklarındaki özel bir alana kopyalamak üzere bir akış oluşturun.

Bu yaklaşımı kullanırken göz önünde bulundurmanız gereken birkaç nokta vardır:

1.  Tek bir varlıkta birden fazla iş süreci akışı çalışıyor olabilir. Bu yaklaşım sayesinde, varlık üzerinde çalışan her iş işlemi akışı için etkin aşamayı depolayan bir özel alan olması en iyisidir. Bu yaklaşım, raporlama bütünlüğünü sağlar.

1.  Raporlama ilgili varlıktan çalıştırıldığından, birden çok varlığı kapsayan iş süreci akışlarını raporlayan tek bir görünüm oluşturmak mümkün değildir.

## <a name="using-the-active-stage-to-run-logic"></a>Mantığı çalıştırmak için etkin aşamayı kullanma

Aşağıda, etkin aşamayı temel alan mantığı çalıştırmak isteyebileceğiniz bazı durumlar verilmiştir:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>İstemci tarafı mantığını çalıştırmak için etkin aşamayı kullanma

İş sürecini kullanırken, otomatik olarak yapmak isteyebileceğiniz pek çok şey vardır. Örneğin:

-   Etkin iş işlem akışını, form veya iş işlem akışındaki yeni kullanılabilir bilgilere göre değiştirin.

-   Adımlar veya form alanları için girilen kullanıcılara değer temelinde, etkin aşamayı bir sonraki veya önceki aşamaya taşıyın.

-   Form sekmelerini ve alanlarını seçili aşamasına göre gizleyin veya gösterin.

-   Etkin iş süreci akışları, etkin veya seçili aşama ya da etkin aşamayı taşıma gibi olayları temel alan bilgilendirici iletileri gösterin ve onları çalıştırın.

> [!TIP]
> Bunlar gibi senaryolar için, iş süreci akışları için desteklenen [Istemci API 'leri](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) kümesini kullanın.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Sunucu tarafı mantığını çalıştırmak için etkin aşamayı kullanma

İş süreci akışını temel alan Otomasyon 'un sunucu tarafında yapılması gereken durumlar olabilir. Örneğin:

-   **Fırsat satışı işleminin** aşamasını **nitelemek** 15 günden daha uzun bir süre etkin değilse kullanıcıya bir e-posta gönderin.

-   Her değiştiğinde **fırsat satışı sürecinin** etkin aşamasına uygun bir etkinlik kümesini otomatik olarak oluşturun.

-   Kapanış için telefon araması etkinliği tamamlandığında **fırsat satışı işlemini** otomatik olarak tamamlama.

> [!TIP]
> İş süreci akışı için varlıkta tanımladığınız klasik Common Data Service iş akışlarını veya akışları kullanın.
> 

Dahili çözüm incelemeleri için etkinlikler oluşturan ve **fırsat satışı sürecinin** **öner** aşamasında müşteriyle birlikte izlenecek bir klasik Common Data Service iş akışı oluşturmak için:

1. Bunu **fırsat satış süreci** varlığında oluşturun ve varlığın **etkin aşama** alanı her değiştiğinde çalıştırılacak şekilde ayarlayın. 
1. **Etkin aşama** alanının **önerilmesine**izin olup olmadığını denetlemek için bir koşul tanımlayın. 
1. Çözümün iç gözden geçirilmesi için bir randevu ve telefon araması kaydı ve çözümü gözden geçirmek için müşteri çağrısı oluşturun.

   ![aşama izleme 'yi kapat](media/best-practices-entity-attributes/close-stage-followup.png)
