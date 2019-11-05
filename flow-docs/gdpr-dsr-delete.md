---
title: Microsoft Flow GDPR veri konusu silme Istekleri | Microsoft Docs
description: GUZ veri konu silme Isteklerini yanıtlamak için Microsoft Flow nasıl kullanacağınızı öğrenin.
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
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 53e33d1c202b05854401573ca16040f17eb138c9
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548091"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Microsoft Flow için GDPR veri sahibine yönelik silme Isteklerini yanıtlama
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Kuruluşun müşteri verilerinden kişisel verilerin kaldırılmasına yönelik "sağdan ERASURE", GDPR içinde önemli bir koruma sağlar. Kişisel verilerin kaldırılması, denetim günlüğü bilgileri hariç tüm kişisel verileri ve sistem tarafından oluşturulan günlükleri kaldırmayı içerir.

Microsoft Flow, kullanıcıların kuruluşunuzun günlük işlemlerinin önemli bir parçası olan Otomasyon iş akışları oluşturmasına olanak tanır. Bir Kullanıcı kuruluşunuzdan ayrıldığında, yöneticinin, kullanıcının oluşturduğu belirli veri ve kaynakların silinip silmeyeceğini el ile gözden geçirmesi ve silmesi gerekir. Kullanıcı hesabının Azure Active Directory silindiği her seferinde otomatik olarak silinen başka kişisel veriler de vardır.

Aşağıdaki tabloda, hangi kişisel verilerin otomatik olarak silineceği ve hangi verilerin bir yöneticinin el ile gözden geçirmesi ve silmesini gerektirdiğini gösterilmektedir:

|El ile inceleme ve silme gerektirir|Kullanıcı Azure Active Directory silindiği zaman otomatik olarak silinir|
|------|------|
|Ortamınızın|Sistem tarafından oluşturulan Günlükler|
|Ortam izinleri * *|çalıştırma geçmişi|
|Var|Etkinlik akışı|
|Akış izinleri|Geçidinde |
|Kullanıcı ayrıntıları|Ağ Geçidi izinleri|
|Bağlantının||
|Bağlantı izinleri||
|Özel bağlayıcı *||
|Özel bağlayıcı izinleri||

\* Bu kaynakların her biri, kişisel verileri içeren "oluşturan" ve "değiştiren" kayıtlarını içerir. Güvenlik nedenleriyle, bu kayıtlar kaynak silinene kadar tutulur.

\* * Common Data Service veritabanı içeren ortamlar için, ortam izinleri (örneğin, ortam Oluşturucu ve yönetici rollerine atanmış kullanıcılar) Common Data Service veritabanında kayıt olarak depolanır. Common Data Service kullanan kullanıcılar için DSRs 'ye nasıl yanıt verileceğini gösteren yönergeler için lütfen [Common Data Service müşteri verilerine karşı DSRS yürütme](https://go.microsoft.com/fwlink/?linkid=872251)konusuna bakın.

El ile inceleme gerektiren veri ve kaynaklar için Microsoft Flow, belirli bir kullanıcının kişisel verilerini bulmak veya değiştirmek için aşağıdaki deneyimleri sunar:

* **Web sitesi erişimi:** [PowerApps yönetim merkezinde](https://admin.powerapps.com/)veya [Microsoft Flow Yönetim merkezinde](https://admin.flow.microsoft.com/) oturum açın

* **PowerShell erişimi:**  [PowerApps Yöneticisi PowerShell cdmizin](https://go.microsoft.com/fwlink/?linkid=871804) 

Aşağıda, bir yöneticinin her bir kaynak türü içindeki her bir kişisel veri türünü silmesi için kullanılabilen deneyimlerin dökümü verilmiştir:

|Kişisel verileri içeren kaynaklar|Web sitesi erişimi|PowerShell erişimi|Otomatik silme|
|-----|----|----|----|
|Sistem tarafından oluşturulan Günlükler|[Office 365 hizmet güveni portalı](https://servicetrust.microsoft.com/)|||
|Ortamınızın|Microsoft Flow Yönetim Merkezi|PowerApps cmdlet 'leri||
|Ortam izinleri *|Microsoft Flow Yönetim Merkezi|PowerApps cmdlet 'leri||
|çalıştırma geçmişi||| 28 günlük bekletme ilkesi üzerinden silindi|
|Etkinlik akışı |||28 günlük bekletme ilkesi üzerinden silindi|
|Kullanıcı işleri|| ||
|Var|Microsoft Flow Oluşturucu portalı * *|||
|Akış izinleri|Microsoft Flow Oluşturucu portalı|||
|Kullanıcı ayrıntıları||PowerApps cmdlet 'leri||
|Bağlantının|Microsoft Flow Oluşturucu portalı| ||
|Bağlantı izinleri|Microsoft Flow Oluşturucu portalı| ||
|Özel bağlayıcı|Microsoft Flow Oluşturucu portalı| ||
|Özel bağlayıcı izinleri|Microsoft Flow Oluşturucu portalı| ||
|Onay geçmişi|Microsoft PowerApps Oluşturucu portalı *|||

\* Common Data Service kapsamında, ortamda bir veritabanı oluşturulursa, ortam izinleri ve model temelli uygulama izinleri, Common Data Service veritabanı örneği içinde kayıt olarak depolanır. Common Data Service kullanan kullanıcılar için DSRs 'ye nasıl yanıt verileceğini gösteren yönergeler için lütfen [Common Data Service müşteri verilerine karşı DSRS yürütme](https://go.microsoft.com/fwlink/?linkid=872251)konusuna bakın.

\*\* yönetici yalnızca Microsoft Flow yönetim merkezinden erişim atanırsa Microsoft Flow Oluşturucu portalından bu kaynaklara erişebilir.

## <a name="manage-delete-requests"></a>Silme isteklerini yönetme

Aşağıdaki adımlar, GDPR için silme isteklerini sağlamak üzere yönetim işlevlerinin nasıl mevcut olduğunu açıklamaktadır. Bu adımlar aşağıda özetlenen sırada gerçekleştirilmelidir.

> [!IMPORTANT]
> Veri bozulmasını önlemek için bu adımları sırasıyla izleyin.
>
>

## <a name="list-and-re-assign-flows"></a>Akışları listeleme ve yeniden atama

Bu adımlar, bir kullanıcı için mevcut akışları kopyalar. Kopyalara yeni sahiplik atarsanız, bu akışlar mevcut iş süreçlerini desteklemeye devam edebilir. Bu akışların kopyalanması, kişisel tanımlayıcı bağlantılarını silmek için önemlidir ve akışın diğer API 'Ler ve SaaS uygulamalarıyla bağlanması için yeni bağlantılar oluşturulmalıdır.

1. [Microsoft Flow Yönetim merkezinde](https://admin.flow.microsoft.com/)oturum açın ve ardından silinen kullanıcının sahip olduğu akışları içeren ortamı seçin.

    ![ortamları görüntüle](./media/gdpr-dsr-delete/view-environments.png)

1. **Kaynakları**, > **akışları**' nı seçin ve ardından yeniden atamak istediğiniz akışın başlığını seçin.

    ![Akışları görüntüle](./media/gdpr-dsr-delete/admin-view-flows.png)

1. **Paylaşımı Yönet**' i seçin.

    ![Paylaşımı Yönet](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. Sağ kenarda görüntülenen **paylaşma** panelinde, kendinizi bir sahip olarak ekleyin ve ardından **Kaydet**' i seçin.

    ![Akış paylaşma](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. [Microsoft Flow](https://flow.microsoft.com/)oturum açın, **Akışlarım**' ı seçin ve ardından **ekip akışları**' nı seçin.

1. Kopyalamak istediğiniz akışın üç nokta **(...)** simgesini seçin ve **farklı kaydet**' i seçin.

    ![Flow farklı kaydet](./media/gdpr-dsr-delete/flow-save-as.png)

1. Gerektiğinde bağlantıları yapılandırıp **devam**' ı seçin.

1. Yeni bir ad belirtin ve ardından **Kaydet**' i seçin.

    ![Akışın kopyasını oluştur](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Akışın bu yeni sürümü, isterseniz ek kullanıcılarla paylaşabileceğiniz **Akışlarım**halinde görünür.

    ![Ekip akışları](./media/gdpr-dsr-delete/team-flows.png)

1. Özgün akışı, onun için üç nokta **(...)** ve ardından **Sil**' i seçerek silin ve istendiğinde yeniden **Sil** ' i seçin. Bu adım Ayrıca, Kullanıcı ve Microsoft Flow arasındaki sistem bağımlılıklarında bulunan temel kişisel tanımlayıcıları da kaldırır.

    ![Akış onayını Sil](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. **Akışlarımı** açıp geçiş denetimini **Açık**olarak açarak akışın kopyasını etkinleştirin.

    ![Akışı etkinleştir](./media/gdpr-dsr-delete/toggle-on.png)

1. Şimdi kopya, özgün sürümle aynı iş akışı mantığını gerçekleştirir.

## <a name="delete-approval-history-from-microsoft-flow"></a>Microsoft Flow onay geçmişini sil

 Microsoft Flow için onay verileri, Common Data Service geçerli veya önceki sürümü içinde depolanır. Bir onay içinde, kişisel bilgiler onay yanıtında bulunan onay atamaları ve açıklamalar biçiminde bulunur. Yöneticiler, bu verilere aşağıdaki adımları izleyerek erişebilir:

1. [PowerApps](https://web.powerapps.com/)'te oturum açın.

1. **Verileri**seçin ve ardından **varlıklar**' ı seçin.

1. **Flow onay** varlığı için üç nokta **(...)** simgesini seçin ve ardından verileri Microsoft Excel 'de açın.

1. Microsoft Excel 'de, gerekli olduğu gibi onay verilerini arayın, filtreleyin ve silin.

Common Data Service kullanan kullanıcılar için DSRs 'ye yanıt verme hakkında daha fazla bilgi için lütfen bkz. [Common Data Service müşteri verilerine karşı DSRS yürütme](https://go.microsoft.com/fwlink/?linkid=872251).


## <a name="delete-connections-created-by-a-user"></a>Bir kullanıcı tarafından oluşturulan bağlantıları silme

Bağlantılar, diğer API 'Ler ve SaaS sistemleriyle bağlantı kurmak için bağlayıcılarla birlikte kullanılır.  Bağlantılar, onları oluşturan kullanıcıya başvurular içerir ve sonuç olarak kullanıcıya tüm başvuruları kaldırmak için silinebilir.

PowerApps Oluşturucu PowerShell cmdlet 'leri

Bir Kullanıcı [PowerApps Oluşturucu PowerShell cmdlet 'Lerinden](https://go.microsoft.com/fwlink/?linkid=871448)Remove-Connection işlevini kullanarak tüm bağlantılarını silebilir:

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-AdminPowerAppConnection | Remove-Connection
```

PowerApps Yöneticisi PowerShell cmdlet 'leri

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminPowerAppConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```

## <a name="delete-the-users-permissions-to-shared-connections"></a>Kullanıcının paylaşılan bağlantı izinlerini silme

PowerApps Oluşturucu PowerShell cmdlet 'leri

Kullanıcı, [PowerApps Oluşturucu PowerShell cmdlet 'lerinde](https://go.microsoft.com/fwlink/?linkid=871448)paylaşılan bağlantılar Remove-Connectionroleatama işlevi için tüm bağlantı rol atamalarını silebilir:

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

PowerApps Yöneticisi PowerShell cmdlet 'leri

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> Sahip rol atamaları, bağlantı kaynağı silinmeden silinemez.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Kullanıcı tarafından oluşturulan özel bağlayıcıları silme

Özel Bağlayıcılar, mevcut kullanıma hazır bağlayıcılarını tamamlar ve diğer API 'Ler, SaaS ve özel geliştirilmiş sistemlerle bağlantı sağlar. Özel Bağlayıcılar, onları oluşturan kullanıcıya başvurular içerir ve sonuç olarak kullanıcıya tüm başvuruları kaldırmak için silinebilir.

PowerApps Oluşturucu PowerShell cmdlet 'leri

Bir Kullanıcı, [PowerApps Oluşturucu PowerShell cmdlet 'Lerinde](https://go.microsoft.com/fwlink/?linkid=871448)Remove-Connector işlevinin tüm özel bağlayıcılarını silebilir:

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

PowerApps Yöneticisi PowerShell cmdlet 'leri
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>Kullanıcının paylaşılan özel bağlayıcılara yönelik izinlerini silme

PowerApps Oluşturucu PowerShell cmdlet 'leri

Kullanıcı, [PowerApps Oluşturucu PowerShell cmdlet 'Lerinde](https://go.microsoft.com/fwlink/?linkid=871448)Remove-Connectorroleatama işleviyle paylaşılan özel bağlayıcı için bağlayıcı rolü atamalarını silebilir:

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

PowerApps Yöneticisi PowerShell cmdlet 'leri
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> Sahip rol atamaları, bağlantı kaynağı silinmeden silinemez.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Kullanıcı tarafından oluşturulan tüm ortamları silme veya yeniden atama

Yönetici olarak, Kullanıcı tarafından oluşturulan ortamların her biri için bir DSR silme isteğini işlerken yapmanız gereken iki karar vardır:

1. Ortamın kuruluşunuzda başka hiç kimse tarafından kullanılmadığını belirlerseniz, ortamı silmeyi tercih edebilirsiniz
1. Ortamın hala gerekli olduğunu belirlerseniz, ortamı silmeyi ve kendinizi (veya kuruluşunuzdaki başka bir kullanıcıyı) ortam yöneticisi olarak eklemeyi tercih edebilirsiniz.
> [!IMPORTANT]
> Bir ortamın silinmesi, tüm uygulamalar, akışlar, bağlantılar vb. dahil olmak üzere ortamdaki tüm kaynakları kalıcı olarak siler. bu nedenle, silmeden önce lütfen bir ortamın içeriğini gözden geçirin.
>
>

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Microsoft Flow yönetim merkezinden bir kullanıcının ortamlarına erişim verme

Yönetici, [Microsoft Flow yönetim merkezinden](https://admin.flow.microsoft.com/)belirli bir kullanıcı tarafından oluşturulan bir ortama yönetici erişimi verebilir. Ortamları yönetme hakkında daha fazla bilgi için lütfen [Microsoft Flow içindeki ortamları kullanma](https://docs.microsoft.com/flow/environments-overview-admin)sayfasına gidin.

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Kullanıcının tüm diğer ortamlara yönelik izinlerini silme

Kullanıcılara (Ortam Yöneticisi, ortam Oluşturucu vb.), Microsoft Flow hizmetinde "rol ataması" olarak depolanan izinler atanabilir.

Common Data Service giriş ile, ortamda bir veritabanı oluşturulursa, bu "rol atamaları" Common Data Service veritabanı örneği içinde kayıt olarak depolanır.

Bir ortamdaki kullanıcının iznini kaldırma hakkında daha fazla bilgi için [Microsoft Flow içindeki ortamları kullanma](https://docs.microsoft.com/flow/environments-overview-admin)bölümüne gidin.

## <a name="delete-gateway-settings"></a>Ağ Geçidi ayarlarını silme

Şirket Içi veri ağ geçitleri için veri sahibine yönelik silme Isteklerini yanıtlama, [burada](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration)bulunabilir.

## <a name="delete-user-details"></a>Kullanıcı ayrıntılarını silme

Kullanıcı ayrıntıları, bir kullanıcı ile belirli bir kiracı arasında bağlantı sağlar. Bu komutu çalıştırmadan önce, bu kullanıcı için tüm akışların yeniden atandığından ve/veya silindiğinden emin olun. Bu tamamlandığında yönetici, **Remove-AdminFlowUserDetails** cmdlet 'ini çağırarak ve Kullanıcı IÇIN nesne kimliğini geçirerek Kullanıcı ayrıntılarını silebilir.

PowerApps Yöneticisi PowerShell cmdlet 'leri
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> Bir Kullanıcı, bireysel veya ekip akışlarına sahip olmaya devam ediyorsa, bu komut bir hata döndürür. Sorunu gidermek için, bu kullanıcı için tüm kalan akışları veya ekip akışlarını silin ve komutu yeniden çalıştırın.
>
>

## <a name="delete-the-user-from-azure-active-directory"></a>Kullanıcıyı Azure Active Directory Sil

Yukarıdaki adımlar tamamlandıktan sonra son adım, [Office 365 hizmet güven portalı](https://servicetrust.microsoft.com/ViewPage/GDPRDSR)'Nda bulunan Azure Data Subject isteği GDPR belgelerinde özetlenen adımları izleyerek kullanıcının Azure Active Directory hesabını silmektir.

## <a name="delete-the-user-from-unmanaged-tenant"></a>Kullanıcıyı yönetilmeyen kiracıdan silme

Yönetilmeyen bir kiracının üyesi olduğunuz olayda [iş ve okul gizlilik portalından](https://go.microsoft.com/fwlink/?linkid=873123)bir **Hesap kapatma** eylemi gerçekleştirmeniz gerekir.

Yönetilen veya yönetilmeyen bir kiracının kullanıcısı olup olmadığınızı anlamak için aşağıdaki eylemleri gerçekleştirin:

1. Aşağıdaki URL 'yi bir tarayıcıda açarak URL adresi:[https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1)yerine e-posta adresinizi değiştirdiğinizden emin olun.
1. **Yönetilmeyen bir kiracının** üyesiyse yanıtta bir `"IsViral": true` görürsünüz.

    {

     "Oturum açma": "foobar@unmanagedcontoso.com",

    "DomainName": "unmanagedcontoso.com",

    "IsViral": **true**,
    
    }

1. Aksi takdirde, yönetilen bir kiracıya ait olursunuz.
