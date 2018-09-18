---
title: Kurumsal geliştiriciler, ISV’ler ve iş ortakları için Microsoft Flow | Microsoft Docs
description: Microsoft Flow için çözüm geliştirmeye giriş.
services: ''
suite: flow
documentationcenter: na
author: mgblythe
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: mblythe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: f510d387b594bb11306f8bc2530573b775e5f08e
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690411"
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>Kurumsal geliştiriciler, ISV’ler ve iş ortakları için Microsoft Flow

Bir geliştirici olarak Microsoft Flow’u genişleterek kuruluşlar ve müşteriler için çok daha güçlü çözümler sağlayabilirsiniz.

## <a name="microsoft-flow-for-enterprise-developers"></a>Kurumsal geliştiriciler için Microsoft Flow

Bir kurumsal geliştirici olarak, Microsoft Flow’da sağlam, gereksinimlere uyarlanmış çözümler oluşturma yönünde kuruluşunuzu güçlendirin:

- **Özel bağlayıcılar derleme**: Microsoft Flow üzerinden kuruluşunuzun verilerine ve web hizmetlerine bağlanmak üzere özel bağlayıcılar geliştirin. [Daha fazla bilgi](https://docs.microsoft.com/connectors/custom-connectors/)

- **Azure İşlevleri derleme**: Özel sunucu tarafı mantığıyla uygulamaların kapsamını genişletmek için Azure İşlevleri hazırlayın. [Daha fazla bilgi](https://docs.microsoft.com/azure/azure-functions/functions-flow-scenario)

- **Microsoft Flow’u ekleme**: Tümleşik çözümler oluşturmak, iş akışlarının veya süreçlerin kuruluşunuzdaki kişilerin zaten çalışmakta olduğu yerlerde görünmesini sağlamak için Microsoft Flow’u doğrudan web siteyi deneyimlerinize ekleyin. [Daha fazla bilgi](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>ISS’ler ve Microsoft iş ortakları için Microsoft Flow

Bir Microsoft iş ortağı veya Bağımsız Yazılım Satıcısı (ISV) olarak ürünlerinizi müşterilerinizin verileriyle ve iş süreçleriyle tümleştirilecek şekilde genişleterek müşteriler tarafından benimsenme hızınızı artırın ve uygulamanızın bir parçası olarak iş süreçlerini otomatikleştirmeye yönelik iş akışları ekleyip bunları özelleştirin. Aşağıdaki yedi adımı tamamladığınızda, uygulamanız 200’ün üzerindeki farklı hizmete bağlanabilen, bulut ölçekli sağlam bir iş akışı yapısından yararlanma olanağına sahip olacak.

| Aşama | Adım | Gerektiği durumlar |
| --- | --- | --- |
| Geliştirme | 1. Verilerinize yönelik özel bağlayıcı oluşturun | Kendi ISV verilerinizi PowerApps veya Microsoft Flow’da kullanıma sunmak istiyorsanız |
| Geliştirme | 2. Kullanıcıların kimliklerini Azure Active Directory (Azure AD) ile doğrulamak için uygulamanıza yönelik destek ekleyin | Microsoft Flow kullanıcı arabirimini eklemek veya çözümünüzü Microsoft AppSource’ta listelemek istiyorsanız | 
| Geliştirme | 3. Web tabanlı iframe’imizi kullanarak uygulamanıza Microsoft Flow kullanıcı arabirimini ekleyin | Uygulamanıza akış oluşturma veya yönetme özelliği eklemek istiyorsanız | 
| Geliştirme | 4. Akış şablonları oluşturun ve yayınlayın | Müşterilerinize yönelik akışları önceden oluşturmak istiyorsanız | 
| Geliştirme | 5. Programlı olarak akış dağıtmak için uygulama mantığı ekleyin | Müşterileriniz için önceden oluşturulmuş akışlarınızı otomatik olarak dağıtmak istiyorsanız | 
| Dağıtım | 6. Microsoft Bulut Çözümü Sağlayıcısı programı aracılığıyla müşterilerinize Microsoft Flow lisansları verin | Müşterilerinizin Office 365 veya Dynamics 365 lisansları yoksa |
| Dağıtım | 7. Çözümünüzü Microsoft AppSource’da listeleyin | ISV çözümünüzün görünürlüğünü artırmak için önerilir |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. API’lerinize bağlanma VEYA müşterilerin API’lerinize bağlanmasını mümkün kılma

Bir ISV olarak genellikle müşterilerin akışlarınız aracılığıyla erişmesini istediğiniz özel verileriniz olur. Özel bir bağlayıcı üzerinden tüm verilerinizi erişime açabilirsiniz. [Daha fazla bilgi](https://docs.microsoft.com/connectors/custom-connectors/)

Oluşturduğunuz bir bağlayıcı müşterilerinizin kullanımına sunmanın iki yolu vardır:
- Bağlayıcı, REST API’ler veya PowerShell aracılığıyla müşterinin kiracısına dağıtılabilir.
- Özel bağlayıcının tüm kullanıcılar tarafından genel olarak kullanılabilir olmasını istiyorsanız sertifika almak için bağlayıcınızı gönderebilirsiniz. [Daha fazla bilgi](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. Kimlik doğrulaması 

Uygulamanızın REST API’leri çağırması ve kimliği doğrulanmış kullanıcı arabirimi eklemesi için son kullanıcıların ve müşterilerin kimliğini Azure AD federasyon çoklu oturum açma kullanarak doğrulaması gerekir. AAD federasyon SSO’yu etkinleştirme hakkında bilgi edinmek için [buraya gidin](https://identity.microsoft.com/). Kimlik doğrulamasız erişimi veya Azure AD dışındaki kimlik sağlayıcıları ile erişimi desteklemiyoruz. 

### <a name="3-embedding-ui-components"></a>3. Kullanıcı arabirimi bileşenleri ekleme

Uygulamanıza Microsoft Flow'u ekleyerek uygulamanız ile Microsoft Flow'un desteklediği tüm diğer hizmetler arasında derin ve bağlam içi bir tümleştirme sağlayabilirsiniz. [Daha fazla bilgi](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. Akış şablonları oluşturun ve yayınlayın

Bağlayıcınız olduktan sonra, hizmetinizin nasıl kullanılacağını gösteren şablonlar yayımlamalısınız. Bu şablonlar, kullanıcıların öğrenmek ve ardından kendi benzersiz iş akışlarına genişletmek için kullanabilecekleri örnekler olmalıdır. [Daha fazla bilgi](../publish-a-template.md)

### <a name="5-deployment"></a>5. Dağıtım

Son kullanıcıların otomatik olarak kullanabilecekleri akışlara erişebilmesini sağlamak için akışları kullanıcının Azure AD kiracısına dağıtın. REST API'lerimizi veya PowerShell’i kullanarak dağıttığınız bir dağıtım paketi kullanın. [Daha fazla bilgi](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. Lisanslama

Müşterilerinizin zaten Office 365 veya Dynamics 365 lisansı varsa, bu lisanslar kullanıcıların Azure AD’de oturum açmak için kullandığı kimliklerle ilişkilendirilir ve sizin başka bir lisanslama işlemi yapmanız gerekmez. Bununla birlikte, müşterileriniz Office 365 veya Dynamics 365 kullanmıyorsa Microsoft Flow için müşterileriniz adına kullanım hakları edinmeniz ve uygulamanızdaki ekli bileşenlerden yararlanabilmeleri için lisanslı olmalarını sağlamanız gerekir.

Müşterileriniz adına lisans edinebilmeniz için [Microsoft Bulut Çözümü Sağlayıcısı](https://partner.microsoft.com/cloud-solution-provider) programını sunuyoruz. Microsoft Flow için plan ve özellik ayrıntılarını öğrenmek üzere göz atmanız gereken iki farklı [fiyatlandırma planı](https://flow.microsoft.com/pricing/) sunulmaktadır.

### <a name="7-list-on-appsource"></a>7. AppSource’ta listeleme

Microsoft Flow’u uygulamanızla tümleştirdikten sonra uygulamanızı AppSource’ta listeleyebilirsiniz. AppSource sayesinde bir uygulama oluşturup bu uygulamayı yeni müşterilerin test sürüşü yapması için AppSource’ta yayımlayarak işletmenize yeni müşteri adayları kazandırabilirsiniz. [Daha fazla bilgi](dev-appsource-test-drive.md)
