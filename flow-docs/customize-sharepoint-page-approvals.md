---
title: Microsoft Flow'la SharePoint sayfa onaylarını yönetme | Microsoft Docs
description: Microsoft Flow'la SharePoint sayfa onaylarını yönetmeyi öğrenin.
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
ms.openlocfilehash: d5e01a3d2e13cc48107e19e0e2bbea3821437273
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65061354"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>Microsoft Flow'la SharePoint sayfa onaylarını yönetme

SharePoint sitesi yöneticileri yeni veya güncelleştirilmiş site sayfalarının yayımlanmadan önce onaylanmasını istemek için Microsoft Flow'u kullanabilir.

Bu makalede SharePoint sitenizi, sitede yapılan değişikliklerin canlı yayına geçmeden önce onaylanmasını istemek için bir akış kullanacak şekilde yapılandırmayı öğreneceksiniz.

## <a name="configure-sharepoint-for-page-approvals"></a>Sayfa onayları için SharePoint'i yapılandırma

### <a name="prerequisites"></a>Önkoşullar 

Bu makaledeki etkinlikleri gerçekleştirmek için SharePoint sitesinin yöneticisi olmalısınız.

1. SharePoint'te site yöneticisi olarak oturum açın.
1. Gezinti çubuğundan **Sayfalar**’ı seçin.

    ![Sayfa onay akışını seçme](media/customize-sharepoint-page-approvals/pages.png)

1. **Akış**'ı ve ardından **Sayfa onay akışını yapılandır**'ı seçin.
    
    ![Sayfa onay akışını seçme](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. **Akış adı**'nı sağlayın, **Onaylayanlar** kutusuna en az bir ad girin ve **Oluştur**'ı seçin.
    
    ![Sayfa onay akışını seçme](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Hepsi bu! Artık her sayfa eklendiğinde veya değiştirildiğinde akışta listelediğiniz **Onaylayanlara** bir onay isteği gider.

Sayfa onay akışı aynı diğer akışlar gibidir; dolayısıyla **Akışlarım** sekmesinde listelenir.

![Sayfa onay akışını seçme](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Sayfayı onay için gönderme

Artık bir sayfa onay akışı oluşturduğunuza göre, sayfa ekleyen veya sayfayı değiştiren herkesin aşağıdakileri yapması gerekir:

 - Sitede bir değişiklik yapın (örneğin, yeni sayfa ekleyin) ve ardından değişikliği kaydedin.

     ![Sayfayı onay için gönderme](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Birinin bu değişikliği onaylamasını bekleyin.
    
    ![Sayfayı onay için gönderme](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Sayfayı onaylama

Her sayfa onay isteği söz konusu olduğunda onaylayanlar bir e-posta alır. İstekleri doğrudan e-postada onaylayabilecekleri gibi (e-posta istemcileri işlem yapılabilir iletileri destekliyorsa) veya e-postadaki sayfayı gözden geçirmek üzere açabilir sonra bu sayfayı SharePoint'te onaylayabilirler.

## <a name="customize-page-approval-flows"></a>Sayfa onay akışlarını özelleştirme

Sayfa onayları arka planda Microsoft Flow'u kullandığından, sayfa onay akışı site sahiplerinin akışta özel iş mantığını eklemelerine ve değiştirmelerine olanak tanır. Akışta değişiklik yapmak için site sahibi **Akışlar**'ı ve ardından sayfa kitaplığında **Akışlarınızı görün**'ü seçerek sayfa onay akışını bulabilir.

## <a name="learn-more"></a>Daha fazla bilgi

- [Sayfa onay akışı](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Sayfa onayını yapılandırma](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
