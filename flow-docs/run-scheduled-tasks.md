---
title: Akışları bir zamanlamaya göre çalıştırın | Microsoft Docs
description: Her gün veya saatte bir zamanlamaya göre akış çalıştırarak yinelenen görevleri otomatikleştirin.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/14/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b737f416c927e7d7d8a7ea28ec81e268aa59b51d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548840"
---
# <a name="run-flows-on-a-schedule"></a>Akışları bir zamanlamaya göre çalıştırma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Bir veya daha fazla görev gerçekleştiren bir akış oluşturun (örneğin, e-postada rapor gönderme):

* günde bir kez, saat veya dakika
* Belirttiğiniz tarihte
* Belirttiğiniz sayıda gün, saat veya dakika sonra

## <a name="create-a-recurring-flow"></a>Yinelenen akış oluşturma
1. [Microsoft Flow](https://flow.microsoft.com)oturum açın ve üst gezinti çubuğundaki **Akışlarım** ' ı seçin.
   
    ![Akışlarım seçeneği](./media/run-scheduled-tasks/create-flow.png)
2. **Boş oluştur**' u seçin.
   
    ![Boş bir akış oluşturun](./media/run-scheduled-tasks/create-from-blank.png)
3. **Tüm bağlayıcılar ve Tetikleyiciler ara** kutusuna **yinelenme**yazın ve ardından **zamanlama-yinelenme**' yi seçin.
   
    ![Yineleme tetikleyicisi bul](./media/run-scheduled-tasks/select-recurrence.png)
4. **Yinelenme** iletişim kutusunda akışın ne sıklıkta çalıştırılmasını istediğinizi belirtin.
   
    Örneğin, akışın her iki haftada bir çalışmasını istiyorsanız **Sıklık** altında **Aralık** ve **hafta** altında **2** değerini belirtin.
   
    ![Yinelenme belirtin](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Gelişmiş seçenekleri belirtin
1. Önceki bölümdeki adımları izleyin ve ardından **Gelişmiş seçenekleri göster**' i seçin.
   
    **Note**: Bu seçenekler, **Aralık** ve **Sıklık** değerinin ayarlandığı değerlere göre değişir. Ekranınız aşağıdaki grafikle eşleşmiyorsa, **Aralık** ve **Sıklık** değerlerinin grafiğin gösterdiği aynı değerlere ayarlandığından emin olun.
2. **Başlangıç zamanının** yerel saat dilimini, Evrensel Eşgüdümlü saatı (UTC) vb. yansıtmayacağını belirtmek Için bir **saat dilimi** seçin.
3. Bu biçimde bir **Başlangıç saati** belirtin:
   <br>YYYY-MM-DDTHH: MM: SSZ
4. **Sıklık**bölümünde **gün** belirttiyseniz, akışın çalıştırılacağı günün saatini belirtin.
5. **Sıklık**bölümünde **hafta** belirttiyseniz, akışın çalıştırılacağı haftanın günü veya günleri ve akışın çalıştırılacağı günün saati veya saatini belirtin.
   
    Örneğin, 4 Ocak 2018, Pazartesi günü (Pasifik saati) gece yarısı, 1 Ocak ve Salı günleri ' de her iki haftada bir akışı başlatmak için gösterilen seçenekleri yapılandırın: 30p (Pasifik saati).
   
    ![Gelişmiş seçenekleri belirtin](./media/run-scheduled-tasks/advanced-options.png)
6. [Sıfırdan bir akış oluşturmak](get-started-logic-flow.md) için akışın ele almak istediğiniz eylem veya eylemleri ekleyin.

## <a name="delay-a-flow"></a>Akışı geciktirme
1. [Microsoft Flow](https://flow.microsoft.com)oturum açın ve üst gezinti çubuğundaki **Akışlarım** ' ı seçin.
   
    ![Boş bir akış oluşturun](./media/run-scheduled-tasks/create-flow.png)
2. **Boş oluştur**' u seçin.
   
    ![Boş bir akış oluşturun](./media/run-scheduled-tasks/create-from-blank.png)
3. [Sıfırdan akış oluşturma](get-started-logic-flow.md) bölümünde açıklanan bir olay belirtin.
4. **Yeni adım**' ı seçin ve ardından **Eylem Ekle**' yi seçin.
   
    ![Akışa eylem ekleme seçeneği](./media/run-scheduled-tasks/add-action.png)
5. Eylemler listesinde aşağıdakilerden birini yapın:
   
   * **Gecikme**' yı seçin, bir **sayı**belirtin ve saniye, dakika veya saat **gibi bir süre** belirtin.
   * **Gecikme tarihine kadar geciktir**' ı seçin ve ardından bu biçimde bir tarih belirtin.<br>YYYY-MM-DDTHH: MM: SSZ
     
     ![gecikme](./media/run-scheduled-tasks/add-delay.png)
     eklemek ![zaman birimi](./media/run-scheduled-tasks/delay.png)
     gecikme belirtin ![](./media/run-scheduled-tasks/delay-until.png)

## <a name="learn-more"></a>Daha fazla bilgi edinin

[Gelişmiş Seçenekler](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) ve bunların nasıl yapılandırılacağı hakkında daha fazla bilgi edinin.

