---
title: "Bir onay isteğini işleme | Microsoft Docs"
description: "Onay isteklerini onaylamayı veya reddetmeyi öğrenin."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: -0r5ZKVEIS4
courseduration: 7m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 6ba7a2cf0fae481457f965627ebf523f063af50d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="process-an-approval-request"></a>Bir onay isteğini onaylama
Önceki konulardan birinde, bir SharePoint listesinde depolanan tweetler için bir onay işlemi oluşturmayı öğrendiniz.  Bu konu başlığında, bir onaylayan yeni bir onay isteği aldığında, bu deneyimin nasıl göründüğünü öğreneceksiniz. 

## <a name="create-and-process-a-request"></a>İstek oluşturma ve işleme
Öncelikle SharePoint listemize bir öğe eklememiz gerekiyor, daha sonra bu öğe için bir onay isteği işleyebiliriz.

1. Önceki konulardan birinde yapılandırılan **ContosoTweets** SharePoint listesini açın.  Yeni bir tweet oluşturmak için **Yeni**’yi seçin. 
   
    ![SharePoint listesi](./media/learning-approval-request/sharepoint-list-home.png)
2. Alanlara aşağıdaki değerleri ekleyip **Kaydet**’i seçin.
   
   * **Başlık** - Tanıtımlar
   * **TweetContent** - Yeni Contoso Flooring serisine göz atın #ohsocontoso
   * **TweetDate** - Bugünün tarihi
     
     ![SharePoint yeni öğe](./media/learning-approval-request/sharepoint-new-tweet.png)
3. **Microsoft Flow**’da **Akışlarım**’ı seçin. 
4. Önceki konu başlıklarından birinde yapılandırılan **Liste öğelerini onay sonrasında Twitter’a gönder** akışını seçin ve ardından **ÇALIŞTRMA GEÇMİŞİ** altında çalışan akışı seçin.
   
    ![Çalıştırma geçmişi](./media/learning-approval-request/run-history.png)
5. **Yeni bir öğe oluşturulduğunda** tetikleyicisini seçin. Yeni oluşturduğunuz liste öğesine ilişkin bilgilerin görüntülendiğini doğrulayın.
   
    ![Akış tetikleyici](./media/learning-approval-request/approval-flow.png)
6. **Outlook** posta kutusunda otomatik onay postasını açın ve **Onayla**’yı seçin. 
   
    ![Outlook isteği](./media/learning-approval-request/outlook-mail.png)
7. **Onay Merkezi**’nde istek ayrıntılarını görüntüleyin, açıklama ekleyin ve **Onayla**’yı seçin. 
   
    ![Onay merkezi](./media/learning-approval-request/approval-center.png)
8. **SharePoint**’te **ContosoTweets** listesini yenileyin ve **ApprovalStatus** değerinin **Evet** olduğunu ve girdiğiniz açıklamanın görüntülendiğini onaylayın. 
   
    ![SharePoint listesini yenileme](./media/learning-approval-request/sharepoint-list-approved.png)

Bu konu başlığında, bir onay isteği e-postası almadan Onay Merkezi’nde isteği işlemeye kadar geçen süreci bir onaylayanın açısından gördünüz.

