---
title: Microsoft Flow GDPR Veri Sahibi Silme İstekleri | Microsoft Docs
description: Microsoft Flow’u kullanarak GDPR Veri Sahibi Silme İstekleri’ni yanıtlamayı öğrenin.
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
ms.date: 4/17/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 523e46269522d50eebe34fc559d69f4c146a2c3f
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58353091"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Microsoft Flow için GDPR Veri Sahibi Silme İstekleri’ni yanıtlama

Bir kuruluşun Müşteri Verilerinden kişisel verilerin kaldırılması işleminin yapıldığı “silme hakkı”, GDPR’de önemli bir korunma yöntemidir. Kaldırılan kişisel veriler, denetim günlüğü bilgileri dışında tüm kişisel verileri ve sistem tarafından oluşturulmuş günlükleri kapsar.

Microsoft Flow, kullanıcıların kuruluşunuzun günlük işlemleri için önem teşkil eden otomasyon iş akışlarını oluşturmasına olanak sağlar. Bir kullanıcı kuruluşunuzdan ayrıldığında, bir yöneticinin el ile inceleyip kullanıcının oluşturduğu belirli verileri ve kaynakları silip silmeyeceğine karar vermesi gerekir. Kullanıcının hesabı Azure Active Directory’den silindiğinde otomatik olarak silinen diğer kişisel veriler vardır.

Aşağıdaki tabloda, hangi kişisel verilerin otomatik olarak silindiği ve hangi verilerin bir yönetici tarafından el ile incelenip silinmesi gerektiği gösterilmektedir:

|El ile incelenip silinmesi gerekir|Kullanıcı Azure Active Directory'den silindiğinde otomatik olarak silinir|
|------|------|
|Ortam*|Sistem tarafından oluşturulan günlükler|
|Ortam izinleri**|Çalıştırma geçmişi|
|Akışlar|Etkinlik Akışı|
|Akış izinleri|Ağ geçidi |
|Kullanıcı ayrıntıları|Ağ geçidi izinleri|
|Bağlantılar*||
|Bağlantı izinleri||
|Özel bağlayıcı*||
|Özel bağlayıcı izinleri||

*Bu kaynakların her biri, kişisel verileri içeren “Oluşturan” ve “Değiştiren” kayıtlarını içerir. Güvenlik nedenleriyle, bu kayıtlar kaynak silinene kadar korunur.

**Common Data Service veritabanını içeren ortamlar için, ortam izinleri (örn. hangi kullanıcıların Ortam Oluşturucu ve Yönetici rollerine atandığı) Common Data Service veritabanında kayıt olarak depolanır. Common Data Service kullanan kullanıcılara yönelik DSR’lerin nasıl yanıtlanacağı hakkında rehberlik için lütfen [Common Data Service Müşteri Verileri’ne karşı DSR’leri yürütme](https://go.microsoft.com/fwlink/?linkid=872251) konusuna bakın.

El ile inceleme gerektiren veriler ve kaynaklar için, Microsoft Flow belirli bir kullanıcının kişisel verilerini bulmaya veya değiştirmeye yönelik olarak aşağıdaki deneyimleri sunar:

* **Web sitesi erişimi:** [PowerApps Yönetim Merkezi](https://admin.powerapps.com/) veya [Microsoft Flow Yönetim Merkezi](https://admin.flow.microsoft.com/)’nde oturum açın

* **PowerShell erişimi:**  [PowerApps Yönetici PowerShell cmdlet'leri](https://go.microsoft.com/fwlink/?linkid=871804) 

Bir yöneticinin her bir kaynak türündeki her bir kişisel veriyi silmek için kullanabileceği deneyimlerin dökümü şöyledir:

|Kişisel verileri kapsayan kaynaklar|Web sitesi erişimi|PowerShell erişimi|Otomatik Silme|
|-----|----|----|----|
|Sistem tarafından oluşturulan günlükler|[Office 365 Hizmet Güveni Portalı](https://servicetrust.microsoft.com/)|||
|Ortam|Microsoft Flow Yönetim Merkezi|PowerApps cmdlet'leri||
|Ortam izinleri*|Microsoft Flow Yönetim Merkezi|PowerApps cmdlet'leri||
|Çalıştırma geçmişi||| 28 günlük bekletme ilkesi aracılığıyla silindi|
|Etkinlik akışı |||28 günlük bekletme ilkesi aracılığıyla silindi|
|Kullanıcı işleri|| ||
|Akışlar|Microsoft Flow Oluşturucu Portalı**|||
|Akış izinleri|Microsoft Flow Oluşturucu Portalı|||
|Kullanıcı ayrıntıları||PowerApps cmdlet'leri||
|Bağlantılar|Microsoft Flow Oluşturucu Portalı| ||
|Bağlantı izinleri|Microsoft Flow Oluşturucu Portalı| ||
|Özel bağlayıcı|Microsoft Flow Oluşturucu Portalı| ||
|Özel bağlayıcı izinleri|Microsoft Flow Oluşturucu Portalı| ||
|Onay Geçmişi|Microsoft PowerApps Oluşturucu Portalı*|||

*Common Data Service’e giriş ile, bir veritabanı ortam içinde oluşturulduysa, ortam izinleri ve model tabanlı uygulama izinleri, Common Data Service veritabanı örneğinde kayıt olarak depolanır. Common Data Service kullanan kullanıcılara yönelik DSR’lerin nasıl yanıtlanacağı hakkında rehberlik için lütfen [Common Data Service Müşteri Verileri’ne karşı DSR’leri yürütme](https://go.microsoft.com/fwlink/?linkid=872251) konusuna bakın.

\*\* Yöneticiye Microsoft Flow Yönetim Merkezi’nden erişim atandıysa, yönetici bu kaynaklara yalnızca Microsoft Flow Oluşturucu Portalı’ndan erişebilir.

## <a name="manage-delete-requests"></a>Silme isteklerini yönetme

Aşağıdaki adımlar yönetim işlevlerinin GDPR için silme isteklerini sunmak üzere var olduğunu açıklar. Bu adımlar aşağıda açıklanan sırayla gerçekleştirilmelidir.

> [!IMPORTANT]
> Veri bozulmasını önlemek için bu adımları sırasıyla izleyin.
>
>

## <a name="list-and-re-assign-flows"></a>Akışları listeleme ve yeniden atama

Bu adımlar, ayrılan bir kullanıcı için mevcut akışları kopyalar. Kopyalara yeni sahiplik atadığınızda, bu akışlar mevcut iş süreçlerini desteklemeye devam edebilir. Bu akışları kopyalamak, ayrılan kullanıcıya yönelik kişisel tanımlayıcı bağlantılarını silmede önemlidir ve akışın diğer API’lerle ve SaaS uygulamalarıyla bağlantı kurması için yeni bağlantılar oluşturulmalıdır.

1. [Microsoft Flow yönetim merkezinde](https://admin.flow.microsoft.com/) oturum açın ve ardından silinen kullanıcının sahip olduğu akışları kapsayan ortamı seçin.

    ![Ortamları görüntüleme](./media/gdpr-dsr-delete/view-environments.png)

1. **Kaynaklar** > **Akışlar**’ı ve ardından yeniden atamak istediğiniz akışın başlığını seçin.

    ![Akışları görüntüleme](./media/gdpr-dsr-delete/admin-view-flows.png)

1. **Paylaşımı yönetin**’i seçin.

    ![Paylaşımı yönetin](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. Sağ kenarda görünen **Paylaş** panelinde kendinizi sahip olarak ekleyin ve **Kaydet**’i seçin.

    ![Akışı paylaşma](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. [Microsoft Flow](https://flow.microsoft.com/)’da oturum açın, **Akışlarım**’ı ve sonra **Ekip akışları**’nı seçin.

1. Kopyalamak istediğiniz akış için üç noktayı **(… )** ve ardından **Farklı Kaydet**’i seçin.

    ![Akışı farklı kaydet](./media/gdpr-dsr-delete/flow-save-as.png)

1. Bağlantıları gerektiği şekilde yapılandırın ve **Devam**’ı seçin.

1. Yeni bir ad sağlayın ve **Kaydet**’i seçin.

    ![Akışın kopyasını oluşturma](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Akışın bu yeni sürümü, isterseniz diğer kullanıcılarla paylaşabileceğiniz **Akışlarım** bölümünde görünür.

    ![Ekip akışları](./media/gdpr-dsr-delete/team-flows.png)

1. Özgün akışı silmek için akışın üç noktasını **(…)**, **Sil**’i ve istenildiğinde yeniden **Sil**’i seçin. Bu adımlar, kullanıcı ile Microsoft Flow arasındaki sistem bağımlılıklarının içerdiği temel alınan kişisel tanımlayıcıları da kaldırır.

    ![Akış onayını silme](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Akışın kopyasını etkinleştirmek için **Akışlarım**’ı açın ve iki durumlu denetimi **Açık** durumuna getirin.

    ![Akışı etkinleştirme](./media/gdpr-dsr-delete/toggle-on.png)

1. Kopya artık özgün sürümle aynı iş akışı mantığını gerçekleştirir.

## <a name="delete-approval-history-from-microsoft-flow"></a>Microsoft Flow’dan onay geçmişini silme

 Microsoft Flow onay verileri, Common Data Service’in şu anki veya bir önceki sürümünde depolanır. Kişisel bilgiler onay içinde bir onay yanıtının içerdiği onay atamaları ve açıklamaları formunda bulunur. Yöneticiler aşağıdaki adımları izleyerek bu verilere erişebilir:

1. [PowerApps](https://web.powerapps.com/)’te oturum açın.

1. **Veri** ve ardından **Varlıklar**’ı seçin.

1. **Akış onayı** varlığına ait üç noktayı seçin **(…)** ve verileri Microsoft Excel’de açın.

1. Microsoft Excel’de onay verilerini gerektiği gibi arayın, filtreleyin ve silin.

Common Data Service kullanan kullanıcılara yönelik DSR’lerin nasıl yanıtlanacağı hakkında ek rehberlik için lütfen [Common Data Service Müşteri Verileri’ne karşı DSR’leri yürütme](https://go.microsoft.com/fwlink/?linkid=872251) konusuna bakın.


## <a name="delete-connections-created-by-a-user"></a>Bir kullanıcı tarafından oluşturulan bağlantıları silme

Bağlantılar, diğer API'ler ve SaaS sistemleriyle bağlantı kurmak için bağlayıcılar ile birlikte kullanılır.  Bağlantılar, onları oluşturan kullanıcılara yönelik başvuruları içerir ve bunun sonucu olarak da kullanıcıya yönelik tüm başvuruları kaldırmak amacıyla silinebilir.

PowerApps Oluşturucu PowerShell cmdlet'leri

Kullanıcı, [PowerApps Oluşturucu PowerShell cmdlet'lerinden](https://go.microsoft.com/fwlink/?linkid=871448) Remove-Connection işlevini kullanarak bağlantılarının tümünü silebilir:

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-Connection | Remove-Connection
```

PowerApps Yönetici PowerShell cmdlet'leri

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```

## <a name="delete-the-users-permissions-to-shared-connections"></a>Kullanıcının paylaşılan bağlantılara yönelik izinlerini silme

PowerApps Oluşturucu PowerShell cmdlet'leri

Kullanıcı, [PowerApps Oluşturucu PowerShell cmdlet'lerindeki](https://go.microsoft.com/fwlink/?linkid=871448) Remove-ConnectionRoleAssignment işlevini kullanarak paylaşılan bağlantılar için bağlantı rolü atamalarının tümünü silebilir:

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

PowerApps Yönetici PowerShell cmdlet'leri

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> Bağlantı kaynağı silinmeden sahip rolü atamaları silinemez.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Kullanıcı tarafından oluşturulan özel bağlayıcıları silme

Özel Bağlayıcılar sistemde bulunmayan mevcut bağlayıcıları tamamlar ve diğer API’lere, SaaS’a ve özel olarak geliştirilmiş sistemlere bağlantı olanağı sağlar. Özel Bağlayıcılar, onları oluşturan kullanıcılara yönelik başvuruları içerir ve bunun sonucu olarak da kullanıcıya yönelik tüm başvuruları kaldırmak amacıyla silinebilir.

PowerApps Oluşturucu PowerShell cmdlet'leri

Kullanıcı, [PowerApps Oluşturucu PowerShell cmdlet'lerinden](https://go.microsoft.com/fwlink/?linkid=871448) Remove-Connection işlevini kullanarak özel bağlayıcılarının tümünü silebilir:

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

PowerApps Yönetici PowerShell cmdlet'leri
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>Kullanıcının paylaşılan özel bağlayıcılara yönelik izinlerini silme

PowerApps Oluşturucu PowerShell cmdlet'leri

Kullanıcı, [PowerApps Oluşturucu PowerShell cmdlet'lerindeki](https://go.microsoft.com/fwlink/?linkid=871448) Remove-ConnectorRoleAssignment işlevini kullanarak paylaşılan özel bağlayıcı için bağlayıcı rolü atamalarının tümünü silebilir:

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

PowerApps Yönetici PowerShell cmdlet'leri
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> Bağlantı kaynağı silinmeden sahip rolü atamaları silinemez.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Kullanıcı tarafından oluşturulan tüm ortamları silme veya yeniden atama

Bir yönetici olarak, bir kullanıcı için kullanıcı tarafından oluşturulmuş ortamların her birinde bir DSR silme isteği işlerken almanız gereken iki karar vardır:

1. Kuruluşunuzdan başka kimsenin ortamı kullanmadığını belirledikten sonra ortamı silmeyi seçebilirsiniz
1. Ortamın hala gerekli olduğunu belirlerseniz, ortamı silmemeyi seçebilir ve kendinizi (veya kuruluşunuzdaki başka bir kullanıcıyı) Ortam Yöneticisi olarak ekleyebilirsiniz.
> [!IMPORTANT]
> Bir ortamı silmek, tüm uygulamalar, akışlar, bağlantılar vb. dahil ortamın içindeki tüm kaynakları kalıcı olarak siler. Bu nedenle lütfen silmeden önce ortamın içeriklerini gözden geçirin.
>
>

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Microsoft Flow Yönetim Merkezi’nden kullanıcının ortamlarına erişim izni verme

Bir yönetici, [Microsoft Flow Yönetim Merkezi](https://admin.flow.microsoft.com/)’ndeki belirli bir kullanıcı tarafından oluşturulmuş bir ortama Yönetici erişimi hakkı verebilir. Ortamları yönetme hakkında daha fazla bilgi için lütfen [Microsoft Flow’da ortamları kullanma](https://docs.microsoft.com/flow/environments-overview-admin) konusuna gidin.

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Kullanıcının diğer tüm ortamlara yönelik izinlerini silme

Kullanıcılara bir ortamda izinler atanabilir (Ortam Yöneticisi, Ortam Oluşturucu vb. gibi) ve bu izinler de Microsoft Flow hizmetinde “rol ataması” olarak depolanır.

Common Data Service’e giriş ile, bir veritabanı ortam içinde oluşturulduysa, bu “rol atamaları”, Common Data Service veritabanı örneğinde kayıt olarak depolanır.

Bir ortamda kullanıcının iznini kaldırma hakkında daha fazla bilgi için [Microsoft Flow’da ortamları kullanma](https://docs.microsoft.com/flow/environments-overview-admin) konusuna gidin.

## <a name="delete-gateway-settings"></a>Ağ Geçidi Ayarlarını Silme

Şirket İçi Veri Ağ Geçitleri için Veri Sahibi Silme İsteklerine verilen yanıta [buradan](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration) erişilebilir.

## <a name="delete-user-details"></a>Kullanıcı Ayrıntılarını Silme

Kullanıcı ayrıntıları, bir kullanıcı ile belirli bir kiracı arasında bağlantı sağlar. Bu komutu çalıştırmadan önce, bu kullanıcı için tüm akışların yeniden atandığından ve/veya silindiğinden emin olun. İşlem tamamlandıktan sonra bir yönetici, **Remove-AdminFlowUserDetails** cmdlet’ini çağırıp kullanıcı için Nesne Kimliğini ileterek kullanıcı ayrıntılarını silebilir.

PowerApps Yönetici PowerShell cmdlet'leri
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> Bir kullanıcı halen bireysel akışlara veya takım akışlarına sahipse bu komut bir hata döndürür. Çözümlemek için, bu kullanıcıya yönelik takım akışlarını veya kalan tüm akışları silin ve komutu yeniden çalıştırın.
>
>

## <a name="delete-the-user-from-azure-active-directory"></a>Azure Active Directory’den kullanıcıyı silme

Yukarıdaki adımlar tamamlandıktan sonra son adım, [Office 365 Hizmet Güveni Portalı](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)’nda bulunabilecek Azure Veri Sahibi İsteği GDPR belgelerinde açıklanan adımları izleyerek Azure Active Directory için kullanıcının hesabını silmektir.

## <a name="delete-the-user-from-unmanaged-tenant"></a>Yönetilmeyen Kiracıdan kullanıcıyı silme

Yönetilmeyen bir kiracının üyesi olmanız durumunda, [İş ve Okul Gizliliği portalından](https://go.microsoft.com/fwlink/?linkid=873123) bir **Hesap kapatma** eylemi gerçekleştirmeniz gerekir.

Yönetilen kiracının mı yoksa yönetilmeyen kiracının mu kullanıcısı olduğunuzu belirlemek için aşağıdaki eylemleri gerçekleştirin:

1. Şu URL’yi bir tarayıcıda açın ve URL’deki e-posta adresinizi değiştirdiğinizden emin olun:[ https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1).
1. **Yönetilmeyen kiracının** üyesiyseniz, yanıtta bir `"IsViral": true` görürsünüz.

    {

     "Login": "foobar@unmanagedcontoso.com",

    "DomainName": "unmanagedcontoso.com",

    "IsViral": **true**,
    
    }

1. Aksi takdirde, yönetilen bir kiracıya aitsiniz demektir.
