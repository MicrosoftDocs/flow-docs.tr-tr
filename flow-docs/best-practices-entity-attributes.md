---
title: İş süreci akışı varlık özniteliklerini kullanmak için en iyi yöntemler | MicrosoftDocs
description: İş süreci akışı varlık özniteliklerini kullanmanın en iyi yöntemlerini öğrenin.
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
ms.openlocfilehash: 950f03d78e708f00f28b68daf7c1012fae231c95
ms.sourcegitcommit: 2931edb777c1ed57e040670fc8a1c55252ac95b1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/25/2019
ms.locfileid: "64472984"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>İş süreci akış özniteliklerini kullanmanı en iyi yöntemleri


Varlıklardaki eski süreçle ilgili öznitelikler kullanım dışı bırakıldı. Burada iş süreci akış varlığında *Etkin Aşama* (activestageid) özniteliğini kullanmaya yönelik en iyi yöntemlerden bazılarını bulabilirsiniz. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>İş süreci akışının etkin aşamasıyla ilgili raporlama

**Müşteri Adayından Fırsat Satışına Geçiş Süreci**'nin açık olduğu etkin aşamayla ilgili raporlama yoluyla potansiyel satışlarınızın görünümünü elde etmek istediğinizi varsayalım.

Daha önce aşamasına göre iş süreçlerini raporlamak için iş süreci akışının her ilgili varlığında bir görünüm tanımlanabilir ve ardından *Etkin Aşama* (activestageid) alanıyla ilgili raporlama yapılabilirdi.

İlgili varlıklarda *Etkin Aşama* (activestageid) alanının kullanımdan kaldırılmasıyla iş süreci akışlarında raporlamanın iki yolu vardır.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>1. Seçenek: İş süreci akış varlığıyla ilgili görünümler ve grafikler **(Önerilen)**

9.0 ve üstü sürümlerde her iş süreci akışı genellikle iş süreci akışıyla aynı adda kendi Common Data Service varlığını oluşturur. İş süreci akışıyla ilgili raporlamak için iş süreci akışının raporlamak istediğiniz varlığını seçin ve ardından aynı daha önce yaptığınız gibi görünümleri ve grafikleri oluşturun.

Örneğimizde **Müşteri Adayından Fırsat Satışına Geçiş Süreci** varlığına gitmek için şu adımları izleyin:
1. https://web.powerapps.com adresine gidin.
1. **Veri**'yi seçin.
1. **Varlıklar**'ı seçin.
1. **Tümü** filtresini ayarlayın.
1. **Müşteri Adayından Fırsat Satışına Geçiş Süreci** varlığını arayın ve seçin.

   ![müşteri adayından fırsat satışına geçiş süreci varlığı](media/best-practices-entity-attributes/lead-opportunity-process.png)

Burada aynı başka varlıkta yaptığınız gibi görünümleri ve grafikleri tanımlayabilirsiniz.

![çeviri işlemi varlığı ayrıntıları](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

Bu yaklaşımın bir avantajı, birden çok varlığa yayılan iş süreci akışlarıyla ilgili raporlamak için tek bir görünüm veya grafik kullanabilmenizdir.

Üstelik iş süreci akış varlığı Common Data Service'teki diğer özel varlıklardan farklı değildir; ihtiyacınız olan tüm bilgileri izlemek için varlığa özel alanlar ekleyebilirsiniz.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>2. Seçenek: Etkin aşamayı ilgili varlığa kopyalama

Alternatif olarak, ilgili varlığı raporlamaya devam etmek için bir akış oluşturarak iş süreci akış varlığındaki *Etkin Aşama* (activestageid) alanını ilgili Common Data Service varlıklarının özel alanına kopyalayın.

Bu yaklaşımı kullanırken aşağıdaki birkaç noktayı aklınızda tutmalısınız:

1.  Tek varlıkta çalışan birden çok iş süreci akışı olması mümkündür. Bu yaklaşımla, en iyi yöntem varlıkta çalışan her iş süreci akışı için etkin aşamayı depolayan bir özel alan bulunmasıdır. Bu yaklaşım raporlamanın bütünlüğünü güvence altına alır.

1.  Raporlama ilgili varlıktan yönlendirildiğinden, birden çok varlığa yayılan iş süreci akışlarını raporlayan tek bir görünüm oluşturmak mümkün değildir.

## <a name="using-the-active-stage-to-run-logic"></a>Etkin aşamayı kullanarak mantık çalıştırma

Burada etkin aşama temelinde mantık çalıştırmak isteyebileceğiniz bazı örnekler verilmiştir:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Etkin aşamayı kullanarak istemci tarafı mantığı çalıştırma

İş sürecini kullanırken otomatik olarak yapılmasını isteyebileceğiniz birçok şey vardır. Örneğin:

-   Form veya iş süreci akışıyla ilgili olarak yeni sağlanan bilgiler temelinde etkin iş süreci akışını değiştirme.

-   Kullanıcıların adımlarda veya form alanlarında girdiği değerler temelinde etki aşamayı sonraki veya önceki aşamaya taşıma.

-   Seçilen aşama temelinde form sekmelerini ve alanlarını gizleme veya gösterme.

-   Etkin iş süreci akışlarını, etkin veya seçilen aşamayı ya da etkin aşamanın taşınması gibi olayları temel alarak bilgilendirici iletiler gösterme ve hesaplamalar çalıştırma.

> [!TIP]
> Bunlar gibi senaryolarda iş süreci akışları için desteklenen [istemci API'lerini](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) kullanın.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Etkin aşamayı kullanarak sunucu tarafı mantığı çalıştırma

İş süreci akışını temel alan otomasyonun sunucu tarafında yapılması gereken durumlar olabilir. Örneğin:

-   **Fırsat Satış Süreci**'nde aşamanın **Uygun Olma** durumu 15 günden uzun süre etkin olduğunda kullanıcıya e-posta gönderme.

-   **Fırsat Satış Süreci**'nin etkin aşaması her değiştiğinde otomatik olarak bu aşamaya uygun bir dizi etkinlik oluşturma.

-   Kapanış için telefon görüşmesi etkinliği tamamlandığında **Fırsat Satış Süreci**'ni otomatik olarak bitirme.

> [!TIP]
> İş süreci akışı için varlıkta tanımladığınız klasik Common Data Service iş akışlarını veya akışları kullanın.
> 

İç çözüm incelemelerine yönelik etkinlikler oluşturan klasik bir Common Data Service iş akışı oluşturmak ve **Fırsat Satış Süreci**'nin **Teklif** aşamasında müşteriyi izlemek için:

1. Bunu **Fırsat Satış Süreci** varlığında oluşturun ve varlığın **Etkin Aşama** alanı her değiştiğinde çalıştırılacak şekilde ayarlayın. 
1. **Etkin Aşama** alanının **Teklif**'e eşit olup olmadığını denetleyecek bir koşul tanımlayın. 
1. Çözümün iç incelemesi ve çözümü incelemeye yönelik müşteri araması için sırasıyla bir randevu ve telefon araması kaydı oluşturun.

   ![aşama izlemeyi kapatma](media/best-practices-entity-attributes/close-stage-followup.png)
