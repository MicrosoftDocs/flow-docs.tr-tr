---
title: Cihazınızda Kullanıcı arabirimi akışlarını ayarlama | Microsoft Docs
description: Cihazınızda Kullanıcı arabirimi akışlarını ayarlama
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
ms.openlocfilehash: 9e5029189df9807ba727efbe377392f87ef20884
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589694"
---
# <a name="set-up-ui-flows"></a>UI akışlarını ayarlama

[Bu konu ön sürüm belgesidir ve değişikliğe tabidir.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Kullanıcı arabirimi akışları oluşturmak için cihazınızı kullanabilmeniz için, burada özetlenen gereksinimleri karşıladığından emin olmanız gerekir.

> [!TIP]
> Bir UI akışı oluşturmadan önce, otomatikleştirmek istediğiniz uygulamanın zaten bir bağlayıcıya sahip olup olmadığını görmek için [Bağlayıcılar listesini](https://flow.microsoft.com/connectors/) denetleyin. Varsa, Kullanıcı arabirimi akışı yerine bir akış oluşturmayı düşünün. [Kendi bağlayıcınızı](https://docs.microsoft.com/connectors/custom-connectors/)da oluşturabilirsiniz.

## <a name="prerequisites"></a>Kaynakları

- [Ücretli](https://flow.microsoft.com/pricing/) veya [deneme](https://flow.microsoft.com/manage/) güç otomatikleştir planı.

- Hem güç otomatikleştirin hem de Windows cihazınızda oturum açmak için bir iş veya okul hesabı.

- Windows 10, Windows Server 2016 veya Windows Server 2019 çalıştıran bir cihaz.
- ABD (QWERTY) klavyesi eklenmiş.

- Microsoft Edge veya Google Chrome ['un sonraki sürümü](https://www.microsoftedgeinsider.com) .

- [Common Data Service veritabanına](https://docs.microsoft.com/power-platform/admin/create-database)sahip bir [ortam](https://docs.microsoft.com/power-platform/admin/environments-overview) .

> [!IMPORTANT]
> Kullanıcı arabirimi akışları Şu anda bölgeler arasında kullanıma alınıyor. Önizleme özelliğini görmüyorsanız veya yeni UI akışları oluşturmazsanız lütfen daha sonra yeniden deneyin.


## <a name="limitations"></a>Algılan

Kullanıcı arabirimi akışları (Önizleme) Ingilizce olarak kullanılabilir.

Aşağıdakiler desteklenmez:

-   Masaüstü Kullanıcı arabirimi akışları

    -   Birden çok izleyici
    -   Sanal makineler
    -   Çift tıklama, fare üzerine gelme, dokunmatik/kalem girişi
    -   Windows etkileşimleri (Dosya Gezgini, başlangıç menüsü, görev çubuğu vb.)

-   Web Kullanıcı arabirimi akışları

    -   Sağ tıklama
    -   Kullanıcı oturumu bilgileri (ör.: tanımlama bilgileri) kayıttan yürütme sırasında yeniden kullanılmaz. Web siteleri için gerektiğinde oturum açma bilgilerini eklemek için betiği düzenlemeniz gerekir.

Her bir özelliğin belgelerine eklenen özelliğe özgü sınırlamalar bulacaksınız.

## <a name="get-your-device-ready"></a>Cihazınızı hazırlayın

UI akışları oluşturmak ve çalıştırmak için aşağıdaki bileşenleri yükler:

|  | **Ada**                             | **Kullanımıyla**  |                                                        
|---|--------------------------------------|----------------------------------------------------------------------|
|   | [UI akışları uygulaması](https://go.microsoft.com/fwlink/?linkid=2102613)                         | Masaüstü Windows uygulamalarını kaydetme                                  |          |
|   | UI akışları tarayıcı uzantısı           | Masaüstü Windows uygulamalarını kaydetme ve test etme. Web uygulamalarını kaydedin. |                                                                                              |
|   | Web sürücüsü                            | Masaüstü Windows uygulamalarını test etme ve çalıştırma                            |                                                                                              |
|   | [Selenium IDE](https://go.microsoft.com/fwlink/?linkid=2107665) | Web uygulamalarını kaydetme ve kayıttan yürütme                                 |  |
|   | [Geçidinde](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409)                              | Bağlanmak için olayları, zamanlanmış akışları veya düğme akışlarını etkinleştirmek, UI akışlarınızı tetiklemeniz (kuruluşunuz içinde çalışan) ve bunları çalıştırmak için kullanılır.              |  | 

## <a name="install-the-ui-flows-app"></a>UI akışları uygulamasını yükler

UI akışları yükleyicisi, masaüstü için Kullanıcı arabirimi akışlarını kaydetmek, düzenlemek ve test etmek için gereken tüm bileşenleri içerir. 

>[!IMPORTANT]
>UI akışları yükleyicisi, WebDriver bileşenini ve Kullanıcı arabirimi akışları tarayıcı uzantısını yüklüyor. Bunların her ikisi de masaüstü için Kullanıcı arabirimi akışlarını kaydetmek, test etmek ve çalıştırmak için gereklidir.

UI akışları uygulamasını yüklemek için şu adımları izleyin:

1. [UI akışları uygulama yükleyicisini indirin](https://go.microsoft.com/fwlink/?linkid=2102613).
1. **Setup. Microsoft. Flow. Uılow. exe** dosyasını açın. Bu dosya, önceki adımda indirdikten sonra **karşıdan yüklemeler** klasörünüzde olabilir.
1. Yüklemeyi gerçekleştirmek için **UI akışları (Önizleme) kurulum** yükleyicisindeki yönergeleri izleyin.

## <a name="activate-the-ui-flows-browser-extension"></a>UI akışları tarayıcı uzantısını etkinleştirin 

UI akışları yükleyicisi tamamlandığında, uzantıyı etkinleştirmek için tarayıcınız istenir.

- Microsoft Edge 'de (Kmıum) tarayıcının sağ üst köşesindeki her bir uyarı simgesini seçin ve ardından **uzantıyı etkinleştir**' i seçin.
-   Google Chrome 'da istendiğinde **uzantıyı etkinleştir** ' i seçin.  


## <a name="install-selenium-ide"></a>Selenium IDE 'yi yükler

Selenium IDE, Web sitelerinde insan etkileşimini kaydetmenizi ve oynatmanızı sağlayan açık kaynaklı bir araçtır.

UI akışlarıyla, Selenium IDE betiklerini Power otomatikleştirmede çalıştırabilir ve Common Data Service ' de güvenli şekilde (uygun BT yönetimi ile) depolanmasını sağlayabilirsiniz.

Selenium IDE 'yi yüklemek için şu adımları izleyin:

1. Microsoft Edge veya Google Chrome 'un sonraki sürümü için Selenium IDE ['Yi indirin ve yükleyin](https://go.microsoft.com/fwlink/?linkid=2107665) .

1. Microsoft Edge 'de (Kmıum), **diğer mağazalardan uzantılara Izin ver**' i seçin ve ardından **Chrome 'a Ekle**' yi seçin.

## <a name="install-the-on-premises-data-gateway"></a>Şirket içi veri ağ geçidini yükler

Kullanıcı arabirimi akışınızı bir [olay, zamanlama veya düğme akışından](../getting-started.md/#types-of-flows)tetiklemek için ağ geçidine ihtiyaç duyarsınız.

>[!TIP]
>Yalnızca cihazınızda UI akışlarınızı oluşturmak, düzenlemek ve test etmek istiyorsanız Ağ Geçidi gerekli değildir.

Gerekirse [Şirket içi veri ağ geçidini yükleyebilirsiniz](https://docs.microsoft.com/data-integration/gateway/service-gateway-install).

## <a name="uninstall-ui-flows"></a>UI akışlarını kaldır

1. **Başlat** menüsünü > **ayarları** > **uygulamalar**' a açın.
1. **UI akışları (Önizleme)** için arama yapın ve ardından seçin.
1. **Kaldır**' ı seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Masaüstü Kullanıcı arabirimi akışları oluşturmayı](create-desktop.md)öğrenin.
- [Web UI akışları oluşturmayı](create-web.md)öğrenin.
- [UI akışlarını](run-ui-flow.md)çalıştırmayı öğrenin.
- [UI akışlarını yönetmeyi](manage.md)öğrenin.
- [Şirket içi ağ geçidi](../gateway-reference.md/#use-a-gateway) hakkında daha fazla bilgi edinin

