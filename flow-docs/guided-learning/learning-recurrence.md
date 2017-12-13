---
title: "Zamanlanan akışlar oluşturma | Microsoft Docs"
description: "Bir zamanlamaya göre çalışan akışlar oluşturmayı öğrenin."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: hh4nmS_M8Co
courseduration: 9m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 85c145364d684b5f91bc9f3bc7d1651f061f29d3
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="create-scheduled-flows"></a>Zamanlanan akışlar oluşturma
Bu konu başlığında, **Yinelenme** olarak adlandırılan bir tetikleyici kullanarak önceden zamanlanmış akışlar çalıştırmayı öğreneceksiniz.  Contoso pazarlama ekibi için bir Excel tablosundan müşteri e-posta adreslerini otomatik olarak OneDrive’a alan bir akış oluşturacaksınız. Akışı günde bir kez elektronik tabloya eklenen yeni e-posta adreslerini bir MailChimp müşteri listesine ekleyecek şekilde yapılandıracaksınız. 

## <a name="create-a-scheduled-flow"></a>Zamanlanan akış oluşturma
1. **Microsoft Flow**’u açın, **Akışlarım**’ı seçin ve **Boş akış oluştur**’u seçin. 
   
    ![](./media/learning-recurrence/flow-create-blank.png)
2. **Yüzlerce bağlantı ve tetikleyiciyi arayın** seçeneğini belirleyin.
3. **Zamanlama** hizmetini arayıp seçin ve sonra **Zamanlama - Yinelenme** tetikleyicisini seçin.
   
    ![](./media/learning-recurrence/flow-recurrence-trigger.png)
4. **Sıklık** değerini **Gün** ve **Aralık** değerini **1** olarak ayarlayın. **Yeni adım**’ı ve **Eylem ekle**’yi seçin. 
   
    ![](./media/learning-recurrence/frequency-interval.png)
5. **Excel** sözcüğünü arayıp **Excel** hizmetini seçin ve daha sora **Excel - Satırları Al** eylemini seçin. 
   
    ![](./media/learning-recurrence/excel-get-rows.png)
   
    **Not**: **Satırı al** değil **Satırları al** seçeneğini belirlediğinizden emin olun. 
6. **Dosya adı**’nı seçin ve dosyanızın olduğu konuma gidin. **Tablo adı**’nı seçin ve elektronik tabloda istediğiniz tabloyu seçin. 
   
    ![](./media/learning-recurrence/excel-get-file.png)
7. Yeni bir eylem ekleyin. 
   
    ![](./media/learning-recurrence/new-step.png)
8. **MailChimp** hizmetini arayın, daha sonra **MailChimp - Üyeyi listeye ekle** eylemini seçin.
   
    ![](./media/learning-recurrence/select-mailchimp.png)
   
    **Not:** MailChimp *premium* bir bağlayıcıdır. Microsoft Flow lisansınıza bağlı olarak, bu bağlayıcıyı kullanmak için bir denemeye kaydolmanız gerekebilir.
9. Açılır menülerden **Liste Kimliği** ve **Durum** alanlarını ekleyin:
   
   * **Liste Kimliği** - İstediğiniz MailChimp posta listesini seçin
   * **Durum** - **Abone**’yi seçin 
     
     ![](./media/learning-recurrence/mailchimp-id-status.png)
10. **E-posta Adresi**’nde, **ContactEmail** alanını eklemek için dinamik içerik özelliğini kullanın. 
    
     ![](./media/learning-recurrence/mailchimp-address.png)
    
     Akışın otomatik olarak ek bir adım oluşturduğunu görürsünüz. Akış ek bir eylem gerektiren bir eylem ayarlayacağınızı algılar. Akış yeni bir e-posta adresi okuduğunda, her satır için yeni bir eylem de oluşturur. 
    
     ![](./media/learning-recurrence/mailchimp-for-each.png)
11. **Ad** ve **Soyadı** alanlarını doldurmak için dinamik içeriği kullanın:
    
    * **Ad** – FirstName
    * **Soyadı** – LastName
      
      ![](./media/learning-recurrence/mailchimp-names.png)

Artık bu akış günde bir kez çalışarak bu Excel tablosundan yeni satırları ve e-posta adresi ile adı alır ve bunları MailChimp Contoso posta listesini doldurmak için kullanarak zaman ve paradan tasarruf etmenize yardımcı olur. 
