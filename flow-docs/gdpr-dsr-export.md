---
title: Microsoft Flow GDPR veri konusu dışarı aktarma Istekleri | Microsoft Docs
description: G, veri konu verme Isteklerine yanıt vermek için Microsoft Flow nasıl kullanacağınızı öğrenin.
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
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 15eff70b8996e5ea130142a1c01699906e199642
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548190"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Microsoft Flow için GDPR veri sahibine dışarı aktarma Isteklerine yanıt verme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Genel Veri Koruma Yönetmeliği (GDPR) ile ilgili yolculukta sizinle iş ortağı taahhüdünün bir parçası olarak, hazırlanmanıza yardımcı olacak belgeler geliştirdik. Belgeler, yalnızca GDPR için hazırlanmak için yaptığımız şeyleri değil, ayrıca Microsoft Flow kullanırken GDPR uyumluluğunu desteklemek için Microsoft ile bu adımları da paylaşacağınızı açıklamaktadır.

## <a name="manage-export-requests"></a>Dışarı aktarma isteklerini yönetme

*Veri taşınabilirliği hakkı* , bir veri konusunun kişisel verilerinin bir kopyasını başka bir veri denetleyicisine aktarılabilecek elektronik bir biçimde ("yapılandırılmış, yaygın olarak kullanılan, makine tarafından okunabilen ve birlikte çalışabilen bir biçimde") istemesine olanak tanır.

Microsoft Flow, belirli bir kullanıcıya ait kişisel verileri bulmak veya dışarı aktarmak için aşağıdaki deneyimleri sunar:

* **Web sitesi erişimi:** [PowerApps yönetim merkezinde](https://admin.powerapps.com/)veya [Microsoft Flow Yönetim merkezinde](https://admin.flow.microsoft.com/)oturum açın.

* **PowerShell erişimi:**  [PowerApps Yöneticisi PowerShell cdmizin](https://go.microsoft.com/fwlink/?linkid=871804).

|**Müşteri verileri**|**Web sitesi erişimi**|**PowerShell erişimi**|
|-----------------|------------------|-------------------|
|Sistem tarafından oluşturulan Günlükler|[Office 365 hizmet güveni portalı](https://servicetrust.microsoft.com/)|
|çalıştırma geçmişi|Microsoft Flow Oluşturucu portalı||
|Var|Microsoft Flow Oluşturucu portalı||
|Akış izinleri| Microsoft Flow Oluşturucu portalı ve Microsoft Flow Yönetim Merkezi||
|Kullanıcı ayrıntıları||PowerApps cmdlet 'leri|
|Bağlantının|Microsoft Flow Oluşturucu portalı|PowerApps cmdlet 'leri |
|Bağlantı izinleri|Microsoft Flow Oluşturucu portalı|PowerApps cmdlet 'leri |
|Özel Bağlayıcılar|Microsoft Flow Oluşturucu portalı|PowerApps cmdlet 'leri |
|Özel bağlayıcı izinleri|Microsoft Flow Oluşturucu portalı|PowerApps cmdlet 'leri |
|Geçidinde|Microsoft Flow Oluşturucu portalı|Şirket içi veri ağ geçidi PowerShell cmdlet 'leri|
|Ağ Geçidi izinleri|Microsoft Flow Oluşturucu portalı|Şirket içi veri ağ geçidi PowerShell cmdlet 'leri|

## <a name="export-a-flow"></a>Akışı dışarı aktarma

Akışa kendilerine erişim izni veren bir son kullanıcı ya da yönetici, şu adımları izleyerek akışı dışarı aktarabilir:

1. [Microsoft Flow](https://flow.microsoft.com/)oturum açın.

1. **Akışlarım** bağlantısını seçin ve ardından dışarı aktarılacak akışı seçin.

1. Seç **... Daha fazla**ve ardından **dışarı aktar**' ı seçin.

    ![Akışı dışarı aktar](./media/gdpr-dsr-export/export-flow.png)

1. **Paket (. zip)** öğesini seçin.

Akışınız artık daraltılmış bir paket olarak kullanılabilir olacaktır. Daha fazla bilgi için bkz. [bir akışı dışarı ve içeri aktarma](https://flow.microsoft.com/blog/import-export-bap-packages/)hakkında blog gönderisi.

## <a name="export-run-history"></a>Çalıştırma geçmişini dışarı aktar

Çalıştırma geçmişi, bir akışta oluşan tüm yürütmelerin bir listesini içerir. Bu veriler, Tetikleyiciler ve eylemler için akışın durum, başlangıç saati, süre ve giriş/çıkış verilerini içerir.

Microsoft Flow Yönetim Merkezi aracılığıyla akışa erişim izni verilen bir son kullanıcı veya yönetici, bu verileri dışarı aktarmak için şu adımları izleyebilir:

1. [Microsoft Flow](https://flow.microsoft.com/)oturum açın.
1. **Akışlarım** bağlantısını seçin ve ardından çalıştırma geçmişini dışarı aktarmak istediğiniz akışı seçin.
1. **Çalıştırma geçmişi** bölmesinde **Tümünü gör**' ü seçin.

    ![çalıştırma geçmişi](./media/gdpr-dsr-export/run-history.png)

1. **CSV 'Yi indir**' i seçin.

    ![CSV 'yi indir](./media/gdpr-dsr-export/download-csv.png)

Çalışma geçmişi bir. csv dosyası olarak indirilir, böylece dosyayı Microsoft Excel 'de veya bir metin düzenleyicisinde açabilir ve sonuçları daha fazla analiz edebilirsiniz.

## <a name="export-a-users-activity-feed"></a>Kullanıcının etkinlik akışını dışarı aktarma

[Microsoft Flow](https://flow.microsoft.com/), etkinlik akışı kullanıcının etkinlik, başarısızlık ve bildirimlerin geçmişini gösterir. Herhangi bir Kullanıcı, aşağıdaki adımları izleyerek etkinlik akışını görüntüleyebilir:

1. [Microsoft Flow](https://flow.microsoft.com/)oturum açın, sağ üst köşenin yakınındaki zil simgesini seçin ve ardından **Tüm etkinliği göster**' i seçin.

    ![Etkinlik akışını göster](./media/gdpr-dsr-export/show-activity-feed.png)

1. **Etkinlik** ekranında sonuçları kopyalayın ve Microsoft Word gibi bir belge düzenleyicisine yapıştırın.

    ![Etkinlik akışını göster](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Kullanıcının bağlantılarını dışarı aktarma

Bağlantılar, akışların API 'lere, SaaS uygulamalarına ve diğer üçüncü taraf sistemlere bağlanmasına imkan tanır. Bağlantılarınızı görüntülemek için şu adımları izleyin:

1. [Microsoft Flow](https://flow.microsoft.com/)oturum açın, sağ üst köşenin yakınındaki dişli simgesini seçin ve ardından **Bağlantılar**' ı seçin.

    ![Bağlantıları göster](./media/gdpr-dsr-export/show-connections.png)
1. Sonuçları kopyalayın ve Microsoft Word gibi bir belge düzenleyicisine yapıştırın.

PowerApps Yöneticisi PowerShell cmdlet 'leri

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Kullanıcının bağlantı izinlerinin listesini dışarı aktarma

Kullanıcı, erişimi olan tüm bağlantılar için bağlantı rolü atamalarını [PowerApps PowerShell cdmler](https://go.microsoft.com/fwlink/?linkid=871804)içindeki Get-connectionroleatama işlevi aracılığıyla dışarı aktarabilir.

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
PowerApps Yöneticisi PowerShell cmdlet 'leri

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Kullanıcının özel bağlayıcılarını dışa aktarma

Özel Bağlayıcılar kullanıma hazır bağlayıcılar ve diğer API 'Ler, SaaS ve özel geliştirilmiş sistemler ile bağlantı kurulmasına olanak tanır. Özel bir bağlayıcının sahipliğini aktarabilir veya silebilirsiniz.

Müşteri bağlayıcıları listesini dışarı aktarmak için şu adımları izleyin:

1. [Microsoft Flow](https://flow.microsoft.com)gidin.
1. Ayarlar **dişli** simgesini seçin.
1. **Özel bağlayıcılar**' ı seçin.
1. Özel bağlayıcıların listesini kopyalayıp Microsoft Word gibi bir metin düzenleyicisine yapıştırın.

    ![Özel bağlayıcıları dışarı aktarma](./media/gdpr-dsr-export/export-custom-connectors.png)

Microsoft Flow verilen deneyimin yanı sıra, tüm özel bağlayıcıları dışarı aktarmak için [PowerApps PowerShell cmdlet 'leri](https://go.microsoft.com/fwlink/?linkid=871804) içindeki Get-Connector işlevini de kullanabilirsiniz.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

PowerApps Yöneticisi PowerShell cmdlet 'leri

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>Kullanıcının özel bağlayıcı izinlerini dışarı aktarma

Bir Kullanıcı [PowerApps PowerShell cdmizin](https://go.microsoft.com/fwlink/?linkid=871804)içindeki Get-Connectorroleatama işlevi aracılığıyla oluşturdukları tüm özel bağlayıcı izinlerini dışarı aktarabilir.

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

PowerApps Yöneticisi PowerShell cmdlet 'leri

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Onay geçmişini dışarı aktar

Microsoft Flow onay geçmişi, bir kullanıcı için alınan veya gönderilen onayların geçmiş kaydını yakalar. Herhangi bir Kullanıcı onay geçmişini şu şekilde görüntüleyebilir:

1. [Microsoft Flow](https://flow.microsoft.com/)oturum açma, **onaylar**seçme ve sonra **geçmişi**seçme.

    ![Onay geçmişini görüntüle](./media/gdpr-dsr-export/view-approval-history.png)

1. Bir liste, kullanıcının aldığı onayları gösterir. Kullanıcılar, gönderilen onayları, **alındı** seçeneğinin yanındaki aşağı oku seçerek ve ardından **gönderildi**' i seçerek gösterebilir.

    ![Alınan onayları görüntüle](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Kullanıcı ayrıntılarını dışarı aktar
Kullanıcı ayrıntıları, bir kullanıcı ile belirli bir kiracı arasında bağlantı sağlar. Yönetici, **Get-AdminFlowUserDetails** cmdlet 'ini çağırarak ve Kullanıcı IÇIN nesne kimliğini geçirerek bu bilgileri dışa aktarabilir.

PowerApps Yöneticisi PowerShell cmdlet 'leri

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Ağ Geçidi ayarlarını dışarı aktar
Şirket Içi veri ağ geçitleri için veri sahibine dışarı aktarma Isteklerine yanıt verme [burada](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration)bulunabilir.

