---
title: Masaüstü Kullanıcı arabirimi akışlarında giriş ve çıkışları kullanma | Microsoft Docs
description: Masaüstü Kullanıcı arabirimi akışlarında girişleri ve çıkışları kullanın.
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
ms.openlocfilehash: 88bea3b8a038c01360fc5f3e61dbf30599b5deba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589777"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Masaüstü Kullanıcı arabirimi akışlarında girişleri ve çıkışları kullanma

[Bu konu ön sürüm belgesidir ve değişikliğe tabidir.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs"></a>Girişleri tanımlama

Girişler, bir veritabanı veya desteklenen herhangi bir bağlayıcı gibi bir dış kaynaktan, Kullanıcı arabirimi akışlarının otomatikleştirtığı eski yazılımlara bilgi geçirmenize olanak sağlar.

Örneğin, eski muhasebe yazılımınızdan giriş için bir SharePoint listesindeki müşteri bilgilerini bir kaynak olarak kullanabilirsiniz.

### <a name="define-inputs-in-the-ui-flows-wizard"></a>UI akışları sihirbazında giriş tanımlama

1. "Yeni giriş" i seçin

   ![](../media/inputs-outputs-desktop/2eb6313a0e966f1fbfc352445b89ee39.png)

1. Girişe bir ad, örnek veri ve açıklama ekleyin.

    - Örnek veriler, kayıt veya test sırasında kullanılır.

    - Açıklama, oluşturduğunuz girdileri ayırt etmek için yararlı olacaktır.

   ![](../media/inputs-outputs-desktop/e33d206bf2158228277a276261c49785.png)

1.  Girdlarınız oluşturulduktan sonra, bir kayıtta kullanmak için ileri ' ye tıklayabilirsiniz.

### <a name="use-inputs-to-pass-information-to-the-application"></a>Uygulamaya bilgi geçirmek için girişleri kullanma

1. Kayıt sırasında **girişi kullan**' ı seçerek bir uygulamadaki girişi kullanabilirsiniz.

1. Listede üç seçenekten birini seçebilirsiniz:

    - UI akışlarında tanımladığınız girdilerden birini seçin ' **giriş alanlarını ayarlama** adımı.

    - Önceden tanımlanmış bir çıkış kullanın (bkz. çıktılar bölümü). Bu, aynı kullanıcı arabirimi akışındaki farklı uygulamalar arasında bilgi geçirmek için kullanışlıdır.

    - Kaydettiğiniz gibi yeni bir giriş oluşturun. Kullanıcı arabirimi akışları ' nda **giriş alanlarını ayarlama** adımını geri görürsünüz.

   ![](../media/inputs-outputs-desktop/de36baa0f85d5a19304e1606de25aa3e.png)

1. Girişi kullanmak istediğiniz konumu seçin. Tanımladığınız örnek değer otomatik olarak kullanılır. Aşağıdaki örnekte "Hello World", "input" giriş adının örnek değeridir ve Microsoft Word içindeki sayfaya eklenir.  
    
    ![](../media/inputs-outputs-desktop/d6b74dc86f38c51cf1daa0582ff0cc33.png)

1. Power otomatikleştir **kaydı ve düzenleme adımları**' nda, seçili olanı görüntülemek için girdileri kullanan eylemler ' i genişletin.

   ![](../media/inputs-outputs-desktop/340aa71942b618431b0455b632f76f52.png)

1. UI akışınızı tetiklendiğinde, ' de giriş değerini değiştirebilirsiniz. Daha fazla bilgi için bkz. girdileri & çıkışları kullanma.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Uygulamadan bilgi ayıklamak için çıkışları kullanın

Çıktılar, Kullanıcı arabirimi akışlarının, veritabanı veya desteklenen herhangi bir [bağlayıcı](https://flow.microsoft.com/connectors/)gibi bir dış hedefe otomatik olarak otomatikleştiren eski yazılımlardan bilgi iletmenizi sağlar.

Örneğin, eski muhasebe yazılımlarınızın müşteri bilgilerini ayıklayabilir ve bunu bir SharePoint listesine ekleyebilirim.

Çıktılar yalnızca, UI akışınızı kaydederken oluşturulabilir.

1. Kayıt sırasında, kaydedici "çıktıyı al" düğmesini seçin

   ![](../media/inputs-outputs-desktop/13f8dfca19c0ed04ca2a0f87bf7055ea.png)

1. "Metin Seç" düğmesini seçin (Şu anda kullanılabilir olan tek çıktı türüdür)

   ![](../media/inputs-outputs-desktop/2845b73ee807a5be747c1dc494570ab7.png)

1. Çıktının metnini seçmek için bir kullanıcı arabirimi öğesine tıklayın. Değer otomatik olarak yakalanacaktır.

   ![](../media/inputs-outputs-desktop/7df19b56aadcd0aef207c7372a04b3c6.png)

   ![](../media/inputs-outputs-desktop/af55a0bf39d805b154a783eff3de131b.png)

1. Çıkışın adını ve açıklamasını tanımlayın.

   ![](../media/inputs-outputs-desktop/a083579ee011dfb76aa21fac116796a3.png)

1. Kaydet ' i seçin **.** 

Çıktılarınız artık sihirbazın adanmış alanında kullanılabilir

   ![](../media/inputs-outputs-desktop/b9f396de0b5893c5a3152b592911f67a.png)

Her bir çıktı şunları içerir:

-  Kayıt sırasında tanımlanan bir çıkış adı
-  Açıklama: Bu alan, bir kayıt sırasında çok sayıda çıkış tanımladığınızda ve bunları kolayca tanımlamak istediğinizde çok yararlı olabilir.
-  Bir eylem adı: çıktının Kullanıcı arabirimi akışında tanımlandığı eylem

## <a name="delete-an-output-from-a-ui-flow"></a>Bir kullanıcı arabirimi akışından çıkış silme

Artık çıktıya ihtiyacınız yoksa, ilişkili eyleme dönüp ve çıkış adını dinamik değerde kaldırarak silebilirsiniz.

## <a name="test-your-ui-flow"></a>UI akışınızı test etme

UI akışlarını test etmek, değişikliklerinizi ve uygun kayıttan yürütme davranışını doğrulamanızı sağlar.

1. Seçim Giriş alanına yeni bir değer girin. 
    
    ![](../media/inputs-outputs-desktop/0b4aef639c4ab30b93413e1e7a5e662d.png)

1. Eski yazılımı otomatik olarak görmek için **Şimdi sına** ' ya tıklayın. UI Flow Otomasyonu, kaydettiğiniz adımları geri oynadığını görürsünüz. **Lütfen kayıttan yürütme süresince cihazlarınızla etkileşim kurun.**

1. Kayıttan yürütme tamamlandıktan sonra UI akışınız için yürütme durumunu görürsünüz:

    - Her eylem için, testin düzgün çalıştığını ve ilişkili girişleri belirten bir durum.

    - Bu test için elde edilen çıktıların değeri.

    - Bir hata üretilme durumunda, hatanın oluştuğu andaki bir ekran görüntüsü ile hangi adımın soruna neden olduğunu görebileceksiniz.

   ![](../media/inputs-outputs-desktop/85056d7942d12a5408005f5b683d432b.png)

## <a name="learn-more"></a>Daha fazla bilgi edinin

- Az önce oluşturduğunuz [Kullanıcı arabirimi akışını nasıl tetikleyeceğinizi](run-ui-flow.md) öğrenin.

- UI akışlarıyla daha fazlasını yapmak istiyorsanız, [giriş ve çıkış](inputs-outputs-web.md) parametreleriyle Kullanıcı arabirimi akışlarını da deneyebilirsiniz.


