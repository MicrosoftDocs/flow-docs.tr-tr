---
title: "Akış oluşturarak görevleri otomatik hale getirme | Microsoft Docs"
description: "Bir veya daha fazla eylem (örneğin, bir kullanıcının SharePoint listesine satır eklemesi gibi olaylar oluştuğunda otomatik olarak e-posta gönderilmesi) gerçekleştiren bir akış oluşturun."
services: 
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/28/2017
ms.author: deonhe
ms.openlocfilehash: fd6ed3973ed09442108bf780f76b750deea20eeb
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-in-microsoft-flow"></a>Microsoft Flow'da akış oluşturma
<iframe width="560" height="315" src="https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

Bir olay tarafından tetiklendikten sonra otomatik olarak bir veya daha fazla görev gerçekleştiren bir akış oluşturun. Örneğin, bir kullanıcı belirttiğiniz anahtar sözcüğü içeren bir tweet attığında size bunu e-posta yoluyla bildiren bir akış oluşturun. Bu örnekte tweet atmak bir olay, e-posta göndermek ise eylemdir.

## <a name="prerequisites"></a>Önkoşullar
* [flow.microsoft.com](https://flow.microsoft.com)'da bir hesap
* Twitter hesabı
* Office 365 kimlik bilgileri

## <a name="specify-an-event-to-start-the-flow"></a>Akışı başlatmak için bir olay belirtin
İlk olarak akışınızın hangi olay veya *tetikleyici* tarafından başlatılacağını seçmeniz gerekir.

1. [Flow.microsoft.com](https://flow.microsoft.com)'da, üst gezinti çubuğunda bulunan **Akışlarım**'ı ve ardından **Boş akış oluştur**'u seçin.
   
    ![Sol gezinti çubuğundaki Akışlar seçeneği](./media/get-started-logic-flow/create-logic-flow.png)
2. **Tüm bağlayıcılar ve tetikleyiciler içinde arayın** yazılı kutuya **Twitter** yazın veya bu ifadeyi yapıştırın, sonra **Twitter - Yeni bir tweet gönderildiğinde**’yi seçin.
   
    ![Twitter olayı](./media/get-started-logic-flow/twitter-search.png)
3. Twitter hesabınızı Microsoft Flow'a henüz bağlamadıysanız **Sign in to Twitter**'ı (Twitter'da oturum aç) seçin ve ardından kimlik bilgilerinizi sağlayın.
   
    ![Twitter'da oturum açma](./media/get-started-logic-flow/twitter-signin.png)
4. **Arama metni** kutusuna bulmak istediğiniz anahtar sözcüğü yazın.
   
    ![Twitter anahtar sözcüğü](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Eylem belirtme
1. **Yeni adım**'ı ve ardından **Eylem ekle**'yi seçin.
   
    ![Eylem ekleme](./media/get-started-logic-flow/add-action-icon.png)
2. **Tüm bağlayıcılar ve eylemler içinde arayın** yazılı kutuya **e-posta gönder** yazın veya bu ifadeyi yapıştırın, sonra **Office 365 Outlook - E-posta gönder**’i seçin.
   
    ![Eylemler listesi](./media/get-started-logic-flow/send-email.png)
3. İstenirse Oturum aç düğmesini seçin ve ardından kimlik bilgilerinizi sağlayın.
4. Görüntülenen formdaki **Kime** kutusuna e-posta adresinizi yazın veya yapıştırın, ardından görüntülenen kişiler listesinden adınızı seçin.
   
    ![Boş e-posta iletisi](./media/get-started-logic-flow/blank-email.png)
5. **Konu** kutusuna **Şuradan yeni tweet:** yazın veya yapıştırın ve ardından boşluk bırakın.
   
    ![Yer tutuculu konu satırı](./media/get-started-logic-flow/message-token.png)
6. Belirteçler listesinde, **Tweet’leyen** belirtecini seçerek bu belirteç için bir yer tutucu ekleyin.
   
    ![Parametre ekleme](./media/get-started-logic-flow/add-parameter.png)
7. **Gövde** kutusuna tıklayın veya dokunun ve sonra **Tweet metni** belirtecine tıklayarak ya da dokunarak bu parametre için bir yer tutucu ekleyin.
8. (isteğe bağlı) E-postanın gövdesine daha fazla belirteç, başka içerik veya her ikisini birden ekleyin.
9. Ekranın üst kısmında akışınıza bir ad verin ve ardından **Akış oluştur**'u seçin.
   
    ![Akış oluştur düğmesini seçme](./media/get-started-logic-flow/create-button.png)
10. Akışlarınızın listesini güncelleştirmek için **Bitti**’yi seçin.
    
     ![Bitti düğmesini seçme](./media/get-started-logic-flow/done-button.png)
11. Belirttiğiniz anahtar sözcüğün bulunduğu bir tweet gönderin.
    
     Bir dakika içinde, bir e-posta iletisi bu yeni tweet'i size bildirir.

## <a name="manage-a-flow"></a>Akışı yönetme
1. [flow.microsoft.com](https://flow.microsoft.com)'da, üst gezinti çubuğunda bulunan **Akışlarım**'ı seçin.
2. Akışlar listesinde, şunlardan herhangi birini yapabilirsiniz:
   
   * Bir akışı duraklatmak için akışı**Kapalı** konumuna getirin.
     
       ![Akışı duraklatma](./media/get-started-logic-flow/pause-flow.png)
   * Bir akışı sürdürmek için akışı **Açık** konumuna getirin.
     
       ![Akışı sürdürme](./media/get-started-logic-flow/resume-flow.png)
   * Bir akışı düzenlemek için, düzenlemek istediğiniz akışa ait kalem simgesini seçin.
     
       ![Akış seçme](./media/get-started-logic-flow/select-flow.png)
   * Bir akışı silmek için **...** simgesini seçip **Sil**’i seçin ve görüntülenen ileti kutusunda **Sil**’i seçin.
     
       ![Sil simgesi](./media/get-started-logic-flow/delete-icon.png)
   * Bir akışın çalıştırma geçmişini görüntülemek için **Akışlarım** sayfasından akışı seçin ve açılan sayfanın **ÇALIŞTIRMA GEÇMİŞİ** bölümündeki geçmişi görüntüleyin.
     
       ![çalıştırma geçmişi](./media/get-started-logic-flow/run-history.png)
     
     Her adımın giriş ve çıkışlarını görmek için çalıştırmalar listesinden bir akış çalıştırması seçin.

**Not**: Hesabınızda en çok 50 akışa sahip olabilirsiniz. 50 akışınız varsa başka bir akış oluşturabilmek için mevcut bir akışınızı silin.

## <a name="next-steps"></a>Sonraki adımlar
* Akışınıza, farklı yollarla bildirim almanızı sağlayacak [adımlar ekleyin](multi-step-logic-flow.md).
* Bir eylemin günlük olarak, belirli bir tarihte veya belirli bir sürenin (dakika cinsinden) ardından gerçekleşmesini istediğinizde [görevleri bir zamanlamaya göre çalıştırın](run-tasks-on-a-schedule.md).
* Uygulamanızın bulutta mantık başlatmasına izin vermek için [uygulamaya bir akış ekleyin](https://powerapps.microsoft.com/tutorials/using-logic-flows/).
* [Takım akışlarını kullanmaya başlayın](create-team-flows.md) ve akış tasarlamak üzere sizinle birlikte çalışmaları için diğer kişileri davet edin.

