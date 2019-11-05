---
title: Web siteleri için Kullanıcı arabirimi akışları oluşturmayı öğrenin | Microsoft Docs
description: Web uygulamalarını UI akışlarıyla otomatikleştirmeyi öğrenin.
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
ms.openlocfilehash: 010b6632a60f2c81c138fa98d850df79be814f68
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589873"
---
# <a name="create-and-test-your-web-ui-flows"></a>Web UI akışlarınızı oluşturma ve test etme

[Bu konu ön sürüm belgesidir ve değişikliğe tabidir.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Basit bir Web UI akışı oluşturmak için aşağıdaki adımları izleyin:

## <a name="create-a-web-ui-flow"></a>Web Kullanıcı arabirimi akışı oluşturma

1. Microsoft Edge veya Google Chrome ['un bir sonraki sürümünü](https://www.microsoftedgeinsider.com/) açın ve ardından [Power otomatikleştirmek](https://flow.microsoft.com/)' a gidin.

1. Gerekirse İş veya okul hesabınızla oturum açın.

1. **Akışlarımı** seçin > **UI akışları (Önizleme)**  > **Yeni**.

   ![Yeni UI akışı oluştur](../media/create-windows-ui-flow/create-new.png "Yeni UI akışı oluştur")

1. **Web uygulaması** > **İleri** Seç
    
   ![Web uygulaması Seç](../media/create-web-ui-flow/select-web-app.png "Web uygulaması Seç")

1. **Akış adı** alanına kullanıcı arabirimi akışınız için bir ad girin.

1. Otomatik hale getirmek istediğiniz Web sitesinin URL 'sini **temel URL** alanına girin ve ardından **kaydediciyi Başlat**' ı seçin.

   ![Bir ad ve URL sağlayın](../media/create-web-ui-flow/give-a-name.png "Bir ad ve URL sağlayın") 

   Selenium IDE başlatılır.

   >[!TIP] 
   >İpucu: aynı sekmede birden çok HTTP veya HTTPS Web sitesinde eylem kaydedebilirsiniz.  

1. Selenium IDE 'de, kaydediciyi başlatmak için ekranın sağ üst tarafındaki kırmızı **REC** düğmesini seçin.

   Önceki adımda seçtiğiniz URL açılır.

   ![Kay 'ı seçin](../media/create-web-ui-flow/select-rec.png "Kay 'ı seçin")

1.  Web sitesinde kaydetmek istediğiniz eylemleri gerçekleştirin. 
    
    >[!TIP]
    >Sağ alt köşedeki kayıt durumunu görebilirsiniz.

    ![Kayıt durumu](../media/create-web-ui-flow/recording-status.png "Kayıt durumu")

1.  Kaydetmeyi bitirdiğinizde Selenium IDE 'nin sağ üst köşesindeki kırmızı **Durdur** düğmesini seçin.

    ![Durdur düğmesi](../media/create-web-ui-flow/stop-button.png "Durdur düğmesi" )

1. Yeni oluşturduğunuz Kullanıcı arabirimi akışını görmek için ekranın sol üst tarafındaki **geçerli Testi Çalıştır** düğmesini seçin.

    ![Geçerli Testi Çalıştır](../media/create-web-ui-flow/run-test.png "Geçerli Testi Çalıştır")

   >[!TIP]
   >Test için Yerel kayıttan yürütmeyi yavaşlatacak adımlar arasında bekleme süresini ayarlayabilirsiniz. Bu ayar yalnızca test amaçlıdır ve Kullanıcı arabirimi akışınız dağıtıldığında hiçbir etkiye sahip değildir.  
  
1. Selenium IDE 'nin sağ üst köşesindeki **projeyi kaydet** düğmesini seçin. Bu kapanır ve ardından projeyi karşıya yükler.

Artık bir Web Kullanıcı arabirimi akışı oluşturduğunuza göre, diğer akışlarınızda bunu kullanın.

## <a name="limitations-and-known-issues-for-web-ui-flows"></a>Web UI akışları için sınırlamalar ve bilinen sorunlar

>[!WARNING]
>**Selenium IDE 'deki parolalar düz metin biçiminde depolanır.**  


**Yeni bir sürüm yüklendikten sonra, Kullanıcı arabirimi akışları artık Windows uygulamalarını kaydeder veya yeniden oynamıyor.**

Yenisini yüklemeden önce önceki sürümü kaldırmanız gerekir.

Bunun için, Başlat menüsünü açın, **ayarlar** > **uygulamalar**' a gidin, > uygulamalar listesinde **Kullanıcı arabirimi akışları** ' nı arayın ve ardından "Kaldır **" ' ı**seçin. Sihirbaz süreç boyunca size yol gösterecektir.

**Kayıttan yürütme için geçici kullanıcı profili**

Selenium IDE kayıtları, geçerli kullanıcının profiliyle yapılır, ancak kayıttan yürütme geçici bir kullanıcı profili kullanılarak yapılır. Bu, kimlik doğrulaması gerektiren Web sitelerinin bir kayıt oturumunda kimlik bilgileri istemebileceği, ancak kayıttan yürütme sırasında kimlik doğrulama adımlarının gerekli olacağı anlamına gelir. 

Bunu çözmek için, kullanıcının oturum açma işlemi için gerekli komutları eklemek üzere betiği el ile düzenlemesi gerekir.

**Diğer sınırlamalar**

-   Bir Web kaydı oturumu sırasında masaüstü uygulamalarını kaydetme. Hem Web hem de masaüstü uygulamalarını otomatikleştirmeniz gerekiyorsa, her tür için ayrı bir UI akışları oluşturabilir ve sonra bunları bir akışta birleştirebilirsiniz.

-   Multi-Factor Authentication (MFA) desteklenmiyor, MFA gerektirmeyen bir kiracı kullanın.

-   Bu Selenium IDE komutları desteklenmez: Run, AnswerOnNextPrompt, ChooseCancelOnNextConfirmation, ChooseCancelOnNextPrompt, ChooseOkOnNextConfirmation, Debugger, ClickAt, DoubleClickAt, Echo, MouseOut, MouseUpAt ve MouseDownAt.

-   Sağ tıklama desteklenmez. 

-   Foreach komutları kullandığınızda ek Web UI akış girişi oluşturulur. Bu sorunu geçici olarak çözmek için, ek alanlara herhangi bir değer girin. Kayıttan yürütmeyi etkilemez.

-   . SIDE dosyası birden çok test projesi içeriyorsa, yalnızca ilk oluşturulan ilki çalışır. 

     >[!TIP]
     >Selenium IDE 'nin testleri, oluşturma tarihine göre değil, ada göre sipariş eder, bu nedenle oluşturulan ilk test listedeki ilk bir durum olamaz.

-   Doğrudan Selenium IDE 'de kayıttan yürütme amaçlanan gibi davranmayabilir. Ancak, Kullanıcı arabirimi akış altyapısı aracılığıyla çalışma zamanında kayıttan yürütme doğru bir şekilde davranır.

## <a name="next-steps"></a>Sonraki adımlar

- [UI akışlarını çalıştırmayı](run-ui-flow.md)öğrenin.

- UI akışlarıyla daha fazlasını yapmak istiyorsanız, [giriş ve çıkış](inputs-outputs-web.md) parametreleriyle Kullanıcı arabirimi akışlarını da deneyebilirsiniz.

