---
title: Microsoft Flow GDPR Veri Sahibi Dışarı Aktarma İstekleri | Microsoft Docs
description: Microsoft Flow’u kullanarak GDPR Veri Sahibi Dışarı Aktarma İstekleri’ni yanıtlamayı öğrenin.
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
ms.date: 4/24/2018
ms.author: keweare
ms.openlocfilehash: 5b813bbd8ba9b4e5a778d9fa424704b61ed6dd31
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34552077"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Microsoft Flow için GDPR Veri Sahibi Dışarı Aktarma İstekleri’ni yanıtlama

Genel Veri Koruma Yönetmeliği (GDPR) yolculuğunuzda sizinle iş ortaklığına girme bağlılığımız kapsamında, hazırlanmanıza yardımcı olması için belgeler geliştirdik. Bu belgeler, yalnızca GDPR’ye hazırlanmak için neler yaptığımızı açıklamakla kalmıyor, aynı zamanda Microsoft Flow kullanırken GDPR uyumluluğunu desteklemek için Microsoft ile bir an önce atabileceğiniz adımların örneklerini paylaşıyor.

## <a name="manage-export-requests"></a>Dışarı aktarma isteklerini yönetme

*Veri taşınabilirliği hakkı*, bir veri sahibine kişisel verilerinin elektronik biçimde (yani “yapılandırılmış, yaygın olarak kullanılan, makine tarafından okunabilir ve birlikte çalışabilen bir biçim”) bir kopyasını isteme olanağı sağlar. Bu kopya da başka bir veri sorumlusuna aktarılabilir.

Microsoft Flow, belirli bir kullanıcının kişisel verilerini bulmak veya dışarı aktarmak için aşağıdaki deneyimleri sunar:

* **Web sitesi erişimi:** [PowerApps Yönetim Merkezi](https://admin.powerapps.com/) veya [Microsoft Flow Yönetim Merkezi](https://admin.flow.microsoft.com/)’nde oturum açın.

* **PowerShell erişimi:** [PowerApps Yönetici PowerShell cdmlet’leri](https://go.microsoft.com/fwlink/?linkid=871804).

|**Müşteri verileri**|**Web sitesi erişimi**|**PowerShell erişimi**|
|-----------------|------------------|-------------------|
|Sistem tarafından oluşturulan günlükler|[Office 365 Hizmet Güveni Portalı](https://servicetrust.microsoft.com/)|
|Çalıştırma geçmişi|Microsoft Flow Oluşturucu Portalı||
|Akışlar|Microsoft Flow Oluşturucu Portalı||
|Akış izinleri| Microsoft Flow Oluşturucu Portalı ve Microsoft Flow Yönetim Merkezi||
|Kullanıcı ayrıntıları||PowerApps cmdlet'leri|
|Bağlantılar|Microsoft Flow Oluşturucu Portalı|PowerApps cmdlet'leri |
|Bağlantı izinleri|Microsoft Flow Oluşturucu Portalı|PowerApps cmdlet'leri |
|Özel bağlayıcılar|Microsoft Flow Oluşturucu Portalı|PowerApps cmdlet'leri |
|Özel bağlayıcı izinleri|Microsoft Flow Oluşturucu Portalı|PowerApps cmdlet'leri |
|Ağ geçidi|Microsoft Flow Oluşturucu Portalı|Şirket İçi Veri Ağ Geçidi PowerShell cmdlet’leri|
|Ağ geçidi izinleri|Microsoft Flow Oluşturucu Portalı|Şirket İçi Veri Ağ Geçidi PowerShell cmdlet’leri|

## <a name="export-a-flow"></a>Akışı dışarı aktarma

Kendisine akış erişimi izni veren bir son kullanıcı veya yönetici şu adımları izleyerek akışı dışarı aktarabilir:

1. [Microsoft Flow](https://flow.microsoft.com/)'da oturum açın.

1. **Akışlarım** bağlantısını ve ardından dışarı aktarılacak akışı seçin.

1. **... Diğer** ve ardından **Dışarı aktar** seçeneklerini belirleyin.

    ![Akışı dışarı aktarma](./media/gdpr-dsr-export/export-flow.png)

1. **Paket (.zip)** seçeneğini belirleyin.

Akışınız artık sıkıştırılmış bir paket olarak kullanılabilir. Daha fazla bilgi için [akışı dışarı ve içeri aktarma](https://flow.microsoft.com/blog/import-export-bap-packages/) ile ilgili blog gönderisine bakın.

## <a name="export-run-history"></a>Çalıştırma geçmişini dışarı aktarma

Çalıştırma geçmişi, bir akış için gerçekleştirilen tüm yürütmelerin bir listesini içerir. Bu veriler, tetikleyiciler ve eylemler için akışın durumunu, başlangıç saatini, süresini ve giriş/çıkış verilerini içerir.

Microsoft Flow Yönetim Merkezi üzerinden akışa erişim izni verilen bir son kullanıcı veya yönetici, bu verileri dışarı aktarmak için şu adımları izleyebilir:

1. [Microsoft Flow](https://flow.microsoft.com/)'da oturum açın.
1. **Akışlarım** bağlantısını ve ardından çalıştırma geçmişini dışarı aktarmak istediğiniz akışı seçin.
1. **ÇALIŞTIRMA GEÇMİŞİ** bölmesinde **Tümünü görüntüle**’yi seçin.

    ![Çalıştırma geçmişi](./media/gdpr-dsr-export/run-history.png)

1. **CSV'yi İndir**’i seçin.

    ![CSV'yi İndir](./media/gdpr-dsr-export/download-csv.png)

Çalıştırma geçmişi, Microsoft Excel’de veya bir metin düzenleyicide açabilmeniz ve sonuçları daha fazla analiz edebilmeniz için bir .csv dosyası olarak indirilir.

## <a name="export-a-users-activity-feed"></a>Bir kullanıcının etkinlik akışını dışarı aktarma

[Microsoft Flow](https://flow.microsoft.com/)’da, etkinlik akışı bir kullanıcının etkinlik, hata ve bildirim geçmişini gösterir. Her kullanıcı etkinlik akışlarını şu adımları izleyerek görüntüleyebilir:

1. [Microsoft Flow](http://flow.microsoft.com/)’da oturum açın, sağ üst köşenin yakınında bulunan zil simgesini ve ardından **Tüm etkinliği göster**’i seçin.

    ![Etkinlik akışını göster](./media/gdpr-dsr-export/show-activity-feed.png)

1. **Etkinlik** ekranında, sonuçları kopyalayın ve Microsoft Word gibi bir belge düzenleyicisine yapıştırın.

    ![Etkinlik akışını göster](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Bir kullanıcının bağlantılarını dışarı aktarma

Bağlantılar, akışların API’lere, SaaS uygulamalarına ve üçüncü taraf sistemlerine bağlanmasına olanak sağlar. Bağlantılarınızı görüntülemek için şu adımları izleyin:

1. [Microsoft Flow](http://flow.microsoft.com/)’da oturum açın, sağ üst köşenin yakınında bulunan dişli simgesini ve ardından **Bağlantılar**’ı seçin.

    ![Bağlantılar sekmesini göster](./media/gdpr-dsr-export/show-connections.png)
1. Sonuçları kopyalayın ve Microsoft Word gibi bir belge düzenleyicisine yapıştırın.

PowerApps Yönetici PowerShell cmdlet'leri

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Bir kullanıcının bağlantı izinlerinin listesini dışarı aktarma

Bir kullanıcı, erişimi olduğu tüm bağlantıların bağlantı rol atamalarını [PowerApps PowerShell cdmlet’lerindeki](https://go.microsoft.com/fwlink/?linkid=871804) Get-ConnectionRoleAssignment işlevi aracılığıyla dışarı aktarabilir.

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
PowerApps Yönetici PowerShell cmdlet'leri

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Bir kullanıcının özel bağlayıcılarını dışarı aktarma

Özel bağlayıcılar sistemde bulunmayan mevcut bağlayıcıları tamamlar ve diğer API’lere, SaaS’a ve özel olarak geliştirilmiş sistemlere bağlantı olanağı sağlar. Bir özel bağlayıcının sahipliğini aktarabilir veya silebilirsiniz.

Özel bağlayıcıların listesini dışarı aktarmak için şu adımları izleyin:

1. [Microsoft Flow](https://flow.microsoft.com)'a gidin.
1. Ayarlar **dişli** simgesini seçin.
1. **Özel Bağlayıcılar**’ı seçin.
1. Özel bağlayıcıların listesini kopyalayıp Microsoft Word gibi bir metin düzenleyicisine yapıştırın.

    ![Özel bağlayıcıları dışarı aktarma](./media/gdpr-dsr-export/export-custom-connectors.png)

Microsoft Flow’da sağlanan deneyime ek olarak, [PowerApps PowerShell cmdlet’lerindeki](https://go.microsoft.com/fwlink/?linkid=871804) Get-Connector işlevini kullanarak tüm özel bağlayıcıları dışarı aktarabilirsiniz.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

PowerApps Yönetici PowerShell cmdlet'leri

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>Bir kullanıcının özel bağlayıcı izinlerini dışarı aktarma

Bir kullanıcı oluşturduğu tüm özel bağlayıcı izinlerini [PowerApps PowerShell cdmlet’lerindeki](https://go.microsoft.com/fwlink/?linkid=871804) Get-ConnectorRoleAssignment işlevi aracılığıyla dışarı aktarabilir.

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

PowerApps Yönetici PowerShell cmdlet'leri

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Onay geçmişini dışarı aktarma

Microsoft Flow Onay Geçmişi bir kullanıcı için alınan veya gönderilen onayların geçmiş kaydını yakalar. Her kullanıcı onay geçmişini şu yolla görüntüleyebilir:

1. [Microsoft Flow](http://flow.microsoft.com/)’da oturum açma, **Onaylar**’ı ve ardından **Geçmiş**’i seçme.

    ![Onay geçmişini görüntüleme](./media/gdpr-dsr-export/view-approval-history.png)

1. Liste, kullanıcının aldığı onayları gösterir. Kullanıcılar gönderdikleri onayları, **Alınan** seçeneğinin yanındaki aşağı ok tuşunu ve ardından **Gönderilen**’i seçerek gösterebilir.

    ![Alınan onayları görüntüleme](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Kullanıcı Ayrıntılarını Dışarı Aktarma
Kullanıcı ayrıntıları, bir kullanıcı ile belirli bir kiracı arasında bağlantı sağlar. Yönetici, **Get-AdminFlowUserDetails** cmdlet’ini çağırıp kullanıcı için Nesne Kimliğini ileterek bu bilgileri dışarı aktarabilir.

PowerApps Yönetici PowerShell cmdlet'leri

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Ağ Geçidi Ayarlarını Dışarı Aktarma
Şirket İçi Veri Ağ Geçitleri için Veri Sahibi Dışarı Aktarma İsteklerine verilen yanıta [buradan](https://docs.microsoft.com/en-us/power-bi/service-gateway-onprem#tenant-level-administration) erişilebilir.

