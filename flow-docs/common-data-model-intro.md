---
title: Common Data Service | Microsoft Docs
description: Verileri içeri aktarmak, verileri dışarı aktarmak veya Common Data Service onay oluşturmak için bir akış oluşturun.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 60e076dadab17beb15ffaec289ec0a2937924668
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546960"
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Common Data Service kullanan bir akış oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
[Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/)kullanan akış oluşturarak iş verilerinin birleştirilmiş bir görünümüyle işlemsel verimliliği artırabilirsiniz. Kuruluşunuzda doğru biçimlendirilmiş standart iş varlıklarını (satış, satın alma, müşteri hizmeti ve üretkenlik gibi) oluşturan bu güvenli iş veritabanını dağıtın. Kurumsal verileri, Microsoft Excel ve Salesforce gibi dış veri kaynakları üzerinde çeşitli avantajlar sunan bir veya daha fazla [özel varlıkta](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/)depolayın.

Örneğin, Microsoft Flow içindeki Common Data Service şu anahtar yollarla yararlanın:

* Verilerin içeri aktarılması, verilerin dışarı aktarılması veya verilerin üzerine işlem yapması için bir akış oluşturun (örneğin, bildirim gönderme). Bu yaklaşımın tam eşitleme hizmeti olmadığını unutmayın; Bu, verileri varlık bazında veya dışarı taşımanıza olanak sağlar.
  
    Ayrıntılı adımlar için, bu konunun ilerleyen kısımlarındaki yordamlara bakın.
* [E-posta yoluyla onay döngüsü oluşturmak](wait-for-approvals.md)yerine, bir varlıkta onay durumunu depolayan bir akış oluşturun ve kullanıcıların öğeleri onaylayabileceği veya reddedebilecekleri özel bir uygulama oluşturun.
  
    Ayrıntılı adımlar için bkz. [Common Data Service bir onay döngüsü oluşturma](common-data-model-approve.md).

**Kaynakları**

* [Microsoft Flow](https://flow.microsoft.com) ve [PowerApps](https://web.powerapps.com)'e kaydolun.
  
    Sorun yaşıyorsanız, [Microsoft Flow](sign-up-sign-in.md) ve [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) 'in sahip olduğunuz hesap türünü destekleyip desteklemediğini ve kuruluşunuzun kaydolma işlemini engellemediğini doğrulayın.
* Daha önce Common Data Service kullanmadıysanız, [PowerApps.com](https://web.powerapps.com/#/entities)'in **varlıklar** sekmesini açın ve ardından **veritabanımı oluştur**' a tıklayın veya dokunun.

## <a name="sign-in-to-your-environment"></a>Ortamınızda oturum açın
1. [Microsoft Flow portalını](https://flow.microsoft.com)açın ve sağ üst köşedeki **oturum aç** ' a tıklayın veya dokunun.
   
    **Note**: **oturum aç** düğmesini göstermek için sol üst menüyü açmanız gerekebilir.
   
    ![Oturum Aç](./media/common-data-model-intro/signin-flow.png)
2. Sağ üst taraftaki menüde, powerapps.com 'de veritabanını oluşturduğunuz ortamı seçersiniz.
   
    **Not**: aynı ortamı seçmezseniz varlıklarınızı görmezsiniz.
   
    ![Ortam seçin](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Şablon açma
1. Ekranın üst kısmındaki **şablonları ara** kutusuna **ortak**yazın veya yapıştırın ve ardından ENTER tuşuna basın.
   
    ![Şablon ara](./media/common-data-model-intro/template-search.png)
2. Şablon listesinde istediğiniz varlığa (veya *nesneye*) istediğiniz verileri içeri aktaran şablona tıklayın veya dokunun.
   
    Örneğin, iletişim bilgilerini Dynamics 365 ' den Common Data Service kopyalayan şablona tıklayın veya dokunun.
   
    ![Şablon seçin](./media/common-data-model-intro/choose-template.png)
3. **Bu şablonu kullan**' a tıklayın veya dokunun.
   
    ![Şablon kullanma](./media/common-data-model-intro/use-template.png)
4. Microsoft Flow 'den Dynamics 365 'e zaten bir bağlantı oluşturmadıysanız **oturum aç**' a tıklayın veya dokunun ve istenirse kimlik bilgilerinizi sağlayın.
   
    ![Dynamics 365 ' de oturum açın](./media/common-data-model-intro/dynamics-signin.png)
5. **Devam**' a tıklayın veya dokunun.
   
    ![Hesapları Onayla](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Akışınızı oluşturun
1. İlk kartta, akışın tetikleyeceği olayı belirtin.
   
    Örneğin, bir Dynamics 365 örneğinden Common Data Service yeni kişileri kopyalayacak bir akış yarayorsunuz. **Bir kayıt oluşturulduğunda**, aşağı oka tıklayarak veya dokunarak ve ardından görüntülenen listedeki bir seçeneğe tıklayarak veya dokunarak örneği belirtin.
   
    ![Dynamics 365 örneğini belirtin](./media/common-data-model-intro/specify-instance.png)
2. seçim Ekranın üst kısmında, oluşturmakta olduğunuz akış için farklı bir ad belirtin.
   
    **Note**: tarayıcı pencereniz ekranı KAPLAMıYORSA Kullanıcı arabirimi biraz farklı görünebilir.
   
    ![Ad akışı](./media/common-data-model-intro/name-flow.png)
3. **Akış oluştur**' a tıklayın veya dokunun.
   
    **Note**: tarayıcı pencereniz ekranı kaplamıyorsa, yalnızca onay işareti görünebilir.
   
    ![akış oluştur](./media/common-data-model-intro/create-flow.png)

Artık bu nesne, kaynak sistemde her oluşturulduğunda, Common Data Service içeri aktarılacaktır. İhtiyaç duyduğunuz şeyi yapan bir şablon bulamazsanız, sıfırdan Common Data Service en üstünde çalışan [bir akış](get-started-logic-flow.md) oluşturabilirsiniz.

Veritabanındaki değişiklikler üzerinde işlem yapabilirsiniz. Örneğin, veri her değiştiğinde bildirim postası gönderebilirsiniz.

