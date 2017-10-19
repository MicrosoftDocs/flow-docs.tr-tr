---
title: "Faturalama ve ölçüm ile ilgili sorular | Microsoft Docs"
description: "Microsoft Flow’da faturalama ve ölçümle ilgili sık sorulan soruların yanıtları"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/21/2016
ms.author: deonhe
ms.openlocfilehash: b627c008e1483360f35b6de579e2c0da32e60c93
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="billing-and-metering-questions"></a>Faturalama ve ölçüm soruları
Bu makalede, Microsoft Flow’da faturalama ve ölçümle ilgili sık sorulan sorular yanıtlanmıştır.

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Mevcut fiyatlandırma planlarını nereden öğrenebilirim?
[Fiyatlandırma sayfasına](https://flow.microsoft.com/pricing/) bakın.

## <a name="where-can-i-find-out-what-my-plan-is"></a>Hangi planı kullandığımı nereden öğrenebilirim?
[Fiyatlandırma sayfasına](https://flow.microsoft.com/pricing/) bakın.

## <a name="how-do-i-switch-plans"></a>Planlar arasında nasıl geçiş yapabilirim?
Üst gezinti menüsünde, **Öğren**’e tıklayın veya dokunun ve sonra **Fiyatlandırma**’ya tıklayın veya dokunun.

![Öğren > Fiyatlandırma](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Ne kadar kullandığımı nasıl öğrenebilirim?
Çalıştırmalarınızın kayıtlarını, bildirimleri ve hataları görüntülemek için **Etkinlik**’e tıklayın veya dokunun.

![Etkinlik bağlantısı](./media/billing-questions/activity-link.png)

Ücretsiz plan veya bir deneme planı kullanıyorsanız, planınıza göre geçerli kullanımınızı görmek için üst gezinti çubuğundaki dişli simgesine tıklayın veya dokunun.   

![Ayarlar düğmesi](./media/billing-questions/settings.png)

Ücretsiz plan veya bir deneme planı kullanmıyorsanız, çalıştırmalar kuruluşunuzdaki tüm kullanıcılara dağıtılır. Bir kuruluştaki kullanılabilir kota ve kullanımı göstermeye yönelik özellikler üzerinde çalışıyoruz.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>Kullanım limitlerini aşarsam ne olur?
Microsoft Flow çalıştırmaları azaltılmaya başlayabilir.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Kullanım limitleri hakkında daha fazla bilgiyi nereden bulabilirim?
[Fiyatlandırma sayfasında](https://flow.microsoft.com/pricing/), **SSS** bölümüne bakın.

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>Çok sık çalıştırma yürütmeyi denersem ne olur?
Planınız akışlarınızın ne sıklıkta çalıştırılacağını belirler. Örneğin, ücretsiz planı kullanıyorsanız akışlarınız 15 dakikada bir çalıştırılabilir. Bir akış, son çalıştırılmasının üzerinden 15 dakika geçmeden tetiklenirse, 15 dakika dolana kadar kuyruğa alınır. Yeni verilerin denetlenmesi, çalıştırma olarak sayılmaz.

## <a name="what-counts-as-a-run"></a>Neler çalıştırma olarak sayılır?
Otomatik tetikleyici aracılığıyla veya el ile başlatılarak tetiklenen her akış, bir çalıştırma olarak değerlendirilir.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Faturalama bakımından Microsoft Hesapları ve iş ya da okul hesapları arasında bir fark var mı?
Evet. Bir Microsoft Hesabı (örneğin, @outlook.com veya @gmail.com ile biten bir hesap) ile oturum açarsanız, yalnızca ücretsiz planı kullanabilirsiniz. Ücretli planın özelliklerinden yararlanmak için iş veya okul e-posta kimliğiyle oturum açın.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Yükseltme yapmaya çalışıyorum, ancak hesabımın uygun olmadığı söyleniyor.
Yükseltmek için, bir iş veya okul hesabı kullanın ya da bu [Power BI makalesindeki](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/) yönergeleri izleyerek bir Office 365 denemesi oluşturun.

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Neden akışımı yalnızca birkaç kez çalıştırmama rağmen çalıştırma haklarım tükendi?
Belirli akışlar, beklediğinizden daha sık çalıştırılabilir. Örneğin, yöneticiniz size e-posta gönderdiğinde size anında iletme bildirimi gönderen bir akış oluşturabilirsiniz. Bu akışın, e-postanın yöneticinizden gelip gelmediğini denetlemesi gerektiğinden, akışın herhangi bir kişiden her e-posta aldığınızda çalıştırılması gerekir. Bu eylem bir çalıştırma olarak sayılır.

İhtiyacınız olan tüm filtreleri tetikleyiciye yerleştirerek bu sorunu çözebilirsiniz. Yukarıdaki örnekte, **Gelişmiş Seçenekler** menüsünü genişletin ve **Kimden** alanında yöneticinizin e-posta adresini belirtin.

## <a name="other-limits-and-caveats"></a>Diğer limitler ve uyarılar
* Her hesapta aşağıdakilerden belirtilen sayıda olabilir:
  * 50 akış
  * 15 Özel Bağlayıcı
  * API başına 20 bağlantı ve toplam 100 bağlantı.
* Bir ağ geçidini yalnızca varsayılan ortama yükleyebilirsiniz.   
* Twitter gibi belirli harici bağlayıcılar, hizmet kalitesini denetlemek için bağlantı daraltma uygular. Daraltma uygulandığında, akışlarınız başarısız olur. Bu azaltmanın ayrıntılarını akışın çalıştırma geçmişinde başarısız olan çalıştırmayı görüntüleyerek inceleyebilirsiniz.

