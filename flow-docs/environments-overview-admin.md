---
title: "Yöneticiler için ortamlara genel bakış | Microsoft Docs"
description: "Microsoft Flow’da ortamları kullanma, oluşturma ve yönetme"
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: f1c50e5d16d5b9fbbd3e6db3128947b0554e9a85
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="using-environments-within-microsoft-flow"></a>Microsoft Flow’daki ortamları kullanma
## <a name="benefits"></a>Avantajları
Microsoft Flow’un yeni bir özelliği olan ortamlar şu avantajları sunar: 

* **Yerel veri konumu**: Ortamlar, farklı bölgelerde oluşturulabilir ve oluşturuldukları coğrafi konuma bağlı olur. Bir ortamda akış oluşturduğunuzda, bu akış o coğrafi konumdaki tüm veri merkezlerine yönlendirilir. Bu sayede performans artar. 
  
    Kullanıcılarınız Avrupa’daysa ortamı Avrupa bölgesinde oluşturup kullanın. Kullanıcılarınız Amerika Birleşik Devletleri’ndeyse ortamı ABD’de oluşturup kullanın. 
  
    Ortamı silerseniz ortamdaki tüm akışlar da silinir. Bu durum, o ortamda oluşturduğunuz tüm bağlantılar, ağ geçitleri, PowerApps uygulamaları ve diğer öğeler için geçerlidir.
* **Veri kaybını önleme**: Bir yönetici olarak, akışların dahili bir konumdan (*OneDrive İş* gibi) veri almasını ve ardından bu verileri herkese açık bir şekilde (örneğin *Twitter* da) yayımlamasını istemezsiniz. Veri kaybını önleme özelliğini kullanarak yalnızca iş verileri ilkesiyle kullanılabilecek hizmetleri denetleyebilirsiniz. 
  
    Örneğin, *SharePoint* ve *OneDrive İş* hizmetlerini yalnızca iş verileri ilkesine ekleyebilirsiniz. Bu ortamda oluşturulan tüm akışlar, bu *SharePoint* ve *OneDrive İş* hizmetlerini kullanabilir. Yalnızca eklediğiniz hizmetler kullanılabilir. 
  
  > [!NOTE]
  > Veri kaybını önleme, P2 lisansını da içeren bazı lisans SKU’larıyla kullanılabilir. 
  > 
  > 
* **Tüm kaynaklar için yalıtım sınırı**: Tüm akışlar, ağ geçitleri, bağlantılar, özel bağlayıcılar, vb. bu ortamda yer alır. Diğer ortamlarda bulunmazlar. 
* **Common Data Service**: Bir yere veri ekleyen bir akış oluşturmak istiyorsunuz. Seçenekleriniz şunlardır:
  
  * Bir Excel dosyasına veri ekleme ve Excel dosyasını OneDrive gibi bir bulut depolama hesabında depolama.
  * Kendi SQL Veritabanınızı oluşturma ve verilerinizi burada depolama.
  * Verilerinizi depolamak için Common Data Service’ı kullanma.
    
    Her ortamda, Common Data Service’taki akışlarınız için sıfır veya bir veritabanı depolama alanı olabilir. Common Data Service’a erişim, satın aldığınız lisansa bağlıdır; Ücretsiz lisansa dahil değildir.

## <a name="limitations"></a>Sınırlamalar
Ortamlar, birçok avantaj sunmanın yanı sıra bazı sınırlamalar uygular. Ortamların yalıtım sınırında olması, hiçbir zaman *ortamlardaki* diğer kaynaklara başvuran kaynaklarınız olamayacağı anlamına gelir. Örneğin, bir ortamda özel bağlayıcı oluşturup farklı bir ortamda hem bu özel bağlayıcıyı hem de bir ağ geçidini kullanan bir akış oluşturmak mümkün değildir.

Bu nedenle, ortamların yalnızca gerektiğinde oluşturulması önemlidir. Çok fazla ortam oluşturmak, kuruluşunuzdaki kullanıcıların kaynakları paylaşmasını zorlaştıracaktır.

## <a name="use-the-default-environment"></a>Varsayılan ortamı kullanma
**Varsayılan** ortam tüm kullanıcıların erişimine açıktır ve tüm kullanıcılar tarafından paylaşılır. Bu ortamda, her kullanıcı akış oluşturabilir.

> [!TIP]
> Önizleme kullanıcıysanız mevcut tüm akışlar varsayılan ortamda yer alır. *Önizleme kullanıcısı*, Microsoft Flow’u Genel Kullanılabilirlik (GA) aşamasından önce kullanan kişidir. 
> 
> 

## <a name="use-the-administrator-center"></a>Yönetici merkezini kullanma
Yöneticiler ortamlar oluşturmak, kullanıcıları bu ortamlara eklemek ve benzer görevleri gerçekleştirmek için yönetici merkezini kullanır. Yönetici merkezini açmanın iki yolu vardır:

#### <a name="option-1-select-settings"></a>1. Seçenek: Ayarlar’ı seçin
1. [flow.microsoft.com](https://flow.microsoft.com) adresinde oturum açın.
2. Ayarlar dişlisini ve listeden **Yönetim Merkezi**’ni seçin:  
   ![Ayarlar ve Yönetici Portalı](./media/environments-overview-admin/settings.png)
3. Yönetici merkezi açılır.

#### <a name="option-2-open-adminflowmicrosoftcom"></a>2. Seçenek: admin.flow.microsoft.com’u açın
[admin.flow.microsoft.com](https://admin.flow.microsoft.com) adresine gidin ve iş hesabınızla oturum açın. Yönetici merkezi açılır.

## <a name="create-an-environment"></a>Ortam oluşturma
1. [Microsoft Flow yönetim merkezinde](https://admin.flow.microsoft.com) **Ortamlar**’ı seçin. Mevcut tüm ortamlar görüntülenir:  
   ![](./media/environments-overview-admin/environments-list.png)
2. **Yeni ortam**’ı seçin. Aşağıdaki bilgileri girin:
   
   | Özellik | Açıklama |
   | --- | --- |
   | Ortam Adı |Ortamınızın adını (`Human Resources` veya `Europe flows` gibi) girin. |
   | Bölge |Ortamınızın barındırılacağı konumu seçin. En iyi performans için kullanıcılarınıza en yakın bölgeyi kullanın. Örneğin, akışınızın kullanıcıları Londra’daysa Avrupa bölgesini seçin. Akışınızın kullanıcıları New York’taysa Amerika Birleşik Devletleri bölgesini seçin. |
3. **Ortam oluşturma**’yı seçin. Yeni ortamınız listelenir. 

Sonra, ortama kullanıcı ekleyin.

## <a name="manage-your-existing-environments"></a>Mevcut ortamlarınızı yönetme
1. [Microsoft Flow yönetim merkezinde](https://admin.flow.microsoft.com) **Ortamlar**’ı seçin:  
   ![](./media/environments-overview-admin/select-environments.png)  
2. Bir ortamı seçip özelliklerini açın. 
3. **Ayrıntılar** bölümünde ortamı oluşturan kişi, ortamın coğrafi konumu ve diğer özellikleri gibi ortamla ilgili ek bilgiler gösterilir.  
   ![](./media/environments-overview-admin/open-environment.png)
4. **Güvenlik**’i seçin. **Ortam rolleri** bölümünde iki seçenek vardır: **Yönetici** ve **Oluşturucu**:  
   
    ![](./media/environments-overview-admin/environment-roles.png)
   
    **Oluşturucular** bir ortamda akışlar, veri bağlantıları ve ağ geçitleri gibi yeni kaynaklar oluşturabilir. 
   
   > [!NOTE]
   > Bir kullanıcının ortamdaki kaynakları *düzenlemek* ve *net-new* kaynakları oluşturmak için **Oluşturucu** olmasına gerek yoktur. Her kaynak oluşturucu, kaynağı kimin düzenleyebileceğini belirleyebilir ve ortam oluşturucusu olmayan kullanıcılara düzenleme izinleri verebilir.
   > 
   > 
   
    Bir **Yönetici**, veri kaybını önleme ilkeleri oluşturabilir ve ortam oluşturma, kullanıcıları ortama ekleme ve yönetici/oluşturucu ayrıcalıkları atama gibi yönetim görevlerini tamamlayabilir.  
   
   1. **Ortam Oluşturucusu**rolünü ve ardından **Kullanıcılar**’ı seçin:  
      ![](./media/environments-overview-admin/add-environment-maker.png)
   2. Oluşturucu rolünü vermek istediğiniz bir ad, e-posta adresi veya kullanıcı grubu girin. Siz yazmaya başladığınızda IntelliSense girdiğiniz metinle eşleşen kullanıcıları/grupları listelemeye başlar. 
   3. Kullanıcı ekleme işlemini tamamlamak için **Kaydet**’i seçin. 
5. **Güvenlik** içinde **Kullanıcı Rolleri**’ni seçin:  
    ![](./media/environments-overview-admin/security-user-roles.png)
   
    Rolleri düzenleme veya silme seçenekleriyle birlikte mevcut tüm roller listelenir. 
   
    Yeni bir rol oluşturmak için **Yeni rol**’ü seçin. 
6. **Güvenlik** içinde **İzin Kümeleri**’ni seçin:  
    ![](./media/environments-overview-admin/security-permission-set.png)
   
    Rolleri düzenleme veya silme seçenekleriyle birlikte mevcut tüm izin kümeleri listelenir. 
   
    Yeni bir küme oluşturmak için **Yeni izin kümesi**’ni seçin. 
7. **Veritabanı** menüsünde verilerinizin depolanacağı bir veritabanı oluşturmayı seçebilirsiniz. Bu veritabanı, Common Data Service’in bir parçasıdır.

## <a name="commonly-asked-questions"></a>Sık sorulan sorular
##### <a name="can-i-migrate-a-microsoft-flow-in-my-us-environment-to-a-europe-environment"></a>ABD ortamımdaki bir Microsoft Flow’u Avrupa ortamına taşıyabilir miyim?
Hayır, akışlar bir ortamdan diğerine taşınamaz. Akışı diğer ortamda yeniden oluşturabilirsiniz.

##### <a name="which-license-includes-the-common-data-service"></a>Hangi lisanslar Common Data Service’ı içerir?
Yalnızca Microsoft PowerApps Plan 2, Common Data Service ile veritabanı oluşturma hakları içerir. Bununla birlikte, ücretli tüm planlar (Microsoft Flow plan 1 ve 2 ve Microsoft PowerApps plan 1 ve 2), Common Data Service’ı kullanma haklarına sahiptir.

[Flow fiyatları](https://flow.microsoft.com/pricing/), size uygun bir plan seçmenize yardımcı olabilir.  

[Faturalama soruları](billing-questions.md) da aldığımız bazı yaygın sorulara gitmenize yardımcı olur. 

##### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>Common Data Service bir ortamın dışında kullanılabilir mi?
Hayır. Common Data Service için bir ortam gerekir. Bu konuda [daha fazla bilgi alın](common-data-model-intro.md).

##### <a name="what-regions-include-microsoft-flow"></a>Hangi bölgeler Microsoft Flow içeriyor?
Microsoft Flow, Office 365’in desteklediği bölgelerin çoğunu desteler; daha fazla ayrıntı için [Bölgelere genel bakış](regions-overview.md) bölümünü inceleyin.

##### <a name="what-is-needed-to-create-my-own-custom-environment"></a>Kendi özel ortamımı oluşturmak için neye ihtiyacım var?
Microsoft Flow Plan 2 lisansına sahip tüm kullanıcılar, varsayılan ortama ek olarak kendi ortamlarını oluşturabilir. Office 365 ve Ücretsiz sürüm dahil tüm Microsoft Flow kullanıcıları, Plan 2 yöneticileri tarafından oluşturulan ortamları kullanabilir, ancak kendi ortamlarını oluşturamaz. 

