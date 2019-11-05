---
title: Flik düğmeleriyle akışları başlatın | Microsoft Docs
description: Kısayol laboratuvarlarına göre Flik 'in fiziksel düğmeleriyle düğme akışlarını kolayca başlatın.
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
ms.openlocfilehash: e6430f78ad2eccecc5af7f6606bb56e1a7eb4599
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544796"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Bir Flik akıllı düğmesine basarak akışlarınızı çalıştırın (Önizleme)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Kısayol laboratuvarlarından, Flik olarak bilinen bir fiziksel düğmeye basarak akışlarınızı tetikleyin. Örneğin, çalışma saatlerinizi izlemek, takviminizi engellemek, bir olayda ziyaretçi saymak veya coğrafi konumları kaydetmek için bir Flik tuşuna basın.

> [!IMPORTANT]
> Akışınızı oluşturmadan önce Flik 'in [Android](https://play.google.com/store/apps/details?id=io.flic.app) veya [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) için mobil uygulamasını kullanarak tüm Flik özelliklerini yapılandırın.
> 
> 

## <a name="prerequisites"></a>Kaynakları
Microsoft Flow ile tis 'yi kullanmak için şunları yapmanız gerekir:

* [Microsoft Flow](https://flow.microsoft.com)erişim.
* Flik 'in [Android](https://play.google.com/store/apps/details?id=io.flic.app) veya [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) mobil uygulaması indirildi ve bir veya daha fazla titreşme eşleştirmek için kullanılır.

## <a name="configure-flic-properties"></a>Flik özelliklerini yapılandırma
Flik 'in olaylarını programlamak için Flik 'in mobil uygulamasını kullanın. Olaylar şunlardır:

* tıklama (bir hızlı basma)
* Çift tıklama (iki hızlı basma)
* Hold (bir uzun basma)

Bu ekran görüntüsünde, Flik yapılandırma sürecinizin nasıl benzebileceğini gösteren bir örnek gösterilmektedir:

![Titreşleri Yapılandır](./media/flic-button-flows/configure-flic-actions.png)

Microsoft Flow için bir Flik olayını bağladıktan sonra, akışlarınız için bir tetikleyici olarak bu Flik 'i seçebilirsiniz. Bu izlenecek yolda daha sonra Tetikleyiciler ' i seçersiniz.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Flik tarafından tetiklenen bir akış oluşturma
Bu kılavuzda, bir danışman her istemcide harcadığı zamanı kaydeden bir akışı çalıştırmak için bir Flik kullanıyoruz. Danışman, varolduktan sonra bir kez daha basar ve istemciye ayrılmadan hemen önce bu, yeniden basar. Flik 'in her bir basması, bağlandığı akışın bir çalıştırmasını başlatır. Akış geçerli saati Google sayfalarına kaydeder ve sonra bir e-posta bildirimi gönderir. E-posta, akış çalıştırması hakkındaki ayrıntıları içerir.

Note: Flik mobil uygulamasını eşleştirmek için kullandığınızdan emin olun ve Microsoft Flow tetiklemek için en az bir **tıklama** eylemi yapılandırın. Bu ekran görüntüsünde, Microsoft Flow tetiklemek için **tıklama** eylemini yapılandırdım. Bu kılavuzda daha sonra, Flik bir kez basıldığında (tıklandı) akışımızın tetikleneceğini yapılandıracağız.

   ![Flik yapılandırması](./media/flic-button-flows/flic-configured-for-flow.png)

Şimdi akışımızı oluşturmaya başlaalım.

### <a name="start-with-a-template"></a>Şablon ile başlama
1. [Microsoft Flow](https://flow.microsoft.com)oturum açın.
   
    ![Oturum Aç](./media/flic-button-flows/sign-into-flow.png)
2. Arama kutusuna **Flik** yazın ve arama simgesini seçin.
   
    ![ara](./media/flic-button-flows/search-flic.png)
3. **Çalışma saatlerinizi Flik akıllı düğme şablonuyla izleyin** .
   
    ![Şablon seç](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Google sayfalarında elektronik tablo oluşturma
1. Şablonun ayrıntılarını gözden geçirin ve bu şablonun Google sayfalarında bir elektronik tablo gerektirdiğini unutmayın.
   
   ![Şablon ayrıntılarını gözden geçirme](./media/flic-button-flows/flic-template-details.png)
2. Google sayfalarında, **Clicktype** ve **timestamp**adlı sütunlara sahip bir sayfa içeren bir elektronik tablo oluşturun.
   
      İpucu: sütunun üst kısmına sütun adını girerek Google sayfalarında sütunları adlandırın. Bu nedenle, aşağıdaki ekran görüntüsünde yer almalıdır:
   
   ![Google sayfası](./media/flic-button-flows/flic-google-sheet.png)
   
   Note: Bu sayfayı daha sonra Bu izlenecek yolda kullanacaksınız.

### <a name="add-the-flic-trigger-to-your-flow"></a>Flik tetikleyicisini akışla ekleyin
1. Şablonun hizmetlerinde oturum açın ve ardından **devam**' ı seçin.
   
     Şablon için gerekli tüm hizmetlerde oturum açtıktan sonra **devam et** özelliği etkinleştirilir.
   
    ![kimlik bilgilerini belirtin](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Arama kutusuna **Flik** ' i girin ve ardından **bir Flik tuşuna basıldığında fara** ' yı seçin.
   
    ![Flik tetikleyicisi ara](./media/flic-button-flows/flic-search-trigger.png)
3. Flik **'e basıldığında** , Flik 'teki Flik **düğme** listesinden kullanmak istediğiniz fınlik 'i seçin.
4. Flik 'e bir kez basıldığında akışı tetiklemek istediğinizi belirtmek için **Olaylar** listesinden **tıklayın ' ı** seçin.
   
    ![Flik eylemini seçin](./media/flic-button-flows/select-flic.png)
   
   İsteğe bağlı olarak, her bir Flik olayının (tıklama, Çift tıklama veya bekletme) akışı tetikleyeceğini belirtmek için **herhangi bir** seçim yapabilirsiniz.
   
   **Çift tıklama** , Flik 'in iki kez hızla basıldığında akışın tetikleyeceğini belirtir. **Hold** , Flik 'teki uzun bir basın akışı tetikleyeceğini belirtir.
   
   Başka akışlar oluşturmak ve **Olaylar** listesindeki diğer olayları kullanarak bunları tetiklemeniz ücretsizdir. Örneğin, bir istemciyi bıraktığınız saati kaydetmek için **çift tıklama** olayını kullanabilirsiniz.

### <a name="configure-the-sheet"></a>Sayfayı yapılandırma
   **Satır ekle** kartında:

1. **Dosya** listesinden daha önce oluşturduğunuz elektronik tabloyu seçin.
2. **Çalışma sayfası** listesinden sayfayı seçin.
   
   Note: sayfayı seçtikten sonra **satır ekle** kartında iki ek kutu belirir. Bu kutular, daha önce oluşturduğunuz sayfada iki sütunu temsil eder.
3. **Tıklama türü** kutusunu seçin ve ardından tür belirtecini Seç **' i** seçin.
4. **Zaman damgası** kutusunu seçin ve ardından **tıklama zaman** belirtecini seçin.
   
    ![Google sayfa verilerini yapılandırma](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>E-posta ayarlarının doğru olduğunu onaylayın
1. **Bana e-posta bildirimi gönder** kartının bu ekran görüntüsüne benzediğini onaylayın.
   
    ![e-posta bildirimini Onayla](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Akışınızı kaydedin ve test edin
1. Akışınıza bir ad verin ve sonra kaydedin.
   
    ![akışınızı kaydetme](./media/flic-button-flows/save.png)

Bunu takip ediyorsanız, Flik 'e basmak akışı tetikler. Akış daha sonra tıklama türünü ve geçerli saati sayfaya kaydeder ve size bir e-posta gönderir.

1. Flik tuşlarına basın.
2. Çalışma sayfanızı Google sayfalarında açın. **Clicktype** ve **timestamp** sütunlarının sırasıyla "Click" ve Time ile doldurulmuş olduğunu görmeniz gerekir.
   
    ![bkz. çalıştırma sonuçları](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. Çalıştırmanın sonuçlarını Microsoft Flow web sitesinden veya Microsoft Flow mobil uygulamadan da görebilirsiniz. Test çalıştırımın bir ekran görüntüsü aşağıda verilmiştir.
   
    ![akışınızı kaydetme](./media/flic-button-flows/flic-test-run-results-portal.png)
4. İşte, akışın çalıştırıldıklarından aldığım bildirim e-postası gövdesi şöyle görünür.
   
    ![akışınızı kaydetme](./media/flic-button-flows/flic-email-body.png)

Ek kredi için, Flik tuşuna basıldığında konumunuzu (Enlem ve Boylam) otomatik olarak kaydetmek için akışı genişletmeyi göz önünde bulundurun.

## <a name="more-information"></a>Daha fazla bilgi
* [Düğme akışlarını paylaşma](share-buttons.md).
* Düğme akışlarınız yürütüldüğünde geçerli verileri göndermek için [düğme tetikleyici belirteçleri](introduction-to-button-trigger-tokens.md) kullanmayı öğrenin.
* [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows)için Microsoft Flow Mobile App 'i yükler.

