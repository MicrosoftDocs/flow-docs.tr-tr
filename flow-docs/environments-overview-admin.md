---
title: Yöneticiler için ortamlara genel bakış | Microsoft Docs
description: Microsoft Flow’da ortamları kullanma, oluşturma ve yönetme
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
ms.openlocfilehash: cf1a618b9e0ed76147eb4ede2aed42111c66b4a5
ms.sourcegitcommit: d00c10759d4afb54517a0b1032f8d0a509006d5b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="using-environments-within-microsoft-flow"></a>Microsoft Flow’daki ortamları kullanma

## <a name="benefits"></a>Avantajları

Ortamlar, aşağıdaki avantajları sunar:

* **Yerel veri konumu**: Ortamlar, farklı bölgelerde oluşturulabilir ve oluşturuldukları coğrafi konuma bağlı olur. Bir ortamda akış oluşturduğunuzda, bu akış o coğrafi konumdaki tüm veri merkezlerine yönlendirilir. Bu sayede performans artar.

    Kullanıcılarınız Avrupa’daysa ortamı Avrupa bölgesinde oluşturup kullanın. Kullanıcılarınız Amerika Birleşik Devletleri'ndeyse ortamı ABD’de oluşturun ve kullanın. 

    > [!IMPORTANT]
    > Ortamı silerseniz ortamdaki tüm akışlar da silinir. Bu durum, o ortamda oluşturduğunuz tüm bağlantılar, ağ geçitleri, PowerApps uygulamaları ve diğer öğeler için geçerlidir.
* **Veri kaybını önleme**: Bir yönetici olarak, akışların dahili bir konumdan (*OneDrive İş* veya maaş bilgilerini içeren bir SharePoint listesi gibi) veri almasını ve ardından bu verileri herkese açık bir şekilde (örneğin *Twitter*’da) yayımlamasını istemezsiniz. Microsoft Flow dağıtımınız içinde veri paylaşabilecek hizmetleri denetlemek için veri kaybı önlemeyi kullanın.

    Örneğin, *SharePoint* ve *OneDrive İş* hizmetlerini yalnızca iş verileri ilkesine ekleyebilirsiniz. Bu ortamda oluşturulan tüm akışlar, bu *SharePoint* ve *OneDrive İş* hizmetlerini kullanabilir. Ancak, yalnızca iş verileri ilkesine dahil olmayan diğer hizmetlerle veri paylaşamaz.

  > [!NOTE]
  > Veri kaybını önleme, P2 lisansını da içeren bazı lisans SKU’larıyla kullanılabilir.

* **Tüm kaynaklar için yalıtım sınırı**: Tüm akışlar, ağ geçitleri, bağlantılar, özel bağlayıcılar, vb. belirli bir ortamda yer alır. Diğer ortamlarda bulunmazlar.
* **Common Data Service**: Bir hizmete veri ekleyen akışlar oluşturma seçeneklerinizi burada bulabilirsiniz:

  * Bir Excel dosyasına veri ekleme ve Excel dosyasını OneDrive gibi bir bulut depolama hesabında depolama.
  * Bir SQL Veritabanı oluşturun ve verilerinizi burada depolayın.
  * Verilerinizi depolamak için Common Data Service’ı kullanma.

    Her ortamda, Common Data Service’taki akışlarınız en fazla bir veritabanı olabilir. Common Data Service’a erişim, satın aldığınız lisansa bağlıdır. Common Data Service, Ücretsiz lisansa dahil değildir.

## <a name="limitations"></a>Sınırlamalar

Ortamlar, birçok avantaj sunmanın yanı sıra bazı sınırlamalar uygular. Ortamların yalıtım sınırında olması, hiçbir zaman *ortamlardaki* kaynaklara başvuran kaynaklarınız olamayacağı anlamına gelir. Örneğin, bir ortamda özel bağlayıcı oluşturup farklı bir ortamda bu özel bağlayıcıyı kullanan bir akış oluşturmak mümkün değildir.

## <a name="use-the-default-environment"></a>Varsayılan ortamı kullanma

**Varsayılan** ortam tüm kullanıcılarla paylaşılır ve tüm kullanıcılar bu **Varsayılan** ortamda akış oluşturabilir.

> [!TIP]
> Önizleme kullanıcıysanız mevcut tüm akışlar varsayılan ortamda yer alır. *Önizleme kullanıcısı*, Microsoft Flow’u Genel Kullanılabilirlik (GA) aşamasından önce kullanan kişidir.

## <a name="the-admin-center"></a>Yönetim merkezi

Yöneticiler, ortamlar oluşturup yönetmek için yönetim merkezini kullanır. Yönetim merkezini açmanın iki yolu vardır:

### <a name="option-1-select-settings"></a>1. Seçenek: Ayarlar’ı seçin

1. [flow.microsoft.com](https://flow.microsoft.com) adresinde oturum açın.
1. Ayarlar dişlisini ve listeden **Yönetim Merkezi**’ni seçin:

   ![Ayarlar ve Yönetici Portalı](./media/environments-overview-admin/settings.png)
1. Yönetici merkezi açılır.

### <a name="option-2-open-adminflowmicrosoftcom"></a>2. Seçenek: admin.flow.microsoft.com’u açın

[admin.flow.microsoft.com](https://admin.flow.microsoft.com) adresine gidin ve iş hesabınızla oturum açın.

## <a name="create-an-environment"></a>Ortam oluşturma

1. [Microsoft Flow yönetim merkezinde](https://admin.flow.microsoft.com) **Ortamlar**’ı seçin. Tüm mevcut ortamları şurada görürsünüz: ![Ortamlar](./media/environments-overview-admin/environments-list.png)
2. **Yeni ortam**’ı seçip gerekli bilgileri sağlayın:


   |     Özellik     |                                                 Açıklama                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Ortam Adı |              Ortamınızın adını (`Human Resources` veya `Europe flows` gibi) girin.              |
   |      Bölge      | Ortamınızın barındırılacağı konumu seçin. En iyi performans için kullanıcılarınıza en yakın bölgeyi kullanın. |
   | Ortam Türü |                  Lisansınızı temel alarak bir ortam türü seçin: Üretim veya Deneme.                   |

     ![ortam ayarları](./media/environments-overview-admin/new-environment-dialog.png)
3. **Ortam oluştur** seçeneğine tıklayın.
4. Artık **Veritabanı oluşturma** veya **Atlama** seçeneklerine sahipsiniz.
5. **Veritabanı Oluştur** seçeneğini belirlerseniz Veritabanı için **Para Birimi** ve **Dil** seçeneği belirlemek üzere bildirim alırsınız. Ayrıca dağıtılan örnek uygulamaları ve verileri almayı da seçebilirsiniz.

   ![veritabanı yapılandırma ayarları](./media/environments-overview-admin/create-database-dialog2.png)


Artık ortama kullanıcılar ekleyebilirsiniz.

## <a name="manage-your-existing-environments"></a>Mevcut ortamlarınızı yönetme

1. [Microsoft Flow yönetim merkezinde](https://admin.flow.microsoft.com) **Ortamlar**’ı seçin:

   ![ortamlar menü öğesi](./media/environments-overview-admin/select-environments.png)
1. Bir ortamı seçip özelliklerini açın.
1. Ortamı oluşturan kişi, ortamın coğrafi konumu ve daha fazlası gibi ortam hakkındaki ek bilgileri görüntülemek için **Ayrıntılar** sekmesini kullanın:

   ![ayrıntılar sekmesi](./media/environments-overview-admin/open-environment.png)
1. **Güvenlik**’i seçin.

    Önceki adımlarda **Veritabanı Oluştur** seçeneğini belirlemediyseniz **Ortam rolleri**’nde iki seçenek bulunur: **Ortam Yöneticisi** ve **Ortam Oluşturucusu**:

    ![yönetici rolleri](./media/environments-overview-admin/environment-roles.png)

    **Oluşturucular** bir ortamda akışlar, veri bağlantıları ve ağ geçitleri gibi yeni kaynaklar oluşturabilir.

   > [!NOTE]
   > Ortamdaki kaynakları *düzenlemek* için kullanıcıların **Oluşturucu** olması gerekmez. Her Oluşturucu, Ortam Oluşturucusu olmayan kullanıcılara izinler vererek kaynaklarını düzenleyecek kişileri belirler.
   > 
   > 

    Bir **Yönetici**, veri kaybını önleme ilkeleri oluşturabilir ve ortam oluşturma, kullanıcıları ortama ekleme ve yönetici/oluşturucu ayrıcalıkları atama gibi yönetim görevlerini gerçekleştirebilir.

   1. **Ortam Oluşturucusu** rolünü ve ardından **Kullanıcılar**’ı seçin: ![oluşturucu rolü](./media/environments-overview-admin/add-environment-maker.png)
   1. **Oluşturucu** rolünü vermek istediğiniz bir ad, e-posta adresi veya kullanıcı grubu girin.
   1. **Kaydet**’i seçin.

1. **Güvenlik** içinde **Kullanıcı Rolleri**’ni seçin:

    ![kullanıcı rolleri](./media/environments-overview-admin/security-user-roles.png)

    Rolleri düzenleme veya silme seçenekleriyle birlikte mevcut tüm roller listelenir.

    Yeni bir rol oluşturmak için **Yeni rol**’ü seçin.
1. **Güvenlik** içinde **İzin Kümeleri**’ni seçin:

    ![izin kümeleri](./media/environments-overview-admin/security-permission-set.png)

    Rolleri düzenleyip silmeye yönelik tüm mevcut izin kümelerini ve seçeneklerini görebilirsiniz.

    Yeni bir izin kümesi oluşturmak için **Yeni izin kümesi**’ni seçin.
1. Verilerinizi depolamak için **Veritabanı Oluştur** seçeneğini belirlediyseniz bu veritabanı Common Data Service’in bir parçası olur. **Güvenlik** sekmesine tıkladığınızda, rol tabanlı güvenliğin uygulanabildiği **Dynamics 365 örneği yönetim merkezi**’ne gezinme bildirimi alırsınız.
![dynamics güvenlik ayarları](./media/environments-overview-admin/Security-Link-D365.png)

1. Ortam veya örnekteki kullanıcı listesinden kullanıcıyı seçin.
  ![dynamics güvenlik ayarları](./media/environments-overview-admin/D365-Select-User.png)

1. Kullanıcıya rol atayın.

   ![kullanıcıya rol atama](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> Bu ortam rollerine atanmış kullanıcılar veya gruplara, ortam veritabanına (varsa) erişme izni otomatik olarak verilmediğinden Veritabanı sahibi tarafından ayrı ayrı erişim sağlanmalıdır. 
>
>

### <a name="database-security"></a>Veritabanı güvenliği
Ortamınızda sağlanan veritabanı şeması oluşturup değiştirme ve veritabanında depolanan verilere bağlanma özelliği, veritabanı kullanıcı rolleri ve izin kümeleri tarafından denetlenir. Ortamınızın veritabanına yönelik kullanıcı rolleri ve izin kümelerini **Güvenlik** sekmesindeki **Kullanıcı rolleri** ve **İzin kümeleri** bölümünden yönetebilirsiniz. 

   ![kullanıcıya rol atama](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Sık sorulan sorular

### <a name="can-i-move-a-flow-between-environments"></a>Bir akışı ortamlar arasında taşıyabilir miyim?

Evet, akışlar bir ortamdan dışarı aktarılıp diğer ortama içeri aktarılabilir.

### <a name="which-license-includes-the-common-data-service"></a>Hangi lisanslar Common Data Service’ı içerir?

Yalnızca Microsoft PowerApps Plan 2, Common Data Service ile veritabanı oluşturma hakları içerir. Bununla birlikte, ücretli tüm planlar (Microsoft Flow plan 1 ve 2 ve Microsoft PowerApps plan 1 ve 2), Common Data Service’ı kullanma haklarına sahiptir.

[Microsoft Flow fiyatlandırma](https://flow.microsoft.com/pricing/) sayfasını ziyaret ederek size en uygun planı seçebilirsiniz.

Faturalandırma hakkında sık sorulan sorulara verilen yanıtları bulmak için [Faturalandırma soruları](billing-questions.md) belgesine göz atın.

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>Common Data Service bir ortamın dışında kullanılabilir mi?

Hayır. Common Data Service için bir ortam gerekir. Bu konuda [daha fazla bilgi alın](common-data-model-intro.md).

### <a name="what-regions-include-microsoft-flow"></a>Hangi bölgeler Microsoft Flow içeriyor?

Microsoft Flow, Office 365’in desteklediği bölgelerin çoğunu destekler; daha fazla ayrıntı için [Bölgelere genel bakış](regions-overview.md) bölümünü inceleyin.

### <a name="whats-needed-to-create-my-own-custom-environment"></a>Kendi özel ortamımı oluşturmak için neye ihtiyacım var?

Microsoft Flow Plan 2 lisansına sahip tüm kullanıcılar kendi ortamlarını oluşturabilir. Tüm Microsoft Flow kullanıcıları, Plan 2 yöneticileri tarafından oluşturulan ortamları kullanabilir, ancak kendi ortamlarını oluşturamaz.
