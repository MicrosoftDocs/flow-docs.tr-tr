---
title: Yöneticiler için ortama genel bakış | Microsoft Docs
description: Microsoft Flow ortamda ortamları kullanma, oluşturma ve yönetme
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: sunayv
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: eb3e1050d22b8f672f47214952428b86186ba145
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547974"
---
# <a name="using-environments-within-microsoft-flow"></a>Microsoft Flow içinde ortamları kullanma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

## <a name="benefits"></a>Larından

Ortamlar aşağıdaki avantajları sağlar:

* **Veri konumu**: ortamlar, farklı bölgelerde oluşturulabilir ve bu coğrafi konuma bağlanır. Bir ortamda akış oluşturduğunuzda, bu akış o coğrafi konumdaki tüm veri merkezlerine yönlendirilir. Bu ayrıca bir performans avantajı sağlar.

    Kullanıcılarınız Avrupa 'daysa ortamı Avrupa bölgesinde oluşturun ve kullanın. Kullanıcılarınız Birleşik Devletler, ortamı ABD 'de oluşturun ve kullanın 

    > [!IMPORTANT]
    > Ortamı silerseniz, bu ortamdaki tüm akışlar da silinir. Bu, bağlantılar, ağ geçitleri, PowerApps ve daha fazlası dahil, bu ortamda oluşturduğunuz tüm öğeler için geçerlidir.
* **Veri kaybını önleme**: bir yönetici olarak, bir dahili konumdan (örneğin, *OneDrive iş* veya maaş bilgileri içeren bir SharePoint listesi) veri alan akışlara gerek kalmaz ve ardından bu verileri herkese açık bir şekilde ( *Örneğin: Twitter*). Microsoft Flow dağıtımınızda hangi hizmetlerin veri paylaşabileceği denetlemek için veri kaybı önleme kullanın.

    Örneğin, *SharePoint* ve *OneDrive iş* hizmetlerini yalnızca iş verileri ilkesine ekleyebilirsiniz. Bu ortamda oluşturulan tüm akışlar, *SharePoint* ve *OneDrive iş* hizmetlerini kullanabilir. Ancak, bunlar yalnızca iş verileri ilkesine dahil olmayan diğer hizmetlerle veri paylaşamaz.

  > [!NOTE]
  > Veri kaybı önleme, P2 lisansı dahil bazı lisans SKU 'ları ile kullanılabilir.

* **Tüm kaynaklar Için yalıtım sınırı**: tüm akışlar, ağ geçitleri, bağlantılar, özel bağlayıcılar, vb. belirli bir ortamda yer alır. Diğer ortamlarda mevcut değildir.
* **Common Data Service**: bir hizmete veri ekleyen bir akış oluşturmak istiyorsanız seçenekleriniz şunlardır:

  * Excel dosyasına veri ekleyin ve Excel dosyasını OneDrive gibi bir bulut depolama hesabında depolayın.
  * Bir SQL veritabanı oluşturun ve ardından verilerinizi depolayın.
  * Verilerinizi depolamak için Common Data Service kullanın.

    Her ortamın, Common Data Service akışlarınız için en fazla bir veritabanı olabilir. Common Data Service erişim, satın aldığınız lisansa bağlıdır; Common Data Service ücretsiz lisansa dahil değildir.

## <a name="limitations"></a>Algılan

Ortamlar birçok avantaj sunmakla birlikte, yeni sınırlamalar da getirir. Ortamların bir yalıtım sınırı olması, ortamlar *genelinde* kaynaklara başvuran kaynaklarınız olmadığı anlamına gelir. Örneğin, bir ortamda özel bağlayıcı oluşturmayabilir ve ardından bu özel bağlayıcıyı farklı bir ortamda kullanan bir akış oluşturabilirsiniz.

## <a name="use-the-default-environment"></a>Varsayılan ortamı kullan

**Varsayılan** ortam tüm kullanıcılar tarafından paylaşılır ve herhangi bir Kullanıcı **varsayılan** ortamda akış oluşturabilir.

> [!TIP]
> Bir önizleme kullanıcısı kullanıyorsanız, mevcut tüm akışlar varsayılan ortamda bulunur. *Önizleme kullanıcısı* , genel kullanıma (GA) sürümünden önce Microsoft Flow kullanan bir kişidir.

## <a name="the-admin-center"></a>Yönetim Merkezi

Yöneticiler, ortamları oluşturmak ve yönetmek için yönetim merkezini kullanır. Yönetim merkezini açmak için iki yol aşağıda verilmiştir:

### <a name="option-1-select-settings"></a>Seçenek 1: ayarları seçin

1. [Flow.Microsoft.com](https://flow.microsoft.com)'de oturum açın.
1. Ayarlar dişli ' ı seçin ve listeden **Yönetim Merkezi** ' ni seçin:

   ![Ayarlar ve Yönetici portalı](./media/environments-overview-admin/settings.png)
1. Yönetici Merkezi açılır.

### <a name="option-2-open-adminflowmicrosoftcom"></a>Seçenek 2: açık admin.flow.microsoft.com

[Admin.Flow.Microsoft.com](https://admin.flow.microsoft.com)adresine gidin ve iş hesabınızla oturum açın.

## <a name="create-an-environment"></a>Ortam oluşturma

1. [Microsoft Flow Yönetim merkezinde](https://admin.flow.microsoft.com) **ortamlar**' ı seçin. Tüm mevcut ortamları görürsünüz: ![ortamlar](./media/environments-overview-admin/environments-list.png)
2. **Yeni ortam** ' ı seçin ve gerekli bilgileri sağlayın:


   |     Özelliði     |                                                 Açıklaması                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Ortam adı |              Ortamınız için `Human Resources`veya `Europe flows`gibi bir ad girin.              |
   |      Geli      | Ortamınızı barındıracak konumu seçin. En iyi performansı elde etmek için kullanıcılarınıza en yakın bölgeyi kullanın. |
   | Ortam türü |                  Lisansınızı temel alan bir ortam türü seçin: üretim veya deneme.                   |

     ![Ortam ayarları](./media/environments-overview-admin/new-environment-dialog.png)
3. **Ortam Oluştur**' a tıklayın.
4. Artık **veritabanı oluşturma** veya **atlama**seçeneğiniz vardır.
5. **Veritabanı oluşturmayı**seçerseniz, veritabanı Için bir **para birimi** ve **dil** girmeniz istenir. Ayrıca, örnek uygulamalar ve verilerin dağıtılmasını da seçebilirsiniz.

   ![veritabanı yapılandırma ayarları](./media/environments-overview-admin/create-database-dialog2.png)


Artık ortama kullanıcı ekleyebilirsiniz.

## <a name="manage-your-existing-environments"></a>Mevcut ortamlarınızı yönetin

1. [Microsoft Flow Yönetim merkezinde](https://admin.flow.microsoft.com) **ortamlar**' ı seçin:

   ![ortamlar menü öğesi](./media/environments-overview-admin/select-environments.png)
1. Özelliklerini açmak için bir ortam seçin.
1. Ortamı kimin oluşturduğunu, coğrafi konumunu ve daha fazlasını içeren bir ortamla ilgili ek bilgileri görüntülemek için **Ayrıntılar** sekmesini kullanın:

   ![Ayrıntılar sekmesi](./media/environments-overview-admin/open-environment.png)
1. **Güvenlik**' i seçin.

    Önceki adımlarda **veritabanı oluştur** ' u seçmediyseniz, **ortam rolleri**' nde Iki seçenek vardır: **Ortam Yöneticisi** ve **ortam Oluşturucu**:

    ![Yönetici rolleri](./media/environments-overview-admin/environment-roles.png)

    Bir **Oluşturucu** , bir ortamda akışlar, veri bağlantıları ve ağ geçitleri gibi yeni kaynaklar oluşturabilir.

   > [!NOTE]
   > Bir kullanıcının bir ortamdaki kaynakları *düzenlemek* Için bir **Oluşturucu** olması gerekmez. Her Oluşturucu, ortam üreticileri olmayan kullanıcılara izinler vererek kaynaklarını düzenleyebileceğini belirler.
   > 
   > 

    **Yönetici** , veri kaybı önleme ilkeleri oluşturabilir ve ortam oluşturma, ortamlara Kullanıcı ekleme ve yönetici/Oluşturucu ayrıcalıkları atama gibi diğer yönetim görevlerini gerçekleştirebilir.

   1. **Ortam Oluşturucu** rolünü ve ardından **Kullanıcılar**: ![Oluşturucu rolü ' nü seçin](./media/environments-overview-admin/add-environment-maker.png)
   1. **Oluşturucu** rolüne vermek istediğiniz bir ad, e-posta adresi veya Kullanıcı grubu girin.
   1. **Kaydet**' i seçin.

1. **Güvenlik**Içinde **Kullanıcı rolleri**' ni seçin:

    ![Kullanıcı rolleri](./media/environments-overview-admin/security-user-roles.png)

    Rol düzenleme veya silme seçenekleri de dahil olmak üzere, mevcut tüm roller listelenir.

    Yeni rol oluşturmak için **Yeni rol** ' i seçin.
1. **Güvenlik**Içinde **izin kümeleri**' ni seçin:

    ![izin ayarı](./media/environments-overview-admin/security-permission-set.png)

    Tüm mevcut izin kümelerini ve rolleri düzenleme veya silme seçeneklerini görürsünüz.

    Yeni izin kümesi oluşturmak için **yeni izin kümesi** ' ni seçin.
1. Verilerinizi depolamak için **veritabanı oluşturmayı**seçerseniz, bu veritabanı Common Data Service bir parçasıdır. **Güvenlik** sekmesine tıkladığınızda, rol tabanlı güvenliğin uygulanabileceğini **Dynamics 365 örnek yönetim merkezine** gitmeniz istenir.
![Dynamics güvenlik ayarları](./media/environments-overview-admin/Security-Link-D365.png)

1. Ortamdaki/örnekteki Kullanıcı listesinden kullanıcıyı seçin.
  ![Dynamics güvenlik ayarları](./media/environments-overview-admin/D365-Select-User.png)

1. Rolü kullanıcıya atayın.

   ![rolü kullanıcıya ata](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> Bu ortam rollerine atanan kullanıcılar veya gruplar, ortamın veritabanına (varsa) otomatik olarak erişim izni verilmez ve bir veritabanı sahibi tarafından ayrı ayrı erişim verilmelidir. 
>
>

### <a name="database-security"></a>Veritabanı güvenliği
Bir veritabanı şeması oluşturup değiştirebilme ve ortamınızda sağlanan bir veritabanında depolanan verilere bağlanma özelliği, veritabanının kullanıcı rolleri ve izin kümeleri tarafından denetlenir. Ortamınızın veritabanı için Kullanıcı rollerini ve izin kümelerini **güvenlik** sekmesinin **Kullanıcı rolleri** ve **izin kümeleri** bölümünden yönetebilirsiniz. 

   ![rolü kullanıcıya ata](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="can-i-move-a-flow-between-environments"></a>Ortamlar arasında bir akışı taşıyabilir miyim?

Evet, akışlar bir ortamdan dışarıya aktarılabilir ve başka bir ortama aktarılabilir.

### <a name="which-license-includes-the-common-data-service"></a>Common Data Service hangi lisansı içerir?

Yalnızca Microsoft PowerApps plan 2, Common Data Service veritabanı oluşturma haklarını içerir. Ancak, tüm ücretli planlar (Microsoft Flow planlar 1 ve 2 ve Microsoft PowerApps planlar 1 ve 2) Common Data Service kullanma haklarına sahiptir.

[Microsoft Flow fiyatlandırma](https://flow.microsoft.com/pricing/) sayfasını ziyaret ederek size doğru bir plan seçin.

Faturalandırma hakkında sık sorulan soruların cevapları için [faturalandırma soruları](billing-questions.md) belgesine bakın.

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>Common Data Service bir ortamın dışında kullanılabilir mi?

Eşleşen. Common Data Service bir ortam gerektirir. Hakkında [daha fazla bilgi edinin](common-data-model-intro.md) .

### <a name="what-regions-include-microsoft-flow"></a>Hangi bölgeler Microsoft Flow içerir?

Microsoft Flow, Office 365 tarafından desteklenen bölgelerin çoğunu destekler, daha fazla ayrıntı için [bölgelere genel bakış](regions-overview.md) bölümüne bakın.

### <a name="whats-needed-to-create-my-own-custom-environment"></a>Kendi özel ortamımı oluşturmak için neler gerekir?

Microsoft Flow plan 2 lisansına sahip tüm kullanıcılar kendi ortamlarını oluşturabilir. Tüm Microsoft Flow kullanıcıları, plan 2 yöneticileri tarafından oluşturulan ortamları kullanabilir, ancak kendi ortamlarını oluşturamaz.
