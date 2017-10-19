---
title: "Yinelenen görevleri kullanıcı girişi alan düğme akışlarıyla otomatikleştirmeyi öğrenme | Microsoft Docs"
description: "Microsoft Flow, yinelenen görevleri otomatikleştirmeyi kolaylaştırır. Akışlarınız, yinelenen bir görev çalıştırırken kullanıcı girişi bile alabilir."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: deonhe
ms.openlocfilehash: 73feb90b3907ee8a7a192f16bc29c5893d0be4bb
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="introducing-button-flows-with-user-input"></a>Kullanıcı girişli düğme akışları tanıtımı
Rutin görevleri yalnızca bir düğmeye dokunarak çalıştırmak için düğme akışı oluşturun. Kullanıcıya akış çalıştırıldığında kullanılacak belirli ayrıntıları sağlama izni vererek akışınızı özelleştirin. Bu konuda, kullanıcıdan giriş alan bir düğme akışı oluşturma ve sonra bu düğme akışını çalıştırma işlemleri gösterilerek kullanıcı girişinin nasıl sağlandığı vurgulanır.

Microsoft Flow web sitesinde veya Microsoft Flow mobil uygulamasında bir düğme akışı oluşturabilirsiniz. Bu konu için, web sitesini kullanacaksınız.

### <a name="prerequisites"></a>Önkoşullar
* Microsoft Flow web sitesinde bir hesap.

## <a name="open-the-template"></a>Şablonu açma
1. [Microsoft Flow web sitesinde](https://flow.microsoft.com) oturum açın, arama kutusuna **Visual Studio** yazın ve sonra Visual Studio ile ilgili tüm şablonları bulmak için arama simgesine tıklayın veya dokunun:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. **Visual Studio’da Önceliği 2 olan bir Hata açın** şablonunu seçin:
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. **Bu şablonu kullan** düğmesini seçin:
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Bu şablon Visual Studio Team Services (VSTS) ve Anında iletme bildirimi hizmetlerini kullanır. Bu hizmetlere bağlantınız yoksa hizmetlerde oturum açmanız gerekir. **Oturum açın** düğmesi yalnızca bir hizmette oturum açmanız gerektiğinde görüntülenir.
4. Gerekli tüm hizmetlerde oturum açtıktan sonra, **Devam** düğmesini seçin:
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. (isteğe bağlı) Portalın üst tarafındaki kutuya istediğiniz bir ad girerek akışın adını değiştirin:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>Kullanıcı girişini özelleştirme
1. Tetikleyici kartında, **Düzenle**’yi seçin:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Özel giriş alanlarını eklemek üzere sayfayı genişletmek için **+** simgesini seçin:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Akışınız çalıştırıldığında kullanılabilir olmasını istediğiniz her özel alan için **Giriş başlığı** ve **Giriş açıklaması** girin.  
   
    Bu örnekte, bu akışı kullanan herkesin hatayı yeniden oluşturmak için gereken adımları girebilmesi ve hatanın önem derecesini değerlendirebilmesi amacıyla iki özel giriş alanı (**Hatayı yeniden oluşturma adımları** ve **Hatanın önem derecesi**) oluşturacaksınız:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>Hatayı özelleştirme
1. **Yeni iş öğesi oluştur** kartının başlık çubuğuna dokunun:
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. VSTS ortamınız için uygun seçimleri yapın ve sonra **Düzenle**’yi seçin:
   
    Örneğin, **ornegim** yazarak ornegim.visualstudio.com’a bağlanın.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Bu kartın diğer alanlarını göstermek üzere **Gelişmiş seçenekleri göster**’i seçin:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. İmleci **Hata başlığı** belirtecinin başına getirin ve sonra **Başlık** metin alanına "Önem Derecesi: " yazın.
5. İmleç hala başlık metin alanındayken, **Hata önem derecesi** belirtecini seçin ve sonra " -- " yazın.  
6. **Açıklama** metin alanında, imlecinizi **Hata açıklaması** belirtecinin hemen sonrasına getirin ve sonra yeni bir satır başlatmak için Enter tuşuna basın.
7. İmlecinizi yeni satıra yerleştirin ve sonra **Hatayı yeniden oluşturma adımları** belirtecini seçin:
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>Anında iletme bildirimini özelleştirme
1. **Anında iletme bildirimi gönder** kartını genişletmek için başlık çubuğuna dokunun.
2. Dinamik içerik belirteçleri listesinde, **Daha fazla görüntüle**’yi seçin ve sonra **Bağlantı** metin alanına **URL** belirtecini ekleyin.
3. **Bağlantı etiketi** metin alanında, **Kimlik** belirtecini ekleyin:
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Akışınızı oluşturmak için menüde **Akış oluştur**’a dokunun:  ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Akışınızı çalıştırma
Bu kılavuzda, az önce oluşturduğunuz düğme akışını çalıştırmak için Microsoft Flow mobil uygulamasını kullanacaksınız. Bir başlığı, açıklaması, yeniden oluşturma adımları ve önem derecesi olan bir hata oluşturmak için gereken tüm kullanıcı girişlerini sağlayacaksınız.  

1. Microsoft Flow mobil uygulamasında, **Düğmeler** sekmesine dokunun ve sonra **Adımlar ile hata raporu oluştur** düğmesine dokunun.
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Raporladığınız hatanın başlığını girin ve sonra **İleri**’ye dokunun. Örnek:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Raporladığınız hatanın açıklamasını girin ve sonra **İleri**’ye dokunun. Örnek:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Raporladığınız hatayı yeniden oluşturma adımlarını girin ve sonra **İleri**’ye dokunun. Örnek:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Raporladığınız hatanın önem derecesini girin ve sonra **İleri**’ye dokunun.  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    Akış çalıştırılır.
6. (isteğe bağlı) Sonuçları göstermek için **Etkinlik** sekmesine dokunun.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. (isteğe bağlı) Akış çalıştırmasının ayrıntılı sonuçlarını, **Yeni iş öğesi oluştur** adımına dokunarak görüntüleyebilirsiniz.
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)  

## <a name="next-steps"></a>Sonraki adımlar
* [Düğme akışları paylaşma](share-buttons.md)
* [Akışlar hakkında bilgi edinin](guided-learning/learning-introducing-flow.md)  
* [Düğme akışları hakkında bilgi edinin](introduction-to-button-flows.md)  
* [Tetikleyici belirteç içeren düğme akışları hakkında bilgi edinin](introduction-to-button-trigger-tokens.md)  

