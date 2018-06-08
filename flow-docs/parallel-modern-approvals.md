---
title: Paralel bir modern onay iş akışı oluşturma | Microsoft Docs
description: Paralel bir modern onay iş akışı oluşturma
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2018
ms.author: deonhe
ms.openlocfilehash: 43b748332a649e5f8d8db5fbe11f53522ce8bb79
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34051398"
---
# <a name="create-parallel-approval-workflows-with-microsoft-flow"></a>Microsoft Flow ile paralel onay iş akışları oluşturma

Paralel onay iş akışında, fatura, satınalma siparişleri, tatil istekleri gibi konuların onaylanması için birden fazla kişi gereklidir. Her birinin onayı diğer tüm onaylayanlardan bağımsızdır.

Bu incelemede, paralel bir onay iş akışını otomatikleştirecek bir akış oluşturmak için Microsoft Flow'u kullanacağız. Bu akış, çalışanın düzenli olarak desteklediği tüm kişilerin (veya grupların) onayını gerektiren bir çalışan tatil isteği işlemini otomatikleştirir. Çalışanlar tatil isteğinde bulunmak için bir [SharePoint listesi](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) kullanır. Tatil onaylarını çalışanın doğrudan yöneticisi, Satış ve İnsan Kaynakları ekipleri vermelidir. Tatil isteği, karar vermesi için her onaylayana yönlendirilir. Akış, durum değişikliklerini içeren bir e-posta gönderir ve ardından SharePoint'i verilen kararlarla güncelleştirir.

## <a name="prerequisites"></a>Önkoşullar

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Oluşturduğunuz SharePoint Online listesinde şu sütunlar bulunmalıdır:

   ![SharePoint listesinin sütunları](./media/parallel-modern-approvals/sharepoint-columns.png)

SharePoint Online listesinin adını ve URL'sini not edin. Daha sonra **SharePoint - Bir öğe oluşturulduğunda** tetikleyicisini yapılandırırken bu bilgileri kullanacağız.

## <a name="create-your-flow-from-the-blank-template"></a>Akışınızı boş şablondan oluşturun

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Tetikleyici ekleyin

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![SharePoint bilgileri](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Tatil isteğini oluşturan kişi için yöneticiyi alma

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Akışınızı adlandırma ve kaydetme

1. Akışınıza bir ad verin ve **Kaydet** simgesine tıklayarak o ana kadar yaptığınız işlemleri kaydedin.

   ![Akışı kaydedin](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> **Kaydet** simgesini seçerek akışınız üzerindeki değişiklikleri düzenli aralıklarla kaydedin.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>İlk yönetici için onay eylemi ekleme

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> Bu eylem, tatil isteğini **Atanan** kutusundaki e-posta adresine gönderir; bu nedenle, **Yöneticiyi al (v2)** listesindeki **E-posta** belirtecini ekleyin.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Satış ekibi için paralel bir dal onay eylemi ekleme

1. **Yöneticiyi al (v2)** ile **Start an approval** (Onay başlat) kartları arasında yer alan aşağı oku seçin.
2. Aşağı oku seçtikten sonra okun üzerinde görünen artı işaretini seçin.
3. **Paralel dal ekle** seçeneğini belirleyin.
4. **Eylem ekle**'yi seçin.

    ![Yönetici getirme eylemini yapılandırın](./media/parallel-modern-approvals/add-parallel-branch.png)
5. Tatil isteğini, satış ekibine gönderecek bir **Start an approval** (Onay başlat) eylemini arayın, seçin ve yapılandırın. **Start an approval** (Onay başlat) eyleminin nasıl ekleneceğini bilmiyorsanız [İlk yönetici için onay eylemi ekleme](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager) bölümündeki adımları inceleyin.

> [!IMPORTANT]
> **Start an approval 2** (Onay 2 başlat) eyleminin **Atanan** kutusunda satış ekibinin e-posta adresini kullanın.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>İnsan kaynakları ekibi için paralel bir dal onay eylemi ekleme

1. İnsan kaynakları ekibine tatil isteği göndermek için bir **Start an approval** (Onay başlat) eylemi ekleyip yapılandırmak üzere [Satış ekibi için paralel bir dal onay eylemi ekleme](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) bölümündeki adımları tekrar uygulayın.

> [!IMPORTANT]
> **Start an approval 3** (Onay 3 başlat) eyleminin **Atanan** kutusunda insan kaynakları ekibinin e-posta adresini kullanın.
> 
> 

Tüm adımları uyguladıysanız akışınız şu örnekteki gibi olacaktır:

   ![Paralel dallar içeren akış](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Paralel dalları ekledikten sonra seçenekleriniz

Paralel dallara eylem ekledikten sonra akışınıza daha fazla adım eklemeye yönelik iki seçeneğiniz vardır:

1. Küçük **Yeni adım ekle** düğmesini (bir dal üzerinde herhangi bir boşluğu veya bir dalın hemen altındaki alanı seçtiğinizde görünen daire şeklindeki artı düğmesi) kullanın. Bu düğme, **söz konusu dala** bir adım ekler. Bu düğmeyle eklediğiniz adımlar söz konusu dal tamamlandıktan sonra çalışır.
1. Tüm iş akışının alt tarafında daha büyük olan **Yeni adım** düğmesini kullanın. Bu düğmeyle eklediğiniz adımlar tüm dallar tamamlandıktan sonra çalışır.

Aşağıdaki bölümlerde, şu adımları her dalda uygulamak için küçük **Yeni adım ekle** düğmesini kullanırız:

* tatil isteğinin onay mı yoksa ret mi aldığını kontrol eden bir koşul ekleme,
* kararı ilgili çalışana bildiren bir e-posta gönderme,
* SharePoint'teki tatil isteğini onay kararıyla güncelleştirme.

Ardından, tatil isteğiyle ilgili olarak verilen tüm kararları özetleyen bir e-posta göndermek için daha büyük olan **Yeni adım** düğmesini kullanırız.

Devam ediyoruz:

## <a name="add-a-condition-to-each-branch"></a>Her dala koşul ekleme

1. **Start an approval** (Onay başlat) dalında herhangi bir boşluğu seçin.
2. Küçük **Yeni adım ekle** düğmesini (önceki adımda boşluk seçmenizin ardından görünen daire şeklindeki artı düğmesi) seçin.
3. Görünen menüden **Koşul ekle** seçeneğini belirleyin.
4. **Koşul** kartındaki ilk kutuyu ve ardından dinamik içerik listesindeki **Start an approval** (Onay başlat) kategorisinden **Yanıt** belirtecini seçin.

    ![Paralel dal koşulu içeren akış](./media/parallel-modern-approvals/configure-approval-condition.png)
5. Listenin (**Koşul kartının** ortasında) **eşittir** olarak ayarlandığından emin olun.
6. Son kutuya **Onayla** ifadesini (bu metin, büyük/küçük harfe duyarlıdır) girin.
7. Koşul kartınız artık şu örnekteki gibi görünecektir:

    ![Paralel dal koşulu içeren akış](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Bu koşul, çalışanın yöneticisine giden **Start an approval** (Onay başlat) eyleminden yanıtı kontrol eder.
   > 
   > 
8. **Start an approval 2** (satış ekibine gönderilen onay isteği) ve **Start an approval 3** (insan kaynakları ekibine gönderilen onay isteği) dallarında yer alan önceki adımları tekrar uygulayın.

## <a name="add-email-actions-to-each-branch"></a>Her dal için e-posta eylemleri ekleme

**Koşul** dalının **EVET İSE** ifadesinin yer aldığı tarafında aşağıdaki adımları uygulayın.

   Not: Akışınız, istek onaylandığında e-posta göndermek için şu adımları kullanır:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![Ön onay e-postası şablonunu yapılandırın](includes/media/parallel-modern-approvals/yes-email-config.png)

Bir istek reddedildiğinde e-posta göndermek için **Koşul** dalının **HAYIR İSE** ifadesinin yer aldığı tarafını kullanın ve ardından ret e-postası için şablon eklemek üzere önceki adımları tekrar uygulayın.

**Start an approval 2** (satış ekibine gönderilen onay isteği) ve **Start an approval 3** (insan kaynakları ekibine gönderilen onay isteği) dallarında yer alan önceki adımları tekrar uygulayın.

## <a name="update-the-vacation-request-with-the-decision"></a>Tatil isteğini verilen kararla güncelleştirme

Kararlar verildiğinde SharePoint'i güncelleştirmek için aşağıdaki adımları uygulayın.

   Not: Bu adımları dalın **EVET İSE** ve **HAYIR İSE** ifadelerinin yer aldığı her iki tarafında da uyguladığınızdan emin olun.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![Öğeyi güncelleştir eylemini yapılandırın](./media/parallel-modern-approvals/configure-update-item.png)

**Start an approval 2** ve **Start an approval 3** dallarında önceki adımları tekrar uygulayın.

## <a name="complete-the-flow"></a>Akışı tamamlama

1. **Yeni adım** > **Eylem ekle** seçeneğini belirleyin.

    ![Öğeyi güncelleştir eylemini yapılandırın](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. Her onayın sonuçlarını özetleyen bir e-posta göndermek için daha önce sağlana adımları uygulayın. Tatil isteğinde bulunan çalışana bu e-postayı gönderin. Kartınız şu örnekteki gibi görünecektir:

   ![Öğeyi güncelleştir eylemini yapılandırın](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>Modern onaylar hakkında daha fazla bilgi edinin

[Modern onaylara giriş](modern-approvals.md)

