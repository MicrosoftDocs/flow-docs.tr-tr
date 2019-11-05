---
title: OneDrive Iş başlatma panelinden akışlar oluşturun | Microsoft Docs
description: OneDrive Iş başlatma panelinden akışlar oluşturun.
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
ms.date: 08/25/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d7ed30741fcc85fea87f5be2d76a8150a0c42100
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548590"
---
# <a name="create-flows-from-the-onedrive-for-business-launch-panel"></a>OneDrive Iş başlatma panelinden akış oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

[SharePoint 'teki Microsoft Flow başlatma paneline](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/)benzer şekilde, OneDrive iş 'teki belirli dosyalardaki akışları çalıştırabilirsiniz. 

Bu özellik, akışı çalıştıran kişinin, özellikle bir BT departmanı tarafından oluşturulan akışlar için geçerli olan kendi kimlik bilgilerini kullanmasını sağlar. 

Kullanıcılar ayrıca, metin, dosya, e-posta, Boolean veya sayı türünde olabilecek, **onaylayan** veya **ileti**gibi çalışma zamanı girişleri için komut istemleri alabilir.

Bu kılavuzda, istek sahibinin Yöneticisi tarafından bir dosyanın onayını istemek için birçok [OneDrive iş şablonundan](https://flow.microsoft.com/search/?q=OneDrive) birini kullanan basit bir akış oluşturacağız.

## <a name="create-a-flow-that-requests-manager-approval-for-a-file-in-onedrive-for-business"></a>OneDrive Iş 'teki bir dosya için yönetici onayı isteyen bir akış oluşturun

1. OneDrive Iş 'te oturum açın.
1. Akışı oluşturmak istediğiniz dosyayı bulun ve seçin.
1. **Eylemleri göster** bağlantısını (üç nokta) seçin.
1. Flow ** > ** akış **Oluştur**' u seçin.

     ![akış oluştur](./media/onedrive-launch-panel/create-flow.png) 

1. Şablonlardan birini seçin.

    Bu örnekte, **Seçili dosya şablonu için yöneticinin onayını iste** ' yi seçin.

     >[!TIP]
     >Oturum açmanızı isteyen herhangi bir bağlayıcıda oturum açın.

1. **Devam**' ı seçin.
1. Şablonda istediğiniz değişiklikleri yapın ve ardından kolayca anımsayabileceğiniz bir adla akışınızı kaydedin.

## <a name="run-the-flow"></a>Akışı çalıştırma

1. OneDrive Iş 'te oturum açın.
1. İstek Yöneticisi onayının bulunduğu dosyayı bulun ve seçin.
1. **Eylemleri göster** bağlantısını (üç nokta) seçin.
1. **Flow**' u seçin. Daha önce oluşturduğunuz akışı görürsünüz.
1. Daha önce oluşturduğunuz akışı seçin.

     ![Akışınızı çalıştırın](./media/onedrive-launch-panel/run-flow.png)


>[!TIP]
>Bu kılavuzda, bir şablondan akışın nasıl oluşturulacağı gösterilmektedir. Ayrıca, Microsoft Flow ' de bulunan yüzlerce bağlayıcı arasından birini kullanmak için boş bir akış oluşturabilirsiniz.

## <a name="learn-more"></a>Daha fazla bilgi edinin

- [Microsoft Flow kullanmaya başlayın](getting-started.md) 
- [Çok adımlı akışlar oluşturun](multi-step-logic-flow.md)
