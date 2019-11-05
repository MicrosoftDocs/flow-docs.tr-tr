---
title: Common Data Service ile otomatik akış oluşturma | Microsoft Docs
description: Common Data Service bağlantı ve Microsoft Flow kullanarak iş akışları oluşturun
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 110f3947cf7ece97bfd9b83ca6a12ee46d04b4d6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547127"
---
# <a name="create-an-automated-flow-by-using-common-data-service"></a>Common Data Service kullanarak otomatik akış oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Common Data Service Bağlayıcısı ile Common Data Service veritabanınızda olayları oluşturma ve güncelleştirme ile başlatılan akışlar oluşturabilirsiniz. Ayrıca, Common Data Service veritabanı içindeki kayıtlar üzerinde oluşturma, güncelleştirme, alma ve silme işlemleri gerçekleştirebilirsiniz.

## <a name="initiate-a-flow-from-common-data-service"></a>Common Data Service akış başlatma

Akışınızı başlatmak için aşağıdaki tetikleyicilerden herhangi birini kullanabilirsiniz:

- Bir kayıt seçildiğinde
- Bir kayıt oluşturulduğunda
- Bir kayıt silindiğinde
- Bir kayıt güncelleştirilirken


> [!div class="mx-imgBorder"]
> tetikleyici ![seçin](./media/cds-connector/Triggers.png)

Seçili tetikleyici bir ortamın seçilmesini gerektiriyorsa, veritabanını her zaman Microsoft Flow çalıştığı ortam içinde kullanılacak `(Current)`öğesini seçebilirsiniz. Akışın belirli bir ortamdaki bir olaya göre her zaman tetiklenmesi istiyorsanız, o ortamı seçin.

> [!div class="mx-imgBorder"]
> ortam](./media/cds-connector/Environments.png) ![seçin

Yeni bir kayıt oluşturursanız, iş biriminizdeki bir kullanıcı tarafından yeni bir kayıt oluşturulduysa veya kuruluşunuzdaki herhangi bir kullanıcı tarafından yeni bir kayıt oluşturulduysa, akışın çalışıp çalışmamadığını öğrenmek için kapsamları kullanabilirsiniz.

> [!div class="mx-imgBorder"]
> kapsam seçin ![](./media/cds-connector/Scopes.png)

|Kapsam|Tetikleme zamanlaması|
| --- | --- |
|İş birimi|İşlem, iş biriminiz tarafından sahip olunan bir kayıt üzerinde gerçekleştirilir|
|Kuruluşunuzun|Eylem, kuruluş veya veritabanı içindeki herkes tarafından alındı|
|Üst öğe: alt departman|İşlem, iş biriminiz veya bir alt iş birimi tarafından sahip olunan bir kayıt üzerinde gerçekleştirilir|
|Kullanıcısını|Eylem size ait bir kayıt üzerinde alındı|

Bir kayıt güncelleştirilirken çalışan Tetikleyiciler, filtreleme özniteliklerini de kullanabilir. Bu, akışın yalnızca tanımlı özniteliklerden herhangi biri güncelleştirilirken çalışmasını sağlar.

> [!IMPORTANT]
> Flow 'un gereksiz çalışma yapmasını engellemek için filtre özniteliklerini kullanın.

Bu akış, akış kullanıcısının sahip olduğu ilk veya son kişi adının güncelleştirildiği her seferinde tetiklenir.

> [!div class="mx-imgBorder"]
> Filtre özniteliklerini ![](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Tetikleme ayrıcalıkları

Kayıt üzerinde oluşturma, güncelleştirme veya silme işlemini temel alan bir akış oluşturmak için, kullanıcının geri çağırma kayıt varlığı üzerinde oluşturma, okuma, yazma ve silme için Kullanıcı düzeyinde izinleri olması gerekir. Ek olarak, tanımlanan kapsamlara bağlı olarak, kullanıcının en azından aynı varlık üzerinde okuma düzeyi gerekebilir.  Ortam güvenliği hakkında [daha fazla bilgi edinin](https://docs.microsoft.com/power-platform/admin/database-security) .

## <a name="write-data-into-common-data-service"></a>Common Data Service veri yazma

Common Data Service veri yazmak için aşağıdaki eylemlerden herhangi birini kullanın:

- Yeni bir kayıt oluştur
- Kayıt güncelleştirme

Verilen Kullanıcı yeni bir hesap kaydı oluşturduğunda bir izleme görevi oluşturma örneği aşağıda verilmiştir.  

> [!div class="mx-imgBorder"]
> ![Izleme görevi](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Gelişmiş kavramlar

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Verileri müşteri, sahip ve ilgili alanlara yazma

Müşteri, sahip ve ilgili alanlara veri yazmak için iki alanın doldurulması gerekir.

| Alan kategorisi | örnek ayarlar |
| --- | --- |
| İnizle | İlgili = kaydın KIMLIĞI (örneğin, hesap KIMLIĞI) ve Ilgili türü listeden seçili olarak. |
| Müşterisi | Kayıt KIMLIĞINI ve listeden seçilen müşteri türünü temsil eder. |
| İnde | Listeden seçilen sistem kullanıcısının veya ekibin KIMLIĞINI ve sahip türünü temsil eder. |

### <a name="enable-upsert-behavior"></a>Büyük davranışı etkinleştir

Zaten varsa kaydı güncelleştiren veya yeni bir kayıt oluşturduğunda, ön Ekle eylemlerini sağlamak için **bir kaydı güncelleştir** komutunu kullanabilirsiniz. Upsert çağırmak için, varlığı ve bir GUID anahtarını sağlayın. Belirtilen türe ve anahtara sahip kayıt varsa, bir güncelleştirme oluşur. Aksi halde, belirtilen anahtara sahip bir kayıt oluşturulur.

### <a name="trigger-behavior"></a>Tetikleme davranışı

Bir kaydın güncelleştirmesinde kayıtlı bir Tetikleyiciniz varsa, akış, verilen kayıttaki her *işlenmiş* güncelleştirme için çalışır. Hizmet, akışınızı zaman uyumsuz olarak ve çağrının gerçekleştiği sırada yakaladığı yük ile çağırır.

> [!NOTE]
> Her birinin saniye içinde iki güncelleştirme varsa, akış en son sürümlü içerikle birden çok kez tetiklenebilir.

Ortamınızda Sistem işlerinin bir biriktirme listesi varsa akış çalıştırmaları gecikebilir.  Bu gecikme gerçekleşirse, akışı çağırmak için sistem işi çalıştırıldığında akışınız tetiklenir.
