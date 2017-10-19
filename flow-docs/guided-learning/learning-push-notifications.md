---
title: "Bir akıştan tweet gönderme | Microsoft Docs"
description: "Bir SharePoint listesindeki verilere dayanarak nasıl tweet göndereceğinizi öğrenin."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: y1iDal8XPAo
courseduration: 15m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 4015377204edfde289cf04835b2660288d0690e1
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="post-tweets-from-a-flow"></a>Bir akıştan tweet gönderme
Bu akış için, **Contoso Flooring** Pazarlama ekibinin **Twitter gönderilerini** ve gönderme tarihlerini depolandığı bir **SharePoint** listesi oluşturacaksınız. Daha sonra, bunlara yönelik içeriği otomatik olarak Tweetleyen bir akış oluşturacaksınız. 

## <a name="connect-microsoft-flow-services"></a>Microsoft Flow Hizmetlerini Bağlama
Bu konu başlığında, **SharePoint** ve **Twitter** hizmetlerini kullanacaksınız. Daha önce kullanmadığınız bir hizmet söz konusuysa, önce yeni hizmete bağlanmanız gerekir. 

1. Microsoft Flow’da **dişli simgesini** ve ardından **Bağlantılar**’ı seçin,
   
    ![Bağlantı alma](./media/learning-push-notifications/2-get-connection.png) 
2. **+Bağlantı oluştur**’u seçin.
   
    ![Bağlantı oluşturma](./media/learning-push-notifications/3-create-connection.png) 
3. Listede aşağıda kaydırarak Twitter’ı bulun ve **+** öğesini bulun.
   
    ![Artı işaretine tıklayın](./media/learning-push-notifications/4-click-plus.png)
4. Bir Twitter hesabını yetkilendirmek için, kullanıcı adınız veya e-postanızı ve parolanızı girip **Uygulamayı yetkilendir**’i seçin.
   
    ![Kimlik ve parola oluşturma](./media/learning-push-notifications/5-create-id-pswd.png)
5. Bağlantılarınızı denetlemek için **dişli simgesini** ve **Bağlantılar**’ı seçin.
   
    ![Bağlantılarım](./media/learning-push-notifications/6-my-connections.png)
   
    Yeni Twitter bağlantınızı ve oluşturduğunuz diğer bağlantıları görmeniz gerekir. 
   
    ![Twitter bağlantısı](./media/learning-push-notifications/7-twitter-connection.png)

## <a name="build-a-sharepoint-list"></a>SharePoint listesi oluşturma
Öncelikle Contoso Flooring için yeni bir SharePoint Online listesi oluşturmanız gerekir. 

1. SharePoint Online’da **Yeni**’yi ve ardından **Liste**’yi seçin.
   
    ![Yeni liste oluşturma](./media/learning-push-notifications/1-new-list.png)
2. Listeyi **Contoso Tweetleri** olarak adlandırın. 
3. **Site gezintisinde göster** onay kutusunun işaretini temizleyip **Oluştur**’u seçin.
   
    ![Liste oluşturma](./media/learning-push-notifications/2-name-create-list.png)
   
    **Oluştur**’u seçtiğinizde SharePoint sizi yeni listenize götürür.
4. Varsayılan olarak, listede yalnızca **Başlık** sütunu bulunur. Başka bir sütun ekleyip bu sütunu **Tweet İçerikleri** olarak adlandırın. Tweetlerinizde söyleyecekleriniz buraya gelir. 
   
   1. Artı işaretini ve ardından **Daha fazla...**’yı seçin
      
       ![Liste oluşturma](./media/learning-push-notifications/3-add-more-column-types.png)
   2. **Birden çok satırlı metin**’i ve ardından **Tamam**’ı seçin.
      
       ![Liste oluşturma](./media/learning-push-notifications/4-add-column.png)
5. Tweet tarihi ve saati için bir sütun ekleyip **Tweet Tarihi** olarak adlandırın.
   
   1. Yukarıdaki **Tweet İçerikleri** ile aynı şekilde, artı işaretini ve ardından **Daha fazla...**’yı seçin
      
       ![Tarih ve saat sütunu](./media/learning-push-notifications/5-date-time-col.png)
   2. Aşağı kaydırarak **Tarih ve Saat Biçimi**’ne ilerleyin. Her ikisini de dahil etmek için **Tarih ve Saat**’i seçin.
      
       ![Tarih ve saat](./media/learning-push-notifications/6-date-time-must-do.png)
   3. **Tamam**’ı seçin. **Contoso Tweetleri** listesi SharePoint sitenizde görünür ve listeye yeni öğeler ekleyebilirsiniz.

## <a name="build-the-flow"></a>Akışı oluşturma
Listeniz oluşturulduğuna göre, artık akışı oluşturabilirsiniz.

### <a name="choose-a-trigger"></a>Tetikleyici seçme
1. Microsoft Flow’da **Akışlarım**’a gidip **Boş akış oluştur**’u seçin.
   
    ![Boş akış oluşturma](./media/learning-push-notifications/8-create-from-blank.png)
2. **Bir öğe oluşturulduğunda** seçeneğini belirleyin.
   
    ![Tetikleyici ekleme](./media/learning-push-notifications/9-add-trigger.png)
   
    Tetikleyicilerimizin tweet içeriği olan yeni bir satır eklendiğinde tetiklenmesini istiyoruz.
3. SharePoint sitenizi seçip ardından önceden ayarladığınız **Contoso Tweetleri** listesini seçin.
   
    ![Yeni öğe oluşturuldu](./media/learning-push-notifications/11-set-trigger.png)

Tetikleyici için gerçekleştirmeniz gereken işlemler bu kadar.

### <a name="add-an-action-to-delay-posting"></a>Gönderme geciktirmeye eylem ekleme
1. **+Yeni adım**’ı ve ardından **Eylem ekle**’yi seçin. 
   
    ![Adım ve eylem ekleme](./media/learning-push-notifications/12-add-step-and-action.png)
2. **Zamanlama** hizmeti bölümünde **Geciktir:**’i seçin. 
   
    ![Geciktir:](./media/learning-push-notifications/13-delay-until-schedule.png)  
3. Gecikme değerini ayarlayın.
   
   1. **Zaman damgası** alanına tıklayın veya dokunun. 
   2. Dinamik içerik kutusu açıldığında, aşağıya kaydırarak SharePoint listesindeki üç sütunu görebilirsiniz: **Başlık**, **Tweet Tarihi** ve **Tweet İçeriği**.
   3. **Tweet Tarihi**’ni seçin. 
      
       ![Zaman damgasına kadar geciktir](./media/learning-push-notifications/14-delay-until-timestamp.png)
      
       Artık bir kullanıcı SharePoint listenize bir öğe eklediğinde, eylemler **Tweet Tarihi** sütununda ayarladığınız tarih ve saate kadar geciktirilir.
      
       ![Dinamik zaman damgası](./media/learning-push-notifications/15-dynamic-timestamp.png)

### <a name="add-an-action-to-post-a-tweet"></a>Tweet göndermek için eylem ekleme
Şimdi akışın **Tweet Tarihi** sütununda belirtilen tarih ve saatte gerçekleştirmesi için başka bir eylem ekleyeceksiniz.

1. **+ Yeni adım**’ı ve **Eylem ekle**’yi seçip **Twitter**’ı arayın.
   
    ![Tweet ekleme](./media/learning-push-notifications/16-add-tweet.png) 
2. **Twitter - Tweet gönder** eylemini seçin.
   
    ![Tweet gönderme](./media/learning-push-notifications/17-post-tweet.png) 
3. **Tweet metni** alanına tıklayın veya dokunun ve dinamik içerik kutusunda **Tweet İçerikleri**’ni seçin. Oluşturduğunuz dizi şöyledir: 
   
    ![Tweet tarihi içeriği](./media/learning-push-notifications/18-tweet-date-content.png)
4. **Akış oluştur...**’u seçin
   
    ![Akış oluşturma](./media/learning-push-notifications/19-tiny-create.png) 
5. **Bitti**’yi seçin.
   
    ![Bitti’ye tıklayın](./media/learning-push-notifications/19-click-done.png)
   
    Akış tamamlanmıştır.
   
    ![Akış tamamlandı](./media/learning-push-notifications/20-flow-is-done.png)
   
    SharePoint listenizde yeni bir öğe oluşturulduğunda, akış önceden ayarlanan tarihe kadar göndermeyi geciktirir. Bu tarih geldiğinde, akış listenizdeki **Tweet İçeriği** sütunundaki metinle birlikte Twitter’a gönderir.

## <a name="next-lesson"></a>Sonraki ders
Sonraki derste, **Yineleme** adlı bir tetikleyiciyi kullanarak **akışları bir zamanlamaya göre çalıştırmayı** öğreneceksiniz.

