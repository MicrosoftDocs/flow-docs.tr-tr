---
title: "Onay isteği oluşturma | Microsoft Docs"
description: "Belge ve işlemleri onaylanmasını nasıl yönetebileceğinizi öğrenin."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: 65yz8tqnWe0
courseduration: 4m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 265cab5029ca3166b5e12c42e2ec02730940d4f0
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="create-an-approval-request"></a>Bir onay isteği oluşturma
Önceki konu başlıklarından birinde, Twitter akışınızı bir SharePoint listesi ile basit bir şekilde nasıl güçlendirebileceğinizi öğrendiniz. Bu konu başlığında, onayları kullanarak işletme ortamına yönelik senaryolar oluşturmayı öğreneceksiniz. Bu sayede, SharePoint listesine erişimi olan herkes tweetlerle katkıda bulunabilir ve sosyal medya ekibi bu tweetleri onaylayabilir veya reddedebilir. Hesabın ve müşterilere gönderilen tweetlerin denetimi ekip tarafından yapılır. 

## <a name="create-an-approval-request-flow"></a>Bir onay isteği akışı oluşturma
1. **Microsoft Flow** giriş sayfasında önce **Onaylar** ve ardından **Onay akışı oluştur** seçeneğini belirleyip ardından aşağı kaydırarak **Onaydan sonra liste öğelerini Twitter’a gönder** şablonunu seçin. 
   
    ![Şablon seçme](./media/learning-approval-center/create-approval.png)
2. **SharePoint**, **Onaylar** ve **Twitter** için hesap kimlik bilgilerinizi doğrulayıp **Devam et**’i seçin. 
   
    ![Kimlik bilgilerini doğrulama](./media/learning-approval-center/verify-credentials.png)

Varsayılan olarak, bu şablon belirli bir listede yeni bir öğe oluşturulduğunda bir onay işlemi başlatır ve öğe onaylanırsa Twitter’a bir tweet gönderir. Bu konu başlığında, SharePoint listesini onay yanıtıyla güncelleştiren adımlar ekleyip öğenin onaylanıp onaylanmadığını belirterek ve onaylayanın önerilen tweete eklemiş olabileceği açıklamaları ekleyerek bu işlemi değiştireceksiniz. 

1. Önceden oluşturduğunuz **ContosoTweets** SharePoint listesine iki yeni sütun ekleyin:
   
   1. Artı işaretini “**+**” ve ardından **Evet/Hayır**’ı seçin
   2. **ApprovalStatus** yazıp **Oluştur**’u seçin
   3. Artı işaretini “**+**” ve ardından **Tek satır metin**’i seçin
   4. **ApproverComments** yazıp **Kaydet**’i seçin
      
      ![Sütun ekleme](./media/learning-approval-center/new-columns.png)
2. **Microsoft Flow**’a dönün ve **Yeni bir öğe oluşturulduğunda** eyleminde aşağıdaki değerleri girin:
   
   * **Site Adresi**: Ekibinizin SharePoint URL’si
   * **Liste Adı**: ContosoTweets
     
     ![Site ve liste](./media/learning-approval-center/site-address.png)
3. **Bir onay işlemi başlat** eyleminde, tüm alanları görüntülemek için **Düzenle**’yi seçin. 
   
    ![Alanları düzenleme](./media/learning-approval-center/edit-all-fields.png)
4. **Başlık** alanında, **Şunun için yeni tweet** yazın ve dinamik içerik listesinden **Başlık**’ı seçin. 
   
    ![Başlık](./media/learning-approval-center/tweet-title.png)
5. **Atanan** alanında, adınızı veya bir test kullanıcısı adını girin ve seçin. 
   
    ![Atanan](./media/learning-approval-center/tweet-assigned-to.png)
6. **Ayrıntılar** alanında, varsayılan öğeleri kaldırıp dinamik içerik listesinde **TweetContent**, **TweetDate** ve **Created by DisplayName** öğelerini **tarihinde** ve **tarafından** sözcükleriyle birleştirilmiş olarak ekleyin. 
   
    ![Ayrıntılar](./media/learning-approval-center/tweet-details.png)
7. **Öğe Bağlantısı** alanında, SharePoint listenizin URL’sini kopyalayıp yapıştırın ve **Öğe Bağlantısı Açıklaması** alanında **Contoso Tweet List** değerini girin. 
   
    ![Öğe bağlantısı](./media/learning-approval-center/tweet-item-link.png)
8. **Koşul** eyleminde, **EVET İSE** kutusunun üzerinde gelin, artı işaretini “**+**” seçin ve **Eylem ekle**’yi seçin. 
   
    ![Eylem ekleme](./media/learning-approval-center/add-an-action.png)
9. **Güncelleştirilmiş öğe** ifadesini arayın, **SharePoint** bağlayıcısını seçin ve **SharePoint - Öğeyi güncelleştir** eylemini seçin.
   
    ![SharePoint öğesini güncelleştirme](./media/learning-approval-center/update-item.png)
10. **Site Adresi** ve **Liste Adı** alanına sitenizin URL’siyle **ContosoTweets** listesini tekrar girin ve **Kimlik** alanına dinamik içerik listesindeki **Kimlik** değerini girin. 
    
     ![Site, liste ve kimlik](./media/learning-approval-center/address-list-id.png)
11. **Başlık** alanını seçin ve dinamik içerik listesinde **başlık** ifadesini arayın. **Yeni bir öğe oluşturulduğunda** eyleminden **Başlık** öğesini ekleyin. 
    
     ![Yeni başlık](./media/learning-approval-center/add-title.png)
12. **ApprovalStatus** alanını seçin ve değeri **Evet** olarak ayarlayın. Sonra **ApproverComments** alanını seçip dinamik içerik listesinden değeri **Açıklamalar** olarak ayarlayın. 
    
     ![Durum ve açıklamalar](./media/learning-approval-center/approver-status.png)
13. **HAYIR İSE, *HİÇBİR ŞEY YAPMA*** kutusunun altında **Eylem ekle**’yi seçin.
    
     ![Hayır eylemi ekleme](./media/learning-approval-center/add-a-no-action.png)
14. **EVET İSE** yapılandırması için kullandığınız adımları kullanarak bir **SharePoint - Öğe güncelleştirme** eylemi oluşturun ve **ApprovalStatus** alanı için **Hayır** değerini ayarlayıp bunun dışındaki diğer alanları aynı biçimde yapılandırın. 
    
     ![Durum = hayır](./media/learning-approval-center/status-no.png)
15. **Tweet at** eylemini ve ardından **Düzenle**’yi seçin ve **Tweet metni**’ni dinamik içerik listesinden **TweetContent** olarak ayarlayın.  Çalışmanızı kaydetmek için sayfanın en üstündeki **Akış oluştur**’u seçin. 
    
     ![Gönderme ve kaydetme](./media/learning-approval-center/post-tweet.png)

Bu, Microsoft Flow’un ekibinizin üretkenliğini artırmasının yalnızca bir yoludur. Ekibiniz fikirler, ilgili haberler veya ürün rehberliği ile katkıda bulunabilir ve nelerin müşterilere tweetleneceğini siz denetlersiniz.

Sonraki konumuzda, bir onaylayanın önerilen bir tweet için yeni bir istek aldığında neler yapabileceğini öğreneceğiz. 

