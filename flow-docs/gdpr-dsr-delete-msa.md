---
title: Microsoft Hesapları (MSA) için Microsoft Flow GDPR Veri Sahibi Silme İstekleri | Microsoft Docs
description: Microsoft Flow’u kullanarak Microsoft Hesapları için GDPR Veri Sahibi Silme İsteklerini yanıtlamayı öğrenin.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: e42da775d5c004bfbe0d6bb8923e6d05aaa5e976
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64454227"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>GDPR Veri Sahibi Silme İsteklerini yanıtlama

Kişisel verilerin kaldırılması işleminin yapıldığı **silme hakkı**, GDPR’de önemli bir korunma yöntemidir. Kaldırılan kişisel veriler, denetim günlüğü bilgileri dışında tüm kişisel verileri kapsar.

Microsoft Flow, kullanıcıların otomatik iş akışları oluşturmasını sağlar. Bir kullanıcı, Microsoft Flow’dan kişisel verilerini silmeye karar verdiğinde kullanıcı kişisel verilerini gözden geçirebilir ve bu verilerin bir kısmının mı yoksa tamamının mı silineceğini belirleyebilir.

Aşağıdaki tabloda, hangi kişisel verilerin otomatik olarak silindiği ve hangi verilerin bir Microsoft Hesabı (MSA) kullanıcısı tarafından gözden geçirilip silinmesi gerektiği gösterilmektedir.

|MSA kullanıcısının gözden geçirip silmesi gerekir|Otomatik olarak silinir|
|------|------|
|Ürün ve hizmet etkinliği|Çalıştırma geçmişi|
|Akışlar|Etkinlik Akışı|
|Bağlantılar||

Microsoft Flow, kullanıcıların otomatik olarak silinmeyen kişisel verileri ve kaynakları bulmasına, gözden geçirmesine veya değiştirmesine yardımcı olacak aşağıdaki deneyimleri sunar:

## <a name="manage-delete-requests"></a>Silme isteklerini yönetme

Aşağıdaki adımlarda, GDPR için silme isteklerine nasıl self servis sunulacağı açıklanmaktadır.

### <a name="delete-product-and-service-activity"></a>Ürün ve hizmet etkinliğini silme

1. Yönetilen hizmet hesabınızla [Microsoft Gizlilik Panosu](https://account.microsoft.com/privacy/)’nda oturum açın.
1. **Etkinlik geçmişi** bağlantısını seçin.

    ![Etkinlik Geçmişi](./media/gdpr-dsr-export-msa/activityhistory.png)

1. Microsoft Flow da dahil olmak üzere, kullandığınız farklı Microsoft uygulamaları ve hizmetleri için etkinlik geçmişinizi arayabilir veya bunlara göz atabilirsiniz. Belirli ürün veya hizmet etkinliği olaylarını kaldırmak için **Sil**’i seçin.

    ![Etkinliği Silme](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Birkaç dakika içinde öğe silinir ve gizlilik panosundan kaldırılır.

### <a name="list-and-delete-flows"></a>Akışları listeleme ve silme

Kullanıcı, şu adımları izleyerek akışlarını listeleyebilir ve [Microsoft Flow](https://flow.microsoft.com)’dan silebilir:

1. [Microsoft Flow](https://flow.microsoft.com)’da oturum açın ve sonra **Akışlarım**’ı seçin.

1. Sildiğiniz akışın yanındaki **...** öğesini seçin ve **Sil** seçeneğini belirleyin.

    ![Etkinliği Silme](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Bağlantıları Silme

Bağlayıcılar, API’ler ve SaaS sistemleriyle iletişim kurmak için bağlantıları kullanır. Bağlantılar, bağlantıyı oluşturan kullanıcıya başvurular içerir. Kullanıcı, aşağıdaki adımları izleyerek istediği zaman bu başvuruları silebilir:

1. [Microsoft Flow](https://flow.microsoft.com)’da oturum açın, dişli simgesini ve ardından **Bağlantılar**’ı seçin.

    ![Etkinliği Silme](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Silmek istediğiniz bağlantıyı seçin, **...** öğesini seçin ve sonra **Sil** seçeneğini belirleyin.

    ![Etkinliği Silme](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Onay isteminde **Sil** simgesini seçin.

    ![Etkinliği Silme](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Sildiğiniz bağlantıyı diğer akışlar kullanıyorsa, yeni bir bağlantının gerekli olduğu size bildirilir. Aksi takdirde, devam etmek için **Sil**’i seçin.
>
>

## <a name="learn-more"></a>Daha fazla bilgi

* [Microsoft Flow](getting-started.md) ile çalışmaya başlama
* Microsoft Flow ile ilgili [yenilikleri](release-notes.md) öğrenin
