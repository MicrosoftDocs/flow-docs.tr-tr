---
title: 'Örnek: iş süreci akışlarıyla çalışma | MicrosoftDocs'
description: Örnek, bir varlık kaydı için iş süreci akış örneklerini alma, bir iş süreci akış örneği ve işlem aşamaları için etkin yolu alma ve bunu değiştirme gibi iş süreci akışlarıyla programlı olarak nasıl çalışılacağını gösterir. etkin aşama.
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
ms.openlocfilehash: 2eb6f7586ddc8d5bf51b9c57f91bbc5c7c10131b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547768"
---
# <a name="sample-work-with-business-process-flows"></a>Örnek: iş süreci akışlarıyla çalışma
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Bu örnek, bir varlık kaydı için iş süreci akış örneklerini alma, bir iş süreci akış örneği ve işlem aşamaları için etkin yolu alma ve bunu değiştirme gibi iş süreci akışlarıyla programlı olarak nasıl çalışılacağını gösterir. etkin aşama. Bu kavramlar hakkında daha fazla bilgi için bkz. [kod kullanarak iş süreci akışlarıyla çalışma](business-process-flows-code.md)  

 Bu örnek, örnek 'den indirilebilir [: iş süreci akışlarıyla çalışma](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Kaynakları  
 Örneği çalıştırabilmeniz için:  

1. Common Data Service ortamına erişiminiz vardır.  

2. Bu örnekte kullanılan lider, fırsat ve Iş akışı varlıkları ve iş süreci akış tanımı varlık kayıtları üzerinde uygun ayrıcalıklara sahiptir.  

3. Örneği çalıştırmak için Visual Studio 2015 veya sonraki bir sürümünü çalıştırın.  

4. Örnek projeyi indirmek ve örnek projede kullanılan NuGet paketlerini geri yüklemek için Internet bağlantısına sahip olmanız gerekir.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Bu örnek ne yapar  

1.  Örnek bir müşteri adayı kaydı oluşturur. Bu, müşteri adayı kaydı için "fırsat satış süreci lideri" iş süreci akışını otomatik olarak oluşturur.  

2.  Müşteri adayı kaydını bir fırsat kaydına dönüştürür.  


4.  `RetrieveProcessInstances` iletisini kullanarak "fırsat" kaydıyla ilişkili iş süreci akış örneklerini alır. Döndürülen koleksiyondaki ilk kayıt, fırsat kaydı için etkin iş süreci akış örneğidir ve bu durumda "fırsat satış süreci Için müşteri adayı" olur.  

5.  `RetrieveActivePath` iletisini kullanarak "fırsat satış süreci Için müşteri adayı" örneği için etkin yolu ve işlem aşamalarını alır.  

6.  "Fırsat satış süreci Için müşteri adayı" örneği için şu anda etkin olan aşamayı alır ve kullanıcıya bir sonraki aşamaya geçiş yapılıp yapılmayacağını sorar. Taşıma onayı ' nda, etkin yoldaki bir sonraki aşamayı "fırsat satış süreci lideri" örneği için etkin aşama olarak ayarlar.  

7.  Son olarak, kullanıcıya örnek çalıştırma sırasında oluşturulan kayıtların silinip silmeyeceğini sorar.  

     Örneğin çıktısı aşağıda verilmiştir:  

    ![Örnek çıkış](media/work-with-bpf-sample-output.png "Örnek çıkış")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Örneği çalıştırın  

1. WorkWithBPF Visual Studio örnek projesini [indirin](https://go.microsoft.com/fwlink/p/?LinkId=846108) ve bilgisayarınızdaki bir klasöre ayıklayın.  

2. Ayıklanan klasörünüzdeki `WorkWithBPF.sln` dosyasını bulun ve Visual Studio 'da açın.  

3. Örnek proje, örneği çalıştırmadan önce geri yüklenmesi gereken NuGet paketlerini kullanır. Visual Studio 'da NuGet paketlerinin otomatik geri yükleme özelliğinin etkinleştirildiğinden emin olun. Daha fazla bilgi: [NuGet paketi geri yüklemeyi etkinleştirme ve devre dışı bırakma](https://go.microsoft.com/fwlink/?linkid=846106)  

    Alternatif olarak, **proje** > **NuGet Paketlerini Yönet**' i seçin ve örnekte kullanılan paketleri El Ile geri yüklemek için **geri yükle** ' yi seçin.  

4. **Hata ayıklamayı başlatmak** > F5 tuşuna basın veya **Hata Ayıkla** öğesini seçin.  

5. Daha önce örneklerden birini daha önce çalıştırdıysanız, kodu çalıştırmak için bilgileri girmeniz gerekir, aksi takdirde daha önce ayarlamış olduğunuz örneklerden birinin numarasını girin.  


   |                                 isteme                                  |                                                                                             Açıklaması                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Dynamics 365 sunucu adı ve bağlantı noktası girin [crm.dynamics.com]       | Dynamics 365 sunucunuzun adını yazın. Kuzey Amerika, varsayılan olarak Dynamics 365 (çevrimiçi) (crm.dynamics.com) ' dir.<br /><br /> Örneğinde <br />crm5.dynamics.com |
   | Bu kuruluşun Microsoft çevrimiçi hizmetler (e/h) [n] içinde sağlanmış olması |                                                 Bu bir Microsoft çevrimiçi hizmetler sağlanmış kuruluştur ise **y** yazın. Aksi takdirde, **n**yazın.                                                  |
   |                          Etkialanı \ Kullanıcı adı girin                          |                                                                                    Microsoft hesabı yazın.                                                                                     |
   |                             Parolayı girin                              |                      Parolanızı yazın. Karakterler, pencerede "\*" olarak gösterilir. Parolanız, daha sonra yeniden kullanmak üzere Microsoft Credential Manager 'a güvenli bir şekilde kaydedilir.                       |
   |                Kuruluş numarası belirtin (1-n) [1]                 |                      Ait olduğunuz kuruluşların listesinden, karşılık gelen numarayı yazın. Varsayılan değer 1 ' dir ve listedeki ilk organizasyonu gösterir.                       |


6. Örnek, [Bu örnekte](#what-this-sample-does) açıklanan işlemleri gerçekleştirecek ve ek seçenekler istenebilir.  

7. Örnek tamamlandığında konsol penceresini kapatmak için ENTER tuşuna basın.  

