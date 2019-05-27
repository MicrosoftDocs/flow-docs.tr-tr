---
title: Başlarken | Microsoft Docs
description: İşlerinizi ve yaşamınızı Microsoft Flow ile otomatik hale getirmeye başlamanın hızlı yolları
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: hero-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/31/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f667401774e49505009cd416f6975ff38683a5c7
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035203"
---
# <a name="get-started-with-microsoft-flow"></a>Microsoft Flow ile çalışmaya başlama #

<iframe width="560" height="315" src="https://www.youtube.com/embed/iMteXfAvDSE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

Hoş Geldiniz! Microsoft Flow sık kullandığınız uygulamalar ile hizmetler arasında otomatik iş akışları oluşturarak dosyaları eşitlemenize, bildirimler almanıza, veri toplamanıza ve daha fazlasını yapmanıza yardımcı olan bir hizmettir.

Ana akış türleri; [otomatik](get-started-logic-flow.md), [düğme](introduction-to-button-flows.md), [zamanlanmış](run-scheduled-tasks.md) ve [iş süreci](business-process-flows-overview.md) akışlarıdır.

Bir Dynamics 365 müşteri etkileşimi özelleştiricisiyseniz; [iş akışları](configure-workflow-steps.md), [eylemler](create-actions.md), [mobil görev akışları](create-mobile-task-flow.md) ve [iletişim kutularını](use-cds-for-apps-dialogs.md) içeren klasik Common Data Service işlemlerini de biliyor olabilirsiniz.

İlk adım olarak [kaydolmanız](sign-up-sign-in.md) gerekir. Zaten bir Microsoft Flow hesabınız varsa tabletinizde, masaüstü bilgisayarınızda ve hatta telefonunuzda [oturum açabilirsiniz](https://flow.microsoft.com/signin).

## <a name="check-out-the-start-page"></a>Başlangıç sayfasını gözden geçirin ##

Microsoft Flow’un [başlangıç sayfasında](https://flow.microsoft.com), [çok çeşitli şablonları keşfedebilir](https://flow.microsoft.com/templates) ve Microsoft Flow’un bazı temel özellikleri hakkında bilgi edinebilirsiniz. Microsoft Flow ile neler yapabileceğiniz ve Microsoft Flow'un işinizi ve hayatınızı nasıl kolaylaştırabileceği hakkında hızlı bir fikir edinebilirsiniz.

Microsoft Flow ile yapabilecekleriniz:

- Kolayca şablonları ve hizmetleri arama.

    ![Akış başlangıç sayfası 1](./media/getting-started/flowhome1.png)

- En popüler hizmetler arasından seçim yapma.

    ![Akış başlangıç sayfası 2](./media/getting-started/flowhome2.png)

- Her akışa yönelik bir genel bakışı görüntüleme.

    ![Akış başlangıç sayfası 3](./media/getting-started/flowhome3.png)

Her şablon belirli bir amaç için tasarlanmıştır. Örneğin, patronunuzdan e-posta geldiğinde size kısa mesaj göndermeye, Twitter’daki potansiyel müşterileri Dynamics 365’e eklemeye veya dosyalarınızı yedeklemeye yönelik şablonlar vardır. Bu şablonlar buz dağının görünen ucudur. Bunlar tam da ihtiyaç duyduğunuz süreçler için özelleştirilmiş akışlar oluşturmanız amacıyla ilham vermek için tasarlanmıştır.

## <a name="create-your-first-flow"></a>İlk akışınızı oluşturma ##

1. Sizin için kullanışlı olan bir şablon seçin. Örneğin, [**E-postayla günlük anımsatıcılar alın**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/) basit bir şablondur:

    ![günlük anımsatıcı şablonu](./media/getting-started/template-details.png)

1. **Devam**’ı seçin.

    ![Bağlantı oluşturma](./media/getting-started/create-connection.png)

1. Günlük anımsatıcının gönderileceği e-posta adreslerini girin. Ardından, anımsatıcı iletisini girin. Son olarak, **Akış oluştur**'u seçin ve ardından akışınızın beklendiği gibi çalıştığını doğrulayın.

    ![Bağlantı için kimlik bilgilerini sağlayın](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > Akışı tetikleyen koşulları ve bu olayın sonucunda oluşan eylemi keşfedebilirsiniz. Akışı kendinize göre özelleştirmek için ayarlarla oynayabilirsiniz. Hatta eylemler ekleyebilir veya silebilirsiniz.

1. **Bitti**’yi seçin.

Şablonlardan akışlar oluşturma hakkında daha fazla bilgi edinmek için [bu öğreticiyi izleyin](get-started-logic-template.md).

## <a name="get-creative"></a>Yaratıcı olun ##

Bir şablondan ilk akışınızı oluşturduğunuza göre, [sıfırdan kendi akışlarınızı oluşturmak](get-started-logic-flow.md) için Microsoft Flow’un desteklediği [150’den fazla veri kaynağından](https://flow.microsoft.com/connectors/) herhangi birini kullanabilirsiniz.

![Akış oluşturma](./media/getting-started/build-a-flow.png)

Sıfırdan bir akış oluşturduğunuzda, iş akışının tamamını denetlersiniz. Başlamanız için birkaç fikir:

- [Çok adımlı akışlar](multi-step-logic-flow.md).
- [Görevleri bir zamanlamaya göre çalıştırma](run-scheduled-tasks.md).
- [Bir onay akışı oluşturma](wait-for-approvals.md).
- [Akışı çalıştırılırken izleme](see-a-flow-run.md).
- [Şablon yayımlama](publish-a-template.md).
- [Bir Microsoft Teams şablonundan akışlar oluşturma](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Koda göz atma

Akış oluşturmak için geliştirici olmanız gerekmez. Bununla birlikte Microsoft Flow akıştaki tüm eylemler ve tetikleyiciler için oluşturulan koda daha yakından bakmanızı sağlayan bir **Koda göz at** özelliği sağlar. Koda göz atmak, tetikleyiciler ve eylemler tarafından kullanılan verileri daha net anlamanızı sağlayabilir. Microsoft Flow tasarımcısının içinden sizin için oluşturulan koda göz atmak için şu adımları izleyin: 

1. Herhangi bir **eylemin** veya **tetikleyicinin** sağ üst köşesindeki **...** menü öğesini seçin. 
1. **Koda göz at**'ı seçin.

    ![Koda göz at](media/getting-started/peek-code.png)

1. Eylemlerin ve tetikleyicilerin tam JSON gösterimine dikkat edin. Doğrudan girdiğiniz metinler gibi tüm girişleri ve kullanılan ifadeleri içerir. Burada ifadeleri seçebilir ve ardından bunları **Dinamik İçerik** ifade düzenleyicisine yapıştırabilirsiniz. Bu size beklediğiniz verilerin akışta var olduğunu doğrulamanın da bir yolunu sağlar.

    ![Koda göz at](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Akışlarınızı kolayca bulma

Yaratıcılığınız harekete geçip fikirler *akmaya* başladığında birçok akış oluşturabilirsiniz. Kaygılanmayın, akışlarınızı kolayca bulabilirsiniz. **Akışlarım**, **Ekip akışları**, **Bağlantılar** veya **Çözümler** ekranın arama kutusunu kullanıp yalnızca girdiğiniz arama terimleriyle eşleşen akışları görüntülemeniz yeterli olur.

![Akışları filtreleme veya arama](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> Arama filtresi yalnızca sayfaya yüklenen akışları bulur. Akışınızı bulamazsanız, sayfanın alt kısmında **Daha fazla yükle**'yi seçin.

## <a name="get-notifications-when-somethings-wrong"></a>Bir şeyler yanlış gittiğinde bildirim alma

Son zamanlarda başarısız olan akışların listesini hızla görmek için Microsoft Flow bildirim merkezini (tasarımcının sağ üst kısmında yer alır) kullanın. Bildirim merkezinde son zamanlarda başarısız olan akışların sayısını gösteren bir sayı görüntülenir.

Son zamanlarda çalıştırılmış, bildirim göndermiş veya başarısız olmuş tüm akışlarınızı görmek için bildirim merkezinde Microsoft Flow'un **Etkinlik** sayfasına gidebilirsiniz.

![Bildirim merkezi](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Mobil uygulamayı kullanma ##

[Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulamasını indirin. Bu uygulama ile [akış etkinliğini izleyebilir](mobile-monitor-activity.md), [akışlarınızı yönetebilir](mobile-manage-flows.md) ve [şablonlardan akışlar oluşturabilirsiniz](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Size yardımcı olmak için buradayız ##

Microsoft Flow ile yapabileceklerinizi görmek için heyecanlanıyoruz ve mükemmel bir deneyim yaşadığınızdan emin olmak istiyoruz. Sorularınızı sormak ve fikirlerinizi paylaşmak için [destekli öğrenim](https://flow.microsoft.com/guided-learning/) öğreticilerimize göz atın ve [topluluğumuza katılın](http://go.microsoft.com/fwlink/?LinkID=787467). Herhangi bir sorunla karşılaşırsanız [destek ekibi ile iletişime geçin](http://go.microsoft.com/fwlink/?LinkID=787479).
