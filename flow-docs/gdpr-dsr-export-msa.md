---
title: Microsoft Hesapları (MSA) için Microsoft Flow GDPR Veri Sahibi Dışarı Aktarma İstekleri | Microsoft Docs
description: Microsoft Flow’u kullanarak Microsoft Hesapları için GDPR Veri Sahibi Dışarı Aktarma İsteklerini yanıtlamayı öğrenin.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
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
ms.openlocfilehash: 6f181a66453573c2f636cbe5130b7fc003a3b151
ms.sourcegitcommit: 5b27ac91b56078e91f45f993f1967731d14af92b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2019
ms.locfileid: "65035025"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Microsoft Flow için GDPR Veri Sahibi Dışarı Aktarma İstekleri’ni yanıtlama

Genel Veri Koruma Yönetmeliği (GDPR) yolculuğunuzda sizinle iş ortaklığına girme bağlılığımız kapsamında, hazırlanmanıza yardımcı olması için belgeler geliştirdik. Bu belgeler, yalnızca GDPR’ye hazırlanmak için neler yaptığımızı açıklamakla kalmıyor, aynı zamanda Microsoft Flow kullanırken GDPR uyumluluğunu desteklemek için Microsoft ile bir an önce atabileceğiniz adımların örneklerini paylaşıyor.

## <a name="manage-export-requests"></a>Dışarı aktarma isteklerini yönetme

*Veri taşınabilirliği hakkı*, veri sahiplerine kişisel verilerinin elektronik biçimde (yani “yapılandırılmış, yaygın olarak kullanılan, makine tarafından okunabilir ve birlikte çalışabilen bir biçim”) bir kopyasını isteme olanağı sağlar. Bu kopya da başka bir veri sorumlusuna aktarılabilir.

Belirli bir kullanıcıya yönelik kişisel verileri bulmak veya dışarı aktarmak için [Microsoft gizlilik panosu](https://account.microsoft.com/privacy/)’nu veya [Microsoft Flow](https://flow.microsoft.com/)’u kullanın.

|Kişisel veriler|Konum|
|-----------------|-------------------|
|Ürün ve hizmet etkinliği|Microsoft gizlilik panosu|
|Akışlar|Microsoft Flow oluşturucu portalı|
|Çalıştırma geçmişi|Microsoft Flow oluşturucu portalı|
|Etkinlik Akışı|Microsoft Flow oluşturucu portalı|
|Bağlantılar|Microsoft Flow oluşturucu portalı|

## <a name="export-product-and-service-activity"></a>Ürün ve hizmet etkinliğini dışarı aktarma

1. Microsoft Hesabınızı (MSA) kullanarak [Microsoft gizlilik panosunda](https://account.microsoft.com/privacy/) oturum açın.
1. **Etkinlik geçmişi**’ni seçin.

    ![Etkinlik Geçmişi](./media/gdpr-dsr-export-msa/activityhistory.png) Kullandığınız farklı Microsoft uygulamaları ve hizmetleri için etkinlik geçmişinize göz atabilirsiniz.
1. **Ürün ve Hizmet Etkinliği** verilerini dışarı aktarmak için sırayla **Verilerinizi indirin** ve **YENİ ARŞİV OLUŞTUR** seçeneğini belirleyin.

    ![Verilerinizi indirin](./media/gdpr-dsr-export-msa/downloaddata.png)

1. **Uygulama ve hizmet kullanımı**’nı ve sonra **Arşiv oluştur**’u seçin.

    ![Verilerinizi indirin](./media/gdpr-dsr-export-msa/create-archive.png)
1. Yeni bir arşiv oluşturulur. **İndir**’i seçerek dışa aktardığınız ürün ve hizmet etkinliği verilerini alın.

    ![İndir](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Akışı dışarı aktarma

Bir akışa erişim izni olan bir son kullanıcı aşağıdaki adımları izleyerek akışı dışarı aktarabilir:

1. [Microsoft Flow](https://flow.microsoft.com/)'da oturum açın.

1. **Akışlarım**’ı ve ardından dışarı aktarılacak akışı seçin.

1. **... Diğer** ve ardından **Dışarı aktar** seçeneklerini belirleyin.

    ![Akışı dışarı aktarma](./media/gdpr-dsr-export/export-flow.png)

1. **Paket (.zip)** seçeneğini belirleyin.

Akışınız artık sıkıştırılmış bir paket olarak kullanılabilir. Daha fazla bilgi için [akışı dışarı ve içeri aktarma](https://flow.microsoft.com/blog/import-export-bap-packages/) ile ilgili blog gönderisine bakın.

## <a name="export-run-history"></a>Çalıştırma geçmişini dışarı aktarma

Çalıştırma geçmişi, bir akış için tüm çalıştırmaların listesini içerir. Bu veriler, tetikleyiciler ve eylemler için akışın durumunu, başlangıç saatini, süresini ve giriş/çıkış verilerini içerir.

Akışa erişim izni olan bir son kullanıcı aşağıdaki adımları izleyerek bu verileri dışarı aktarabilir:

1. [Microsoft Flow](https://flow.microsoft.com/)'da oturum açın.
1. **Akışlarım** bağlantısını ve ardından çalıştırma geçmişini dışarı aktarmak istediğiniz akışı seçin.
1. **ÇALIŞTIRMA GEÇMİŞİ** bölmesinde **Tümünü görüntüle**’yi seçin.

    ![Çalıştırma geçmişi](./media/gdpr-dsr-export/run-history.png)

1. **CSV'yi İndir**’i seçin.

    ![CSV'yi İndir](./media/gdpr-dsr-export/download-csv.png)

Çalıştırma geçmişi, Microsoft Excel’de veya bir metin düzenleyicide açabilmeniz ve sonuçları daha fazla analiz edebilmeniz için bir .csv dosyası olarak indirilir.

## <a name="export-a-users-activity-feed"></a>Bir kullanıcının etkinlik akışını dışarı aktarma

[Microsoft Flow](https://flow.microsoft.com/)’da, etkinlik akışı bir kullanıcının etkinlik, hata ve bildirim geçmişini gösterir. Kullanıcılar etkinlik akışlarını şu adımları izleyerek görüntüleyebilir:

1. [Microsoft Flow](http://flow.microsoft.com/)’da oturum açın, sağ üst köşenin yakınında bulunan zil simgesini ve ardından **Tüm etkinliği göster**’i seçin.

    ![Etkinlik akışını göster](./media/gdpr-dsr-export/show-activity-feed.png)

1. **Etkinlik** ekranında, sonuçları kopyalayın ve Microsoft Word gibi bir metin düzenleyicisine yapıştırın.

    ![Etkinlik akışını göster](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Bir kullanıcının bağlantılarını dışarı aktarma

Bağlantılar, akışların API’lere, SaaS uygulamalarına ve üçüncü taraf sistemlerine bağlanmasına olanak sağlar. Bağlantılarınızı görüntülemek için şu adımları izleyin:

1. [Microsoft Flow](http://flow.microsoft.com/)’da oturum açın, sağ üst köşenin yakınında bulunan dişli simgesini ve ardından **Bağlantılar**’ı seçin.

    ![Bağlantılar sekmesini göster](./media/gdpr-dsr-export/show-connections.png)
1. Sonuçları kopyalayın ve Microsoft Word gibi bir metin düzenleyicisine yapıştırın.
