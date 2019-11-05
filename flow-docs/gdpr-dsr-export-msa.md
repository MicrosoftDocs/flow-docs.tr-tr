---
title: Microsoft hesapları için Microsoft Flow GDPR Data Subject dışarı aktarma Istekleri (MSA) | Microsoft Docs
description: Microsoft hesapları için GMBU veri sahibine yönelik dışarı aktarma Isteklerini yanıtlamak üzere Microsoft Flow nasıl kullanacağınızı öğrenin.
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
ms.date: 5/25/2018
ms.author: Deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 253d6785228fb28b5c78d0cae629a237a2e176da
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548143"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Microsoft Flow için GDPR veri sahibine dışarı aktarma Isteklerine yanıt verme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Genel Veri Koruma Yönetmeliği (GDPR) ile ilgili yolculukta sizinle iş ortağı taahhüdünün bir parçası olarak, hazırlanmanıza yardımcı olacak belgeler geliştirdik. Belgeler, yalnızca GDPR için hazırlanmak için yaptığımız şeyleri değil, ayrıca Microsoft Flow kullanırken GDPR uyumluluğunu desteklemek için Microsoft ile bu adımları da paylaşacağınızı açıklamaktadır.

## <a name="manage-export-requests"></a>Dışarı aktarma isteklerini yönetme

*Veri taşınabilirliği hakkı* , veri ilgilileri, başka bir veri denetleyicisine aktarılabilecek elektronik bir biçimde ("yapılandırılmış, yaygın olarak kullanılan, makine tarafından okunabilen ve birlikte çalışabilen bir biçimde") kişisel verilerinin bir kopyasını talep etmesine olanak tanır.

Belirli bir kullanıcı için kişisel verileri bulmak veya dışarı aktarmak için [Microsoft Gizlilik panosu](https://account.microsoft.com/privacy/)'nu veya [Microsoft Flow](https://flow.microsoft.com/) kullanın.

|Kişisel veriler|Konumuna|
|-----------------|-------------------|
|Ürün ve hizmet etkinliği|Microsoft Gizlilik panosu|
|Var|Microsoft Flow Oluşturucu portalı|
|çalıştırma geçmişi|Microsoft Flow Oluşturucu portalı|
|Etkinlik akışı|Microsoft Flow Oluşturucu portalı|
|Bağlantının|Microsoft Flow Oluşturucu portalı|

## <a name="export-product-and-service-activity"></a>Ürün ve hizmet etkinliğini dışarı aktarma

1. Microsoft hesabınızı (MSA) kullanarak [Microsoft Gizlilik panosu](https://account.microsoft.com/privacy/) 'nda oturum açın.
1. **Etkinlik geçmişini**seçin.

    ![etkinlik geçmişi](./media/gdpr-dsr-export-msa/activityhistory.png) kullandığınız farklı Microsoft uygulamaları ve hizmetleri için etkinlik geçmişinize gözatabilmeniz gerekir.
1. **Ürün ve hizmet etkinlik** verilerini dışarı aktarmak Için **verilerinizi indir**' i SEÇIN ve ardından **Yeni Arşiv oluştur**' u seçin.

    ![Verilerinizi indirin](./media/gdpr-dsr-export-msa/downloaddata.png)

1. **Uygulama & hizmeti kullanımı**' nı seçin ve ardından **Arşiv oluştur**' u seçin.

    ![Verilerinizi indirin](./media/gdpr-dsr-export-msa/create-archive.png)
1. Yeni bir arşiv oluşturulur. Verdiğiniz ürün ve hizmet etkinliği verilerinizi almak için **İndir** ' i seçin.

    ![İndirme](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Akışı dışarı aktarma

Bir akışa erişimi olan Son Kullanıcı şu adımları izleyerek akışı dışarı aktarabilir:

1. [Microsoft Flow](https://flow.microsoft.com/)oturum açın.

1. **Akışlarımı**seçin ve ardından dışarı aktarılacak akışı seçin.

1. Seç **... Daha fazla**ve ardından **dışarı aktar**' ı seçin.

    ![Akışı dışarı aktar](./media/gdpr-dsr-export/export-flow.png)

1. **Paket (. zip)** öğesini seçin.

Akışınız artık daraltılmış bir paket olarak kullanılabilir olacaktır. Daha fazla bilgi için bkz. [bir akışı dışarı ve içeri aktarma](https://flow.microsoft.com/blog/import-export-bap-packages/)hakkında blog gönderisi.

## <a name="export-run-history"></a>Çalıştırma geçmişini dışarı aktar

Çalıştırma geçmişi, bir akış için tüm çalıştırmaların bir listesini içerir. Bu veriler, Tetikleyiciler ve eylemler için akışın durum, başlangıç saati, süre ve giriş/çıkış verilerini içerir.

Akışa erişimi olan bir son kullanıcı, bu verileri dışarı aktarmak için şu adımları izleyebilir:

1. [Microsoft Flow](https://flow.microsoft.com/)oturum açın.
1. **Akışlarım** bağlantısını seçin ve ardından çalıştırma geçmişini dışarı aktarmak istediğiniz akışı seçin.
1. **Çalıştırma geçmişi** bölmesinde **Tümünü gör**' ü seçin.

    ![çalıştırma geçmişi](./media/gdpr-dsr-export/run-history.png)

1. **CSV 'Yi indir**' i seçin.

    ![CSV 'yi indir](./media/gdpr-dsr-export/download-csv.png)

Çalışma geçmişi bir. csv dosyası olarak indirilir, böylece sonuçları çözümlemek için Microsoft Excel 'de veya bir metin düzenleyicisinde açabilirsiniz.

## <a name="export-a-users-activity-feed"></a>Kullanıcının etkinlik akışını dışarı aktarma

[Microsoft Flow](https://flow.microsoft.com/), etkinlik akışı kullanıcının etkinlik, başarısızlık ve bildirimlerin geçmişini gösterir. Kullanıcılar, aşağıdaki adımları izleyerek etkinlik akışını görüntüleyebilir:

1. [Microsoft Flow](https://flow.microsoft.com/)oturum açın, sağ üst köşenin yakınındaki zil simgesini seçin ve ardından **Tüm etkinliği göster**' i seçin.

    ![Etkinlik akışını göster](./media/gdpr-dsr-export/show-activity-feed.png)

1. **Etkinlik** ekranında sonuçları kopyalayın ve Microsoft Word gibi bir metin düzenleyicisine yapıştırın.

    ![Etkinlik akışını göster](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Kullanıcının bağlantılarını dışarı aktarma

Bağlantılar, akışların API 'lere, SaaS uygulamalarına ve diğer üçüncü taraf sistemlere bağlanmasına imkan tanır. Bağlantılarınızı görüntülemek için şu adımları izleyin:

1. [Microsoft Flow](https://flow.microsoft.com/)oturum açın, sağ üst köşenin yakınındaki dişli simgesini seçin ve ardından **Bağlantılar**' ı seçin.

    ![Bağlantıları göster](./media/gdpr-dsr-export/show-connections.png)
1. Sonuçları kopyalayın ve Microsoft Word gibi bir metin düzenleyicisine yapıştırın.
