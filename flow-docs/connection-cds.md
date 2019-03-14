---
title: Uygulamalar için Common Data Service ile otomatik akış oluşturma | Microsoft Docs
description: Uygulamalar için Common Data Service bağlantısı ve Microsoft Flow kullanarak iş akışları oluşturma
services: ''
suite: flow
documentationcenter: na
author: brandonsimons
manager: ryjones
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: brandonsimons
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f9a417f99b6ea4105a451b65f7ccabbf36922d78
ms.sourcegitcommit: 61f0eb1fdc54da02eb57dadf09899fa6f308b00d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57524509"
---
# <a name="create-an-automated-flow-by-using-common-data-service-for-apps"></a>Uygulamalar için Common Data Service'i kullanarak otomatik akış oluşturma

Uygulamalar için Common Data Service bağlayıcısıyla Common Data Service veritabanınızın içinde oluşturma ve güncelleştirme olayları tarafından başlatılan iş akışları oluşturabilirsiniz. Buna ek olarak, Uygulamalar için Common Data Service veritabanının içindeki kayıtlar üzerinde oluşturma, güncelleştirme, alma ve silme eylemleri de gerçekleştirebilirsiniz.

## <a name="initiate-a-flow-from-common-data-service-for-apps"></a>Uygulamalar için Common Data Service'den akış başlatma

Akışınızı başlatmak için aşağıdaki tetikleyicilerden birini kullanabilirsiniz:

- Kayıt seçildiğinde
- Kayıt oluşturulduğunda
- Kayıt silindiğinde
- Kayıt güncelleştirildiğinde


> [!div class="mx-imgBorder"]
> ![Tetikleyici seçin](./media/cds-connector/Triggers.png)

Seçilen tetikleyici için ortam seçilmesi gerekiyorsa, her zaman Microsoft Flow'un çalıştırıldığı ortamın içindeki veritabanını kullanan `(Current)` ayarını seçebilirsiniz. Akışınızın her zaman belirli bir ortamdaki bir olayla tetiklenmesini istiyorsanız, söz konusu ortamı seçin.

> [!div class="mx-imgBorder"]
> ![Ortam seçin](./media/cds-connector/Environments.png)

Akışınızın yeni kayıt oluşturduğunuzda, departmanınızdaki bir kullanıcı kayıt oluşturduğunda veya kuruluşunuzdaki herhangi bir kullanıcı kayıt oluşturduğunda çalıştırılacağını belirlemek için kapsamları kullanabilirsiniz.

> [!div class="mx-imgBorder"]
> ![Kapsam seçin](./media/cds-connector/Scopes.png)

|Kapsam|Tetikleyici zamanlaması|
| --- | --- |
|Departman|Departmanınızın sahip olduğu bir kayıt üzerinde eylem yapıldı|
|Kuruluş|Kuruluşunuzun veya veritabanınızın içindeki biri tarafından eylem yapıldı|
|Üst Öğe: Alt departman|Departmanınızın veya alt departmanın sahip olduğu bir kayıt üzerinde eylem yapıldı|
|Kullanıcı|Sizin sahip olduğunuz bir kayıt üzerinde eylem yapıldı|

Bir kayıt güncelleştirildiğinde çalıştırılan tetikleyiciler filtre özniteliklerini de kullanabilir. Bu sayede akışın yalnızca tanımlanan özniteliklerden biri güncelleştirildiğinde çalıştırılması sağlanır.

> [!IMPORTANT]
> Akışınızın gereksiz çalıştırılmasını önlemek için filtre özniteliklerini kullanın.

Akış kullanıcısının kişilerinden birini adı veya soyadı her güncelleştirildiğinde bu akış tetiklenir.

> [!div class="mx-imgBorder"]
> ![Filtre öznitelikleri](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Tetikleyici ayrıcalıkları

Kayıt üzerindeki oluşturma, güncelleştirme veya silme eylemleriyle tetiklenen bir akış oluşturmak için, kullanıcının Callback Registration varlığı üzerinde oluşturma, okuma, yazma ve silme eylemleri için kullanıcı düzeyi izinlerine sahip olması gerekir. Ayrıca, tanımlanan kapsamlara bağlı olarak kullanıcının aynı varlık üzerinde en azından aynı düzeyde okuma izni de olmalıdır.  Ortam güvenliği hakkında [daha fazla bilgi edinin](https://docs.microsoft.com/power-platform/admin/database-security).

## <a name="write-data-into-common-data-service-for-apps"></a>Uygulamalar için Common Data Service'e veri yazma

Uygulamalar için Common Data Service'e veri yazarken aşağıdaki eylemlerden birini kullanın:

- Yeni kayıt oluşturma
- Kaydı güncelleştirme

Burada, belirlenen kullanıcı yeni hesap kaydı oluşturduğunda bir izleme görevi oluşturma örneği verilmiştir.  

> [!div class="mx-imgBorder"]
> ![İzleme görevi](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Gelişmiş kavramlar

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Müşteri, sahip ve ilgili alanlarına veri yazma

Müşteri, sahip ve ilgili alanlarına veri yazmak için iki alanın doldurulması gerekir.

| Alan kategorisi | Örnek ayarlar |
| --- | --- |
| İlgili | İlgili = kaydın kimliği (örneğin, hesap kimliği) ve listeden seçilen İlgili Türü. |
| Müşteri | Kaydın kimliğini ve listeden seçilen müşteri türünü temsil eder. |
| Sahip | Sistem kullanıcısının veya takımın kimliğini ve listeden seçilen sahip türünü temsil eder. |

### <a name="enable-upsert-behavior"></a>Upsert davranışını etkinleştir

Varsa kaydı güncelleştiren veya yeni kayıt oluşturan upsert eylemleri sağlamak için **kaydı güncelleştir** komutundan yararlanabilirsiniz. Upsert çağrısı yapmak için varlığı ve GUID anahtarını sağlayın. Belirtilen türe ve anahtara sahip bir kayıt varsa, güncelleştirme yapılır. Aksi takdirde, belirtilen anahtarla bir kayıt oluşturulur.

### <a name="trigger-behavior"></a>Tetikleyici davranışı

Kaydın güncelleştirmesine kaydedilmiş bir tetikleyici varsa, belirlenen kayıtta *işlenen* her güncelleştirmede akış çalıştırılır. Hizmet akışınızı zaman uyumsuz olarak ve çağrı yapıldığı zaman yakaladığı yükle birlikte çağırır.

> [!NOTE]
> Birkaç saniye arayla gerçekleşen iki güncelleştirmeniz varsa, içeriğin en son sürümüyle akış birden çok kez tetiklenebilir.

Ortamınızda bir sistem işleri kapsamı varsa akış çalıştırmaları geciktirilebilir.  Böyle bir gecikme olursa, akışı çağıran sistem işi çalıştırıldığında akış tetiklenir.
