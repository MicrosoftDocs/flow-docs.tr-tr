---
title: Birden çok onaylayanla modern bir onay iş akışı oluşturma | Microsoft Docs
description: 'Birden çok onaylayanla modern bir onay iş akışı oluşturma '
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 269239bd3fbb07c78bf316f9e58003690c63d878
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548975"
---
# <a name="manage-sequential-approvals-with-microsoft-flow"></a>Microsoft Flow ile sıralı onayları yönetme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Bazı iş akışları, son onaylayanın oturumu kapatmak için gerekli olan ön onay gerektirir. Örneğin, bir şirket, Finans Departmanı tarafından onaylanmadan önce $1000,00 üzerinde faturalar için ön onay gerektiren sıralı bir onay ilkesine sahip olabilir.

Bu kılavuzda, çalışan tatil isteklerini yöneten sıralı bir onay akışı oluşturacağız.

> [!NOTE]
> SharePoint burada yalnızca bir örnek olarak kullanılır; onay akışları oluşturmak gerekli değildir. Microsoft Flow 200 ' den fazla hizmetten istediğinizi kullanarak akışlarınızın akışını sağlayabilirsiniz.


## <a name="detailed-steps-in-the-flow"></a>Akıştaki ayrıntılı adımlar
Akış:

1. Bir çalışan bir [SharePoint Online listesinde](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7)tatil isteği oluşturduğunda başlar.
2. Tatil isteğini onay merkezine ekler ve ardından isteğin ön onaylayana e-posta ile gönderir.
3. Çalışana onay öncesi kararına e-posta ile gönderir.
4. SharePoint Online listesini, onaylayanın kararını ve açıklamalarını güncelleştirir.
   
   Note: istek önceden onaylanmışsa, akış şu adımlarla devam eder:
5. İsteği son onaylayana gönderir.
6. Çalışana son kararı e-posta ile gönderir.
7. SharePoint listesini son kararlarla güncelleştirir.

Bu görüntü, önceki adımları özetler:

   ![akışın Visio diyagramı](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>Kaynakları
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Bu izlenecek yolun amaçları doğrultusunda, oluşturduğunuz SharePoint Online listesinde şu sütunlar bulunmalıdır:

   ![SharePoint liste sütunları](./media/sequential-modern-approvals/sharepoint-columns.png)

SharePoint Online listesinin adını ve URL 'sini unutmayın. Bu öğeleri daha sonra SharePoint 'i yapılandırdığınızda, **Yeni bir öğe oluşturulduğunda** tetikler kullanıyoruz.

## <a name="create-your-flow-from-the-blank-template"></a>Boş şablondan akışınızı oluşturun
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Tetikleyici ekleme
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![SharePoint bilgileri](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Tatil isteğini oluşturan kişi için yöneticiyi al
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. Akışınız için bir ad girin ve ardından şu ana kadar yaptığımız işi kaydetmek için **akış oluştur** ' u seçin.
   
    ![akışı Kaydet](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > Akışınızdan değişiklikleri kaydetmek için ekranın en üstünden **akışı Güncelleştir** ' i seçin.
   > 
   > 
   
    ![Güncelleştirme eylemini seçin](./media/sequential-modern-approvals/update.png)

Her kaydetme işleminden sonra ekranın üst kısmından **akışı Düzenle** ' yi seçin ve sonra değişiklik yapmaya devam edin.

## <a name="add-an-approval-action-for-pre-approvals"></a>Ön onaylar için onay eylemi ekleme
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Note: Bu eylem, **atanan** kutusunda e-posta adresine ön onay isteğini gönderir.

## <a name="add-a-condition"></a>Koşul ekleme
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> Bu koşul, **bir onay başlatma** eyleminden yanıtı denetler.
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>Ön onaylar için e-posta eylemi ekleme
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![önceden onaylanmış e-posta şablonunu yapılandırma](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>Önceden onaylanan istekler için güncelleştirme eylemi ekleme
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![öğe yapılandırmasını Güncelleştir](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>Onaylayanın yöneticisini alın
1. Daha önce başka bir **yönetici al** eylemi eklemek ve daha sonra yapılandırmak için, daha önce bu [istekleri oluşturan kişi için yöneticiyi al](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) adımını kullanın. Bu süre, ön onaylayanın yöneticisini alırız.
2. İşiniz bittiğinde **yöneticiyi al 2** kartı bu görüntüye benzemelidir. **Bu akış kartında kullanılan uygulama ve hizmetlerden dinamik Içerik ekleme** Içindeki **yönetici al** kategorisinden **e-posta** belirtecini kullandığınızdan emin olun.
   
   ![ön onaylayanın yöneticisini al](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>Son onay eylemini ekleme
1. Daha önce eklemek ve ardından başka bir **onay eylemi başlatmak** için daha önce yaptığımız [Ön onaylar adımları için onay Ekle eylemini](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) kullanın. Bu eylem son onay için bir e-posta isteği gönderir.
2. İşiniz bittiğinde, kartın Şu görüntüye benzemesi gerekir:
   
    ![onayı yapılandırma](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>Son onay koşulunu ekleyin
1. Son onaylayanın kararını denetleyen bir koşul eklemek ve **ardından bir koşulu** [yapılandırmak için bu](sequential-modern-approvals.md#add-a-condition) adımları tekrarlayın.

## <a name="send-email-with-final-approval"></a>Son onay ile e-posta gönder
1. Tatil istekleri onaylandığında e-posta gönderen bir eylem eklemek ve daha sonra yapılandırmak için, [Ön onaylar için e-posta Ekle eyleminin](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) adımlarını kullanın.
2. İşiniz bittiğinde, kartınız şu görüntüye benzemelidir:
   
   ![son onay e-posta şablonu](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>SharePoint 'i onay ile Güncelleştir
1. Tatil isteği onaylandığında SharePoint 'i güncelleştiren bir eylem eklemek ve ardından yapılandırmak üzere [önceden onaylanan istekler için güncelleştirme ekleme işlemi](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) adımlarını kullanın.
2. İşiniz bittiğinde, kartın Şu görüntüye benzemesi gerekir:
   
    ![öğe yapılandırmasını Güncelleştir](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>Ön onay reddi ile e-posta gönderin
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![Reddedilen istekler için yapılandırma](./media/sequential-modern-approvals/configure-rejected-email.png)

Note: Bu eylem, **koşul** KARTıNıN altında **Hayır, hiçbir şey yapma** dalına eklenmelidir.

## <a name="update-sharepoint-with-pre-approval-rejection"></a>SharePoint 'i onay öncesi reddetme ile Güncelleştir
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![Reddedilen istekler için SharePoint 'i Güncelleştir](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>Son ret ile e-posta gönder
1. Tatil isteği son onaylayan tarafından reddedildiğinde e-posta gönderen bir eylem eklemek ve daha sonra yapılandırmak için, [ön onay reddetme ile e-posta gönderme](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) adımlarını kullanın.
   
    Note: Bu eylem, **Koşul 2** KARTıNıN altındaki **Hayır Ise, hiçbir şey yapma** dalına eklenmelidir.
2. İşiniz bittiğinde, kartın Şu görüntüye benzemesi gerekir:
   
   ![Reddedilen istekler için yapılandırma](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>Son ret ile SharePoint 'i Güncelleştir
1. Son onaylayan, tatil isteğini reddettiğinde SharePoint 'i güncelleştiren bir eylem eklemek ve ardından yapılandırmak için [SharePoint 'i ön onay reddi Ile güncelleştirme](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) adımlarını kullanın.
2. İşiniz bittiğinde, kartın Şu görüntüye benzemesi gerekir:
   
   ![öğe kartını Güncelleştir](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. Yaptığımız işi kaydetmek için **akışı Güncelleştir** ' i seçin.
   
   ![Güncelleştirme eylemini seçin](./media/sequential-modern-approvals/update.png)

Bunu takip ediyorsanız, akışınız Şu görüntüye benzemelidir:

![akışa genel bakış](./media/sequential-modern-approvals/completed-flow.png)

Flow 'u oluşturduğumuz artık bunu bir eylemde görlim.

## <a name="request-an-approval"></a>Onay isteyin
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

İsteğiniz şu resme benzemelidir:

![tatil isteği](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>Bekleyen onay isteklerini görüntüleme
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>Bir isteği önceden onaylama
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>İsteği Onayla
Bir isteği onaylama adımları, [bir isteği önceden onaylama](sequential-modern-approvals.md#pre-approve-a-request) adımlarıyla aynıdır

Note: Son onaylayan, tatil isteğini yalnızca istek önceden onaylandıktan sonra alır.

## <a name="reject-a-request"></a>İsteği reddetme
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>Daha fazla bilgi
[Tek onaylayan modern onaylar Kılavuzu](modern-approvals.md)

