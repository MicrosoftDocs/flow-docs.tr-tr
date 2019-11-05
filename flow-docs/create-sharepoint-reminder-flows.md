---
title: SharePoint öğeleri için bir anımsatıcı akışı oluşturun | Microsoft Docs
description: SharePoint öğeleri için son tarihleri hatırlatan akışlar oluşturun.
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
ms.date: 04/30/2019
ms.author: deonhe
ms.openlocfilehash: c7c87df5288ba58d303de441b41e7493cd713f4a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547557"
---
# <a name="sharepoint-remind-me"></a>SharePoint bana anımsat
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

SharePoint listeleri ve kitaplıkları tarihleri izlemek için özel meta veri sütunları tanımlamanıza izin verildi. Microsoft Flow SharePoint ile tümleştirmeyle, SharePoint 'te Tarih Saat sütunlarına göre kolayca uyarı mektubu akışları oluşturabilirsiniz. Anımsatıcı akışlarla, SharePoint 'teki herhangi bir belge veya öğe için bir tarih önceden önceden belirlenen gün sayısı üzerinde, kişisel bir e-posta uyarısı alırsınız.

## <a name="prerequisites"></a>Kaynakları
- Microsoft SharePoint Online 'a erişin.
- Bir SharePoint listesi veya DateTime sütunu olan kitaplık.
- Microsoft Flow erişim.

## <a name="create-a-reminder-flow"></a>Anımsatıcı akışı oluşturma

 1. Geçerli görünümde en az bir DateTime sütunu olan bir [SharePoint listesi](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) oluşturun. 
 1. **Akış** > seçin > **tarihi devre dışı bırakıldı** (Bu sütun **, anımsatıcı için** tarih/saat olan sütundur).

     ![Anımsatıcı akışını seçin](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. **Bir anımsatıcı uyarısını bir anımsatıcı** olarak almak istediğinizde, bir **akış adı** ve tarih saat sütunu girişinden önceki gün sayısını girin.

    ![Anımsatıcı akış ayrıntılarını ayarla](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. **Anımsatıcı Kartı ayarla** sayfasında **Oluştur** ' u seçin.

1. Akışın oluşturulduğunu belirten aşağıdaki iletiyi alırsınız:

    ![Anımsatıcı akışı oluşturuldu](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Alınan anımsatıcıları Onayla

Daha önce oluşturduğunuz **bir anımsatıcı akış kümesi** üzerinde yaptığınız bir süre önce **Bu çok günde bana anımsat** ' ı kullanarak e-posta aracılığıyla bir anımsatıcı alacaksınız. 

## <a name="edit-your-flow"></a>Akışınızı düzenleme

Anımsatıcı akışı diğer akışlar gibidir, bu sayede [Microsoft Flow](https://flow.microsoft.com)aracılığıyla erişebilir ve düzenleyebilirsiniz.

## <a name="learn-more"></a>Daha fazla bilgi edinin

- [Microsoft Flow](https://flow.microsoft.com)kullanmaya başlama.
- SharePoint 'te bir [Anımsatıcı akışı](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) ayarlayın.


