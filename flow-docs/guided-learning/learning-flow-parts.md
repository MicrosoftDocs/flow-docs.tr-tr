---
title: "Microsoft Flow’un yapı taşları | Microsoft Docs"
description: "Microsoft Flow’un farklı bölümlerini ve bu bölümlerin birbirleriyle ilişkilerini inceleyin. Şablonları kullanarak ve sıfırdan yeni akışlar oluşturun."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: 9U8jMRO-Jv0
courseduration: 9m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 6a7fe2d56c7bc3b2253b675ce26f3f29042a7a71
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="building-blocks-of-microsoft-flow"></a>Microsoft Flow’un yapı taşları
Microsoft Flow’un temel özelliklerini öğrendiğinize göre **bir Microsoft Flow turuna** çıkabiliriz. Şablonlardan ve sıfırdan akış oluşturmaya hızlıca bakacağız.

## <a name="check-out-the-templates"></a>Şablonlara göz atın
flow.microsoft.com sayfasının üstündeki **Şablonlar** bağlantısına tıklarsanız web hizmetlerinizle birlikte hemen kullanabileceğiniz birkaç şablonla karşılanırsınız. **Yapabileceklerinizi hızlıca anlamak** ve Microsoft Flow’un işletmenize nasıl yardımcı olabileceğini görmek için bu uygulamaları keşfedin.

![Akış şablonları](./media/learning-flow-parts/template-list.png)

Her şablon akışı, bir olay meydana geldiğinde bildirim alma, bir hizmetten diğerine yeni bir dosyayı kopyalama veya SharePoint onaylarını izleme gibi belirli bir amaç için tasarlanmıştır. Bu şablonlar **kullanıma hazırdır**.  Akışları hesabınıza eklemek için **şablonları yapılandırmanız** yeterlidir. Bunu yapmak için **Bu şablonu kullan**’a tıklayın, gerekli hizmetlerde oturum açın ve ardından gösterilen formları tamamlayın.  Örneğin, bu akış bir SharePoint listesi değiştirildiğinde e-posta bildirimleri gönderecek bir şablondan bir şablondan oluşturulmuştur. 

![Flow örnek şablonu](./media/learning-flow-parts/example-template.png)

Kullanabileceğiniz yüzlerce şablonu **Web için Microsoft Flow** ya da **Mobil için Microsoft Flow**’da bulabilirsiniz.

![Flow web ve mobil](./media/learning-flow-parts/flow-web-mobile.png)

## <a name="create-a-flow-from-scratch"></a>Sıfırdan akış oluşturma
Şablon kullanarak akış oluşturmayı gördünüz; peki, otomatikleştirmek istediğiniz bir görev varken uygun şablonu bulamıyorsanız ne yapmanız gerekir? **Sıfırdan akış oluşturabilirsiniz**.  Sıfırdan akış oluşturduğunuzda boş bir tuvalden başlayıp **hizmet, tetikleyici ve eylemler** ekleyerek akışınızı oluşturursunuz.  

![Boş akış](./media/learning-flow-parts/flow-from-blank.png)

## <a name="building-blocks-of-a-flow"></a>Bir akışın yapı taşları
Şablon aracılığıyla veya sıfırdan oluşturmanızdan bağımsız olarak tüm akışlarınız, belirli yollarla birlikte çalışan ve akış çizelgelerine benzeyen **yapı taşlarına** sahip olur.

* **Hizmetler**, bir akıştaki verilerin kaynakları ve hedefleridir.
* **Tetikleyiciler** bir akışı başlatan olaylardır.
* **Eylemler** akış tarafından gerçekleştirilen görevlerdir.
* **Koşullar** bir akışta if/then mantığını dallara ayırmaya olanak tanır.
* **Döngüler**, eylemleri birden fazla kez yinelemeye yöneliktir.

### <a name="services"></a>Hizmetler
Microsoft Flow çok sayıda farklı **uygulama ve hizmete** bağlanabilir.  **Twitter**, **Github**, **Wunderlist**, **Office 365** ve **Google Docs**, bu hizmetlere örnek olarak verilebilir.  Bunlar Microsoft Flow’a veri sağlamanın yanında Microsoft Flow tarafından gerçekleştirilen işlerin **hedeflerini** sunan **kaynaklardır**.  **flow.microsoft.com** sayfasının üst kısmındaki **Hizmetler** bağlantısına tıklayarak hizmetlerin tam listesini görebilirsiniz.

![Flow bağlayıcıları](./media/learning-flow-parts/flow-connectors.png)

### <a name="triggers"></a>Tetikleyiciler
Her akış bir **tetikleyici** ile başlar.  Çok sayıda farklı türde tetikleyici vardır.  Bunlardan bazıları **belirli bir kullanıcının tweet göndermesi** veya **Dropbox hesabınıza bir dosya kaydedilmesi** gibi bağlı web hizmetlerinizde gerçekleşen olaylardır.  **Tekrarlayan bir zamanlamaya göre akış çalıştırma** veya **web isteğine yanıt olarak akış çalıştırma** gibi diğer tetikleyiciler ise yerleşiktir.  Son olarak, **Microsoft Flow veya Microsoft PowerApps düğmesine** tıklayarak akış başlatma gibi elle tetikleyiciler vardır.  Tetikleyiciler genellikle akışınıza **gerçekleşen olay hakkında bilgiler iletir**.

![Akış tetikleyiciler](./media/learning-flow-parts/flow-triggers.png)  

### <a name="actions"></a>Eylemler
**Eylem**, akış tetiklendikten sonra **gerçekleşmesini** istediğiniz olayları ifade eder.  Bu olay bir **bildirim**, bir kaynaktan bir hedefe **veri veya dosya kopyalama**, **sosyal medyada yayınlama** veya **bir süre için erteleme** gibi diğer eylemleri içerebilir.  Eylemleri ayrıca diğer eylemlerle kullanılacak **bir hizmetten veri almak** için de kullanabilirsiniz.

![Akış eylemleri](./media/learning-flow-parts/flow-actions.png) 

### <a name="conditions"></a>Koşullar
**Koşullar**, akışınıza karar eklemenize olanak tanır.  Bir koşul değerlendirdiğinde akış bir **evet** yoluna ve **hayır** yoluna ayrılır.   Örneğin, **Dropbox**’ta yayınlanmış tatil fotoğraflarınızı **OneDrive**’a kopyalamak isterseniz **Dropbox yeni dosya** tetikleyicisinden sonra dosya adının *tatil* sözcüğünü içerip içermediğini denetleyen ve içeriyorsa dosyayı **OneDrive**’a kopyalayan, aksi takdirde bir işlem yapmayan bir koşul oluşturabilirsiniz.

![Akış koşulu](./media/learning-flow-parts/flow-condition.png) 

### <a name="loops"></a>Döngüler
**Döngüler**, bir eylemin tekrarlayarak veya bir öğe koleksiyonunda öğe başına bir kez oluşması gerektiğinde bir eylemi birden çok kez yürütmenize olanak tanır.

## <a name="next-lesson"></a>Sonraki ders
Bu konuda, Microsoft Flow’a göz attık.  **Şablonlar**’a göz attık ve **sıfırdan şablon oluşturma** hakkında konuştuk.  Uygulama ve hizmetlere, akışı başlatmak üzere **tetikleyicilere**, akışta bir olayın gerçekleşmesi için **eylemlere**, karar almak için **koşullara** ve bir akışta olayları yinelemek için **döngülere** bağlanarak akış oluşturacağız.  **Microsoft Flow hakkında bilgi edinmenin en kolay yolu bir şablonla başlamak** ve sonra, kullanmakta olduğunuz uygulamalarla hizmetlere bu şablonu bağlamaktır. 

Ardından, bu Kılavuzlu Öğrenme kursunda şimdiye kadar öğrendiklerimizi gözden geçireceğiz.

