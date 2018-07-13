---
title: Onay iş akışlarını kolayca otomatikleştirin. | Microsoft Docs
description: SharePoint, Dynamics CRM, Salesforce, OneDrive İş, Zendesk veya WordPress ile tümleştirilen onay iş akışlarını otomatikleştirin.
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
ms.date: 07/20/2017
ms.author: deonhe
ms.openlocfilehash: bd89bca994a77072815a73ba1cbc7ba1db6955d3
ms.sourcegitcommit: 4a8d11e1768cd0ca96a60b6f5548a68c0c8999e5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38949735"
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Microsoft Flow ile bir onay iş akışını oluşturma ve test etme

Microsoft Flow ile SharePoint, Dynamics CRM, Salesforce, OneDrive İş, Zendesk veya WordPress gibi çeşitli hizmetlerdeki belge ya da işlemlerin onaylanmasını yönetebilirsiniz.

Onay iş akışı oluşturmak için **Onaylar - Onay başlat** eylemini herhangi bir akışa ekleyin. Bu eylem eklendikten sonra, akışınız belge veya işlemlerin onay süreçlerini yönetebilir. Örneğin faturaları, iş emirlerini veya satış tekliflerini onaylayan belge onay akışları oluşturabilirsiniz. Ayrıca tatil isteklerini, fazla mesaileri veya seyahat planlarını onaylamak üzere işlem onayı akışları da oluşturabilirsiniz.

Onaylayanlar istekleri e-posta gelen kutularından, Microsoft Flow web sitesindeki [onay merkezinden](https://flow.microsoft.com/manage/approvals/received/) veya Microsoft Flow uygulamasından yanıtlayabilir.

## <a name="create-an-approval-flow"></a>Bir onay akışı oluşturma
Oluşturup test edeceğimiz akış, aşağıda genel hatlarıyla sunulmuştur:

   ![Akışa genel bakış](./media/modern-approvals/create-flow-overview.png)

Akış, aşağıdaki adımları gerçekleştirir:

1. Bir SharePoint Online listesinde tatil isteği oluşturulduğunda başlatılır.
2. Tatil isteğini onay merkezine ekler ve sonra onaylayana e-posta ile gönderir.
3. Tatil isteğinde bulunan kişiye, onayı veren kişinin kararını içeren bir e-posta gönderir.
4. SharePoint Online listesini, onayı veren kişinin karar açıklamalarıyla güncelleştirir.

## <a name="prerequisites"></a>Önkoşullar
Bu kılavuzu tamamlamak için şunlara erişebiliyor olmanız gerekir:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

SharePoint Online listenizde şu sütunları oluşturun:

   ![SharePoint Online listesi sütunları](./media/modern-approvals/sharepoint-list-fields.png)

SharePoint Online listesinin adını ve URL'sini not edin. **SharePoint - Bir öğe oluşturulduğunda** tetikleyicisini yapılandırırken bu bilgilere ihtiyaç duyacaksınız.

## <a name="create-your-flow-from-the-blank-template"></a>Akışınızı boş şablondan oluşturun
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Tetikleyici ekleyin

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

**Site Adresi** ve **Liste Adı**, bu kılavuzun önceki adımlarında not ettiğiniz bilgilerdir.

![SharePoint bilgileri](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Profil eylemi ekleme

1. **Yeni adım**'ı ve ardından **Eylem ekle**'yi seçin.
   
    ![Yeni adım](./media/modern-approvals/select-sharepoint-add-action.png)
2. **Eylem seçin** arama kutusuna **profil** yazın.
   
    ![Profil araması yapın](./media/modern-approvals/search-for-profile.png)
3. **Office 365 Kullanıcıları - Profilimi al** eylemini bulun ve seçin.
   
    ![Office kullanıcılarını seçin](./media/modern-approvals/select-my-profile.png)
4. Akışınıza bir ad verin ve **Akış oluştur**'a tıklayarak yaptığınız işlemleri kaydedin.
   
    ![Akışı kaydedin](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Onay eylemi ekleme

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Bu eylem, onay isteğini **Atanan** kutusundaki e-posta adresine gönderir.
>
>

## <a name="add-a-condition"></a>Koşul ekleme

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Onaylar için e-posta eylemi ekleme

Tatil isteği onaylandığında e-posta göndermek için şu adımları izleyin:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![Onay e-postası şablonunu yapılandırın](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Onaylanan istekler için güncelleştirme eylemi ekleme

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> **Site Adresi**, **Liste Adı**, **Kimlik** ve **Başlık** alanları gereklidir.
>
>

![Öğeyi güncelleştir eylemini yapılandırın](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Reddedilen istekler için e-posta eylemi ekleme

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![Reddedilen istekler için yapılandırma](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Reddedilen istekler için güncelleştirme eylemi ekleme

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > **Site Adresi**, **Liste Adı**, **Kimlik** ve **Başlık** alanları gereklidir.
   >
   >

![Öğeyi güncelleştir kartı](./media/modern-approvals/configure-update-item-no.png)

1. **Akışı güncelleştir**'e tıklayarak yaptığınız işlemleri kaydedin.
   
    ![Güncelleştir eylemini seçin](./media/modern-approvals/update.png)

Tüm adımları uyguladıysanız akışınız şu ekran görüntüsüne benzer olacaktır:

![Akışa genel bakış](./media/modern-approvals/completed-flow.png)

Akışı oluşturduk, şimdi test etme zamanı!

## <a name="request-an-approval"></a>Onay isteği gönderme

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

Akışınızı oluşturup test ettikten sonra diğer kişilere nasıl kullanılacağını açıklamayı unutmayın.

## <a name="learn-more"></a>Daha fazla bilgi

* [Bekleyen onay isteklerini](approve-reject-requests.md) görüntüleme ve yönetme
* [Sıralı onay akışları](sequential-modern-approvals.md) oluşturun.
* [Paralel onay iş akışları](parallel-modern-approvals.md) oluşturun.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulamasını yükleyin.
