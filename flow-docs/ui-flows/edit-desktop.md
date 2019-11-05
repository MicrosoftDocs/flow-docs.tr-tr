---
title: Masaüstü Kullanıcı arabirimi akışlarını düzenlemeyi öğrenin | Microsoft Docs
description: Masaüstü Kullanıcı arabirimi akışlarını düzenlemeyi öğrenin.
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d5b7e186ae5c644f00f57946fff5ef3e946ba2ba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589832"
---
# <a name="edit-desktop-ui-flows"></a>Masaüstü Kullanıcı arabirimi akışlarını düzenleme

[Bu konu ön sürüm belgesidir ve değişikliğe tabidir.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Masaüstü Kullanıcı arabirimi akışları Windows masaüstü uygulamalarını otomatikleştirin. Karşılaşabileceğiniz sorunlar, bu sorunlara yönelik geçici çözümler ve bu önizleme sürümünde desteklenmeyen senaryolar hakkında daha fazla bilgi edinmek için lütfen [bilinen sorunlara](create-desktop.md#known-issues-and-solutions) bakın.

## <a name="prerequisites"></a>Kaynakları
Masaüstü Kullanıcı arabirimi akışı. Düzenlemek için bir tane yoksa, [Şimdi bir masaüstü UI akışı oluşturun](create-desktop.md#create-and-test-desktop-ui-flows) .

## <a name="edit-actions"></a>Eylemleri Düzenle

![Eylemleri Düzenle](../media/edit-desktop/edit-actions.png "Eylemleri Düzenle")

Kaydınızı şu şekilde düzenleyebilirsiniz:

-   Bunu destekleyen eylemler için değeri değiştirin.
-   Bir adımı silin.
-   Kaydın tamamını silin.
-   Sürükle ve bırak ile eylemlerin sırasını değiştirin. Kaydınızın tutarlılığını bozulabileceği için bununla ilgili dikkatli olun.

Gelişmiş parametreler şunları değiştirmenize izin verir:

-  Eylem gerçekleştirildikten sonra gecikme. Örneğin, PT0S ile PT1S arasında bir saniye erteleyerek tek bir gecikme ekleyebilirsiniz. Bu, hedef uygulamanın, Kullanıcı arabirimi akışının bir sonraki adımından önce tamamlanmamış bir yanıt süresi olduğunda yararlı olabilir.
-   Hedef kullanıcı arabirimi öğesi için [seçici](edit-desktop.md#set-the-selector) .

## <a name="add-a-recording"></a>Kayıt ekleme

UI akışınızı birden çok oturumda kaydetmek isteyebilirsiniz. İlk kaydınızı tamamladıktan sonra aşağıdaki gibi ilerleyebilirsiniz:

1. [Power otomatikleştirmede](https://flow.microsoft.com)oturum açın.
1. **Akışlarım** > **Kullanıcı arabirimi akışları (Önizleme)** seçeneğini belirleyin.
1. Düzenlemek istediğiniz UI akışını seçin.
   ![](../media/edit-desktop/select-ui-flow.png)
1. **Düzenle**' yi seçin. 
1. **Yeni adım**' ı seçin.

   ![Yeni adım](../media/edit-desktop/new-step.png "Yeni adım")

1. Eylem listesinden **uygulamayı kaydet** ' i seçin.

   ![Uygulamayı Kaydet](../media/edit-desktop/select-record-ui-actions.png "Uygulamayı Kaydet")

1. **Kaydediciyi Başlat**' ı seçin.

   ![Kaydı Başlat 'ı seçin](../media/create-windows-ui-flow/select-launch-recorder.png "Kaydı Başlat 'ı seçin")

   Kaydedici denetimi ekranınızın en üstünde görüntülenir.

   ![Kaydedici denetimi](../media/create-windows-ui-flow/recorder-control.png "Kaydedici denetimi")

1. Kaydetmek istediğiniz uygulamayı başlatın.

     >[!TIP]
     >Farenize uygulamada denetimlerin üzerine gittiğinde, mavi bir ana hattın her bir denetimi vurguladığına dikkat edin. Bir denetim seçmeden önce her zaman mavi vurgu bekle.
     >
     >Mavi vurgu öğe etrafında görünmezse, düzgün şekilde kaydedilmeyebilir.

1. Kaydedici denetiminden **kayıt** ' ı seçin.

1. Kaydettiğiniz uygulamanın kullanıcı arabirimindeki adımları gerçekleştirin ve ardından kaydedici denetiminde **bitti** ' yi seçin.
1. **Kaydet**' i seçin ve ardından UI akışınızı test edin.

## <a name="add-a-manual-action"></a>El ile eylem ekleme

Bir uygulamayı en az bir eylemle kaydettikten sonra, bu uygulama için aşağıdaki eylemlerden herhangi birini el ile ekleyebilirsiniz.

| **Ön**          | **Açıklamanın**                                                       |
|---------------------|-------------------------------------------------------------------|
| Uygulamayı kapat   |                                                                   |
| Sağ tıklama         |                                                                   |
| Anahtarları gönder           | CTRL + C gibi anahtarlar ve tuş bileşimleri gönderin.                             |
| Sol tıklama          |                                                                   |
| Metin al            | Bir kullanıcı arabirimi öğesinden metni okuyup çıkış olarak kullanın. |
| Metin girin          |                                                                   |
| Get öğesi etkin | Bir kullanıcı arabirimi öğesinin etkin veya devre dışı olup olmadığını denetle.         |
| Clear öğesi       | Düzenlenebilir bir kullanıcı arabirimi öğesindeki değeri temizleyin.             |
| Saniye bekle    | Sonraki adıma geçmeden önce bekleyin.                           |

El ile eylem eklemek için aşağıdaki adımları izleyin:

1. [Power otomatikleştirmede](https://flow.microsoft.com)oturum açın.
1. **Akışlarım** > **Kullanıcı arabirimi akışları (Önizleme)** seçeneğini belirleyin.
1. Düzenlemek istediğiniz UI akışını seçin.
   ![](../media/edit-desktop/select-ui-flow.png)
1. **Düzenle**' yi seçin. 
1. Yeni adım eklemek istediğiniz adımları içeren kayıt kartını seçin.
   Kart genişletilir ve kaydedilen adımları görüntüler.

   ![Kayıt kartını seçin](../media/edit-desktop/manual-select-recording-card.png)

1. Kayıt kartında, son kaydedilen adımın hemen altındaki **Eylem Ekle** ' yi seçin.
   Daha önce izlenecek yolda listelenen el ile eylemlerin listesini görürsünüz. 

1. Eklemek istediğiniz eylemi seçin. Burada, **Get öğesi etkin**seçeneğini seçtim, ancak senaryonuz için anlamlı olan herhangi bir eylemi seçebilirsiniz.

   ![. Png eklemek için eylem seçin](../media/edit-desktop/select-action-to-add.png)

Eylem eklendikten sonra, eylemin gelişmiş seçeneklerinde **seçiciyi** ayarlamanız gerekecektir.

![Eylem Gelişmiş Seçenekler](../media/edit-desktop/action-advanced-options.png "Eylem Gelişmiş Seçenekler")

### <a name="set-the-selector"></a>Seçiciyi ayarla

Seçici, kayıttan yürütme sırasında eylemin gerçekleştirileceği Kullanıcı arabirimi öğesini tanımlar. Mümkünse, bu bilgileri aynı kullanıcı arabirimi öğesini hedefleyen ayrı bir adımdan kopyalamanız/yapıştırmanız önerilir.

Seçicinin biçimi:

```json
{  
   "type":"WinUIA",
   "parameters":{  
      "elementStack":[  

      ],
      "elementXPath":""
   }
}
```

Seçici öğesinin **Elemementstack** ve **elementxpath** alanları için verileri sağlamanız gerekir.

İşte, **Elemementstack** 'in nasıl görünebileceğini bir örnektir.

![Öğe yığını](../media/edit-desktop/elementstack.png "Öğe yığını")

**Elementxpath** 'ı [WINAPPDRIVER UI kaydedicisini](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/)kullanarak yakalayabilirsiniz.

![WAD aracı](../media/edit-desktop/wad-tool.png "WAD aracı")

Seçicinin **Elementxpath** öğesinde sonucu kullanmadan önce ilk öğeyi (/Window 'tan önceki her şey) kaldırın.

Seçicinizi doğru bir şekilde çalıştığına emin olmak için UI akışınızı test edin.

## <a name="next-steps"></a>Sonraki adımlar

- Yeni düzenlediğiniz [Kullanıcı arabirimi akışını nasıl çalıştıracağınızı](run-ui-flow.md) öğrenin.

- UI akışlarıyla daha fazlasını yapmak istiyorsanız, [giriş ve çıkış](inputs-outputs-web.md) parametreleriyle Kullanıcı arabirimi akışlarını da deneyebilirsiniz.

