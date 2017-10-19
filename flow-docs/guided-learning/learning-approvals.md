---
title: "Microsoft Flow ile Onay İstekleri | Microsoft Docs"
description: "Bir onay iş akışını yönetmek için Microsoft Flow’u nasıl kullanacağınızı öğrenin."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: o-pgEBW3fOI
courseduration: 14m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 049b713ed653ab5555e5f48f63e46cce7f3207ee
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="approval-requests"></a>Onay istekleri
Microsoft Flow **Bildirim alma**, **dosya kopyalama** ve **veri toplama** konularına ek olarak **onay sürecinizi sorunsuz hale getirme** konusunda da size yardımcı olabilir.

## <a name="vacation-scenario"></a>Tatil senaryosu
Bir takımın **yöneticisi** olduğunuzu ve çalışanlarınızdan bir **SharePoint listesinde** **tatil istekleri** oluşturmasını istediğinizi varsayalım. Şimdi yeni tatil isteklerinin **hızla işlenmesi** ve istekte bulunan kişinin **otomatik olarak bilgilendirilmesi** için bu liste öğelerini temel alan bir **onay süreci** oluşturmak istiyorsunuz.  

## <a name="sharepoint-and-microsoft-flow"></a>SharePoint ve Microsoft Flow
**SharePoint**, Microsoft Flow’a **yerleşik** olarak sahiptir.  **SharePoint listenizden** **Akış** açılır menüsüne ve ardından **Akış oluştur**’a tıklayın.

![Akış oluşturma](./media/learning-approvals/new-flow.png)   

**Sağdaki menüden** bunun gibi bir **şablon** bulun.

![Onay Şablonu](./media/learning-approvals/approval-template.png)

## <a name="using-the-template"></a>Şablonu kullanma
Şablondaki **SharePoint** tetikleyicisi, liste bilgilerinizle **önceden doldurulmuş** olarak sağlanır.  Tek yapmanız gereken, **onaylayıcı** için bir **e-posta adresi** eklemektir.  Bu işlemin **özgün SharePoint öğesini değiştirmediğini** unutmayın.  Öğeyi değiştirmek için **SharePoint - Öğeyi güncelleştir** eylemini eklememiz gerekir.

![Öğeyi güncelleştir](./media/learning-approvals/update-item.png)

Peki *Send emailScope* ’un **if no** dalı ne işe yarar?  Varsayılan olarak hiçbir şey yapmaz.  İstek yazarına isteğin reddedildiğini belirten bir ileti göndermek için bir eylem eklemek isteyebilirsiniz. 

![If no](./media/learning-approvals/if-no.png)

## <a name="next-lesson"></a>Sonraki ders
Şimdi bu bölümde öğrendiklerimizi gözden geçirelim.

