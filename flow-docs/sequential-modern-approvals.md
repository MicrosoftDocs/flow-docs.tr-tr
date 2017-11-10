---
title: "Birden çok onaylayana sahip modern bir onay iş akışı oluşturma | Microsoft Docs"
description: "Birden çok onaylayanla modern bir onay iş akışı oluşturma "
services: 
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/08/2017
ms.author: deonhe
ms.openlocfilehash: 8620cd49f9e19f6641909fcab3103568d148e565
ms.sourcegitcommit: 01325305b9d2cf964acac9feb6cca0af66db7440
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2017
---
# <a name="manage-sequential-approvals-with-microsoft-flow"></a>Microsoft Flow ile sıralı onayları yönetme
Son onaylayanın oturumu kapatabilmesi için bazı iş akışları ön onay gerektirir. Örneğin, bir şirketin 1000 ABD dolarının üzerindeki faturalar için Finans departmanının onayından önce bir ön onay verilmesini gerektiren sıralı onay ilkesi olabilir.

Bu incelemede, çalışanların tatil isteklerini yöneten sıralı bir onay akışı oluşturacağız.

## <a name="detailed-steps-in-the-flow"></a>Akıştaki ayrıntılı adımlar
Akış:

1. Bir çalışan [SharePoint Online listesinde](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) tatil isteği oluşturduğunda başlar.
2. Tatil isteğini onay merkezine ekledikten sonra, ön onayı verecek kişiye e-posta ile gönderir.
3. Çalışana ön onay kararını e-posta ile gönderir.
4. SharePoint Online listesini ön onayı veren kişinin kararı ve açıklamalarıyla birlikte güncelleştirir.
   
   Not: İstek önceden onaylandıysa, akış şu adımlarla devam eder:
5. Son onaylayana isteği gönderir.
6. Çalışana son kararı e-posta ile gönderir.
7. SharePoint listesini son karar ile güncelleştirir.

Şu görüntü, önceki adımları özetlemektedir:

   ![Akışın Visio diyagramı](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>Önkoşullar
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Oluşturduğunuz SharePoint Online listesinde şu sütunlar bulunmalıdır:

   ![SharePoint listesinin sütunları](./media/sequential-modern-approvals/sharepoint-columns.png)

SharePoint Online listesinin adını ve URL'sini not edin. Daha sonra **SharePoint - Yeni bir öğe oluşturulduğunda** tetikleyicisini yapılandırırken bu bilgileri kullanacağız.

## <a name="create-your-flow-from-the-blank-template"></a>Akışınızı boş şablondan oluşturun
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Tetikleyici ekleyin
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![Sharepoint bilgileri](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Tatil isteğini oluşturan kişi için yöneticiyi alma
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. Akışınıza bir ad verin ve **Akış oluştur**'a tıklayarak yaptığınız işlemleri kaydedin.
   
    ![Akışı kaydedin](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > Değişiklikleri akışınıza kaydetmek için ekranın üst tarafından düzenli aralıklarla **Akışı güncelleştir**'i seçin.
   > 
   > 
   
    ![Güncelleştir eylemini seçin](./media/sequential-modern-approvals/update.png)

Her kaydetme işleminden sonra ekranın üst tarafından **Akışı düzenle** seçeneğini belirleyin ve değişiklik yapmaya devam edin.

## <a name="add-an-approval-action-for-pre-approvals"></a>Ön onaylar için onay eylemi ekleme
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Not: Bu eylem, ön onay isteğini **Atanan** kutusundaki e-posta adresine gönderir.

## <a name="add-a-condition"></a>Koşul ekleme
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> Bu koşul yanıttan denetler **Start an approval** (Onay başlat) eyleminden yanıtı kontrol eder.
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>Ön onaylar için e-posta eylemi ekleme
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![Ön onay e-postası şablonunu yapılandırın](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>Önceden onaylanan istekler için güncelleştirme eylemi ekleme
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![Öğeyi güncelleştir eylemini yapılandırın](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>Önceden onaylayanın yöneticisini getirme
1. **Yöneticiyi al** eylemi ekleyip ardından bu eylemden bir tane daha yapılandırmak için daha önce uyguladığımız [Tatil isteğini oluşturan kişi için yöneticiye ulaşma](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) adımlarını uygulayın. Şimdi ise önceden onaylayanın yöneticisine ulaşacağız.
2. İşlemi tamamladığınızda **Yöneticiyi al 2** kartı şu görüntüdeki gibi olacaktır. **Bu akışta kullanılan uygulama ve hizmetlerden dinamik içerik ekleyin** kartındaki **Yöneticiyi al** kategorisinden **E-posta** belirtecini kullandığınızdan emin olun.
   
   ![Önceden onaylayanın yöneticisini alın](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>Son onay eylemini ekleme
1. **Onay başlat** eylemi ekleyip ardından bu eylemden bir tane daha yapılandırmak için daha önce uyguladığımız [Ön onaylar için onay eylemi ekleme](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) bölümündeki adımları uygulayın. Bu eylem son onay için bir e-posta isteği gönderir.
2. İşlemi tamamladığınızda kart şu görüntüdeki gibi olacaktır:
   
    ![Onayı yapılandırın](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>Son onay koşulunu ekleme
1. Son onaylayanın kararını kontrol edecek bir **Koşul** ekleyip yapılandırmak için [Koşul ekleme](sequential-modern-approvals.md#add-a-condition) bölümündeki adımları tekrar uygulayın.

## <a name="send-email-with-final-approval"></a>Son onayı içeren bir e-posta gönderme
1. Tatil istekleri onaylandığında e-posta gönderecek bir eylem ekleyip yapılandırmak için [Ön onaylar için e-posta eylemi ekleme](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) adımlarını uygulayın.
2. İşlemi tamamladığınızda kartınız şu görüntüdeki gibi olacaktır:
   
   ![Son onay e-posta şablonu](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>SharePoint'i onay ile güncelleştirme
1. Tatil isteği onaylandığında SharePoint'i güncelleştirecek bir eylem ekleyip yapılandırmak için [Önceden onaylanan istekler için güncelleştirme eylemi ekleme](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) bölümündeki adımları uygulayın.
2. İşlemi tamamladığınızda kart şu görüntüdeki gibi olacaktır:
   
    ![Öğeyi güncelleştir eylemini yapılandırın](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>Ön onay reddini içeren bir e-posta gönderme
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![Reddedilen istekler için yapılandırma](./media/sequential-modern-approvals/configure-rejected-email.png)

Not: Bu eylem, **Koşul** kartının altındaki **HAYIR İSE, HİÇBİR ŞEY YAPMA** dalına eklenmelidir.

## <a name="update-sharepoint-with-pre-approval-rejection"></a>SharePoint'i ön onay reddi ile güncelleştirme
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![Reddedilen istekler için SharePoint'i güncelleyin](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>Son reddi içeren bir e-posta gönderme
1. Tatil isteği, son onaylayan tarafından reddedildiğinde e-posta gönderecek bir eylem ekleyip yapılandırmak için [Ön onay reddini içeren bir e-posta gönderme](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) bölümündeki adımları uygulayın.
   
    Not: Bu eylem, **Koşul 2** kartının altındaki **HAYIR İSE, HİÇBİR ŞEY YAPMA** dalına eklenmelidir.
2. İşlemi tamamladığınızda kart şu görüntüdeki gibi olacaktır:
   
   ![Reddedilen istekler için yapılandırma](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>SharePoint'i son ret ile güncelleştirme
1. Tatil isteği, son onaylayan tarafından reddedildiğinde SharePoint'i güncelleyecek bir eylem ekleyip yapılandırmak için [SharePoint'i ön onay reddi ile güncelleştirme](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) bölümündeki adımları uygulayın.
2. İşlemi tamamladığınızda kart şu görüntüdeki gibi olacaktır:
   
   ![Öğeyi güncelleştir kartı](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. **Akışı güncelleştir**'e tıklayarak yaptığınız işlemleri kaydedin.
   
   ![Güncelleştir eylemini seçin](./media/sequential-modern-approvals/update.png)

Tüm adımları uyguladıysanız akışınız şu görüntüdeki gibi olacaktır:

![Akışa genel bakış](./media/sequential-modern-approvals/completed-flow.png)

Akışı oluşturduğumuza göre artık nasıl çalıştığını inceleyebiliriz.

## <a name="request-an-approval"></a>Onay isteği gönderme
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

İsteğiniz şu görüntüye benzer olacaktır:

![Tatil isteği](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>Bekleyen onay isteklerini görüntüleme
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>Bir isteği önceden onaylama
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>İsteği onaylama
Bir isteği onaylamak için uygulanacak adımlar [bir isteği önceden onaylamak](sequential-modern-approvals.md#pre-approve-a-request) için uygulanacak adımlarla aynıdır.

Not: Son onaylayan, tatil isteğini yalnızca istek önceden onaylandığında alır.

## <a name="reject-a-request"></a>Bir isteği reddetme
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>Ek bilgi
[Tek onaylayan modern onayları incelemesi](modern-approvals.md)

