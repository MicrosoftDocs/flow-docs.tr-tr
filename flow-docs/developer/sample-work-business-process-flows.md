---
title: 'Örnek: İş süreci akışlarıyla çalışma (Dynamics 365 Customer Engagement Geliştirici Kılavuzu) | MicrosoftDocs'
description: Bu örnekte, bir varlık kaydı için iş süreci akışını alma, bir iş süreci akışı örneği ve süreç aşamaları için etkin yolu alma ve etkin aşamayı değiştirme gibi işlemleri gerçekleştirerek iş süreci akışlarıyla program aracılığıyla nasıl çalışılacağı gösterilmektedir.
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 6f3543b666e471d1f7fa0fe24fc718e50d35aec8
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58352976"
---
# <a name="sample-work-with-business-process-flows"></a>Örnek: İş süreci akışlarıyla çalışma

Bu örnekte, bir varlık kaydı için iş süreci akışını alma, bir iş süreci akışı örneği ve süreç aşamaları için etkin yolu alma ve etkin aşamayı değiştirme gibi işlemleri gerçekleştirerek iş süreci akışlarıyla program aracılığıyla nasıl çalışılacağı gösterilmektedir. Bu kavramlar hakkında bilgi edinmek için bkz. [Kod kullanarak iş süreci akışlarıyla çalışma](business-process-flows-code.md)  

 Bu örnek şu konumdan indirilebilir: [Örnek: İş süreci akışlarıyla çalışma](https://go.microsoft.com/fwlink/p/?LinkId=846108)  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Önkoşullar  
 Örneği çalıştırmadan önce:  

1. Bir Common Data Service ortamına erişim sağlayın.  

2. Bu örnekte kullanılan Müşteri Adayı, Fırsat ve İş Akışı varlıkları ile iş süreci akış tanımı varlık kayıtları üzerinde uygun ayrıcalıklara sahip olun.  

3. Örneği çalıştırmak için Visual Studio 2015 veya üzeri bir sürümünü edinin.  

4. Örnek projeyi indirmek ve örnek projede kullanılan NuGet paketlerini geri yüklemek için İnternet bağlantınız olsun.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Bu örnek ne yapar?  

1.  Örnek bir Müşteri Adayı kaydı oluşturur. Bunun sonucunda Müşteri Adayı kaydı için otomatik olarak "Müşteri Adayından Fırsata Satış Süreci" iş süreci akışının bir örneği oluşturulur.  

2.  Müşteri Adayı kaydını Fırsat kaydına dönüştürür.  


4.  `RetrieveProcessInstances` iletisini kullanarak "Fırsat" kaydı ile ilişkili iş süreci akışı örneklerini alır. Döndürülen koleksiyondaki ilk kayıt, fırsat kaydına ait etkin iş süreci akışı örneğidir. Bu durumda "Müşteri Adayından Fırsata Satış Süreci" örneği olacaktır.  

5.  `RetrieveActivePath` iletisini kullanarak "Müşteri Adayından Fırsata Satış Süreci" örneği için etkin yolu ve süreç aşamalarını alır.  

6.  "Müşteri Adayından Fırsata Satış Süreci" örneği için şu andaki etkin aşamayı alır ve kullanıcıya bir sonraki aşamaya geçmek isteyip istemediğini sorar. Geçiş onayını aldığında, etkin yolda bulunan sıradaki aşamayı "Müşteri Adayından Fırsata Satış Süreci" örneği için etkin aşama olarak ayarlar.  

7.  Son olarak, kullanıcıya örneğin çalıştırılması sırasında oluşturulan kayıtları silmek isteyip istemediğini sorar.  

     Örneğin çıktısı aşağıdaki gibidir:  

    ![Örnek çıktısı](media/work-with-bpf-sample-output.png "Örnek çıktısı")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Örneği çalıştırma  

1. WorkWithBPF Visual Studio örnek projesini [indirip](https://go.microsoft.com/fwlink/p/?LinkId=846108) bilgisayarınızdaki bir klasöre ayıklayın.  

2. Ayıkladığınız klasörde `WorkWithBPF.sln` dosyasını bulup Visual Studio'da açın.  

3. Örnek proje, örneği çalıştırmadan önce geri yüklenmeleri gereken NuGet paketleri kullanır. Visual Studio'da NuGet paketlerinin otomatik olarak geri yüklenmesinin etkinleştirildiğinden emin olun. Daha fazla bilgi: [NuGet paketlerini geri yüklemeyi etkinleştirme ve devre dışı bırakma](https://go.microsoft.com/fwlink/?linkid=846106)  

    Alternatif olarak, **Proje** > **NuGet Paketlerini Yönet**’i ve sonra **Geri Yükle**’yi seçerek örnekte kullanılan paketleri el ile geri yükleyin.  

4. F5 tuşuna basın veya **Hata Ayıkla** > **Hata Ayıklamayı Başlat**’ı seçin.  

5. Daha önce örneklerden birini çalıştırmadıysanız kodu çalıştırmak için bilgi girmeniz gerekir. Aksi takdirde, daha önce ayarladığınız örneklerden birinin numarasını girin.  


   |                                 İstem                                  |                                                                                             Açıklama                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Bir Dynamics 365 sunucu adı ve bağlantı noktası [crm.dynamics.com] girin       | Dynamics 365 sunucunuzun adını yazın. Kuzey Amerika'da varsayılan değer Dynamics 365 (çevrimiçi) (crm.dynamics.com) olacaktır.<br /><br /> Örnek: <br />crm5.dynamics.com |
   | Bu kuruluş için Microsoft çevrimiçi hizmetlerde sağlama yapılıyor mu (e/h) [h] |                                                 Microsoft çevrimiçi hizmetlerde kendisi için sağlama yapılan bir kuruluşsanız **e** yazın. Aksi takdirde **h** yazın.                                                  |
   |                          Etki alanı\kullanıcı adı girin                          |                                                                                    Microsoft hesabınızı yazın.                                                                                     |
   |                             Parolayı girin                              |                      Parolanızı yazın. Karakterler pencerede "\*" olarak görünür. Parolanız daha sonra yeniden kullanılmak üzere Microsoft Kimlik Bilgileri Yöneticisi'nde güvenli bir şekilde kaydedilir.                       |
   |                Bir kuruluş numarası belirtin (1-n) [1]                 |                      Gösterilen ait olduğunuz kuruluşların listesinden ilgili numarayı yazın. Varsayılan değer 1’dir, listedeki ilk kuruluşa işaret eder.                       |


6. Örnek, [Bu örnek ne yapar?](#what-this-sample-does) bölümünde açıklanan işlemleri gerçekleştirir ve size ek seçenekler sunabilir.  

7. Örnek tamamlandığında konsol penceresini kapatmak için ENTER tuşuna basın.  

