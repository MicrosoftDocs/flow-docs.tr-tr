---
title: Bir öğe dizisi üzerinde döngü oluşturmak için Her birine uygula eylemini kullanın. | Microsoft Docs
description: Bir öğe dizisi üzerinde birden çok koşulu denetleyen ve bu koşullara bağlı olarak eylem gerçekleştiren bir döngü oluşturmak için Microsoft Flow’u kullanın.
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
ms.openlocfilehash: 914fe6d84bb63e1f3e184794d34fbfd58ad30963
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64459883"
---
# <a name="use-the-apply-to-each-action-in-microsoft-flow-to-process-a-list-of-items-periodically"></a>Bir öğe listesini düzenli aralıklarla işlemek için Microsoft Flow’daki Her birine uygula eylemini kullanın.
Birçok tetikleyici, bir olaya (örneğin, gelen kutunuza yeni bir e-posta gelmesi) bağlı olarak anında akış başlatabilir. Bu tetikleyiciler kullanışlı olsa da bazen önceden tanımlanmış bir zamanlamaya göre bir veri kaynağını sorgulayan ve veri kaynağındaki öğelerin özelliklerine göre belirli eylemler gerçekleştiren bir akış çalıştırmak istersiniz. Bunu yapmak için akışınız bir zamanlamaya (günde bir kere gibi) göre başlatılabilir ve **Her birine uygula** gibi bir döngü eylemini kullanarak bir öğe listesini işleyebilir. Örneğin, **Her birine uygula** eylemini kullanarak bir veritabanından alınan kayıtları ya da Microsoft SharePoint’ten alınan bir öğe listesini güncelleştirebilirsiniz.

Bu kılavuzda, 15 dakikada bir çalışan ve aşağıdakini yapan bir akış oluşturacağız:

1. Office 365 Outlook Gelen Kutunuzdaki son 10 okunmamış iletiyi getirir.
2. 10 iletinin her birini denetleyerek konusunda **hemen toplanıyoruz** ifadesi geçip geçmediğini doğrular.
3. E-postanın müdürünüz tarafından ya da yüksek önem derecesiyle gönderilip gönderilmediğini denetler.
4. Konusunda **hemen toplanıyoruz** yazan ve müdürünüz tarafından ya da yüksek önem derecesiyle gönderilen tüm e-postaları okundu olarak işaretler ve bir anında iletme bildirimi gönderir.

Bu kılavuzda oluşturacağımız akışın ayrıntıları bu diyagramda gösterilmiştir:

![Oluşturulmakta olan akışa genel bakış](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Önkoşullar
Bu kılavuzdaki adımların başarılı bir şekilde uygulanabilmesi için gereksinimler şunlardır:

* [Microsoft Flow](https://flow.microsoft.com)’u kullanmak için kayıtlı bir hesap.
* Bir Office 365 Outlook hesabı.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulaması.
* Office 365 Outlook’a ve anında iletme bildirimi hizmetine bağlantı.

## <a name="create-a-flow"></a>Akış oluşturma
1. [Microsoft Flow](https://flow.microsoft.com)’da oturum açın:
2. **Akışlarım** sekmesini seçin ve boş bir akış oluşturun:
   
    ![Boş akış oluştur](./media/apply-to-each/foreach-1.png)
3. Zamanlamayla ilgili tüm hizmetleri ve tetikleyicileri bulmak için arama kutusuna "zamanlama" yazın.
4. Akışınızın bir sonraki adımda sağlayacağınız bir zamanlamaya göre çalıştırılacağını belirtmek için **Zamanlama - Yineleme** tetikleyicisini seçin:
   
    ![Zamanlama yineleme eylemi](./media/apply-to-each/foreach-2.png)
5. Zamanlamayı her 15 dakikada bir çalışacak biçimde ayarlayın:
   
    ![Zamanlamanın çalışması](./media/apply-to-each/foreach-3.png)
6. **+ Yeni adım**’ı seçip **Eylem ekle**’yi seçin ve sonra Microsoft Outlook ile ilgili tüm eylemleri aramak için arama kutusuna **outlook** yazın.
7. **Office 365 Outlook - E-postaları al** eylemini seçin:
   
    ![E-postaları al eylemini seçin](./media/apply-to-each/foreach-4.png)
8. Bunu yaptığınızda **E-postaları al** kartı açılır. **E-postaları al** kartını Gelen Kutusu klasörünün en üstündeki 10 okunmamış e-postayı seçecek şekilde yapılandırın. Ekler akışta kullanılmayacağından ekleri dahil etmeyin:
   
    ![E-posta kartını yapılandırma](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Bu noktada, gelen kutunuzdan bazı e-postaları getiren basit bir akış oluşturmuş oldunuz. Bu e-postalar bir dizi halinde döndürülür; **Her birine uygula** eylemi için bir dizi gerektiğinden, tam olarak ihtiyacınız olan şey de budur.
   > 
   > 

## <a name="add-actions-and-conditions"></a>Eylem ve koşul ekleme
1. **+ Yeni adım**’ı, **Diğer**’i ve sonra **Her birine uygula ekle** eylemini seçin:
   
    ![Her birine uygula’yı seçin](./media/apply-to-each/foreach-6.png)
2. **Her birine uygula** kartındaki **Önceki adımlardan bir çıkış seçin** kutusuna **Gövde** belirtecini ekleyin. Bu, **Her birine uygula** eyleminde kullanılacak e-postaların gövdelerini alır:
   
    ![Gövde belirteci ekleme](./media/apply-to-each/foreach-7.png)
3. **Koşul ekle**’yi seçin:
   
    ![Koşul ekleme](./media/apply-to-each/foreach-8.png)
4. **Koşul** kartını her e-postanın konusunda “hemen toplanıyoruz” sözcüklerini arayacak şekilde yapılandırın:
   
   * **Nesne Adı** kutusuna **Konu** belirtecini ekleyin.
   * **İlişki** listesinden **İçerir**’i seçin.
   * **Değer** kutusuna **hemen toplanıyoruz** yazın.
     
     ![Koşulu yapılandırma](./media/apply-to-each/foreach-subject-condition.png)
5. **Diğer**’i seçip **EVET İSE, HİÇBİR ŞEY YAPMA** dalından **Koşul ekle**’yi seçin. Bunu yaptığınızda **Koşul 2** kartı açılır. Bu kartı aşağıdaki gibi yapılandırın:
   
   * **Nesne Adı** kutusuna **Önem** belirtecini ekleyin.
   * **İlişki** listesinden **Eşittir**’i seçin.
   * **Değer** kutusuna **Yüksek** yazın.
     
     ![Koşul ekleme](./media/apply-to-each/foreach-importance-condition.png)
6. **EVET İSE, HİÇBİR ŞEY YAPMA** bölümünden **Eylem ekle**’yi seçin. Bunu yaptığınızda açılan **Eylem seçin** kartında, arama koşulunun (yüksek önem derecesiyle gönderilen **hemen toplanıyoruz** e-postası) doğru olması durumunda gerçekleşmesi gereken eylemi tanımlayabilirsiniz:
   
    ![Eylem ekleme](./media/apply-to-each/foreach-9.png)
7. **Bildirim** sözcüğünü arayın ve **Bildirimler - Bana mobil bildirim gönder** eylemini seçin:
   
    ![Bildirimi arama ve seçme](./media/apply-to-each/foreach-10.png)
8. **Bana mobil bildirim gönder** kartında, bir e-postanın konusu "hemen toplanıyoruz" ifadesini içeriyorsa gönderilecek anında iletme bildirimin ayrıntılarını sağlayın ve **Eylem ekle**’yi seçin:
   
    ![Bildirimi yapılandırma](./media/apply-to-each/foreach-11.png)
9. Arama terimi olarak **okundu** yazın ve **Office 365 Outlook - Okundu olarak işaretle** eylemini seçin. Bunu yaptığınızda, anında iletme bildirimi gönderildikten sonra e-posta okundu olarak işaretlenir:
   
    ![Okundu olarak işaretle eylemini ekleme](./media/apply-to-each/foreach-12.png)
10. **Okundu olarak işaretle** kartının **İleti Kimliği** kutusuna **İleti Kimliği** belirtecini ekleyin. **İleti Kimliği** belirtecini bulmak için **Daha fazla görüntüle**’yi seçmeniz gerekebilir. Bu, okundu olarak işaretlenecek iletinin kimliğini belirtir:
    
     ![İleti kimliği ekleme](./media/apply-to-each/foreach-13.png)
11. **Koşul 2** kartına dönün ve **HAYIR İSE, HİÇBİR ŞEY YAPMA** dalında:
    
    * **Eylem ekle**’yi seçip arama kutusuna **yöneticiyi al** yazın.
    * Sonuç listesinden **Office 365 Kullanıcıları - Yöneticiyi al** eylemini seçin.
    * **Yöneticiyi Al** kartının **Kullanıcı** kutusuna *tam* e-posta adresinizi girin.
      
      ![Yöneticiyi alma eylemini ekleme ve yapılandırma](./media/apply-to-each/foreach-get-manager.png)
12. **Diğer**’i seçip **HAYIR İSE** dalından **Koşul ekle**’yi seçin. Bunu yaptığınızda **Koşul 3** kartı açılır. Kartı, e-postayı gönderenin e-posta adresinin (Kimden belirteci), müdürünüzün e-posta adresi (E-posta belirteci) ile aynı olup olmadığını denetleyecek şekilde yapılandırın:
    
    * **Nesne Adı** kutusuna **Kimden** belirtecini ekleyin.
    * **İlişki** listesinden **İçerir**’i seçin.
    * **Değer** kutusuna **E-posta** belirtecini girin.
      
      ![Arama koşulunu yapılandırma](./media/apply-to-each/foreach-condition3-card.png)
13. **Koşul 3** kartının **EVET İSE, HİÇBİR ŞEY YAPMA** bölümünden **Eylem ekle**’yi seçin. Bunu yaptığınızda açılan **EVET İSE** kartında, arama koşulunun (müdürünüz tarafından gönderilen e-posta) doğru olması durumunda gerçekleşmesi gereken eylemi tanımlayabilirsiniz:
    
     ![Koşulu yapılandırma](./media/apply-to-each/foreah-condition3-add-action.png)
14. **Bildirim** sözcüğünü arayın ve **Bildirimler - Bana mobil bildirim gönder** eylemini seçin:
    
     ![Bildirim arama eylemi](./media/apply-to-each/foreach-10.png)
15. **Bana mobil bildirim gönder 2** kartında, e-posta müdürünüzden geldiyse gönderilecek anında iletme bildiriminin ayrıntılarını sağlayın ve **Eylem ekle**’yi seçin:
    
     ![Bildirim kartını yapılandırma](./media/apply-to-each/foreach-boss-notification.png)
16. **Office 365 Outlook - Okundu olarak işaretle** eylemini ekleyin. Bunu yaptığınızda, anında iletme bildirimi gönderildikten sonra e-posta okundu olarak işaretlenir:
    
     ![Okundu olarak işaretle eylemini ekleme](./media/apply-to-each/foreach-12.png)
17. **Okundu olarak işaretle 2** kartına **İleti Kimliği** belirtecini ekleyin. **İleti Kimliği** belirtecini bulmak için **Daha fazla görüntüle**’yi seçmeniz gerekebilir. Bu, okundu olarak işaretlenecek iletinin kimliğini belirtir:
    
     ![Okundu olarak işaretle eylemini yapılandırma](./media/apply-to-each/foreach-mark-as-read2.png)
18. Akışınızı adlandırın ve sonra oluşturun:
    
     ![Akışınıza bir ad verip akışı kaydedin](./media/apply-to-each/foreach-14.png)

Buraya kadar iyi takip ettiyseniz, akışınız şu diyagrama benzemelidir:

![Oluşturulan akışa genel bakış](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>Akışı çalıştırma
1. Kendinize, konusunda **hemen toplanıyoruz** yazan yüksek önem dereceli bir e-posta gönderin (veya kuruluşunuzdaki bir kişiden böyle bir e-posta göndermesini isteyin).
2. E-postanın gelen kutunuzda ve okunmamış olduğunu doğrulayın.
3. Microsoft Flow’da oturum açın, **Akışlarım**’ı ve sonra **Şimdi çalıştır**’ı seçin:
   
    ![hemen çalıştırma](./media/apply-to-each/foreach-run-1.png)
4. Akışı gerçekten çalıştırmak istediğinizi onaylamak için **Akışı çalıştır**’ı seçin:
   
    ![Çalıştırmayı onaylama](./media/apply-to-each/foreach-run-2.png)
5. Birkaç dakika sonra başarılı çalıştırma işleminin sonuçlarını görmeniz gerekir:
   
    ![Çalıştırma sonuçları](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Çalıştırma işleminin sonuçlarını görüntüleme
Artık akışı başarıyla çalıştırdığınıza göre mobil cihazınızda anında iletme bildirimini almanız gerekir.

1. Mobil cihazınızda Microsoft Flow uygulamasını açıp **Etkinlik** sekmesini seçin. Toplantıyla ilgili anında iletme bildirimini görürsünüz:
   
    ![Etkinlik sekmesini seçme](./media/apply-to-each/foreach-notification-1.png)
2. Bildirimin içeriğini tam olarak görmek için bildirimi seçmeniz gerekebilir. Bildirimin aşağıdakine benzeyen tam halini görürsünüz:
   
    ![Bildirim ayrıntıları](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > Anında iletme bildirimini almazsanız mobil cihazınızın çalışan bir veri bağlantısı olduğunu doğrulayın.
   > 
   > 

