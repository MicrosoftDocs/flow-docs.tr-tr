---
title: Faturalandırma ve ölçüm soruları | Microsoft Docs
description: Microsoft Flow faturalama ve ölçümle ilgili sık sorulan soruların yanıtları
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 69fecb42ba2b89f7a3f5b7541f62a4ee984832ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546189"
---
# <a name="billing-and-metering-questions"></a>Faturalandırma ve ölçüm soruları
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bu makale, Microsoft Flow faturalama ve ölçümle ilgili sık sorulan soruları yanıtlar.

>[!NOTE]
> PowerApps ve Microsoft Flow, 1 Ekim 2019 ' den itibaren [Yeni bir lisanslama modeli](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) kullanır. 

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Hangi fiyatlandırma planlarının kullanılabildiğini nereden bulabilirim?

[Fiyatlandırma sayfasına](https://flow.microsoft.com/pricing/)bakın.

## <a name="where-can-i-find-out-what-my-plan-is"></a>Planımın ne olduğunu nereden bulabilirim?

[Fiyatlandırma sayfasına](https://flow.microsoft.com/pricing/)bakın.

## <a name="how-do-i-switch-plans"></a>Nasıl yaparım? geçiş planları yapılsın mı?

Üst gezinti menüsünde > **fiyatlandırmayı** **öğrenin** ' i seçin ve ardından değiştirmek istediğiniz planı seçin.

![> Fiyatlandırması öğrenin](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Nasıl yaparım? ne kadar kullandığım hakkında bilgi sahibi misiniz?

Ücretsiz bir plansanız veya deneme planınızdan, planınıza göre geçerli kullanımınızı göstermek için üst gezinti çubuğundaki dişli simgesine tıklayın veya dokunun. 

![Ayarlar düğmesi](./media/billing-questions/settings.png)

Ücretli bir plansanız, çalıştırmalar kuruluşunuzdaki tüm kullanıcılar tarafından havuza alınır. Kurumsal cihazlarda kullanılabilir kotayı ve kullanımı kullanıma sunma özellikleriyle çalışıyoruz.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>Kullanımım sınırları aşarsa ne olur?

Microsoft Flow, akışlarınızın çalışmasını kısıtlar.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Kullanım limitleriyle ilgili daha fazla bilgiyi nerede bulabilirim?

[Fiyatlandırma sayfasında](https://flow.microsoft.com/pricing/), **SSS** bölümüne bakın.

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>Çalıştırmaları çok sık yürütmeye çalışırsam ne olur?

Planınız, akışlarınızın ne sıklıkla çalışacağını belirler. Örneğin, ücretsiz planınız varsa akışlarınız 15 dakikada bir çalışabilir. Bir akış, son çalıştırıldıktan sonra 15 dakikadan kısa bir süre sonra tetiklenirse, 15 dakika geçene kadar sıraya alınır.

## <a name="what-counts-as-a-run"></a>Ne bir çalıştırma olarak sayılır?

Bir akış her tetiklendiğinde otomatik bir tetikleyici tarafından veya el ile başlatılarak bu bir çalıştırma olarak kabul edilir. Yeni verilerin denetimleri, çalıştırma olarak sayılmaz.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Faturalandırma için Microsoft hesapları ile iş veya okul hesapları arasında farklar var mı?

Yes. Bir Microsoft hesabıyla oturum açarsanız (@outlook.com veya @gmail.combiten bir hesap gibi), yalnızca ücretsiz planı kullanabilirsiniz. Ücretli plandaki özelliklerden yararlanmak için iş veya okul e-posta adresiyle oturum açın.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Yükseltme yapmaya çalışıyorum, ancak hesabımın uygun olmadığını söyledim.

Yükseltmek için bir iş veya okul hesabı kullanın ya da bir [Office 365 deneme hesabı](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/)oluşturun.

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Flow 'un yalnızca birkaç kez çalıştırılmasının nedeni neden çalıştırıldım?

Belirli akışlar beklediğinizden daha sık çalıştırılabilir. Örneğin, yöneticinizin size bir e-posta göndermesi durumunda size anında iletme bildirimi gönderen bir akış oluşturabilirsiniz. Flow 'un e-postanın yöneticisinden geldiğini denetlemesi gerektiğinden, bu akışın her bir e-posta aldığınızda çalışması gerekir. Bu eylem bir çalıştırma olarak sayılır.

İhtiyaç duyduğunuz tüm filtrelemeyi tetikleyiciye yerleştirerek bu soruna geçici bir çözüm bulabilirsiniz. Anında iletme bildirimi örneğinde, **Gelişmiş Seçenekler** menüsünü genişletin ve **Kimden** alanında yöneticinizin e-posta adresini belirtin.

## <a name="other-limits-and-caveats"></a>Diğer sınırlar ve uyarılar

* Her hesap şu kadar sayıda olabilir:
  * 250 akış.
  * 15 özel bağlayıcı.
  * API başına 20 bağlantı ve 100 bağlantı toplamı.
* Yalnızca varsayılan ortamda bir ağ geçidi yükleyebilirsiniz.
* Twitter gibi bazı dış bağlayıcılar, hizmet kalitesini denetlemek için bağlantı azaltma uygular. Daraltma etkin olduğunda akışlarınız başarısız olur. Akışlarınız başarısız olursa, akışın çalıştırma geçmişinde başarısız olan çalıştırmanın ayrıntılarını gözden geçirin.
