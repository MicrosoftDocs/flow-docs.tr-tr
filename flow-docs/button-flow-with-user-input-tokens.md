---
title: Yinelenen görevleri Kullanıcı girişi alan düğme akışlarıyla otomatikleştirmeyi öğrenin | Microsoft Docs
description: Microsoft Flow yinelenen görevleri otomatik hale getirmeyi kolaylaştırır. Akışlarınız, yinelenen bir görevi çalıştırırken kullanıcı girişi de alabilir.
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
ms.date: 02/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a1bc5161bdd0e6a098d57cefafba99d3c89e6c97
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546455"
---
# <a name="introducing-button-flows-with-user-input"></a>Kullanıcı girişiyle düğme akışlarına giriş
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Rutin görevleri yalnızca bir düğmeye dokunarak çalıştırmak için bir düğme akışı oluşturun. Kullanıcının akış çalışırken kullanılacak belirli ayrıntıları sağlamasına izin vererek akışınızı özelleştirin. Bu konu, kullanıcıdan girdi alan ve sonra düğme akışını çalıştıran ve Kullanıcı girişini nasıl sağlayacağınızı vurgulayan bir düğme akışı oluşturma işleminde size kılavuzluk eder.

Microsoft Flow web sitesinde veya mobil uygulamada Microsoft Flow bir düğme akışı oluşturabilirsiniz. Bu konu için Web sitesini kullanacaksınız.

### <a name="prerequisites"></a>Kaynakları
* Microsoft Flow web sitesinde bir hesap.

## <a name="open-the-template"></a>Şablonu açın
1. [Microsoft Flow web sitesinde](https://flow.microsoft.com)oturum açın, arama kutusuna **Visual Studio** girin ve sonra Visual Studio ile ilgili tüm şablonları bulmak için arama simgesine tıklayın veya dokunun:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. **Visual Studio şablonunda bir Priority 2 hatası aç '** ı seçin:
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. **Bu şablonu kullan** düğmesini seçin:
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Bu şablon Visual Studio Team Services (VSTS) ve anında Iletme bildirimi hizmetlerini kullanır. Bunlardan birine bağlantınız yoksa, bu hizmetlerde oturum açmanız gerekir. **Oturum aç** düğmesi yalnızca bir hizmette oturum açmanız gerektiğinde görünür.
4. Tüm gerekli hizmetlerde oturum açtıktan sonra, **devam** düğmesini seçin:
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. seçim Portalın üst kısmındaki kutuya seçtiğiniz bir adı yazarak akışın adını değiştirin:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>Kullanıcı girişini özelleştirme
1. Tetikleyici kartında **Düzenle**' yi seçin:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Özel giriş alanları ekleyebilmek için sayfayı genişletmek üzere **+** simgesini seçin:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Bir Kullanıcı akışınızı çalıştırdığında kullanılabilir hale getirmek istediğiniz her bir özel alan için **giriş başlığını** ve **giriş açıklamasını** girin.  
   
    Bu örnekte, bu akışı kullanan herkesin hatayı yeniden oluşturma ve hatanın önem derecesini derecelendirme adımlarını girebilmesi için iki özel giriş alanı (**hata yeniden üretme adımları** ve **hata önem derecesi**) oluşturacaksınız:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>Hatayı özelleştirme
1. **Yeni iş öğesi oluştur** kartının başlık çubuğuna dokunun:
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. VSTS ortamınız için uygun olan seçimleri yapın ve ardından **Düzenle**' yi seçin:
   
    Örneğin, **MyInstance**yazarak myinstance.VisualStudio.com 'e bağlanın.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Bu kartın diğer alanlarını açığa çıkarmak için **Gelişmiş seçenekleri göster** ' i seçin:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. İmleci **hata başlığı** belirtecinden önce yerleştirin ve sonra **başlık** metin alanına "önem derecesi:" yazın.
5. İmleç hala başlık metin alanında **hata önem derecesi** belirtecini seçin ve ardından "--" yazın.  
6. **Açıklama** metni alanında, imlecinizi **hata açıklama** belirtecinin hemen sonrasına yerleştirin ve ardından ENTER tuşuna basarak yeni bir satır başlatın.
7. İmlecinizi yeni satıra yerleştirip **hata yeniden üretme adımları** belirtecini seçin:
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>Anında iletme bildirimini özelleştirme
1. **Anında iletme bildirimi gönder** kartında başlık çubuğuna dokunarak genişletin.
2. Dinamik içerik belirteçleri listesinde **daha fazla göster**' i seçin ve ardından **bağlantı** metni alanına **URL** belirtecini ekleyin.
3. **Bağlantı etiketi** metin alanına, **kimlik** belirtecini ekleyin:
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Akışınızı oluşturmak için menüde **akış oluştur** ' a dokunun: ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Akışınızı çalıştırın
Bu kılavuzda, yeni oluşturduğunuz düğme akışını çalıştırmak için Microsoft Flow mobil uygulamasını kullanacaksınız. Bir başlık, açıklama, yeniden üretme adımları ve önem düzeyi ile bir hata oluşturmak için gereken tüm kullanıcı girişlerini sağlarsınız.  

1. Microsoft Flow için mobil uygulamada, **düğmeler** sekmesine dokunun ve ardından **adımlarda hata raporu oluştur** düğmesine dokunun.
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Rapor ettiğiniz hatanın başlığını girin ve ardından **İleri**' ye dokunun. Örneğin:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Rapor ettiğiniz hatanın açıklamasını girip **İleri**' ye dokunun. Örneğin:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Raporladığınız hatayı yeniden oluşturmak için gereken adımları girin ve ardından **İleri**' ye dokunun. Örneğin:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Rapor ettiğiniz hatanın önem derecesini girip **bitti**' ye dokunun:  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    Akış çalışır.
6. seçim Sonuçları göstermek için **etkinlik** sekmesine dokunun.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. seçim **Yeni iş öğesi oluştur** adımına dokunarak akışın çalışmasının ayrıntılı sonuçlarını gösterin.
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>Farklı giriş türleri kullanma

Düğme akışlarınız zengin veri türlerini de kabul edebilir. Düğme akışlarının kabul edeceği veri girişi türlerinin listesi aşağıdadır: 

- Metinleri
- Açılan listeler (radyo düğmeleri gibi)
- E-posta adresi
- Dosya (örneğin, telefonunuzdaki bir fotoğraf)
- Evet veya Hayır onay kutusu
- Sayısından
- Tarih (takvim seçiciyle)

Bu giriş türlerini kullanmak için **el ile bir akış tetikleyicisi tetikleyicisi** ekleyin ve ardından bu türlerden birini akışınıza ekleyin:

![Giriş seçenekleri](media/button-flow-with-user-input-tokens/input-options.png)

Buna ek olarak, bazı girdileri gerekli ve diğerleri için isteğe bağlı olarak atamak isteyebilirsiniz. Eylem menüsünü (...) kullanın. sağ tarafta) her giriş alanı. Düğme başına beş giriş sınırı vardır.

![İsteğe bağlı belirteçleri seçin](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Düğme akışlarını paylaşma](share-buttons.md)
* [Düğme akışları hakkında bilgi edinin](introduction-to-button-flows.md)  
* [Tetikleyici belirteçleriyle düğme akışları hakkında bilgi edinin](introduction-to-button-trigger-tokens.md)  

