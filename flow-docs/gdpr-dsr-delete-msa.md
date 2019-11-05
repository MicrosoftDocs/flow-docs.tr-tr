---
title: Microsoft hesapları için Microsoft Flow GDPR veri konusu silme Istekleri (MSA) | Microsoft Docs
description: Microsoft hesapları için guz veri konu silme Isteklerini yanıtlamak üzere Microsoft Flow nasıl kullanacağınızı öğrenin.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 379c88842b9724c7bdb6adfed79e2bb11497694d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548055"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>GDPR veri konusu silme Isteklerini yanıtlama
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Kişisel verilerin kaldırılmasına ilişkin **hak** , GDPR içinde bir anahtar korumasından oluşur. Kişisel verileri kaldırmak, denetim günlüğü bilgileri hariç tüm kişisel verileri kaldırmayı içerir.

Microsoft Flow, kullanıcıların otomatik iş akışları oluşturmasına olanak tanır. Bir Kullanıcı Microsoft Flow kişisel verilerini silmeye karar verdiğinde, Kullanıcı kendi kişisel verilerini gözden geçirebilir ve bunun bir kısmını veya tümünü silip silmeyeceğinizi belirleyebilir.

Aşağıdaki tabloda, hangi kişisel verilerin otomatik olarak silineceği ve hangi verilerin bir Microsoft hesabı (MSA) kullanıcısına gözden geçirmesini ve silmesini gerektirdiğini gösterilmektedir.

|MSA kullanıcısının gözden geçirmesini ve silmesini gerektirir|Otomatik olarak silindi|
|------|------|
|Ürün ve hizmet etkinliği|çalıştırma geçmişi|
|Var|Etkinlik akışı|
|Bağlantının||

Microsoft Flow, kullanıcıların otomatik olarak silinmeyen kişisel verileri ve kaynakları bulmasına, incelemesine veya değiştirmesine yardımcı olmak için aşağıdaki deneyimleri sunar:

## <a name="manage-delete-requests"></a>Silme isteklerini yönetme

Aşağıdaki adımlarda, GDPR için silme isteklerinin nasıl kendine kullanılacağı açıklanır.

### <a name="delete-product-and-service-activity"></a>Ürün ve hizmet etkinliğini Sil

1. MSA ile [Microsoft Gizlilik panosu](https://account.microsoft.com/privacy/) 'nda oturum açın.
1. **Etkinlik geçmişi** bağlantısını seçin.

    ![Etkinlik geçmişi](./media/gdpr-dsr-export-msa/activityhistory.png)

1. Microsoft Flow dahil olmak üzere, kullandığınız farklı Microsoft uygulamaları ve hizmetleri için etkinlik geçmişinizi arayabilir veya bu geçmişinize gözatada gidebilirsiniz. Belirli ürün veya hizmet etkinlik olaylarını kaldırmak için **Sil** ' i seçin.

    ![Etkinliği sil](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Birkaç dakika içinde, öğe silinir ve gizlilik panosundan kaldırılır.

### <a name="list-and-delete-flows"></a>Akışları listeleme ve silme

Bir Kullanıcı, aşağıdaki adımları tamamlayarak akışlarını [Microsoft Flow](https://flow.microsoft.com) listeleyebilir ve silebilir:

1. [Microsoft Flow](https://flow.microsoft.com)oturum açın ve **Akışlarım**' ı seçin.

1. Sildiğiniz akışın yanında **..** . öğesini seçin ve **Sil**' i seçin.

    ![Etkinliği sil](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Bağlantıları sil

Bağlayıcılar API 'Ler ve SaaS sistemleriyle iletişim kurmak için bağlantıları kullanır. Bağlantılar, onları oluşturan kullanıcıya başvuruları içerir. Kullanıcı bu başvuruları istediğiniz zaman silebilir:

1. [Microsoft Flow](https://flow.microsoft.com)açın, dişli simgesini seçin ve ardından **Bağlantılar**' ı seçin.

    ![Etkinliği sil](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Silmek istediğiniz bağlantıyı seçin, **...** öğesini seçin ve **Sil**' i seçin.

    ![Etkinliği sil](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Onay isteminde **Sil** simgesini seçin.

    ![Etkinliği sil](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Diğer akışlar bağlantıyı kullanıyorsa, yeni bir bağlantının gerekli olduğu bildirilir. Aksi takdirde, devam etmek için **Sil** ' i seçin.
>
>

## <a name="learn-more"></a>Daha fazla bilgi edinin

* [Microsoft Flow](getting-started.md) kullanmaya başlayın
* Microsoft Flow [yenilikleri öğrenin](release-notes.md)
