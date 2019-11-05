---
title: Kurumsal geliştiriciler, ISV 'Ler ve iş ortakları için Microsoft Flow | Microsoft Docs
description: Microsoft Flow çözümleri geliştirmeye giriş.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: f26143533e84bc3ea8bc0784fef3c56eeb0551e1
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547823"
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>Kurumsal geliştiriciler, ISV 'Ler ve iş ortakları için Microsoft Flow
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Bir geliştirici olarak, kuruluşlar ve müşteriler için daha da güçlü çözümler sağlayan Microsoft Flow genişletebilirsiniz.

## <a name="microsoft-flow-for-enterprise-developers"></a>Kurumsal geliştiriciler için Microsoft Flow

Kurumsal bir geliştirici olarak, Microsoft Flow üzerinde güçlü özel çözümler oluşturmak için kuruluşunuzu güçlendirin:

- **Özel bağlayıcılar oluşturun**: Microsoft Flow aracılığıyla kuruluşunuzun verilerine ve Web hizmetlerine bağlanmak için özel bağlayıcılar geliştirin. [Daha fazla bilgi edinin](https://docs.microsoft.com/connectors/custom-connectors/)

- **Azure Işlevleri oluşturun**: uygulamaları özel sunucu tarafı mantığıyla genişletmek Için Azure işlevleri oluşturun. [Daha fazla bilgi edinin](/azure/azure-functions/app-service-export-api-to-powerapps-and-flow)

- **Microsoft Flow ekleyin**: doğrudan Web sitenizin deneyimlerinizde, Tümleşik çözümler oluşturmak, iş akışları veya süreçlerinizi kuruluşunuzdaki kişilerin zaten yaptıkları yerde kullanıma sunmak için Microsoft Flow ekleyin. [Daha fazla bilgi edinin](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>ISV 'Ler ve Microsoft iş ortakları için Microsoft Flow

Bir Microsoft iş ortağı veya bağımsız yazılım satıcısı (ISV) olarak, ürünlerinizi müşterilerinizin verileri ve iş süreçlerinizle tümleşecek şekilde genişleterek müşteri benimsemesini hızlandırın ve iş süreçlerini bir parçası olarak otomatikleştirmek için iş akışları ekleyin ve özelleştirin. Uygulamanızı. Aşağıdaki yedi adımı tamamladıktan sonra, uygulamanız 200 ' den farklı hizmetlere bağlanabilecek sağlam bir bulut ölçeğinde iş akışı altyapısından faydalanmanıza olanak sağlar.

| Aşaması | Indan | Gerektiğinde? |
| --- | --- | --- |
| Geliştirmeye | 1. verilerinize özel bir bağlayıcı oluşturun | Kendi ISV verilerinizi PowerApps veya Microsoft Flow kullanıma sunmak istiyorsanız |
| Geliştirmeye | 2. Azure Active Directory (Azure AD) ile kullanıcıların kimliğini doğrulamak için uygulamanıza yönelik destek ekleyin | Microsoft Flow Kullanıcı arabirimini veya listeyi eklemek istiyorsanız Microsoft AppSource | 
| Geliştirmeye | 3. Web tabanlı iframe 'imizi kullanarak Microsoft Flow Kullanıcı arabirimini uygulamanıza ekleyin | Uygulamanızda akış oluşturmayı veya yönetimini eklemek istiyorsanız | 
| Geliştirmeye | 4. akış şablonları oluşturma ve yayımlama | Müşterileriniz için akışları önceden oluşturmak istiyorsanız | 
| Geliştirmeye | 5. program aracılığıyla akışları dağıtmak için uygulama mantığı ekleyin | Müşterileriniz için önceden oluşturulmuş akışlarınızı otomatik olarak dağıtmak istiyorsanız | 
| Dağılı | 6. müşterilerinizin Microsoft Bulut çözüm sağlayıcısı programı aracılığıyla Microsoft Flow için lisanslarına izin verin | Müşterilerinizin Office 365 veya Dynamics 365 lisansı yoksa |
| Dağılı | 7. Microsoft AppSource çözümünüzü listeleyin | ISV çözümünüzün görünürlüğünü artırmak için önerilir |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. API 'lerinize bağlanma veya müşterilerin API 'lerinize bağlanmasını sağlama

ISV olarak, genellikle müşterilerin akışlarınızla erişmesini istediğiniz özel verileriniz vardır. Özel bir bağlayıcı aracılığıyla verilerinizin herhangi birine erişmesini sağlayabilirsiniz. [Daha fazla bilgi edinin](https://docs.microsoft.com/connectors/custom-connectors/)

Oluşturulduktan sonra, bağlayıcıyı müşterileriniz için kullanılabilir hale getirmek için iki yol vardır:
- Bağlayıcı, REST API 'Leri veya PowerShell aracılığıyla Müşterinin kiracısına dağıtılabilir.
- Özel bağlayıcıyı tüm kullanıcılar için genel olarak kullanılabilir hale getirmek için bağlayıcınızı sertifika için gönderebilirsiniz. [Daha fazla bilgi edinin](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. kimlik doğrulaması 

REST API 'Leri çağırmak ve kimliği doğrulanmış kullanıcı arabirimini eklemek için, uygulamanızın son kullanıcıların ve müşterilerin kimliğini doğrulamak için Azure AD Federasyon çoklu oturum açma 'yı kullanması gerekir. AAD Federal SSO 'Yu etkinleştirme hakkında daha fazla bilgi için [buraya gidin](https://identity.microsoft.com/) . Kimliği doğrulanmamış erişim veya Azure AD 'den farklı kimlik sağlayıcılarıyla erişim desteğiniz yok. 

### <a name="3-embedding-ui-components"></a>3. UI bileşenlerini katıştırma

Uygulamanız ile Microsoft Flow desteklediği tüm diğer hizmetler arasında derin ve bağlam içi tümleştirmeyi sağlamak için Microsoft Flow ekleyin. [Daha fazla bilgi edinin](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. akış şablonları oluşturma ve yayımlama

Bir Bağlayıcınız olduktan sonra, hizmetinizin nasıl kullanılacağını gösteren şablonlar yayımlamanız gerekir. Bu şablonlar, kullanıcıların kendi benzersiz iş akışlarına öğrenmek ve daha sonra genişletmek için kullanabileceği örnekler olarak görev yapar. [Daha fazla bilgi edinin](../publish-a-template.md)

### <a name="5-deployment"></a>5. dağıtım

Son kullanıcılara otomatik olarak kullanabilecekleri akışlara erişim sağlamak için akışları kullanıcının Azure AD kiracısına dağıtın. REST API 'lerimizi veya PowerShell 'i kullanarak dağıttığınız bir dağıtım paketi kullanın. [Daha fazla bilgi edinin](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. Lisanslama

Müşterileriniz zaten Office 365 veya Dynamics 365 ' ye sahipseniz ve bu lisanslar kullanıcıların Azure AD ile oturum açmasını sağlayan kimliklerle ilişkiliyse, sizin için ek lisans gereksinimleri yoktur. Ancak, müşterileriniz Office 365 veya Dynamics 365 ' i kullanıyorsa, uygulamanızda bu ekli bileşenlerden faydalanmak için lisanslanmalarını sağlamak üzere Microsoft Flow için kullanım hakları edinmeniz gerekir.

Müşterilerinizin adına lisans almak için [Microsoft bulut çözüm sağlayıcısı](https://partner.microsoft.com/cloud-solution-provider) programı sunuyoruz. Microsoft Flow için kullanılabilen iki farklı [fiyatlandırma planı](https://flow.microsoft.com/pricing/) vardır ve bu, plan ve özellik ayrıntılarını denetlemeniz gerekir.

### <a name="7-list-on-appsource"></a>7. AppSource üzerinde listeleme

Uygulamanıza Microsoft Flow tümleştirdikten sonra, bunu AppSource 'ta listeleyebilirsiniz. AppSource ile, bir uygulama oluşturup yeni müşterilerin test sürüşi için AppSource 'ta yayımlayarak, işletmenize yeni müşteri adayları oluşturabilirsiniz. [Daha fazla bilgi edinin](dev-appsource-test-drive.md)
