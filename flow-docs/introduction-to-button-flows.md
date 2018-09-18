---
title: Düğme akışlarıyla yinelenen görevleri otomatikleştirmeyi ve çalıştırmayı öğrenme | Microsoft Docs
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
ms.openlocfilehash: cbcbce51bb950ef9154f356ce44a651f25ce55bd
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690103"
---
# <a name="introducing-button-flows"></a>Düğmesi akışları tanıtımı
## <a name="what-are-button-flows"></a>Düğme akışları nedir?
Tek bir düğmeye dokunarak çalıştırabilmek istediğimiz çok sayıda yinelenen görev vardır. Örneğin, günlük ekip eşitlemesine katılmalarını hatırlatmak üzere ekibinize hızlıca e-posta göndermeniz veya gün boyunca planlanan başka giriş olmayacağını öğrendikten sonra kod tabanınızın yeni bir Visual Studio Online derlemesini başlatmanız gerekebilir. Düğme akışları bunları ve diğer birçok görevi mobil cihazınızda tek bir düğmeye dokunarak gerçekleştirmenize olanak tanır.

**Not** Mobil cihazınızdan veya Flow portalından düğme akışları oluşturabilirsiniz.  
  ![Genel bakış görüntüsü](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Neden düğme oluşturmalıyım?
Yinelenen görevleri mobil cihazlarınızla dilediğiniz yerden ve dilediğiniz zaman kolayca çalıştırabilmenizi sağlayacak düğmeler oluşturun. Yürütme düğmeleri size zaman kazandırır ve gerçekleştirdikleri görevler otomatik hale getirildiğinden, elle yaptığınız işlemlere göre daha az hata oluşur.  

## <a name="create-a-button"></a>Düğme oluşturma
### <a name="prerequisites"></a>Önkoşullar
* Flow’a erişim. Erişiminizi yöneticiniz sağlayabilir.
* Düğmenizi oluşturmak üzere bağlayıcıları kullanma izinlerine sahip bir hesap. Örneğin, Dropbox’a erişen bir düğme oluşturmak için Dropbox hesabı gerekir.

### <a name="from-the-portal"></a>Portaldan
Bu kılavuzda Visual Studio Online (VSO) derlemesi başlatan ve derleme başladığında size bildirim gönderen bir düğme oluşturalım:  

1. **Gösteriliyor** açılır listesini seçin ve **Düğme** kategorisini belirleyin. Bunun yapılması, şablon listesini yalnızca düğme akışlarında kullanılabilecek düğmeleri gösterecek şekilde filtreler.  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-1.png)   
2. Şablon listesinden **VSO’da yeni derleme tetikleme** şablonunu seçin.  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-2.png)  
3. **VSO’da yeni derleme tetikleme** sayfasındaki **Bu şablonu kullan** düğmesini seçin.   
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-3.png)  
4. Oturum açmadıysanız bu noktada oturum açmanız istenir:  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-4.png)  
5. Flow’da oturum açtıktan sonra, seçtiğiniz şablonlarda kullanılan bağlayıcılarda oturum açmanız istenir. Bu örnekte, yukarıdaki 2. adımda **VSO’da yeni derleme tetikleme** şablonunu seçtiğimiz için, henüz oturum açmadıysanız VSO’da (ve birlikte çalıştığınız diğer bağlayıcılarda) oturum açmanız gerekir:  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Flow’un VSO hesabınıza erişmesine yetki vermeyi kabul ediyorsanız **Kabul Et** düğmesini seçin.  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-5.png)   
   **Not** Her bağlayıcıyı benzer şekilde yetkilendirmeniz gerekir. Sonraki adıma geçmeye hazır olduğunuzda tasarımcı aşağıdaki gibi görünmelidir. Devam etmek için **Devam** düğmesini seçin:  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-6.png)   
7. Başlatmak istediğiniz derlemenin özelliklerini yapılandırmak için artık hazırsınız:    
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-7.png)  
8. **Yeni bir derlemeyi kuyruğa al** kartındaki **Hesap adı**, **Proje adı**, **Derleme tanım kimliği**, **Kaynak dalı** ve isteğe bağlı olarak **Parametreler** öğesini seçin veya girin:    
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-8.png)  
9. Ardından, **Anında iletme bildirimi gönder** kartında anında iletme bildiriminin özelliklerini yapılandırın. Varsayılan olarak, bu anında iletme bildirimi derlemenin durumunu gösteren bir Web sayfasına HTML bağlantısı gönderecek şekilde yapılandırılır:  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-9.png)  
10. Düğme akışınızı kaydetmek için **Akış oluştur** düğmesini seçin: ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-10.png)  
11. Birkaç dakika içinde şu başarı iletisini görmeniz gerekir:  
    ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-11.png)  

Tebrikler, bir düğme akışı oluşturdunuz! Artık bu düğmeyi, dilediğiniz zaman ve dilediğiniz yerde Flow uygulamasındaki **Düğmeler** sekmesinden çalıştırabilirsiniz. Çalışması için "düğmeye" basmanız yeterli! Microsoft Flow mobil uygulaması [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows)’da kullanılabilir.

### <a name="from-your-mobile-device"></a>Mobil cihazınızdan
**Not**: Bu kılavuzda bir Android cihazındaki ekranlar gösterilmektedir; bir iOS cihazındaki ekranlar ve deneyim aynıdır.

Flow uygulamasında:

1. **Gözat** sekmesini seçin ve **Düğme** kategorisine doğru kaydırın.  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. **Tümünü gör** bağlantısını seçin. Bu bağlantı çalışmaya hazır tüm düğme şablonlarını gösterir.     
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. **Ekibinize toplantıya katılmayı hatırlatan bir e-posta gönderin** şablonunu seçin    
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Sayfanın altındaki **BU ŞABLONU KULLAN** bağlantısını seçin.    
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. Bu şablonun kullandığı tüm hizmetlerde oturum açmanız gerekir:    
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Tüm hizmetlerde oturum açtıktan sonra **İleri** bağlantısını seçin.      
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. **Oluştur** bağlantısını seçin. Burada ayrıca akışı gözden geçirebilir ve örneğin e-postanızı kişiselleştirmek için gereken değişiklikleri yapabilirsiniz.        
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Birkaç dakika sonra düğme akışı oluşturulur. **AKIŞIMI GÖR**'ü seçin:   
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. **Akışlarım** sekmesinde tüm akışlarınızı görüntüleyin  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Tebrikler, bir düğme akışı oluşturdunuz! Artık bu düğmeyi, dilediğiniz zaman ve dilediğiniz yerde Flow uygulamasındaki **Düğmeler** sekmesinden çalıştırabilirsiniz. Çalışması için "düğmeye" basmanız yeterli! Flow uygulaması şu anda Android ve iOS mobil cihazlarında kullanılabilir.  

![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Düğme akışını tetikleme
Bir düğme akışı oluşturduktan sonra çalıştırmanız gerekir. Düğme akışlarını yalnızca Flow uygulamasından çalıştırabileceğiniz için Android veya iOS mobil cihazınıza Flow’un yüklü olduğundan emin olun.  

1. Şimdi Flow uygulamasını başlatın, sayfanın altındaki **Düğmeler** sekmesine dokunun ve tetiklemek istediğiniz düğme akışını temsil eden *düğmeye* dokunun:  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Akış çalışırken ilerleme durumuna bakın:  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Son olarak, sayfa güncelleştirilir ve düğme akışının tamamlandığı gösterilir:  
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/trigger-button-3.png)   

Bir akışı çalıştırmak için tüm yapmanız gereken budur. 

Bu noktada e-postanın gönderildiğini belirten anında iletme bildirimini almanız gerekir.  

## <a name="monitor-your-button-flow-runs"></a>Düğme akışınızın çalışmasını izleyin
Flow uygulamanızın **Etkinlik** sekmesinden düğme akışlarını izleyebilirsiniz:   
![Genel bakış görüntüsü](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Not**: Çalıştırma hakkında bilgi edinmek üzere çalışma sonuçlarının ayrıntılarına inmek için herhangi bir etkinliğe dokunun.  

![Genel bakış görüntüsü](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Düğme akışlarını yönetme
Bir düğmeyi dilediğiniz zaman ve dilediğiniz yerde etkinleştirmeniz/devre dışı bırakmanız, düzenlemeniz veya silmeniz için düğme akışlarının tam denetimi sizdedir. Mobil uygulamadan veya akış portalından **Akışlarım**’ı seçerek akışlarınızı yönetmeye başlayın.    

Flow uygulamasının **Akışlarım** sekmesinde:

1. Yönetmek istediğiniz akışı seçin:    
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Gerçekleştirmek istediğiniz işleme göre bu seçeneklerin herhangi birine dokunabilirsiniz:    
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Bir akışı silmek için **Akışı sil**’e dokunun.  

**Not** Bir akışı sildiğinizde tüm çalışma geçmişi silinir:   
![Genel bakış görüntüsü](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Bir düğme akışını düzenlemeyi bitirdikten sonra değişikliklerinizi kaydetmek için **Güncelleştir**’e dokunun:   
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Belirli bir düğme akışına ait tüm çalışmaların sonuçlarını görmek için **Çalıştırma geçmişi**’ne dokunun:    
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Bir akışı devre dışı bırakırsanız **Düğmeler** sekmesinde artık kullanılamaz:    
   ![Genel bakış görüntüsü](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Sonraki adımlar
* [Düğme akışları paylaşın](share-buttons.md).
* Düğme akışlarınız çalıştırıldığında gerçek zamanlı veriler gönderilmesini sağlayan [düğme tetikleyicisi belirteçlerini](introduction-to-button-trigger-tokens.md) kullanmayı öğrenin.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulamasını yükleyin.

