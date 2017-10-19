---
title: "Akışları bir zamanlamaya göre çalıştırma | Microsoft Docs"
description: "Akışları, bir zamanlamaya göre (örneğin, her gün veya her saat) çalıştırarak yinelenen görevleri otomatik hale getirin."
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/14/2017
ms.author: stepsic
ms.openlocfilehash: 1c36abb44be31795e7d458628cc7ec7483187f49
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="run-flows-on-a-schedule"></a>Akışları bir zamanlamaya göre çalıştırma
Bir veya daha fazla görevi gerçekleştiren (örneğin e-postayla rapor gönderme) bir akış oluşturma:

* günde, saatte veya dakikada bir kez
* belirttiğiniz bir tarihte
* belirttiğiniz sayıda gün, saat veya dakika geçtikten sonra

## <a name="create-a-recurring-flow"></a>Yinelenen akış oluşturma
1. [Microsoft Flow](https://flow.microsoft.com)’da oturum açın ve üst gezinti çubuğunda bulunan **Akışlarım**’ı seçin.
   
    ![Akışlarım seçeneği](./media/run-tasks-on-a-schedule/create-flow.png)
2. **Boş akış oluştur**’u seçin.
   
    ![Boş akış oluşturma](./media/run-tasks-on-a-schedule/create-from-blank.png)
3. **Tüm bağlayıcıları ve tetikleyicileri ara** kutusuna **Yinelenme** yazın ve **Zamanlama - Yinelenme**’yi seçin.
   
    ![Yinelenme tetikleyicisini bulma](./media/run-tasks-on-a-schedule/select-recurrence.png)
4. **Yinelenme** iletişim kutusunda, akışın ne sıklıkla çalıştırılmasını istediğinizi belirtin.
   
    Örneğin, akışın iki haftada bir çalıştırılmasını istiyorsanız **Aralık** için **2** seçeneğini ve **Sıklık** için **Hafta** seçeneğini belirtin.
   
    ![Yinelenmeyi belirtme](./media/run-tasks-on-a-schedule/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Gelişmiş seçenekleri belirtme
1. Önceki bölümdeki adımları izleyin ve **Gelişmiş seçenekleri göster**’i seçin.
   
    **Not**: Bu seçenekler **Aralık** ve **Sıklık** için ayarlanan değerlere göre değişir. Ekranınız aşağıdaki grafikle eşleşmiyorsa, **Aralık** ve **Sıklık** öğelerinin grafikte gösterilen değerlerle eşleştiğinden emin olun.
2. **Başlangıç saatinin** yerel bir saat dilimini, Evrensel Eşgüdümlü Saati (UTC) vb. yansıtıp yansıtmayacağını belirtmek için bir **Saat dilimi** seçin.
3. Aşağıdaki biçimde bir **Başlangıç saati** belirtin:
   <br>YYYY-MM-DDTHH:MM:SSZ
4. **Sıklık** bölümünde **Gün** seçeneğini belirttiyseniz, akışın günün hangi saatinde çalıştırılacağını belirtin.
5. **Sıklık** bölümünde **Hafta** seçeneğini belirttiyseniz, akışın haftanın hangi gününde veya günlerinde ve günün hangi saatinde veya saatlerinde çalıştırılacağını belirtin.
   
    Örneğin, 1 Ocak 2018 Pazartesi tarihinde öğlen saatinden (Pasifik saati) önce başlamayacak bir akış belirtmek ve iki haftada bir Salı günleri 17:30’da (Pasifik saati) akışı çalıştırmak için seçenekleri gösterildiği gibi yapılandırın.
   
    ![Gelişmiş seçenekleri belirtme](./media/run-tasks-on-a-schedule/advanced-options.png)
6. Akışın almasını istediğiniz eylemi veya eylemleri, [Sıfırdan akış oluşturma](get-started-logic-flow.md) bölümünde açıklandığı şekilde ekleyin.

## <a name="delay-a-flow"></a>Bir akışı geciktirme
1. [Microsoft Flow](https://flow.microsoft.com)’da oturum açın ve üst gezinti çubuğunda bulunan **Akışlarım**’ı seçin.
   
    ![Boş akış oluşturma](./media/run-tasks-on-a-schedule/create-flow.png)
2. **Boş akış oluştur**’u seçin.
   
    ![Boş akış oluşturma](./media/run-tasks-on-a-schedule/create-from-blank.png)
3. [Sıfırdan akış oluşturma](get-started-logic-flow.md) bölümünde açıklanan şekilde, bir olay belirtin.
4. **Yeni adım**'ı ve ardından **Eylem ekle**'yi seçin.
   
    ![Akışa eylem ekleme seçeneği](./media/run-tasks-on-a-schedule/add-action.png)
5. Eylemler listesinde şunlardan birini yapın:
   
   * **Gecikme**’yi seçin, bir **Sayı** belirtin ve saniye, dakika veya saat gibi bir **Birim** belirleyin.
   * **Geciktir:** öğesini seçin ve ardından bu biçimde bir tarih belirtin.<br>YYYY-MM-DDTHH:MM:SSZ
     
     ![Gecikme ekleme](./media/run-tasks-on-a-schedule/add-delay.png)
     ![Gecikme süresini saat birimleriyle belirtme](./media/run-tasks-on-a-schedule/delay.png)
     ![Gecikme belirtme](./media/run-tasks-on-a-schedule/delay-until.png)

