---
title: Flic düğmeleriyle akış başlatma | Microsoft Docs
description: Shortcut Labs’in Flic aracından fiziksel düğmelerle akışları kolayca başlatın.
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
ms.date: 05/19/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bbcb6c8950e8ac5959880727604e0355b3150c6f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64455630"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Flic akıllı düğmesine basarak akışlarınızı çalıştırma (Önizleme)
Shortcut Labs’in Flic olarak bilinen fiziksel düğmesine basarak akışlarınızı tetikleyin. Örneğin, Flic düğmesine basarak çalışma saatlerinizi izleyebilir, takviminizi engelleyebilir, bir olayın ziyaretçilerini sayabilir veya coğrafi konumları kaydedebilirsiniz.

> [!IMPORTANT]
> Akışınızı oluşturmadan önce, Flic’in [Android](https://play.google.com/store/apps/details?id=io.flic.app) veya [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) için mobil uygulamasını kullanarak tüm Flic özelliklerini yapılandırın.
> 
> 

## <a name="prerequisites"></a>Önkoşullar
Flic’leri Microsoft Flow’la kullanmak için:

* [Microsoft Flow](https://flow.microsoft.com)’a erişiminiz olmalıdır.
* Flic'in [Android](https://play.google.com/store/apps/details?id=io.flic.app) veya [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) mobil uygulamasını indirmiş ve bunu kullanarak bir veya birden çok Flic’i eşleştirmiş olmalısınız.

## <a name="configure-flic-properties"></a>Flic özelliklerini yapılandırma
Flic’in olaylarını programlamak için Flic'in mobil uygulamasını kullanın. Olaylar şunlardır:

* tıklama (bir kez hızla basma)
* çift tıklama (iki kez hızla basma)
* tutma (bir kez uzun basma)

Bu ekran görüntüsünde Flic yapılandırma işleminizin nasıl olabileceğine ilişkin bir örnek gösterilir:

![Flic’leri yapılandırma](./media/flic-button-flows/configure-flic-actions.png)

Bir Flic olayını Microsoft Flow’a bağladıktan sonra, akışlarınızın tetikleyicisi olarak o Flic’i seçebilirsiniz. Bu yönergelerin ilerleyen bölümünde tetikleyicileri seçeceksiniz.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Flic tarafından tetiklenen bir akış oluşturma
Bu yönergelerde, bir danışmanın her müşteride ne kadar zaman harcadığını kaydeden bir akış çalıştırmak için Flic kullanıyoruz. Danışman müşteriye geldiğinde Flic’e bir kez basıyor ve müşteriden ayrılmadan hemen önce yeniden basıyor. Flic’e her basıldığında, bağlantılı olduğunu akışın bir çalıştırması başlatılıyor. Akış, geçerli zamanı Google E-Tablolarına kaydediyor ve ardından bir e-posta bildirimi gönderiyor. E-posta, akış çalıştırması hakkındaki ayrıntıları içeriyor.

Not: Flic mobil uygulamasını kullandınız ve en az bir yapılandırma mutlaka **tıklayın** tetikleyici Microsoft Flow için eylem. Bu ekran görüntüsünde, Microsoft Flow’u tetiklemek için **tıklama** eylemini yapılandırdım. Bu yönergenin devamında akışımızı Flic’e bir kez basıldığında (tıklandığında) tetiklenecek şekilde yapılandırıyoruz.

   ![flic yapılandırın](./media/flic-button-flows/flic-configured-for-flow.png)

Şimdi akışımızı oluşturmaya başlayalım.

### <a name="start-with-a-template"></a>Şablonla başlama
1. [Microsoft Flow](https://flow.microsoft.com)'da oturum açın.
   
    ![Oturum açın](./media/flic-button-flows/sign-into-flow.png)
2. Arama kutusuna **flic** girin ve arama simgesini seçin.
   
    ![flic arayın](./media/flic-button-flows/search-flic.png)
3. **Flic akıllı düğmesiyle çalışma saatlerinizi izleme** şablonunu seçin.
   
    ![şablonu seçin](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Google E-Tabloları’nda bir elektronik tablo oluşturma
1. Şablonun ayrıntılarını gözden geçirin ve bu şablon için Google E-Tabloları’nda bir elektronik tablo gerektiğine dikkat edin.
   
   ![şablon ayrıntılarını gözden geçirin](./media/flic-button-flows/flic-template-details.png)
2. Google E-Tabloları’nda, **ClickType** ve **TimeStamp** adlı sütunların bulunduğu bir sayfa içeren bir elektronik tablo oluşturun.
   
      İpucu: Google e-tablolar, sütunlar, sütunun üst sütun adı girerek adlandırın. Bu durumda, sayfanız şu ekran görüntüsündeki gibi görünecektir:
   
   ![Google E-Tablosu](./media/flic-button-flows/flic-google-sheet.png)
   
   Not: Bu kılavuzda daha sonra bu sayfayı kullanırsınız.

### <a name="add-the-flic-trigger-to-your-flow"></a>Flic tetikleyicisini akışınıza ekleme
1. Şablonun hizmetlerinde oturum açın ve **Devam**’ı seçin.
   
     Siz şablon için gerekli olan hizmetlerde oturum açtıktan sonra **Devam** seçeneği etkinleştirilir.
   
    ![kimlik bilgilerini sağlayın](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Arama kutusuna **flic** girin ve **Flic - Flic’e basıldığında** tetikleyicisini seçin.
   
    ![flic tetikleyicisini arayın](./media/flic-button-flows/flic-search-trigger.png)
3. **Flic - Flic’e basıldığında** kartındaki **Flic düğmesi** listesinde, kullanmak istediğiniz Flic’i seçin.
4. Flic’e bir kez basıldığında akışı tetiklemek istediğinizi belirtmek için **Olaylar** listesinde **tıklama** öğesini seçin.
   
    ![flic eylemini seçin](./media/flic-button-flows/select-flic.png)
   
   İsteğe bağlı olarak, her Flic olayının (tıklama, çift tıklama veya tutma) akışı tetikleyeceğini belirtmek için **herhangi biri** öğesini seçebilirsiniz.
   
   **Çift tıklama**, Flic’e hızla iki kez basıldığında akışın tetikleneceğini belirtir. **Tutma**, Flic’e uzun süre basıldığında akışın tetikleneceğini belirtir.
   
   Başka akışlar oluşturup bunları **Olaylar** listesindeki diğer olayları kullanarak tetikleme özgürlüğüne sahipsiniz. Örneğin, müşteriden ayrıldığınız saati kaydetmek için **çift tıklama** olayını kullanabilirsiniz.

### <a name="configure-the-sheet"></a>Sayfayı yapılandırın
   **Satır ekle** kartında:

1. **Dosya** listesinde, daha önce oluşturmuş olduğunuz elektronik tabloyu seçin.
2. **Çalışma Sayfası** listesinde, sayfayı seçin.
   
   Not: İki kutu görünmez **Satır Ekle** siz sayfayı seçtikten sonra kartı. Bu kutular, daha önce oluşturduğunuz sayfadaki iki sütunu temsil eder.
3. **ClickType** kutusunu ve sonra da **Tıklama türü** belirtecini seçin.
4. **Timestamp** kutusunu ve sonra da **Tıklama zamanı** belirtecini seçin.
   
    ![Google E-Tabloları verilerini yapılandırın](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>E-posta ayarlarının doğru olduğunu onaylama
1. **Bana e-posta bildirimi gönder** kartının bu ekran görüntüsündeki gibi göründüğünü onaylayın.
   
    ![e-posta bildirimini onaylayın](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Akışınızı kaydetme ve test etme
1. Akışınıza bir ad verin ve akışı kaydedin.
   
    ![akışınızı kaydedin](./media/flic-button-flows/save.png)

Buradaki adımları izlediyseniz, Flic’e bir kez basıldığında akış tetiklenir. Ardından akış, tıklama türünü ve geçerli zamanı sayfaya kaydeder ve size bir e-posta gönderir.

1. Flic’inize bir kez basın.
2. Google E-Tabloları’nda çalışma sayfanızı açın. **ClickType** ve **Timestamp** sütunlarının sırasıyla “tıklama” ve zaman bilgisiyle doldurulduğunu görüyor olmalısınız.
   
    ![çalıştırma sonuçlarını görün](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. Çalıştırma sonuçlarını Microsoft Flow web sitesinde veya Microsoft Flow mobil uygulamasında da görebilirsiniz. İşte benim test çalıştırmamın ekran görüntüsü.
   
    ![akışınızı kaydedin](./media/flic-button-flows/flic-test-run-results-portal.png)
4. Akışın çalıştırılması sonucu aldığım bildirim e-postasının gövdesi de şöyle görünüyor.
   
    ![akışınızı kaydedin](./media/flic-button-flows/flic-email-body.png)

İşi biraz daha ileri götürmek için, Flic’e basıldığındaki konumunuzu (enlem ve boylam) otomatik olarak kaydedecek şekilde akışın kapsamını genişletmeyi düşünebilirsiniz.

## <a name="more-information"></a>Ek bilgi
* [Düğme akışları paylaşın](share-buttons.md).
* Düğme akışlarınız yürütüldüğünde güncel verilerin gönderilmesi için [düğme tetikleyici belirteçleri](introduction-to-button-trigger-tokens.md) kullanmayı öğrenin.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulamasını yükleyin.

