---
title: Veri kaybı önleme (DLP) ilkelerine giriş. | Microsoft Docs
description: Microsoft Flow için veri kaybı önleme ilkelerine giriş.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 46f646fb81fcf7043ff612a240528fed72638048
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548540"
---
# <a name="data-loss-prevention-dlp-policies"></a>Veri kaybı önleme (DLP) ilkeleri
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bu belgede, veri kaybı önleme ilkeleri sunulmaktadır. Bu, kurumsal verilerinizin tanımladığınız bağlayıcıların bir listesiyle paylaşılmalarına yardımcı olur.

## <a name="whats-a-data-loss-prevention-policy"></a>Veri kaybı önleme ilkesi nedir?

Kuruluşun verileri, başarısı için kritik öneme sahiptir. Verilerin karar verme için hazır olması gerekir, ancak erişimi olmayan izleyiciler ile paylaşılmaması için korunması gerekir. Bu verileri korumak için Microsoft Flow, hangi tüketici bağlayıcılarının iş verilerine erişebileceğini ve bunları paylaşabileceğini tanımlayan ilkeler oluşturma ve zorunlu kılabilirsiniz. Verilerin nasıl paylaşılacağını tanımlayan bu ilkeler, veri kaybı önleme (DLP) ilkeleri olarak adlandırılır.

## <a name="why-create-a-dlp-policy"></a>Neden DLP İlkesi oluşturulsun?

Hangi tüketici bağlayıcılarının iş verilerinize erişebileceğini ve bunları paylaşabileceğini açıkça tanımlamak için DLP İlkesi oluşturursunuz. Örneğin, Microsoft Flow kullanan bir kuruluş, SharePoint 'teki iş verilerinin Twitter akışında otomatik olarak yayımlanmasını istemiyor olabilir. Bunu engellemek için SharePoint verilerinin, kaynak olarak kullanılabilir olmasını engelleyen bir DLP İlkesi oluşturursunuz.

## <a name="benefits-of-a-dlp-policy"></a>DLP ilkesinin avantajları

* Verilerin kuruluş genelinde tek bir şekilde yönetilmesini sağlar.
* Önemli iş verilerinin sosyal medya siteleri gibi bağlayıcılarda yanlışlıkla yayımlanmasını engeller.

## <a name="managing-dlp-policies"></a>DLP ilkelerini yönetme

### <a name="prerequisites-for-managing-dlp-policies"></a>DLP ilkelerini yönetmek için Önkoşullar

* Ortam Yöneticisi ya da Kiracı Yöneticisi izinleri.

    [Ortamlar makalesindeki](environments-overview-admin.md)izinler hakkında daha fazla bilgi edinebilirsiniz.
* Bir [Microsoft Flow P2 lisansı](billing-questions.md).

## <a name="create-a-dlp-policy"></a>DLP İlkesi oluşturma

### <a name="prerequisites-for-creating-dlp-policies"></a>DLP ilkeleri oluşturma önkoşulları

DLP İlkesi oluşturmak için en az bir ortam için izinleriniz olmalıdır.

Şirketinizin SharePoint sitesindeki verilerin Twitter 'da yayımlanmasını önleyen bir DLP İlkesi oluşturmak için şu adımları izleyin:

1. [Microsoft Flow Yönetim merkezinde](https://admin.flow.microsoft.com) (Yönetim Merkezi) oturum açın.

1. Veri Ilkeleri sekmesini seçin ve ardından **Yeni ilke** bağlantısını seçin:

    ![Oturum Aç](./media/prevent-data-loss/create-policy-1.png)
1. **Veri grupları** sekmesini seçin.

1. Sayfanın üst kısmındaki **veri Ilkesi adı** etiketinde DLP Ilkesinin adını *contoso Için güvenli veri erişimi* olarak girin:

    ![Oturum Aç](./media/prevent-data-loss/create-policy-2.png)

1. **Ortamlar** sekmesinde [ortamı](environments-overview-admin.md) seçin.

    > [!NOTE]
    > Ortam Yöneticisi olarak yalnızca tek bir ortam için uygulanan ilkeler oluşturabilirsiniz. Bir kiracı yöneticisi olarak, tüm ortamların birleşimine uygulanan ilkeler oluşturabilirsiniz:
    >
    >

    ![Ortam seçin](./media/prevent-data-loss/create-policy-3.png)

1. **Veri grupları** sekmesini seçin:

    ![veri grupları seçin](./media/prevent-data-loss/create-policy-4.png)

1. **Yalnızca iş verileri** Grup kutusunun içinde yer alan **Ekle** bağlantısını seçin:

    ![Ekle 'yi seçin](./media/prevent-data-loss/create-policy-5.png)

1. **Bağlayıcı Ekle** sayfasından **SharePoint** ve **Salesforce** bağlayıcılarını seçin:

   ![bağlayıcıları seçin](./media/prevent-data-loss/create-policy-6.png)

1. İş verilerini paylaşabilen bağlayıcıları eklemek için **Bağlayıcılar Ekle** düğmesini seçin.

1. Ekranın sağ üst köşesindeki **Ilkeyi kaydet** ' i seçin.

1. Birkaç dakika sonra, veri kaybı önleme ilkeleri listesinde yeni DLP ilkeniz görüntülenir:

    ![DLP listesi](./media/prevent-data-loss/create-policy-9.png)

1. **Isteğe bağlı** Ekibinize bir e-posta veya başka bir iletişim gönderin, yeni bir DLP ilkesinin artık kullanılabilir olduğunu uyarır.

Tebrikler, uygulamanın SharePoint ile Salesforce arasında veri paylaşmasını sağlayan ve diğer hizmetlerle veri paylaşımını engelleyen bir DLP İlkesi oluşturdunuz.

> [!NOTE]
> Bir hizmeti bir veri grubuna eklemek, otomatik olarak diğer veri grubundan kaldırır. Örneğin, Twitter şu anda **yalnızca iş verileri** veri grubunda bulunuyorsa ve Iş verilerinin Twitter ile paylaşılmasına izin vermek Istemiyorsanız, Twitter hizmetini **iş verilerine izin verilmez** veri grubuna eklemeniz yeterlidir. Bu işlem Twitter 'ı yalnızca iş verileri veri grubundan kaldırır.
>
>

## <a name="data-sharing-violations"></a>Veri paylaşımı ihlalleri

Yukarıda özetlenen DLP ilkesini oluşturduğunuz varsayılarak, bir Kullanıcı Salesforce ( **yalnızca iş** verileri veri grubunda bulunur) ve Twitter ( **iş verilerine izin verilmez** veri grubunda bulunur) arasında veri paylaşan bir akış oluşturursa, Kullanıcı oluşturduğunuz veri kaybı önleme ilkesiyle çakışma nedeniyle akışın **askıya alındığını** bildirdi.

![akış oluştur](./media/prevent-data-loss/10.png)

Kullanıcılarınız, askıya alınmış akışlar hakkında sizinle iletişim kuradıysanız göz önünde bulundurmanız gereken birkaç nokta vardır:

1. Bu örnekte, iş verilerini SharePoint ile Twitter arasında paylaşmak için geçerli bir iş nedeni varsa, DLP ilkesini düzenleyebilirsiniz.

1. Kullanıcıdan, DLP ilkesiyle uyum sağlamak için akışı düzenlemesini isteyin.

1. Bu iki varlık arasında veri paylaşımıyla ilgili bir karar yapana kadar kullanıcıdan akışı askıya alınma durumunda bırakmasını isteyin.

## <a name="find-a-dlp-policy"></a>DLP İlkesi bulma

### <a name="admins"></a>Mins

Yöneticiler, belirli DLP ilkelerini bulmak için yönetim merkezindeki arama özelliğini kullanabilir.

> [!NOTE]
> Yöneticiler, tüm DLP ilkelerini yayımlayarak kuruluştaki kullanıcıların akış oluşturmadan önce ilkelerden haberdar olmasını sağlar.
>
>

### <a name="makers"></a>Cıları

Yönetici izinleriniz yoksa ve kuruluşunuzdaki DLP ilkeleri hakkında daha fazla bilgi edinmek istiyorsanız yöneticinize başvurun. Ayrıca, [Oluşturucu ortamları makalesinden](environments-overview-maker.md) daha fazla bilgi edinebilirsiniz

> [!NOTE]
> DLP ilkeleri yalnızca yöneticiler tarafından düzenlenebilir veya silinebilir.
>
>

## <a name="edit-a-dlp-policy"></a>DLP ilkesini düzenleme

1. [Yönetim merkezini](https://admin.flow.microsoft.com)başlatın.

1. Başlatan Yönetim merkezinde, sol taraftaki **veri ilkeleri** bağlantısını seçin.

    ![veri ilkelerini seçin](./media/prevent-data-loss/2.png)

1. Mevcut DLP ilkeleri listesinde arama yapın ve düzenlemek istediğiniz ilkenin yanındaki Düzenle düğmesini seçin.

1. İlkede gerekli değişiklikleri yapın. Örneğin, ortamı veya veri gruplarındaki Hizmetleri değiştirebilirsiniz.

1. Değişikliklerinizi kaydetmek için **Ilkeyi kaydet** ' i seçin.

> [!NOTE]
> Kiracı yöneticileri tarafından oluşturulan DLP ilkeleri, ortam yöneticileri tarafından görüntülenebilir, ancak ortam yöneticileri tarafından düzenlenemez.
>
>

## <a name="delete-a-dlp-policy"></a>DLP ilkesini silme

1. [Yönetim merkezini](https://admin.flow.microsoft.com)başlatın.

1. Sol taraftaki **veri ilkeleri** sekmesini seçin.

    ![Veri İlkeleri sekmesini seçin](./media/prevent-data-loss/2.png)

1. Mevcut DLP ilkeleri listesinde arama yapın ve silmek istediğiniz ilkenin yanındaki Sil düğmesini seçin:

    ![Sil düğmesini seçin](./media/prevent-data-loss/3-delete.png)

1. **Sil** düğmesini seçerek ilkeyi gerçekten silmek istediğinizi onaylayın:

    ![ilkeyi gerçekten silmek istediğinizi onaylayın](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>DLP İlkesi izinleri

DLP ilkeleri yalnızca kiracı ve ortam yöneticileri tarafından oluşturulabilir ve değiştirilebilir. [Ortamlar](environments-overview-admin.md) makalesindeki izinler hakkında daha fazla bilgi edinin.


## <a name="custom-and-http-connectors"></a>Özel ve HTTP bağlayıcıları

Özel ve HTTP bağlayıcıları, bir Microsoft Flow şablonu veya PowerShell kullanılarak DLCI 'Ler 'e eklenmelidir.

> [!TIP]
> Şema sürümü 2018-11-01 ' den düşürülemiyor. HTTP desteği bir ilkeden kaldırılamaz. HTTP desteğini kaldırmaya çalışırsanız, DLP İlkesi bozulmuş olabilir. Ayrıca, bir DLP İlkesi HTTP bağlayıcılarını destekleyecek şekilde güncelleştirilirse, bu HTTP özelliklerini kullanan geçerli akışlar kapatılabilir.

Bir ilkeye ekleyebileceğiniz HTTP bağlayıcıları aşağıda verilmiştir:

- HTTP (ve HTTP + Swagger)
- HTTP Web kancası
- HTTP Isteği

## <a name="add-connectors-custom-and-http-connectors-with-templates"></a>Özel Bağlayıcılar ve şablonlar ile HTTP bağlayıcıları ekleme

Bir [şablonu](https://flow.microsoft.com/galleries/public/templates/ae9683086770420e902c043e5ed4b363/)kullanarak bir ilkeye özel bağlayıcı eklemek için, ilke adını, bağlayıcının ekleneceği grubu ve bağlayıcının adı, kimliği ve türünü girin. Özel bağlayıcıyı verilen ilkeye ve gruba eklemek için akışı bir kez çalıştırın.

HTTP bağlayıcılarını [şablon](https://flow.microsoft.com/galleries/public/templates/834eb1366aa54335a5f979014a9e0477/)aracılığıyla mevcut bir ilkeye eklemek için, eklemek istediğiniz ilkenin adını girin ve ardından akışı çalıştırın.

## <a name="add-custom-and-http-connectors-with-powershell"></a>PowerShell ile özel ve HTTP bağlayıcıları ekleme

PowerShell kullanarak bir ilkeye özel bağlayıcılar ve/veya HTTP bağlayıcıları desteği eklemek için, en son PowerApps PowerShell betiklerini [indirip](https://docs.microsoft.com/powerapps/administrator/powerapps-powershell) içeri aktarın ve ardından Şu cmdlet 'leri kullanın: ' New-AdminDlpPolicy ', ' set-AdminDlpPolicy ', ' İlkeyi değiştirmek için Add-CustomConnectorToPolicy ' ve ' Remove-CustomConnectorFromPolicy '. ' Get-Help-Detailed ' cmdlet 'ini başvuru olarak kullanın.


> [!IMPORTANT]
> HTTP bağlayıcıları içerecek bir DLP İlkesi oluştururken veya güncelleştirirken şema sürüm 2018-11-01 ' yı kullanın. Şablonu veya PowerShell 'i kullanarak HTTP desteği eklemek, yalnızca belirtilen ilkeyi etkiler. Yönetim Merkezi ile oluşturulan yeni ilkeler HTTP bağlayıcılarını içermez.



## <a name="next-steps"></a>Sonraki adımlar

* [Ortamlar hakkında daha fazla bilgi edinin](environments-overview-admin.md)
* [Microsoft Flow hakkında daha fazla bilgi edinin](getting-started.md)
* [Yönetim Merkezi hakkında daha fazla bilgi edinin](admin-center-introduction.md)
* [Veri tümleştirme hakkında daha fazla bilgi edinin](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)
