---
title: Onay iş akışlarını kolayca otomatikleştirin. | Microsoft Docs
description: SharePoint, Dynamics CRM, Salesforce, OneDrive Iş, Zendesk veya WordPress ile tümleştirilen onay iş akışlarını otomatikleştirin.
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c46ac3dc65b6e1a3970bd0b9b4ef17df5bef16f8
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548712"
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Microsoft Flow bir onay iş akışı oluşturma ve test etme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Microsoft Flow ile SharePoint, Dynamics 365, Salesforce, OneDrive Iş, Zendesk veya WordPress gibi çeşitli hizmetlerde belge veya işlemlerin onayını yönetebilirsiniz.

Bir onay iş akışı oluşturmak için **onaylar-onay Başlat** eylemini herhangi bir akışa ekleyin. Bu eylemi ekledikten sonra, akışınız belge veya işlemlerin onayını yönetebilir. Örneğin, faturaları, iş emirlerini veya satış tekliflerini onaylamak için belge onay akışları oluşturabilirsiniz. Ayrıca, tatil isteklerini, fazla mesaiyi veya seyahat planlarını onaylamak için işlem onay akışları da oluşturabilirsiniz.

Onaylayanlar, e-posta gelen kutusuna, Microsoft Flow web sitesindeki [onay merkezinden](https://flow.microsoft.com/manage/approvals/received/) veya Microsoft Flow uygulamasına yönelik isteklere yanıt verebilir.

## <a name="create-an-approval-flow"></a>Onay akışı oluşturma
Oluşturacağız ve test ettiğimiz akışa bir genel bakış aşağıda verilmiştir:

   ![akışa genel bakış](./media/modern-approvals/create-flow-overview.png)

Flow aşağıdaki adımları gerçekleştirir:

1. Bir SharePoint Online listesinde bir tatil isteği oluşturduğunda başlatılır.
2. Tatil isteğini onay merkezine ekler ve ardından onaylayana e-posta ile gönderir.
3. Kullanıcının tatil isteğinde bulunduğu kişiye karar veren bir e-posta gönderir.
4. SharePoint Online listesini onaylayanın karar yorumlarıyla güncelleştirir.

## <a name="prerequisites"></a>Kaynakları
Bu yönergeyi tamamlamak için şu erişime sahip olmanız gerekir:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Bu sütunları SharePoint Online listenizde oluşturun:

   ![SharePoint Online listesi sütunları](./media/modern-approvals/sharepoint-list-fields.png)

SharePoint Online listesinin adını ve URL 'sini unutmayın. Bu öğelerin daha sonra SharePoint 'i yapılandırdığınızda **bir öğe oluşturulduğunda** tetiklemeniz gerekir.

## <a name="create-your-flow-from-the-blank-template"></a>Boş şablondan akışınızı oluşturun
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Tetikleyici ekleme

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

**Site adresi** ve **liste adı** Bu izlenecek yolda daha önce not ettiğiniz öğelerdir.

![SharePoint bilgileri](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Profil eylemi ekleme

1. **Yeni adım**' ı seçin ve ardından **Eylem Ekle**' yi seçin.
   
    ![Yeni adım](./media/modern-approvals/select-sharepoint-add-action.png)
2. **Eylem seçin** arama kutusuna **profil** girin.
   
    ![profil ara](./media/modern-approvals/search-for-profile.png)
3. **Office 365 kullanıcıları-profilimi al** eylemini bulun ve seçin.
   
    ![Office kullanıcılarını seçin](./media/modern-approvals/select-my-profile.png)
4. Akışınız için bir ad girin ve ardından şu ana kadar yaptığımız işi kaydetmek için **akış oluştur** ' u seçin.
   
    ![akışı Kaydet](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Onay eylemi ekleme

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Bu eylem onay isteğini **atanan** kutusundaki e-posta adresine gönderir.
>
>

## <a name="add-a-condition"></a>Koşul ekleme

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Onaylar için e-posta eylemi ekleme

Tatil isteği onaylandığında e-posta göndermek için şu adımları izleyin:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![onaylanan e-posta şablonunu yapılandırma](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Onaylanan istekler için güncelleştirme eylemi ekleme

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> **Site adresi**, **liste adı**, **kimlik**ve **başlık** gereklidir.
>
>

![öğe yapılandırmasını Güncelleştir](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Ret için e-posta eylemi ekleme

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![Reddedilen istekler için yapılandırma](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Reddedilen istekler için güncelleştirme eylemi ekleme

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > **Site adresi**, **liste adı**, **kimlik**ve **başlık** gereklidir.
   >
   >

![öğe kartını Güncelleştir](./media/modern-approvals/configure-update-item-no.png)

1. Yaptığımız işi kaydetmek için **akışı Güncelleştir** ' i seçin.
   
    ![Güncelleştirme eylemini seçin](./media/modern-approvals/update.png)

Bunu takip ediyorsanız, akışınız şu ekran görüntüsüne benzemelidir:

![akışa genel bakış](./media/modern-approvals/completed-flow.png)

Flow 'u oluşturduğumuz için sınama zamanı!

## <a name="request-an-approval"></a>Onay isteyin

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]


## <a name="create-long-running-approvals"></a>Uzun süre çalışan onaylar oluşturma

Akışınız 30 günden uzun süre boyunca çalışıyorsa, onayları Common Data Service ' de depolamayı göz önünde bulundurun. Bu, özgün akışın çalışma süresi dolduktan sonra bile onay isteklerine yanıt olarak davranan akışlar oluşturmanızı mümkün kılar. Bunu yapmak için, biri onay isteği göndermek üzere iki akış, diğeri ise onay isteğine verilen yanıtlar üzerinde iş mantığını çalıştırmak için diğer **bir onay oluştur (v2)** eylemine dayanır. [Uzun süre çalışan onaylar](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/long-lived-approvals-other-approval-improvements)hakkında daha fazla bilgi edinin.

>[!TIP]
> Modern e-posta istemcileri kullanıyorsanız, bir isteğin hala gerekli olup olmadığını merak etmeniz gerekmez, çünkü Microsoft Flow onay tamamlandığını belirtmek için e-postayı otomatik olarak güncelleştirir.

## <a name="cancel-an-approval-requests"></a>Onay isteklerini iptal et

Bazen gönderdiğiniz onay isteğini iptal etmek isteyebilirsiniz. İstekte muhtemelen bir hata yapmış olabilirsiniz veya artık ilgili değildir. Her iki durumda da, isteği gönderen kişi şu adımları izleyerek Iptal edebilir:

1. Onayı seçin
1. Yan bölmedeki **onayı Iptal et** ' i seçin.

>[!TIP]
>İptal ettiğiniz onay isteklerini görüntülemek için her zaman **Geçmiş** sekmesini seçebilirsiniz.

>[!NOTE]
> İptal özelliği, **onay oluştur (v2)** eyleminde desteklenir.

## <a name="request-approvals-from-guest-users"></a>Konuk kullanıcılardan onay isteme

Onay isteklerini, kuruluşunuz dışındaki kişilere gönderebilirsiniz. Bunu yapmak için, [kullanıcıları diğer kiracılardan Konuk olarak davet](https://docs.microsoft.com/azure/active-directory/b2b/add-user-without-invite)ederek Azure Active Directory (Azure AD) Konuk kullanıcıları kullanın.

Bir konuğa bir rol atadığınızda, bu, konuğa onay sürecine katılması gereken izni verir.

Akışınızı oluşturup sınadığınıza göre, başkalarının onu nasıl kullanacağınızı öğrendiğinizden emin olun.

## <a name="learn-more"></a>Daha fazla bilgi edinin

* [Bekleyen onay isteklerini](approve-reject-requests.md) görüntüleme ve yönetme
* [Sıralı onay akışları oluşturun.](sequential-modern-approvals.md)
* [Paralel onay akışları oluşturun.](parallel-modern-approvals.md)
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows)için Microsoft Flow Mobile App 'i yükler.
