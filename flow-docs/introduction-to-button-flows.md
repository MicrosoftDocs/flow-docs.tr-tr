---
title: Düğme akışlarıyla yinelenen görevleri otomatikleştirmeyi ve çalıştırmayı öğrenin | Microsoft Docs
description: Düğme akışlarına giriş.
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
ms.date: 01/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 403c3d7cc116555ab26d5e4168587de5e5a6720f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547529"
---
# <a name="introducing-button-flows"></a>Düğme akışlarına giriş
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-flows"></a>Düğme akışları nelerdir?
Tek bir düğmeye dokunarak çalıştırabilmemiz için her şey yaptığımız çok sayıda yinelenen görev vardır. Örneğin, günlük takım eşitlemesine katılması için ekibinize hızlı bir şekilde e-posta gönderin veya gün için planlanmış başka bir çek olmadığı bildirildikten sonra kod tabanınızda yeni bir Visual Studio Online derlemesi başlatmak isteyebilirsiniz. Düğme akışları, mobil cihazınızda bir düğmeye dokunarak bunları ve diğer birçok görevi gerçekleştirmenize olanak tanır.

**Göz önünde** Mobil cihazınızdan ya da Flow portalından düğme akışları oluşturabilirsiniz.  
  ![genel bakış resmi](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Neden düğme oluşturmalıyım?
Mobil cihazınızdan istediğiniz zaman yinelenen görevleri dilediğiniz yerden kolayca çalıştırabilmeniz için düğmeler oluşturun. Düğmelerin yürütülmesi size zaman kazandırır ve gerçekleştirdikleri görevler otomatikleştirildiğinden, bunları el ile gerçekleştirmenizden daha az hata olacaktır.  

## <a name="create-a-button"></a>Düğme oluştur
### <a name="prerequisites"></a>Kaynakları
* Akışa erişim. Yöneticiniz size erişim sağlayabilir.
* Düğme oluşturmak için bağlayıcıları kullanma izinlerine sahip bir hesap. Örneğin, Dropbox 'a erişen bir düğme oluşturmak için bir Dropbox hesabına ihtiyacınız olacaktır.

### <a name="from-the-portal"></a>Portaldan
Bu kılavuzda, Visual Studio Online (VSO) oluşturmayı Başlatan bir düğme oluşturalım ve derleme başladığında bunu size bildirmek için bildirim gönderiyor:  

1. **Gösteriliyor** açılan listesini seçin ve **düğme** kategorisini seçin. Bu, şablon listesini yalnızca düğme akışlarında kullanılabilecek olanlarla filtreler.  
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-1.png)   
2. Şablon listesinden **VSO 'da yeni bir derleme Tetikle '** i seçin.  
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-2.png)  
3. **VSO 'da yeni bir derleme tetikleyin** sayfasında **Bu şablonu kullan** düğmesini seçin.   
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-3.png)  
4. Oturum açmadıysanız şu noktada bunu yapmanız istenir:  
   ![Genel Bakış görüntüsü](./media/introduction-to-button-flows/create-button-4.png)  
5. Flow 'a kaydolduktan sonra seçtiğiniz şablonda kullanılan bağlayıcılarda oturum açmanız istenir. Bu örnekte, yukarıdaki 2. adımda **VSO 'da yeni bir derleme tetikleyeceğiz** , daha önce oturum açmadıysanız VSO 'da (ve üzerinde çalıştığınız diğer bağlayıcılar) oturum açmamız gerekir:  
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Flow 'un VSO hesabınıza erişmesine izin vermeyi kabul ediyorsanız **kabul et** düğmesini seçin.  
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-5.png)   
   **Göz önünde** Her bağlayıcıyı benzer şekilde yetkilendirmeniz gerekir. Bir sonraki adıma geçmeye hazırsanız tasarımcı aşağıdaki gibi görünmelidir. İlerlemek için **devam** düğmesini seçin:  
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-6.png)   
7. Şimdi başlatmak istediğiniz derleme için özellikleri yapılandırmaya hazırsınız:    
   ![Genel Bakış görüntüsü](./media/introduction-to-button-flows/create-button-7.png)  
8. **Hesap adı**, **Proje adı**, **derleme tanımı kimliği**, **kaynak dalı** ve isteğe bağlı olarak **Parametreler**' i **Yeni bir derleme** kartında seçin veya girin:    
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-8.png)  
9. Sonra anında **iletme bildirimi gönder** kartında anında iletme bildiriminin özelliklerini yapılandırın. Varsayılan olarak, bu anında iletme bildirimi, derleme durumunu görüntüleyen bir Web sayfasına HTML bağlantısı gönderecek şekilde yapılandırılmıştır:  
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-9.png)  
10. Düğme akışınızı kaydetmek için **akış oluştur** düğmesini seçin: ![genel bakış resmi](./media/introduction-to-button-flows/create-button-10.png)  
11. Bu başarı iletisini birkaç dakika içinde görmeniz gerekir:  
    ![Genel Bakış görüntüsü](./media/introduction-to-button-flows/create-button-11.png)  

Tebrikler, bir düğme akışı oluşturdunuz! Artık bu düğme akışını Flow uygulamasındaki **düğmeler** sekmesinden dilediğiniz yerde çalıştırabilirsiniz. "Düğme" düğmesine basmanız yeterlidir ve çalışır! Microsoft Flow Mobile App, [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows)için kullanılabilir.

### <a name="from-your-mobile-device"></a>Mobil cihazınızdan
**Note**: Bu kılavuzda bir Android cihazındaki ekranlar görüntülenirken, bir iOS cihazında ekranlar ve deneyim benzerdir.

Akış uygulamasında:

1. **Tarayıcı** sekmesini seçin ve **düğme** kategorisine kaydırın.  
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. **Tümünü görüntüle** bağlantısını seçin. Bu, tüm çalışmaya devam düğmesi şablonlarını görüntüler.     
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. **Ekibinize bir toplantı şablonuna katılması hatırlatmak için e-posta gönder** ' i seçin    
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Sayfanın alt kısmındaki **Bu şablonu kullan** bağlantısını seçin.    
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. Bu şablonun kullandığı tüm hizmetlerde oturum açmanız gerekir:    
   ![Genel Bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Tüm hizmetlerde oturum açtıktan sonra **sonraki** bağlantıyı seçin.      
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. **Oluştur** bağlantısını seçin. Ayrıca, akışı gözden geçirebilir ve örneğin e-postayı kişiselleştirmek için ihtiyacınız olan tüm değişiklikleri yapabilirsiniz.        
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Birkaç dakika sonra düğme akışı oluşturulur. **AKıŞıMı göster**' i seçin:   
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Akışlarım sekmesinde tüm akışlarınızı görüntüleme  
   ![genel bakış resmi](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Tebrikler, bir düğme akışı oluşturdunuz! Artık bu düğme akışını Flow uygulamasındaki **düğmeler** sekmesinden dilediğiniz yerde çalıştırabilirsiniz. "Düğme" düğmesine basmanız yeterlidir ve çalışır! Flow uygulaması şu anda Android ve iOS mobil cihazlarında kullanılabilir.  

![Genel Bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Düğme akışını tetikleme
Bir düğme akışı oluşturduğunuza göre, şimdi çalıştırmanız zaman vardır. Akış uygulamasından yalnızca düğme akışlarını çalıştırabileceğiniz için, Android veya iOS mobil cihazınıza akış yüklediğinizden emin olun.  

1. Şimdi Flow uygulamasını başlatın, sayfanın altında bulunan **düğmeler** sekmesine dokunun ve tetiklemek istediğiniz düğme akışını temsil eden *düğmeye* dokunun:  
   ![genel bakış resmi](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Akış çalışırken ilerlemeyi görün:  
   ![Genel Bakış görüntüsü](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Son olarak, düğme akışının tamamlandığını belirten sayfa güncellenir:  
   ![Genel Bakış görüntüsü](./media/introduction-to-button-flows/trigger-button-3.png)   

Flow çalıştırmak için bu şey vardır. 

Artık e-postanın gönderildiğini belirten anında iletme bildirimi alacaksınız.  

## <a name="monitor-your-button-flow-runs"></a>Düğme akışı çalıştırmalarını izleyin
Akan uygulamanın **etkinlik** sekmesinden düğme akışlarını izleyebilirsiniz:   
![genel bakış resmi](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Note**: çalıştırma hakkında bilgi edinmek için herhangi bir etkinliğe dokunarak çalışma sonuçlarının ayrıntılarına gidin.  

![Genel Bakış görüntüsü](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Düğme akışlarını yönetme
Düğme akışlarınız üzerinde tam denetim sahibi olursunuz, böylece dilediğiniz zaman, herhangi bir düğmeyi etkinleştirebilir/devre dışı bırakabilir, düzenleyebilir veya silebilirsiniz. Akışlarınızı yönetmeye başlamak için mobil uygulamadan veya Flow portalından **Akışlarım** ' ı seçin.    

Flow uygulamasının **Akışlarım** sekmesinde:

1. Yönetmek istediğiniz akışı seçin:    
   ![Genel Bakış görüntüsü](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Gerçekleştirmek istediğiniz seçeneğe göre şu seçeneklerden birine dokunabilirsiniz:    
   ![Genel Bakış görüntüsü](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Akışı silmek için **akışı Sil** ' e dokunun.  

**Göz önünde** Bir akışı sildiğinizde tüm çalıştırma geçmişi silinir:   
![genel bakış resmi](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Bir düğme akışını düzenledikten sonra değişikliklerinizi kaydetmek için **Güncelleştir** ' e dokunun:   
   ![genel bakış resmi](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Belirli bir düğme akışının tüm çalıştırmalarının sonuçlarını görmek için **çalıştırma geçmişi** ' ne dokunun:    
   ![genel bakış resmi](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Bir akışı devre dışı bırakırsanız, **düğme** sekmesinde artık kullanılamaz:    
   ![genel bakış resmi](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Sonraki adımlar
* [Düğme akışlarını paylaşma](share-buttons.md).
* Düğme akışlarınız çalıştırıldığında gerçek zamanlı veri göndermek için [düğme tetikleyici belirteçlerini](introduction-to-button-trigger-tokens.md) kullanmayı öğrenin.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows)için Microsoft Flow Mobile App 'i yükler.

