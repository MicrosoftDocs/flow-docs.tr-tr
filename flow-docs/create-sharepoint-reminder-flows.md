---
title: SharePoint öğeleri için anımsatıcı akışı oluşturma | Microsoft Docs
description: SharePoint öğelerinin son tarihini size anımsatan akışlar oluşturun.
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
ms.openlocfilehash: b0f1aa80fb92c9718d2b0697d3abb0b0d2478013
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65061124"
---
# <a name="sharepoint-remind-me"></a>SharePoint bana anımsat

SharePoint listeleri ve kitaplıkları tarihleri izlemek için özel meta veri sütunları tanımlamanıza olanak tanıyordu. Microsoft Flow'un SharePoint'le tümleştirilmesiyle, SharePoint'teki DateTime sütunları temelinde kolayca anımsatıcı akışları oluşturabilirsiniz. Anımsatıcı akışlarıyla, SharePoint'teki herhangi bir belge veya öğenin tarihinden belirlenen sayıda gün önce kişisel bir e-posta uyarısı alırsınız.

## <a name="prerequisites"></a>Önkoşullar
- Microsoft SharePoint Online'a erişim.
- DateTime sütunu olan bir SharePoint listesi veya kitaplığı.
- Microsoft Flow erişimi.

## <a name="create-a-reminder-flow"></a>Anımsatıcı akışı oluşturma

 1. Geçerli görünümde en az bir DateTime sütunu olan bir [SharePoint listesi](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) oluşturun. 
 1. **Akış** > **Anımsatıcı ayarla** > **Devre dışı bırakma tarihi** (bu anımsatıcı için DateTime değerini içeren sütun) öğesini seçin.

     ![Anımsatıcı akışı seçme](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. **Anımsatıcı ayarla** kartında bir **Akış adı** ve anımsatıcı uyarısını DateTime sütun girdisinden kaç gün önce almak istediğinizi belirtin.

    ![Anımsatıcı akışının ayrıntılarını ayarlama](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. **Anımsatıcı ayarla** kartında **Oluştur**'u seçin.

1. Akışın oluşturulduğunu belirten aşağıdaki iletiyi alırsınız:

    ![Anımsatıcı akışı oluşturuldu](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Anımsatıcıların alındığını onaylama

**Anımsatıcı ayarla** akışında daha önce oluşturduğunuz **Şu kadar gün önceden bana hatırlat** girdisi temelinde e-postayla bir anımsatıcı alırsınız. 

## <a name="edit-your-flow"></a>Akışınızı düzenleme

Anımsatıcı akışı da diğer akışlar gibidir, bu nedenle [Microsoft Flow](https://flow.microsoft.com) aracılığıyla bu akışa erişebilir ve bunu düzenleyebilirsiniz.

## <a name="learn-more"></a>Daha fazla bilgi

- [Microsoft Flow](https://flow.microsoft.com) ile çalışmaya başlama.
- SharePoint'te [anımsatıcı akışı](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) oluşturma.


