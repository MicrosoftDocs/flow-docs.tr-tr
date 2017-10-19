---
title: Common Data Service | Microsoft Docs
description: "Common Data Service’i kullanarak, verileri içeri veya dışarı aktaracağınız ya da onay oluşturacağınız bir akış oluşturun."
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
ms.openlocfilehash: a63ccacb1e6d9bd63d5a11a8db6ea01a9fc37333
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Common Data Service’ı kullanan bir akış oluşturma
[Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/)'ı kullanan bir akış oluşturarak iş verilerinin birleşik bir görünümünü elde edin ve operasyonel verimliliği artırın. İyi biçimlendirilmiş standart iş varlıkları (ör. Satış, Satın Alma, Müşteri Hizmetleri ve Üretkenlik) oluşturan bu güvenli iş veritabanını kuruluşunuzda dağıtın. Kuruluş verilerinizi, dış veri kaynaklarından (örneğin, Microsoft Excel ve Salesforce) daha fazla avantaj sunan bir veya daha fazla [özel varlıkta](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/) depolayın.

Örneğin, şu temel yolları kullanarak Microsoft Flow'da Common Data Service'tan yararlanın:

* Verileri içeri aktarmak, dışarı aktarmak veya veriler doğrultusunda eylem gerçekleştirmek (bildirim göndermek gibi) için bir akış oluşturun. Bu yaklaşımın, tam bir eşitleme hizmeti olmadığını ve yalnızca verileri varlık temelinde içeri ve dışarı taşımanızı sağladığını unutmayın.
  
    Ayrıntılı adımlar için, bu konu başlığının ilerleyen kısımlarında ele alınacak olan yordamlara göz atın.
* [E-posta yoluyla onay döngüsü oluşturmak](wait-for-approvals.md) yerine, onay durumunu bir varlıkta depolayan bir akış oluşturun ve kullanıcıların öğeleri onaylayıp reddedebilecekleri özel bir uygulama geliştirin.
  
    Ayrıntılı adımlar için bkz. [Common Data Service ile onay döngüsü oluşturma](common-data-model-approve.md).

**Önkoşullar**

* [Microsoft Flow](https://flow.microsoft.com)’a ve [PowerApps](https://web.powerapps.com)'e kaydolun.
  
    Bir sorunla karşılaşırsanız [Microsoft Flow](sign-up-sign-in.md)'un ve [PowerApps](https://powerapps.microsoft.com/en-us/tutorials/signup-for-powerapps/)'in sahip olduğunuz hesap türünü desteklediğini ve kuruluşunuzun, kaydolma işlemini engellemediğini doğrulayın.
* Common Data Service'ı daha önce kullanmadıysanız [powerapps.com](https://web.powerapps.com/#/entities)'daki **Varlıklar** sekmesini açın ve ardından **Veritabanımı oluştur**'a tıklayın veya dokunun.

## <a name="sign-in-to-your-environment"></a>Ortamınızda oturum açma
1. [Microsoft Flow portalını](https://flow.microsoft.com) açıp sağ üst köşede bulunan **Oturum aç**'a tıklayın veya dokunun.
   
    **Not**: **Oturum aç** düğmesini göstermek için sol üst köşedeki menüyü açmanız gerekebilir.
   
    ![Oturum açma](./media/common-data-model-intro/signin-flow.png)
2. Sağ üst köşedeki menüden, powerapps.com’da veritabanını oluşturduğunuz ortamı seçersiniz.
   
    **Not**: Aynı ortamı seçmezseniz varlıklarınızı göremezsiniz.
   
    ![Ortam seçme](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Şablon açma
1. Ekranın en üstünde bulunan **Şablonlarda ara** kutusuna **common** (ortak) yazın veya yapıştırın ve ardından Enter'a basın.
   
    ![Şablon arama](./media/common-data-model-intro/template-search.png)
2. Şablonlar listesinde, istediğiniz kaynaktan istediğiniz varlığa (veya *nesneye*) veri aktaran şablona tıklayın veya dokunun.
   
    Örneğin, Dynamics 365'teki kişi bilgilerini Common Data Service'a kopyalayan şablona tıklayın veya dokunun.
   
    ![Şablon seçme](./media/common-data-model-intro/choose-template.png)
3. **Bu şablonu kullan**'a tıklayın veya dokunun.
   
    ![Şablon kullanma](./media/common-data-model-intro/use-template.png)
4. Henüz Microsoft Flow'dan Dynamics 365'e bir bağlantı oluşturmadıysanız **Oturum aç**'a tıklayın veya dokunun, ardından istenmesi durumunda kimlik bilgilerinizi verin.
   
    ![Dynamics 365'te oturum açma](./media/common-data-model-intro/dynamics-signin.png)
5. **Devam**'a tıklayın veya dokunun.
   
    ![Hesapları onaylama](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Akışınızı oluşturma
1. İlk kartta, akışı tetikleyecek olayı belirtin.
   
    Örneğin, Dynamics 365'in bir örneğindeki yeni kişileri Common Data Service'a kopyalayacak bir akış oluşturuyorsunuz. **Bir kayıt oluşturulduğunda**'nın altında, aşağı oka ve ardından görüntülenen listedeki bir seçeneğe tıklayarak veya dokunarak örneği belirtin.
   
    ![Dynamics 365 örneği belirtme](./media/common-data-model-intro/specify-instance.png)
2. (isteğe bağlı) Ekranın üst kısmında, oluşturmakta olduğunuz akış için farklı bir ad belirtin.
   
    **Not**: Tarayıcı pencereniz ekranı kaplamıyorsa kullanıcı arabirimi biraz farklı görünebilir.
   
    ![Akışı adlandırma](./media/common-data-model-intro/name-flow.png)
3. **Akış oluştur**'a tıklayın veya dokunun.
   
    **Not**: Tarayıcı pencereniz ekranı kaplamıyorsa yalnızca onay işareti görüntülenebilir.
   
    ![Akış oluşturma](./media/common-data-model-intro/create-flow.png)

Artık bu nesne, kaynak sistemde her oluşturulduğunda Common Data Service'a aktarılır. Sizin için gerekli olan işlemleri yapan bir şablon bulamazsanız Common Data Service'ın üzerinde çalışan [bir akışı sıfırdan oluşturabilirsiniz](get-started-logic-flow.md).

Veritabanındaki değişiklikler doğrultusunda eylemler gerçekleştirebilirsiniz. Örneğin, her veri değişikliğinde bir bildirim e-postası gönderebilirsiniz.

