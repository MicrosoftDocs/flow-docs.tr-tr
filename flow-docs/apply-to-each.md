---
title: Bir dizi öğe aracılığıyla döngü gerçekleştirmek için her bir eylemi Uygula eylemini kullanın. | Microsoft Docs
description: Birden çok koşulu denetlemek ve bu koşullara göre eylemler gerçekleştirmek için bir öğe dizisinde döngü yapmak üzere Microsoft Flow kullanın.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/16/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e2852de959f62d5c0ee76fabc9841e3fc9663f73
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545996"
---
# <a name="use-the-apply-to-each-action-in-microsoft-flow-to-process-a-list-of-items-periodically"></a>Öğelerin bir listesini düzenli aralıklarla işlemek için Microsoft Flow her bir eyleme Uygula eylemini kullanın
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Birçok tetikleyici, gelen kutunuza yeni bir e-posta geldiğinde olduğu gibi bir olaya bağlı olarak bir akışı hemen başlatabilir. Bu Tetikleyiciler harika, ancak bazen, veri kaynağındaki öğelerin özelliklerine göre belirli eylemleri gerçekleştirerek önceden tanımlanmış bir zamanlamaya göre bir veri kaynağını sorgulayan bir akış çalıştırmak istersiniz. Bunu yapmak için, akışınız bir zamanlamaya göre (günde bir kez) başlayabilir ve öğelerin listesini işlemek için **her birine Uygula** gibi bir döngü eylemi kullanabilirsiniz. Örneğin, Microsoft SharePoint 'teki bir veritabanından veya öğe listesinden kayıtları güncelleştirmek için **her birine Uygula** ' yı kullanabilirsiniz.

Bu kılavuzda, 15 dakikada bir çalışan bir akış oluşturacağız ve şunları yapar:

1. Office 365 Outlook gelen kutunuzda son 10 okunmamış iletiyi alır.
2. Konunun **Şimdi karşılayıp karşılamadığını** onaylamak için 10 iletinin her birini denetler.
3. E-postanın patronunuzdan mı ait olduğunu veya yüksek önem derecesiyle gönderilip gönderilmediğini denetler.
4. Bir anında iletme bildirimi gönderir ve **Şu anda konu içinde tanışan** bir e-posta okur ve patronunuzdan ya da yüksek önem derecesiyle gönderilmiştir.

Bu diyagramda, bu kılavuzda oluşturacağımız akışın ayrıntıları gösterilmektedir:

![oluşturulan akışa genel bakış](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Kaynakları
Bu kılavuzda adımları başarıyla gerçekleştirmeye yönelik gereksinimler şunlardır:

* [Microsoft Flow](https://flow.microsoft.com)kullanmak için kayıtlı bir hesap.
* Office 365 Outlook hesabı.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows)için mobil uygulama Microsoft Flow.
* Office 365 Outlook ve anında iletme bildirimi hizmeti bağlantıları.

## <a name="create-a-flow"></a>Akış oluşturma
1. [Microsoft Flow](https://flow.microsoft.com)oturum aç:
2. **Akışlarım** sekmesini seçin ve ardından boş bir akış oluşturun:
   
    ![boş oluştur](./media/apply-to-each/foreach-1.png)
3. Zamanlama ile ilgili tüm hizmetleri ve Tetikleyicileri aramak için arama kutusuna "Schedule" yazın.
4. Akışınızı, daha sonra sağlayacağımız bir zamanlamaya göre çalışacağını göstermek için **zamanlama-yinelenme** tetikleyicisini seçin:
   
    ![Yinelenme zamanlaması eylemi](./media/apply-to-each/foreach-2.png)
5. Zamanlamayı 15 dakikada bir çalışacak şekilde ayarlayın:
   
    ![çalıştırma zamanlaması](./media/apply-to-each/foreach-3.png)
6. **+ Yeni adım**' ı seçin, **eylem ekleyin**ve sonra Microsoft Outlook ile ilgili tüm eylemleri aramak için arama kutusuna **Outlook** yazın.
7. **Office 365 Outlook-e-postaları al** eylemini seçin:
   
    ![e-posta al eylemini seçin](./media/apply-to-each/foreach-4.png)
8. Bu işlem **e-posta al** kartını açar. **E-postaları al** kartını, gelen kutusu klasöründeki ilk 10 okunmamış e-postayı seçmek üzere yapılandırın. Akışta kullanılmayacağından ekleri eklemeyin:
   
    ![e-posta kartını yapılandırma](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Şimdiye kadar, gelen kutunuzdan bazı e-postalar alan basit bir akış oluşturdunuz. Bu e-postalar bir dizide döndürülür; **her eyleme Uygula** bir dizi gerektirir, bu nedenle bu tam olarak gereklidir.
   > 
   > 

## <a name="add-actions-and-conditions"></a>Eylemler ve koşullar ekleme
1. **+ Yeni adım**, **daha fazla**' yı seçin ve ardından **her eyleme bir Uygula ekleyin** :
   
    ![her birine Uygula ' yı seçin](./media/apply-to-each/foreach-6.png)
2. Her bir karta **Uygula** sayfasındaki **önceki adımlardan çıkış seçin** kutusuna **gövde** belirtecini ekleyin. Bu, her bir eyleme **Uygula** bölümünde kullanılacak e-postaların gövdesini çeker:
   
    ![gövde belirteci Ekle](./media/apply-to-each/foreach-7.png)
3. **Koşul Ekle**' yi seçin:
   
    ![Koşul Ekle](./media/apply-to-each/foreach-8.png)
4. **Koşul** kartını, her bir e-postanın konusunu "şimdi buluşmak" kelimelerinizle arayacak şekilde yapılandırın:
   
   * **Nesne adı** kutusuna **Konu** belirtecini ekleyin.
   * **İlişki** listesinde **Contains** ' i seçin.
   * **Değer** kutusuna **Şimdi buluşın** girin.
     
     ![koşulu Yapılandır](./media/apply-to-each/foreach-subject-condition.png)
5. **Daha fazla**' yı SEÇIN ve **Evet Ise, hiçbir şey yapma** dalından **Koşul Ekle** ' yi seçin. Bu **durum 2** kartını açar; Bu kartı şu şekilde yapılandırın:
   
   * **Nesne adı** kutusuna **önem** belirtecini ekleyin.
   * **İlişki** listesinde **eşittir** ' i seçin.
   * **Değer** kutusuna **yüksek** girin.
     
     ![Koşul Ekle](./media/apply-to-each/foreach-importance-condition.png)
6. **Evet, HIÇBIR şey yapma** bölümünden **Eylem Ekle** ' yi seçin. Bu işlem, arama koşulunun ( **Şimdi karşılanacak** e-postanın yüksek önem derecesine sahip olduğu) doğru olması durumunda ne olacağını tanımlayabileceğiniz **bir eylem seçin** kartını açar:
   
    ![Eylem Ekle](./media/apply-to-each/foreach-9.png)
7. **Bildirim**araması yapın ve ardından **bildirimleri seçin-bir mobil bildirim gönder** eylemi:
   
    ![Arama ve seçme bildirimi](./media/apply-to-each/foreach-10.png)
8. **Bana mobil bildirim gönder** kartında, bir e-postanın konusu "Şimdi tanışın" içeriyorsa gönderilecek anında iletme bildiriminin ayrıntılarını girin ve ardından **Eylem Ekle**' yi seçin:
   
    ![Bildirimi Yapılandır](./media/apply-to-each/foreach-11.png)
9. Arama terimi olarak **Oku** yazın ve ardından **Office 365 Outlook-okundu olarak işaretle** eylemini seçin. Bu işlem, anında iletme bildirimi gönderildikten sonra her e-postayı okundu olarak işaretler:
   
    ![okundu eylemi olarak işaretle ekleme](./media/apply-to-each/foreach-12.png)
10. **Ileti kimliği** belirtecini **okundu olarak Işaretle** kartının **ileti kimliği** kutusuna ekleyin. **Ileti kimliği** belirtecini bulmak için **daha fazla görüntüle** ' yi seçmeniz gerekebilir. Bu, okundu olarak işaretlenecek iletinin kimliğini belirtir:
    
     ![ileti kimliği Ekle](./media/apply-to-each/foreach-13.png)
11. **Koşul 2** kartına geri dönerek, **Hayır, hiçbir şey yapma** Dalı:
    
    * **Eylem Ekle**' yi seçin ve sonra arama kutusuna **yöneticiyi al** yazın.
    * Arama sonuçları listesinden **Office 365 kullanıcıları-yöneticiyi al** eylemini seçin.
    * **Yönetici al** kartının **Kullanıcı** kutusuna *tam* e-posta adresinizi girin.
      
      ![Yöneticiyi al eylemini ekleme ve yapılandırma](./media/apply-to-each/foreach-get-manager.png)
12. **Daha fazla**' yı seçin ve **ardından dal '** dan **Koşul Ekle** ' yi seçin. Bu **durum 3** kartını açar; e-posta gönderenin e-posta adresi (Kimden belirteci), patron e-posta adresiniz (e-posta belirteci) ile aynı olup olmadığını denetlemek için kartı yapılandırın:
    
    * **Nesne adı** kutusuna **from** belirtecini ekleyin.
    * **İlişki** listesinde **Contains** ' i seçin.
    * **Değer** kutusuna **e-posta** belirtecini girin.
      
      ![arama koşulunu yapılandırma](./media/apply-to-each/foreach-condition3-card.png)
13. **Koşul 3** kartının **Evet, hiçbir şey yapma** bölümünden **Eylem Ekle** ' yi seçin. Bu işlem, arama koşulu (e-posta, patronunuzdan gönderildiyse) doğru olduğunda ne olması gerektiğini tanımlayacağınızı belirleyen **Evet** kartını açar:
    
     ![koşulu Yapılandır](./media/apply-to-each/foreah-condition3-add-action.png)
14. **Bildirim**araması yapın ve ardından **bildirimleri seçin-bir mobil bildirim gönder** eylemi:
    
     ![bildirim eylemi ara](./media/apply-to-each/foreach-10.png)
15. **Bana mobil bildirim gönder 2** kartında, e-posta, patronunuzdan alıyorsa gönderilecek anında iletme bildiriminin ayrıntılarını girin ve ardından **Eylem Ekle**' yi seçin:
    
     ![bildirim kartını yapılandırma](./media/apply-to-each/foreach-boss-notification.png)
16. **Office 365 Outlook-okundu olarak işaretle** eylemini ekleyin. Bu işlem, anında iletme bildirimi gönderildikten sonra her e-postayı okundu olarak işaretler:
    
     ![okundu eylemi olarak işaretle ekleme](./media/apply-to-each/foreach-12.png)
17. **Ileti kimliği** belirtecini **okundu 2 kartı olarak işaretle** ' ye ekleyin. **Ileti kimliği** belirtecini bulmak için **daha fazla görüntüle** ' yi seçmeniz gerekebilir. Bu, okundu olarak işaretlenecek iletinin kimliğini belirtir:
    
     ![okundu olarak işaretle eylemini yapılandırma](./media/apply-to-each/foreach-mark-as-read2.png)
18. Akışınızı adlandırın ve ardından oluşturun:
    
     ![akışınıza bir ad verin ve kaydedin](./media/apply-to-each/foreach-14.png)

Daha sonra, akışınız şu diyagrama benzer görünmelidir:

![oluşturulan akışa genel bakış](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>Akışı çalıştırma
1. Kendinize konu içinde **Şimdi buluşla** (veya kuruluşunuzdaki bir e-posta göndermesini sağlayan) yüksek öneme sahip bir e-posta gönderin.
2. E-postanın gelen kutunuzda olduğunu ve okunmamış olduğunu doğrulayın.
3. Microsoft Flow oturum açın, **Akışlarım**' ı seçin ve **Şimdi Çalıştır**' ı seçin:
   
    ![Şimdi Çalıştır](./media/apply-to-each/foreach-run-1.png)
4. Akışı gerçekten çalıştırmak istediğinizi onaylamak için **akışı Çalıştır** ' ı seçin:
   
    ![çalıştırmayı Onayla](./media/apply-to-each/foreach-run-2.png)
5. Birkaç dakika sonra başarılı çalıştırmanın sonuçlarını görmeniz gerekir:
   
    ![sonuçları Çalıştır](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Çalıştırmanın sonuçlarını görüntüleme
Akışı başarıyla çalıştırdığınıza göre, mobil cihazınızda anında iletme bildirimini almalısınız.

1. Mobil cihazınızda Microsoft Flow uygulamasını açın ve **etkinlik** sekmesini seçin. Toplantı hakkında anında iletme bildirimi görürsünüz:
   
    ![Etkinlik sekmesini seçin](./media/apply-to-each/foreach-notification-1.png)
2. Bildirimin tüm içeriğini görmek için bildirimi seçmeniz gerekebilir. Aşağıdakine benzer şekilde tam bildirimi görürsünüz:
   
    ![Bildirim ayrıntıları](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > Anında iletme bildirimi almazsanız, mobil cihazınızın çalışan bir veri bağlantısı olduğunu doğrulayın.
   > 
   > 

