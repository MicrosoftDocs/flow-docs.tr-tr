---
title: Diğer Akışlardan Kullanıcı arabirimi akışlarını çalıştırma | Microsoft Docs
description: Diğer Akışlardan Kullanıcı arabirimi akışlarını çalıştırma
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
ms.openlocfilehash: 275ef331d37ff83d8890b4b6ddd750dc038dd099
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589745"
---
# <a name="run-ui-flows"></a>UI akışlarını çalıştırma

[Bu konu ön sürüm belgesidir ve değişikliğe tabidir.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Bir UI akışını oluşturup test ettikten sonra, bunu bir olay, zamanlama veya düğmeden çalıştırabilirsiniz. Bunu mümkün kılmak için, Kullanıcı arabirimi akışınızı [otomatik bir akışa](../get-started-logic-flow.md), [düğme akışına](../introduction-to-button-flows.md), [Zamanlanmış bir akışa](../run-scheduled-tasks.md)veya [iş süreci akışına](../business-process-flows-overview.md)ekleyin.

## <a name="prerequisites"></a>Kaynakları

- Cihazınız için şirket [içi veri ağ geçidinin](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409) , Power OTOMATIKLEŞTIRMEDE Kullanıcı arabirimi akışını tetiklenmesi gerekir.
   
   Ağ Geçidi, güç otomatikleştirme ve cihazınız (UI akışlarınızın çalıştırıldığı) arasında kurumsal düzeyde güvenli bir bağlantıdır. Power otomatikleştirmek, şirket içi cihazınıza erişmek için ağ geçidini kullanarak bir olay, zamanlama veya düğmeden Kullanıcı arabirimi akışlarınızı tetikleyebilmenizi sağlar.
- Bir iş veya okul hesabı. 

   >[!IMPORTANT]
   >Ağ geçidini kurmak, Power otomatikleştirmede oturum açmak ve Windows cihazınızda oturum açmak için aynı iş veya okul hesabını kullanmanız gerekir.
   

## <a name="run-your-ui-flow-from-an-event-button-schedule-or-business-process-flow"></a>Kullanıcı arabirimi akışınızı bir olay, düğme, zamanlama veya iş süreci akışından çalıştırın

Bu örnekte, yeni bir e-posta geldiğinde bir UI akışını tetiklemek için otomatik bir akış kullanacağız.

1. [Power otomatikleştirmek](https://flow.microsoft.com/)' a gidin.
1. Sol gezinti çubuğunda **Akışlarım** ' ı seçin.
1. **Yeni**' yi ve ardından boş ' ı seçerek **Otomatik**' i seçin.

   >[!TIP]
   >Gereksinimlerinize uyacak başka bir akış türü seçebilirsiniz.

1. Flow **adı** kutusuna akışınıza bir ad verin.
1. "Yeni e-posta" araması yapın ve ardından tetikleyiciler listesinden **Yeni bir e-posta geldiğinde (v3)** seçeneğini belirleyin. 
    
   ![Tetikleyici seçin](../media/run-ui-flow/2d4ec17d239169a46905cef1829fa3a1.png "Tetikleyici seçin")

1. **Oluştur**' u ve ardından **yeni adım**' ı seçin.

1. **UI akışlarını**arayın ve ardından **Eylemler**listesinden **Masaüstü Için bir kullanıcı arabirimi akışı Çalıştır** ' ı seçin. 

   ![Arama eylemi](../media/run-ui-flow/search-action.png "Arama eylemi")

1. Ağ Geçidi bilgilerini ve cihaz kimlik bilgilerini sağlayın. 

   Bunu cihaz başına bir kez yapmanız gerekir:

    - **Bağlantı adı**: cihazın akış bağlantısı için bir ad seçin. Ağ Geçidi adından farklı olabilir.
    - **Kullanıcı adı**: cihazınızın iş veya okul hesabını belirtin.
    - **Kimlik doğrulama türü**: Windows ' u seçin.
    - **Parola**: iş veya okul hesabınızın parolası.
    - **Ağ geçidi**: yükleme sırasında oluşturduğunuz ağ geçidini seçin.

      ![Bağlantı ayarları](../media/run-ui-flow/connection-settings.png "Bağlantı ayarları")

      >[!TIP]
      >Ağ geçidinizin görmüyorsanız, farklı bir bağlantı seçmeniz gerekebilir. Bunu yapmak için, **Masaüstü IÇIN UI Flow (Önizleme) kartını Çalıştır** ' ın sağ üst tarafındaki **...** seçeneğini belirleyin ve **bağlantılarım**' dan kullanmak istediğiniz bağlantıyı seçin.

      ![Yeni bir bağlantı seçin](../media/run-ui-flow/select-new-connection.png "Yeni bir bağlantı seçin")

1. Daha önce oluşturduğunuz Kullanıcı arabirimi akışını seçin.

   ![UI akışını seçin](../media/run-ui-flow/select-ui-flow.png "UI akışını seçin")

1. Otomatik akışınızı kaydetmek için **Kaydet** ' i seçin.

1. Bunu tetiklemek için bir e-posta göndererek akışınızı test edin. Kullanıcı arabirimi akışınızı kaydettiğiniz adımları geri oynadığını görürsünüz. 

![Bir UI akışını çağıran başarılı çalıştırma](../media/run-ui-flow/successful-run.png "Bir UI akışını çağıran başarılı çalıştırma")

>[!TIP]
>Akış çalışırken cihazlarınızla etkileşime geçin.

## <a name="use-inputs-and-outputs"></a>Girişleri ve çıkışları kullanma

Bir UI akışı içinde giriş ve çıkış tanımladığınızda, ve bu girişlere bilgi geçirebilirsiniz.

1. Bir akışa bir kullanıcı arabirimi akışı eklediğinizde, UI akışında tanımlanan girişlerin listesini görebilirsiniz.

   ![UI akış girişleri](../media/run-ui-flow/inputs.png "UI akış girişleri")

1. Kullanıcı arabirimi akışındaki her giriş alanını akıştaki önceki adımlardan alınan değerlerle doldurabilirsiniz. Bunu yapmak için, giriş alanını seçin ve ardından belirteç seçicisinden bir giriş seçin.


1. Akışta daha sonra görünen eylemler için giriş olarak UI akışınızdan çıktılar de kullanabilirsiniz. Bunu yapmak için, giriş alanını seçin ve ardından belirteç seçicisinden bir giriş seçin.

## <a name="limitations-and-known-issues"></a>Sınırlamalar ve bilinen sorunlar

- Ağ Geçidi kümeleri desteklenmez.
- ABD dışı (QWERTY) klavyeler bu yeniden kiralamasında desteklenmediğinden, anahtar sırasının ABD dışı (QWERTY) klavyeden kaydedildiği bir giriş adımının yürütülmesi ABD 'deki (QWERTY) anahtar konturlarına neden olur.

## <a name="learn-more"></a>Daha fazla bilgi edinin

 - Şirket [içi veri ağ geçidini](https://docs.microsoft.com/data-integration/gateway/service-gateway-app)yükler.
 - Şirket [içi veri ağ geçidi uygulaması belgelerini kullanın](https://docs.microsoft.com/flow/gateway-manage) .
 - Şirket içi veri ağ geçidinde [sorun giderin](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) .
