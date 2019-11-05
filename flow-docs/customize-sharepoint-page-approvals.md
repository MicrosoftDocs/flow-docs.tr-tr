---
title: SharePoint sayfa onaylarını Microsoft Flow yönetme | Microsoft Docs
description: Microsoft Flow ile SharePoint sayfa onaylarını yönetmeyi öğrenin.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 1b328b604f9b199c2303dde3a0aa00898f188ada
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547645"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>SharePoint sayfa onaylarını Microsoft Flow yönetme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

SharePoint site yöneticileri, yeni veya güncelleştirilmiş Site sayfalarının yayımlanmadan önce onaylanmasını gerektirmek için Microsoft Flow kullanabilir.

Bu makalede, SharePoint sitenizi, canlı çalışmadan önce sitede değişiklik yapılmasını gerektirmek üzere bir akış kullanmak üzere nasıl yapılandıracağınızı öğreneceksiniz.

## <a name="configure-sharepoint-for-page-approvals"></a>SharePoint 'i sayfa onayları için yapılandırma

### <a name="prerequisites"></a>Kaynakları 

Bu makaledeki etkinlikleri gerçekleştirmek için bir SharePoint site yöneticisi olmanız gerekir.

1. SharePoint 'te bir site yöneticisi olarak oturum açın.
1. Gezinti çubuğundan **Sayfalar** ' ı seçin.

    ![Sayfa onay akışını seçin](media/customize-sharepoint-page-approvals/pages.png)

1. **Flow** ' u ve ardından **sayfa onay akışını Yapılandır**' ı seçin.
    
    ![Sayfa onay akışını seçin](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. **Onaylayanlar** kutusuna bir **akış adı**, en az bir ad girin ve ardından **Oluştur**' u seçin.
    
    ![Sayfa onay akışını seçin](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

İşte bu kadar! Artık bir sayfa eklendiğinde veya değiştirildiğinde, bir onay isteği akışta listelenen **onaylayanlara** gider.

Sayfa onay akışı tıpkı diğer akışlara benzer, bu nedenle **Akışlarım** sekmesinde listelenir.

![Sayfa onay akışını seçin](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Bir sayfayı onaya gönder

Artık bir sayfa onay akışı oluşturduğunuza göre, bir sayfayı ekleyen veya değiştiren herkesin şunları yapması gerekir:

 - Sitede bir değişiklik yapın (örneğin, yeni bir sayfa ekleyin) ve değişikliği kaydedin.

     ![Sayfayı onaya gönder](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Birisinin değişikliği onaylamasını bekleyin.
    
    ![Sayfayı onaya gönder](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Bir sayfayı onaylama

Onaylayanlar bir sayfa onay isteği olduğunda bir e-posta alır. İstekleri doğrudan e-postada onaylayabilir (e-posta istemcisi uygulanabilir iletileri destekliyorsa) veya gözden geçirmek için e-postadaki sayfayı açıp SharePoint 'teki sayfayı onaylayabilir.

## <a name="customize-page-approval-flows"></a>Sayfa onay akışlarını özelleştirme

Sayfa onayları arka planda Microsoft Flow kullandığından, sayfa onay akışı site sahiplerinin, akışta özel iş mantığını değiştirmek ve eklemek için kullanılabilir. Akışı değiştirmek için, site sahibi **akışları** seçebilir ve ardından sayfa onay akışını bulmak için sayfalar kitaplığındaki **akışlarınızı görüntüleyin** ' i seçin.

## <a name="learn-more"></a>Daha fazla bilgi edinin

- [Sayfa onay akışı](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Sayfa onayını yapılandırma](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
