---
title: Masaüstü Kullanıcı arabirimi akışları oluşturmayı öğrenin | Microsoft Docs
description: Windows uygulamaları için masaüstü UI akışları oluşturmayı öğrenin.
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
ms.openlocfilehash: e03b23387f5c3837b9b3f7e9ce023f8c31ce79a3
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589790"
---
# <a name="create-and-test-desktop-ui-flows"></a>Masaüstü Kullanıcı arabirimi akışları oluşturma ve test etme

[Bu konu ön sürüm belgesidir ve değişikliğe tabidir.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]


Windows masaüstü uygulamalarını otomatikleştirmek için masaüstü Kullanıcı arabirimi akışları oluşturun. 

Karşılaşabileceğiniz sorunlar, bu sorunlara yönelik geçici çözümler ve bu önizleme sürümünde desteklenmeyen senaryolar hakkında daha fazla bilgi edinmek için lütfen bu konunun ilerleyen kısımlarında yer alan [bilinen sorunlara](create-desktop.md#known-issues-and-solutions) bakın.


> [!TIP]
> Benzer bir model izleyerek, diğer Windows masaüstü uygulamalarını otomatikleştirebilirsiniz.

## <a name="create-a-desktop-ui-flow"></a>Masaüstü Kullanıcı arabirimi akışı oluşturma

Aşağıdaki adımlarda, hesaplayıcı uygulamasının iki sayıyı toplamak ve daha sonra kullanmak üzere sonucu depolamak için nasıl otomatikleştirildiğini göstereceğiz. 

1. Cihazınızın UI akışlarını oluşturmaya [hazırlı](setup.md) olduğundan emin olun. <!--Todo: link to the prereqs section-->

1. [Power otomatikleştir](https://flow.microsoft.com)'i açmak Için Microsoft Edge veya Google Chrome ['un kmıum sürümünü](https://www.microsoftedgeinsider.com) kullanın ve ardından bir iş veya okul e-posta hesabıyla oturum açın.

1. **Akışlarımı** seçin > **UI akışları (Önizleme)**  > **Yeni**.

   ![Yeni UI akışı oluştur](../media/create-windows-ui-flow/create-new.png "Yeni UI akışı oluştur")

1. **Masaüstü uygulaması** ' nı seçin ve ardından **İleri**' yi seçin.

   ![Masaüstü seçin](../media/create-windows-ui-flow/select-desktop.png "Masaüstü seçin") 

1. **Akış adı** alanına kullanıcı arabirimi akışınız için bir ad girin ve ardından **İleri**' yi seçin.

   ![Masaüstü seçin](../media/create-windows-ui-flow/give-a-name.png "Masaüstü seçin") 

1. Bu kılavuzda giriş kullanmadığınız için, isteğe bağlı olarak **ayarlama giriş** ekranını atlamak için en altta **İleri ' yi** seçin.

1. Açmak için **uygulama kartını kaydet** ' i seçin.

   ![Kayıt uygulamasını seçin](../media/create-windows-ui-flow/select-record-app.png "Kayıt uygulamasını seçin")

1. **Kaydediciyi Başlat**' ı seçin.

   ![Kaydı Başlat 'ı seçin](../media/create-windows-ui-flow/select-launch-recorder.png "Kaydı Başlat 'ı seçin")

   Kaydedici denetimi ekranınızın en üstünde görüntülenir.

   ![Kaydedici denetimi](../media/create-windows-ui-flow/recorder-control.png "Kaydedici denetimi")

1. Hesaplayıcı uygulamasını başlatın.

     >[!TIP]
     >Farenize uygulamada denetimlerin üzerine gittiğinde, mavi bir ana hattın her bir denetimi vurguladığına dikkat edin. Bir denetim seçmeden önce her zaman mavi vurgu bekle.
     >
     >Mavi vurgu öğe etrafında görünmezse, düzgün şekilde kaydedilmeyebilir.

1. Kaydedici denetiminden **kayıt** ' ı seçin.
1. İlk sayıyı seçin, **+** seçin, ikinci sayıyı seçin ve sonra **=** ' yi seçin.

    ![Hesaplayıcı uygulaması](../media/create-windows-ui-flow/app-to-record.png "Hesaplayıcı uygulaması")

1. Kaydetmek istediğiniz eylemleri tamamladıktan sonra kaydedici denetiminde **bitti** ' yi seçin.

1. Kaydettiğiniz uygulamayı kapatın.

1. Kayıtlı adımların ekran görüntülerini görüntülemek için "<app name> Betiği Çalıştır" ile başlayan kartı seçin.

     >[!TIP]
     >Kaldırmak isteyebileceğiniz ek adımları kaldırmak için **...**  > **Sil** ' i seçin.

    ![Kayıtlı adımları göster](../media/create-windows-ui-flow/show-recorded-steps.png "Kayıtlı adımları göster")

1. **İleri ' yi**seçin. 

1. Bu kılavuzda çıkış kullanmadığınız için, isteğe bağlı olarak **Kurulum çıkışlarını** atla adımını atlamak için **İleri ' yi** seçin.

## <a name="test-your-ui-flow"></a>UI akışınızı test etme

UI akışınızı test etmek her zaman harika bir fikirdir. Bunu yapmak için **Şimdi sına** düğmesini seçin ve ardından UI akışınızı çalıştırmayı izleyin.
    
 >[!IMPORTANT]
 >En iyi sonuçlar için, kayıttan yürütme süresince cihazlarınızla etkileşime girmeyin.

1. Akışınızı kaydetmek ve Kullanıcı arabirimi akışları özelliğinden çıkmak için **Kaydet ve çık** ' ı seçin.


## <a name="known-issues-and-solutions"></a>Bilinen sorunlar ve çözümleri

- Kaydetmeye *başlamadan önce kaydetmek* istediğiniz uygulamaları açın ve en üst düzeye çıkarın.

- UI akışları her teste veya çalıştırmaya sahip uygulamaların yeni bir örneğini başlattığında, UI akışınız sonuna bir [ **kapatma** eylemi](edit-desktop.md#add-a-manual-action) eklemek isteyebilirsiniz.

- Gereksiz/yinelenen eylemleri kaldırmak için kaydedilen eylemler kartında **.** .. > **Sil** ' i seçin. Kaydınızın türüne ve hızına göre yinelenen eylemler oluşturulabilir. 

- Sağ tıklama doğru şekilde kayıttan çalmayabilir. Bu tür durumlarda, kaydetme sırasında, hedef kullanıcı arabirimi öğesinde UI akışlarını odaklanmak için sol ' a tıklayın ve ardından sağ tıklayın.

- Kullanıcı arabirimi akışları artık yeni bir sürüm yükledikten sonra Windows uygulamalarını kayıt veya kayıttan çalırsa, önceki sürümü kaldırın ve ardından yeni bir sürüm yüklemeniz gerekir.


### <a name="unsupported-application-types"></a>Desteklenmeyen uygulama türleri

-   Windows etkileşimleri (Dosya Gezgini, başlangıç menüsü, görev çubuğu vb.).

-   Web tarayıcıları (Chrome, IE, Edge, Edge Bermıum, Firefox, Mozilla, vb.).
    Lütfen web sitelerini otomatikleştirmek için [Web UI akışı oluşturma](edit-web.md) bölümüne bakın.

-   Java uygulamaları.

-   Uygulamalar ' a tıklayın.

-   Elektron uygulamalar gibi bir Web görünümü olan uygulamalar.

-   Microsoft Office 2016 ve öncesi. 

-   Çevrimiçi Microsoft Office.

### <a name="unsupported-configurations"></a>Desteklenmeyen yapılandırmalar

-   Çoklu ekran.

-   Konak cihazda veya sanal makinede çalışan UI akışları uygulamasıyla bir sanal makine istemcisi (Uzak Masaüstü, Citrix, vb.) üzerinden kayıt. Hiçbiri desteklenir.

-   Ana pencere başlıklarının aynı olduğu bir uygulamanın birden çok örneği.

-   Aynı başlığa sahip uygulama pencereleri (örneğin, birden çok **Adsız – ileti (HTML)** yeni posta pencereleri aynı anda etkin.

-   Belirli bir cihazdaki eşzamanlı kayıt oturumları.

-   Belirli bir cihazdaki eşzamanlı kayıttan yürütme oturumları. Eş zamanlı kullanıcı arabirimi akışı çalıştırmaları durumunda, ilki öncelikli olur ve ilk bir işlem tamamlanana kadar sonraki işlemler başarısız olur.

-   Kaydedildiği cihazdan farklı bir klavye düzenine sahip bir cihazda kayıttan yürütme.

-   Microsoft Flow tarayıcı farklı bir cihaz veya Windows oturumunda olduğunda bir cihazda veya Windows oturumunda kaydetme işlemi.

### <a name="unsupported-action-types-and-behaviors"></a>Desteklenmeyen eylem türleri ve davranışları

Aşağıdaki eylemler kaydedilmeyecek:

-   Çift tıklayın.

-   Fare hareketi.

-   Fare üzerine gelme.

-   Tıklayın ve sürükleyin.

-   Dokunmatik veya kalem girişi.

-   Kaydetmeden önce uygulamayı açın.

-   Kayıttan yürütme başlatılmadan önce kapatılan uygulama.

## <a name="unreliable-behaviors-and-workarounds-for-microsoft-office-desktop"></a>Microsoft Office (Masaüstü) için güvenilmez davranışlar ve geçici çözümler
- Kayıttan yürütme işlemi sırasında şerit otomatik olarak gizlenmek üzere ayarlandıysa ortaya çıkabilecek sorunlardan kaçınmak için kayıttan yürütmeye başlamadan önce şeridi sabitleyin.
- Öğeleri tıklatıp sürükleyerek seçmeyin. Örneğin, Microsoft Excel 'de hücreleri seçmek için SHIFT-Click kullanmayın ve fareyi sürükleyerek Microsoft Word veya Microsoft PowerPoint 'te metin seçmeyin.
- Bazı öğeler, Microsoft Word ve Microsoft PowerPoint masaüstü uygulamaları için Kullanıcı arabirimi akışlarında (Önizleme) düzgün çalışmayabilir. Örneğin, boş başlangıç gibi Dosya menüsündeki seçenekler veya Microsoft Word 'de paragraf ekleme veya Microsoft PowerPoint 'teki slaytların yerleşimini değiştirme gibi denetimler çalışmayabilir.

## <a name="next-steps"></a>Sonraki adımlar

- Az önce oluşturduğunuz [Kullanıcı arabirimi akışını nasıl tetikleyeceğinizi](run-ui-flow.md) öğrenin.

- UI akışlarıyla daha fazlasını yapmak istiyorsanız, [giriş ve çıkış](inputs-outputs-web.md) parametreleriyle Kullanıcı arabirimi akışlarını da deneyebilirsiniz.

