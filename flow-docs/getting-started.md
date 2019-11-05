---
title: Kullanmaya başlayın | Microsoft Docs
description: Power otomatikleştirmek ile işinizi ve hayatınızı otomatik hale getirmeye başlamak için hızlı yollar
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/31/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 54d1478f34743b6059692b927da8baf2c49a35a7
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589846"
---
# <a name="get-started-with-power-automate"></a>Power otomatikleştirmek ile çalışmaya başlama

[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

<br>
<iframe width="1129" height="635" src="https://www.youtube.com/embed/hCuxuUaGC6Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Hoş geldiniz! Güç otomatikleştirme, dosyaları senkronize etmek, bildirimler almak, veri toplamak ve daha fazlası için sık kullandığınız uygulamalar ve hizmetler arasında otomatik iş akışları oluşturmanıza yardımcı olan bir hizmettir.

Ana akış türleri [Otomatik](get-started-logic-flow.md), [düğme](introduction-to-button-flows.md), [Zamanlanmış](run-scheduled-tasks.md)ve [iş süreci](business-process-flows-overview.md) akışıdır.

## <a name="types-of-flows"></a>Akış türleri

Güç otomatikleştirme, güç platformunun üç tek bir değerinden biridir. İş akışı ve süreç otomasyonu için düşük bir kod platformu sağlar. Farklı akış türlerinin listesi aşağıda verilmiştir:

| **Akış türü**                                                                       | **Kullanım örneği**                                                                                  | **Hedef**                                                                             |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| [Otomatik akışlar](get-started-logic-flow.md)                 | Bir olay tarafından tetiklendikten sonra bir veya daha fazla görevi otomatik olarak gerçekleştiren bir akış oluşturun. | Bulut veya şirket içi hizmetler için [Bağlayıcılar](https://docs.microsoft.com/connectors/) . |
| [Düğme akışları](introduction-to-button-flows.md)              | Dilediğiniz zaman, mobil cihazınız aracılığıyla herhangi bir yerde yinelenen görevleri çalıştırın.                        |                                                                                        |
| [Zamanlanan akışlar](run-scheduled-tasks.md)                    | Bir zamanlamaya göre bir veya daha fazla görev gerçekleştiren bir akış oluşturun.             |                                                                                        |
| [İş süreci akışları](business-process-flows-overview.md) | Kişilerin istedikleri sonuca gelmesi için takip etmek üzere bir adım kümesi tanımlayın.                 | İnsan süreçleriniz                                                                        |
| [UI akışları (Önizleme)](ui-flows/overview.md)                                                | Eski yazılımda el ile gerçekleştirilen adımların kayıttan yürütülmesini kaydedin ve otomatikleştirin.                    | Otomasyon için kullanılabilir API 'Ler bulunmayan masaüstü ve Web uygulamaları.    |

Power otomatikleştirmede **Akışlarım** sekmesinden tüm akışları oluşturabilir ve yönetebilirsiniz.

Dynamics 365 kullanıcısı kullanıyorsanız, [iş akışları](configure-workflow-steps.md), [Eylemler](create-actions.md), [mobil görev akışları](create-mobile-task-flow.md)ve [iletişim kutuları](use-cds-for-apps-dialogs.md)da dahil olmak üzere klasik Common Data Service işlemler hakkında bilgi sahibi olabilirsiniz.

İlk adım [kaydolup](sign-up-sign-in.md), Power otomatikleştirmeye sahip bir hesabınız zaten varsa tabletinizde, masaüstü bilgisayarınızda veya hatta telefonunuzda [oturum açın](https://flow.microsoft.com/signin) .

## <a name="check-out-the-start-page"></a>Başlangıç sayfasına göz atın ##

Power otomatikleştirmek için [Başlangıç sayfasında](https://flow.microsoft.com) , [farklı bir şablon kümesini araştırabilir](https://flow.microsoft.com/templates) ve Power otomatikleştirmek için önemli özellikler hakkında bilgi edinebilirsiniz. Mümkün olduğunca hızlı bir fikir edinebilirsiniz ve Power otomatikleştirmenin işletmenize ve hayatınızı nasıl yardımcı olduğunu öğrenin.

Power otomatikleştirmede şunları yapabilirsiniz:

- Şablonlar ve hizmetler için kolayca arama yapın.

    ![Akış başlangıç sayfası 1](./media/getting-started/flowhome1.png)

- En popüler hizmetler arasından seçim yapın.

    ![Akış başlangıç sayfası 2](./media/getting-started/flowhome2.png)

- Her bir akışa genel bakış konusuna bakın.

    ![Akış başlangıç sayfası 3](./media/getting-started/flowhome3.png)

Her şablon belirli bir amaç için tasarlanmıştır. Örneğin, patronunuzdan e-posta göndermek, Twitter 'nın Dynamics 365 ' e müşteri adayı eklemek veya dosyalarınızı yedeklemek için bir kısa mesaj göndermeye yönelik şablonlar vardır. Bu şablonlar yalnızca Iceberg 'nin ipucu. Bu kişiler, ihtiyacınız olan eksiksiz süreçler için özelleştirilmiş akışlar oluşturmanızı amaçlar.

## <a name="create-your-first-flow"></a>İlk akışınızı oluşturma ##

1. Sizin için yararlı olan bir şablon seçin. Basit bir şablon, [**e-posta ile günlük anımsatıcıları alır**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/):

    ![günlük anımsatıcı şablonu](./media/getting-started/template-details.png)

1. **Devam**' ı seçin.

    ![Bağlantı oluştur](./media/getting-started/create-connection.png)

1. Günlük anımsatıcının gönderileceği e-posta adreslerini girin. Sonra, anımsatıcı iletisini girin. Son olarak, **akış oluştur**' u seçin ve akışın beklendiği gibi çalıştığını doğrulayın.

    ![Bağlantı için kimlik bilgilerini girin](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > Akışı tetikleyen koşulları ve bu olayın sonucunda oluşan eylemi inceleyebilirsiniz. Akışın kendinizinkini oluşturmak için, ayarlarla birlikte oynayın. Hatta eylemler ekleyebilir veya silebilirsiniz.

1. **Bitti**' yi seçin.

Şablonlardan akış oluşturma hakkında daha fazla bilgi edinmek için [Bu öğreticiyi izleyin](get-started-logic-template.md) .

## <a name="get-creative"></a>Yaratıcı yararlanın ##

Bir şablondan ilk akışınızı oluşturduğunuza göre, [sıfırdan kendi akışlarınızı oluşturmak](get-started-logic-flow.md)Için Power otomatikleştirmenin desteklediği 150 'den fazla [veri kaynağından](https://flow.microsoft.com/connectors/) birini kullanın.

![Akış oluşturma](./media/getting-started/build-a-flow.png)

Sıfırdan bir akış oluşturduğunuzda, tüm iş akışını kontrol edersiniz. Başlamanızı sağlamak için birkaç fikir aşağıda verilmiştir:

- [Birçok adımla akar](multi-step-logic-flow.md).
- [Görevleri bir zamanlamaya göre çalıştırın](run-scheduled-tasks.md).
- [Bir onay akışı oluşturun](wait-for-approvals.md).
- [Bir akışı eylemde izleyin](see-a-flow-run.md).
- [Şablon yayımlayın](publish-a-template.md).
- [Microsoft ekipleri şablonundan akışlar oluşturun](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Koda göz atın

Akış oluşturmak için geliştirici olmanız gerekmez, ancak Power otomatikleştirmek, herkesin bir akıştaki tüm eylemler ve Tetikleyiciler için oluşturulan koda daha yakından bakabilen bir **kod Özeti** sağlar. Koda göz atma, Tetikleyiciler ve eylemler tarafından kullanılan veriler hakkında daha net bir fikir verebilir. Power otomatikleştir Tasarımcısı içinden akışlarınız için oluşturulan koda gözatmak için aşağıdaki adımları izleyin: 

1. Herhangi bir **eylemin** veya **tetikleyicinin**sağ üst köşesindeki **...** menü öğesini seçin. 
1. **Kodu Gözat**' ı seçin.

    ![Koda göz atın](media/getting-started/peek-code.png)

1. Eylemlerin ve tetikleyicilerin tam JSON gösterimine dikkat edin. Bu, doğrudan girdiğiniz metin ve kullanılan ifadeler gibi tüm girişleri içerir. Burada ifadeleri seçip **dinamik içerik** ifade düzenleyicisine yapıştırabilirsiniz. Bu, Ayrıca, seçtiğiniz verileri akışta doğrulamanızı sağlayacak bir yol da sağlayabilir.

    ![Koda göz atın](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Akışlarınızı kolayca bulun

Creative juıces *akışa başladığınızda*, birçok akış oluşturabilirsiniz. Endişelenmeyin, akışlarınızı bulmak kolaydır, yalnızca girdiğiniz arama terimleriyle eşleşen akışları göstermek için **Akışlarım**, **Takım akışları**, **Bağlantılar**veya **çözümler** ekranındaki arama kutusunu kullanın.

![Akışları filtreleme veya arama](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> Arama filtresi yalnızca sayfaya yüklenmiş olan akışları bulur. Akışınızı bulamazsanız sayfanın alt kısmında **daha fazla yükle** seçimini yapmayı deneyin.

## <a name="get-notifications-when-somethings-wrong"></a>Yanlış bir sorun olduğunda bildirim alın

Kısa süre önce başarısız olan akışların listesini hızlıca görmek için Power otomatikleştir bildirim merkezini (tasarımcının sağ üst kısmında bulunur) kullanın. Bildirim Merkezi, yakın zamanda başarısız olan akış sayısını belirten bir sayı görüntüler.

Bildirim merkezinden, son zamanlarda çalıştırılan, gönderilen bildirimler veya başarısız olan tüm akışlarınızı görmek için Power otomatikleştirmede **etkinlik** sayfasına gidebilirsiniz.

![Bildirim Merkezi](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Mobil uygulamayı kullanma ##

[Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)veya [Windows Phone](https://aka.ms/flowmobilewindows)için Power otomatikleştir mobil uygulamasını indirin. Bu uygulamayla, [akış etkinliğini izleyebilir](mobile-monitor-activity.md), [akışlarınızı yönetebilir](mobile-manage-flows.md) ve [şablonlardan akışlar oluşturabilirsiniz](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Yardımcı olmaya çalışıyoruz ##

Power otomatikleştirmede yapabileceklerinizi görmek için heyecanlıyız ve harika bir deneyiminizin olduğundan emin olmak istiyoruz. [Kılavuzlu öğrenme](https://flow.microsoft.com/guided-learning/) öğreticilerimize göz atın ve sorularınızı sormak ve fikirlerinizi paylaşmak için [topluluğumuza katılarak](https://go.microsoft.com/fwlink/?LinkID=787467) emin olun. Herhangi bir sorunla karşılaşırsanız [desteğe başvurun](https://go.microsoft.com/fwlink/?LinkID=787479) .
