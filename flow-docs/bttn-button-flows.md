---
title: "Bttn ile akış başlatma | Microsoft Docs"
description: "bttn kullanarak akış başlatmayı öğrenin"
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
ms.date: 05/30/2017
ms.author: deonhe
ms.openlocfilehash: c4010f95ad2db3c4f3b97b39f0b45934c7b69c48
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Button Corporation tarafından tasarlanan fiziksel düğmelerle akışlarınızı çalıştırın (Önizleme)
Bir bttn'ye ([The Button Corporation](https://my.bt.tn/) tarafından tasarlanan fiziksel bir düğme) basarak akışlarınızı tetikleyin. Örneğin, akış tetikleyen bir bttn'ye basarak şu görevleri gerçekleştirebilirsiniz:

* konum bilgilerinizle birlikte yardım masanızla iletişime geçme
* ekibinize e-posta gönderme
* takviminizi engelleme
* yeni malzeme siparişi verme

> [!IMPORTANT]
> bttn'nizi bir akışta kullanabilmek için [kaydetmeniz](https://my.bt.tn/) gerekir.
> 
> [!TIP]
> Akışınızı oluşturmadan önce [bttn web sitesinde](https://my.bt.tn/) ad, konum ve e-posta adresi gibi tüm bttn özelliklerini yapılandırın.
> 
> 

Ayrıca [Flic fiziksel düğmesi](flic-button-flows.md) kullanarak da akış tetikleyebilirsiniz.

## <a name="prerequisites"></a>Önkoşullar
* [Microsoft Flow](https://flow.microsoft.com)’a erişiminiz olmalıdır.
* En az bir [kayıtlı bttn](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>bttn tarafından tetiklenen bir akış oluşturma
Bu incelemede, bir [bttn](https://my.bt.tn/)'ye yalnızca bir kez basarak tetikleyebileceğimiz bir akış oluşturmak için yardım masası şablonu kullanacağız. Akış çalıştığında bir destek isteği oluşturur ve bu isteği yardım masasına gönderir. Destek isteği, yardım gereken yerin konumunu destek masasına bildirir. Bu incelemede bir şablondan bu akışın nasıl oluşturulacağı gösterilmektedir ancak akışınızın tüm yönleri üzerinde size tam denetim sağlayan boş şablonu da kullanabilirsiniz.

bttn'niz için hızlı bir şekilde akış oluşturmak ve Zendesk, Google, SharePoint ve daha birçok hizmete bağlanmak için şu şablonlardan herhangi birini kullanabilirsiniz:

![bttn şablonları](./media/bttn-button-flows/bttn-templates.png)

İpucu: Bu incelemenin amaçları doğrultusunda bttn'nize tipik bir ofis binasındaki bir konferans salonunu temsil eden bir ad verin.

bttn'nizin ayarları şu örnekteki (bttn sitesinden) gibi olmalıdır:

![bttn şablonları](./media/bttn-button-flows/bttn-config.png)

bttn'nizi kaydedip yapılandırdığınıza göre akışımızı oluşturmaya başlayabiliriz.

### <a name="sign-in-and-select-a-template"></a>Oturum açın ve bir şablon seçin
1. [Microsoft Flow](https://flow.microsoft.com)'da oturum açın.
   
    ![Oturum açın](./media/bttn-button-flows/sign-into-flow.png)
   
    Not: Alternatif olarak [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulamasında akış oluşturabilirsiniz.
2. Arama kutusuna **bttn** yazın ve arama simgesini seçin.
   
    ![Arama](./media/bttn-button-flows/bttn-search-template.png)
   
    Arama simgesini seçtikten sonra bttn'lerle kullanabileceğiniz tüm şablonlar görünür.
3. **Toplantı odasına yönelik teknik destek ekibini aramak için bttn kullanın** şablonunu seçin.
   
    ![Destek şablonu](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Microsoft Flow'u bttn'nize bağlanması için yetkilendirin
1. İstenirse bttn'de ve Office 365 Outlook hizmetlerinde oturum açın, bunu yaptığınızda **Devam** düğmesi etkinleşir.
   
    ![Kimlik bilgileri](./media/bttn-button-flows/bttn-provide-credentials.png)
2. bttn hizmetinde oturum açtığınızda, Microsoft Flow'u bttn'lerinizi kullanması için yetkilendirin.
   
    **Önemli**: Microsoft Flow'u bttn'lerinizi kullanması için yetkilendirmezseniz bttn'lerinizi göremez veya Microsoft Flow'dan bunlara bağlanamazsınız.
   
    ![Yetkilendir](./media/bttn-button-flows/authorize-bttn.png)
3. Her iki hizmette de oturum açtıktan sonra **Devam**'ı seçin.
   
    ![Devam](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Akışı tetikleyen bttn'yi seçin
1. **Bir bttn'ye basıldığında** kartında, bttn kimliklerinin listesini açın ve ardından kullanmak istediğiniz bttn'yi seçin.
   
    ![bttn seçin](./media/bttn-button-flows/bttn-id.png)
   
    Akışınız artık şu örnekteki gibi olacaktır.
   
    ![Akışa genel bakış](./media/bttn-button-flows/bttn-done.png)
2. Akışınıza bir ad verin ve ardından **Akış oluştur**'u seçin.
   
    ![Akışı kaydedin](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Akışınızı test edin ve sonuçları onaylayın
1. bttn'nizin üzerindeki düğmeye basın.
2. Başarıyla çalıştığını doğrulamak için akışınızın çalıştırma geçmişini görüntüleyin.
   
    Microsoft Flow Web sitesinde veya mobil cihazınızda çalıştırma geçmişi kontrol edebilirsiniz.
   
    Not: Çalıştırma durumu, birisi destek isteği e-postasında **Kabul et** seçeneğini belirleyene kadar **çalışıyor** şeklindedir.
3. Ayrıca e-postanın, destek ekibine gönderilip gönderilmediğini de doğrulayabilirsiniz.
   
    Tüm adımları uyguladıysanız destek e-postası şu örnekteki gibi görünür:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Sorun giderme
* Akışınız tetiklenmediyse The Button Corporation'ın sitesinde oturum açın ve düğme etkinliğinin (basma eylemleri) kaydedilip kaydedilmediğini kontrol edin.
* Ayrıca Microsoft Flow sitesinde çalıştırma etkinliğinin ayrıntılarını inceleyebilir ve hata iletilerini kontrol edebilirsiniz.

## <a name="more-information"></a>Ek bilgi
* [Düğme akışları paylaşın](share-buttons.md).
* Düğme akışlarınız çalıştığında geçerli verileri göndermek için [düğme tetikleyici belirteçlerini](introduction-to-button-trigger-tokens.md) kullanmayı öğrenin.
* [Android için Microsoft Flow uygulamasını yükleyin](https://aka.ms/flowmobiledocsandroid).
* [iOS için Microsoft Flow uygulamasını yükleyin](https://aka.ms/flowmobiledocsios).

