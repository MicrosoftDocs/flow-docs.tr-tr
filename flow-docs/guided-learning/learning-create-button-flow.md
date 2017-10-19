---
title: "Düğme akışı oluşturma | Microsoft Docs"
description: "Bir düğmeyle tetiklenen bir akış oluşturmayı öğrenin."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: s8ozmlVRV-Q
courseduration: 11m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: e72013611d6dbd21c06716805d42fbdd4eff7cfc
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-button-flow"></a>Düğme akışı oluşturma
Bu konu başlığında, Contoso Flooring Company için **bir düğme akışı oluşturmayı** öğreneceksiniz. 

Düğme akışları bir ekibe **e-posta göndermek** ve gerçekleştirilecek **görevleri bildirmek** için kullanılabilir. Akışların **sahipliği** **bir çalışana atanabilir** veya bir ekipteki **birden çok üye tarafından paylaşılabilir**.  

1. Öncelikle [Microsoft Flow web sitesine](https://ms.flow.microsoft.com) gidip oturum açın.
2. Oturum açma tamamlandıktan sonra, **Akışlarım**’ı ve ardından **Boş akış oluştur**’u seçin.
   
    ![Boş akış oluşturma](./media/learning-create-button-flow/2-create-from-blank.png)
   
    Öncelikle bir tetikleyiciye ihtiyacınız olacak. Düğme akışı, bu durumda uygun bir seçenektir. 
3. Listenizde yoksa, sayfanın altında **Yüzlerce bağlayıcı ve tetikleyiciyi arayın**’ı seçip **düğme** yazarak bulabilirsiniz. 
4. **Mobil için akış düğmesi**’ni seçin.
   
    ![Arama düğmesi](./media/learning-create-button-flow/3-button-flow.png) 
5. **Mobil için akış düğmesi - El ile bir akış tetikleme**’yi seçin.
   
    ![El ile tetikleyici seçin](./media/learning-create-button-flow/4-press-it.png)
6. Girdi ekranında, **Girdi metni ekle**’yi seçin,
   
    ![Girdi ekleme](./media/learning-create-button-flow/5-add-input.png)
7. İlk metin kutusuna **Contoso Flooring** ve ikinci metin kutusuna **Ambar teslim e-postası** yazın.
   
    ![Girdi ekleme](./media/learning-create-button-flow/6-text-for-flow.png)
8. **Yeni adım**’ı seçin. 
   
    ![Girdi metni](./media/learning-create-button-flow/7-input-description.png)
9. **Eylem ekle**'yi seçin. 
   
    ![Eylem ekleme](./media/learning-create-button-flow/8-add-an-action.png)
10. **Office 365 Outlook** bağlayıcısını seçin. Yoksa, **outlook** sözcüğünü arayın.
    
     ![Outlook’u arama](./media/learning-create-button-flow/9-search-outlook.png)
11. **Office 365 Outlook - E-posta gönder**’i seçin.
    
     ![E-posta gönderme](./media/learning-create-button-flow/10-send-email.png)
    
     Düğmeye basıldığında tüm Contoso Ambar ekibine, binanın neresinde oldukları fark etmeksizin, teslimatın alındığını bildiren bir e-posta gönderilir.
12. Alanları genişletin ve e-postayı Contoso Flooring için özelleştirin.
    
    1. **Alıcı** alanına kuruluşunuzda geçerli bir e-posta adresi girin.
    2. **Konu** alanına **Teslimat Alındı** yazın. 
    3. Sağ tarafta bir **Dinamik içerik** kutusunun açıldığını fark edeceksiniz. Konu satırında düğmeye basılma tarihi ve saatini göstermek için **Tarih** ve **Zaman damgası**’nı seçin. 
       
        ![E-posta tarih saati](./media/learning-create-button-flow/11-email-date-time.png)
13. Şimdi, e-posta için **Ambar Ekibi, bugünkü teslimat alınmıştır. Lütfen yük boşaltma alanına gelin** gibi basit bir **Gövde** girin.
14. Akışı kaydetmek için **Akış oluştur**’u seçin.
    
     ![Akış oluşturma](./media/learning-create-button-flow/12-create-flow.png)

## <a name="create-a-team-flow"></a>Takım akışı oluşturma
Bu düğme akışını bir ekip akışı oluşturmak için örnek olarak kullanabilirsiniz. Ya bu akışı oluşturan kişi hastalık nedeniyle şirket dışındaysa? Ya şirketten ayrılırsa? Bu akışın çalışmaya devam ettiğinden emin olmanız gerekir. Bunu yapmak için ikincil sahipler ekleyin.

1. İkincil sahip eklemek için akışınızda **ekip simgesini** seçin.
   
    ![Ekip akışı oluşturma](./media/learning-create-button-flow/13-create-team-flow.png) 
2. İkincil sahip eklemek için ad, e-posta adresi veya kullanıcı grubu girin.
   
    ![İkincil sahip ekleme](./media/learning-create-button-flow/14-add-co-owners.png)
3. İkincil sahipleri kaldırmak için, adlarının yanındaki çöp kutusu simgesini seçin.
   
    ![İkincil sahipleri kaldırma](./media/learning-create-button-flow/15-remove-co-owners.png)
4. Kaldırma işlemini tamamlamak için **Bu sahibi kaldır**’ı seçin.
   
    ![İkincil sahipleri kaldırma](./media/learning-create-button-flow/16-agree-to-remove.png)

## <a name="summary"></a>Özet
Bu derste, **düğme akışı oluşturmayı** öğrendiniz. 

Akış, bir ambar çalışanının dakikalar içinde bir **teslimatı** **ekibine bildirmesini** sağladı ve böylece ekip diğer görevlere ayırabileceği zamanı bekleyerek harcamamış oldu. 

Çalışan daha sonra kendisi olmadığında diğer kullanıcıların aynı akışı tetikleyebilmesi için bu düğmeyi ekibiyle paylaştı.

## <a name="next-lesson"></a>Sonraki ders
**Anında iletme bildirimlerini** kullanan bir akış oluşturmak için sonraki derse göz atın.

