---
title: Bttn ile akışları başlatma | Microsoft Docs
description: Akışlarınıza bir bttn ile nasıl başlayacağınızı öğrenin
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5835593c7bd020cdfce5f463a7fc198907c4ba6c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545682"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>(Önizleme) düğme şirketinin fiziksel düğmeleriyle (bttns) akışlarınızı çalıştırma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Bir bttn tuşuna basarak akışlarınızı tetikleyin ( [Button Corporation](https://my.bt.tn/)tarafından yapılan fiziksel bir düğme). Örneğin, bu görevleri gerçekleştirmek için bir akışı tetikleyen bir bttn tuşlarına basabilirsiniz:

* konum bilgileri ile yardım masanızla iletişim kurar
* ekibinize bir e-posta gönderir
* Takviminizi engeller
* yeniden sipariş malzemeleri

> [!IMPORTANT]
> Bir akışta kullanabilmeniz için bttn 'nizi [kaydetmeniz](https://my.bt.tn/) gerekir.
> 
> [!TIP]
> Akışınızı oluşturmadan önce [bttn Web sitesinde](https://my.bt.tn/) ad, konum ve e-posta adresi gibi tüm bttn özelliklerini yapılandırın.
> 
> 

Ayrıca, [Flik fiziksel düğmesini](flic-button-flows.md)kullanarak da bir akış tetikleyebilirsiniz.

## <a name="prerequisites"></a>Kaynakları
* [Microsoft Flow](https://flow.microsoft.com)erişim.
* En az bir [kayıtlı bttn](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Bir bttn tarafından tetiklenen bir akış oluşturma
Bu kılavuzda, bir [bttn](https://my.bt.tn/)'nin tek bir basma ile tetikleyebileceğiniz bir akış oluşturmak için bir yardım masası şablonu kullanırız. Akış çalıştırıldığında, bir destek isteği oluşturur ve ardından yardım masasına gönderir. Destek isteği, yardım 'ın gerekli olduğu odanın konumunu sağlar. Bu izlenecek yol, bir şablondan bu akışın nasıl oluşturulacağını gösterir, ancak akışlarınızın tüm yönleri üzerinde size tam denetim sağlayan boş şablonu kullanabilirsiniz.

Bttn 'niz için hızlı bir şekilde akış oluşturmak ve Zendesk, Google ve SharePoint 'e bağlanmak için şu şablonlardan herhangi birini kullanabilirsiniz:

![bttn şablonları](./media/bttn-button-flows/bttn-templates.png)

İpucu: Bu izlenecek yol Için, bttn 'ye tipik bir ofis binasında bir konferans odasını temsil eden bir ad verin.

Bttn 'nizin ayarlarının bu örneğe benzer olması gerekir (bttn Web sitesinden):

![bttn şablonları](./media/bttn-button-flows/bttn-config.png)

Bttn 'nizi kaydoldığınıza ve yapılandırdığınıza göre, akışımızı oluşturmaya başlaalım.

### <a name="sign-in-and-select-a-template"></a>Oturum açın ve bir şablon seçin
1. [Microsoft Flow](https://flow.microsoft.com)oturum açın.
   
    ![Oturum Aç](./media/bttn-button-flows/sign-into-flow.png)
   
    Göz: Alternatif olarak, [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows)için Microsoft Flow mobil uygulamasında akış oluşturabilirsiniz.
2. Arama kutusuna **bttn** girin ve arama simgesini seçin.
   
    ![aramanız](./media/bttn-button-flows/bttn-search-template.png)
   
    Arama simgesini seçtikten sonra bttn ile kullanabileceğiniz tüm şablonlar görünür.
3. **Toplantı odası şablonu için teknik destek çağırmak Için bttn kullanın** seçeneğini belirleyin.
   
    ![Destek şablonu](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Bttn 'nize bağlanmak için Microsoft Flow yetkilendirme
1. İstenirse, bttn ve Office 365 Outlook hizmetlerinde oturum açın, bu işlem **devam** düğmesini etkinleştirir.
   
    ![Credentials](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Bttn hizmetinde oturum açtığınızda, bttns 'yi kullanmak için Microsoft Flow yetkilendirin.
   
    **Önemli**: bttns 'yi kullanmak için Microsoft Flow yetkilendirmezseniz, Microsoft Flow buradan göremez veya bunlara bağlanamazsınız.
   
    ![yetki](./media/bttn-button-flows/authorize-bttn.png)
3. Her iki hizmeti de oturum açtıktan sonra **devam**' ı seçin.
   
    ![Devam](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Akışı tetikleyen bttn 'yi seçin
1. **Bir bttn 'ye basıldığında** , bttn kimlikleri listesini açın ve sonra kullanmak istediğiniz bttn 'yi seçin.
   
    ![bttn 'yi seçin](./media/bttn-button-flows/bttn-id.png)
   
    Akışınız artık bu örneğe benzemelidir.
   
    ![akışa genel bakış](./media/bttn-button-flows/bttn-done.png)
2. Akışınıza bir ad verin ve ardından **akış oluştur** ' u seçerek kaydedin.
   
    ![akışı Kaydet](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Akışınızı test etme ve sonuçları doğrulama
1. Bttn 'inizdeki düğmeye basın.
2. Akışının başarıyla çalıştığını onaylamak için akışınızın çalıştırma geçmişini görüntüleyin.
   
    Microsoft Flow web sitesinde veya mobil cihazınızda çalıştırma geçmişini kontrol edebilirsiniz.
   
    Note: çalışma durumu, birisi destek-istek e-postasında **Onayla** ' yı seçinceye kadar **çalışıyor** olarak ayarlanır.
3. Ayrıca, e-postanın destek ekibine gönderildiğini de doğrulayabilirsiniz.
   
    Bunu takip ediyorsanız, destek e-postası Şu örneğe benzer şekilde görünür:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Sorunu
* Akışınız tetiklenmediyse, Button Corporation 'ın sitesinde oturum açın ve düğme etkinliğinin (basışlar) kaydedilip kaydedilmediğini onaylayın.
* Ayrıca, Microsoft Flow sitesinde Çalıştır etkinliğinin detayına gidebilir ve hata iletilerini kontrol edebilirsiniz.

## <a name="more-information"></a>Daha fazla bilgi
* [Düğme akışlarını paylaşma](share-buttons.md).
* Düğme akışlarınız çalıştırıldığında geçerli verileri göndermek için [düğme tetikleyici belirteçlerini](introduction-to-button-trigger-tokens.md) kullanmayı öğrenin.
* [Android için Microsoft Flow uygulamasını yükler](https://aka.ms/flowmobiledocsandroid).
* [İOS için Microsoft Flow uygulamasını yükler](https://aka.ms/flowmobiledocsios).

