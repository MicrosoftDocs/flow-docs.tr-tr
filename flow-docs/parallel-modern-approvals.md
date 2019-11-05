---
title: Paralel bir modern onay iş akışı oluşturun | Microsoft Docs
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6cbaaecf70e4f6549a790861130dcde0b5a888e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548944"
---
# <a name="create-parallel-approval-workflows-with-microsoft-flow"></a>Microsoft Flow ile paralel onay iş akışları oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bir paralel onay iş akışında, faturalar, satın alma siparişleri, tatil istekleri vb. gibi öğelerin onaylanması için birden çok kişi gerekir. Her birinin onayı diğer onaylayanlardan bağımsızdır.

Bu izlenecek yolda, paralel onay iş akışını otomatikleştiren bir akış oluşturmak için Microsoft Flow kullanırız. Bu akış, çalışanın düzenli olarak desteklediği tüm kişilerden (veya ekiplerden) onay gerektiren bir çalışan tatil isteği işlemini otomatikleştirir. Çalışanlar tatil istemek için bir [SharePoint listesi](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) kullanır. Tatil onayları çalışanın doğrudan Yöneticisi, satış ekibi ve Insan kaynakları ekibi 'nden gereklidir. Her bir tatil isteği bir karar için her onaylayana yönlendirilir. Akış, durum değişiklikleri ile e-posta gönderir ve ardından SharePoint 'i kararlarla güncelleştirir.

## <a name="prerequisites"></a>Kaynakları

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Oluşturduğunuz SharePoint Online listesinde şu sütunlar bulunmalıdır:

   ![SharePoint liste sütunları](./media/parallel-modern-approvals/sharepoint-columns.png)

SharePoint Online listesinin adını ve URL 'sini unutmayın. Bu öğeleri daha sonra SharePoint 'i yapılandırmak için kullanıyoruz. **bir öğe oluşturulduğunda** tetikleyici.

## <a name="create-your-flow-from-the-blank-template"></a>Boş şablondan akışınızı oluşturun

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Tetikleyici ekleme

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![SharePoint bilgileri](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Tatil isteğini oluşturan kişi için yöneticiyi al

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Akışınızı adlandırın ve kaydedin

1. Akışınız için bir ad girin ve ardından, şimdiye kadar yaptığımız işi kaydetmek için **Kaydet** simgesini seçin.

   ![akışı Kaydet](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> Akışındaki değişiklikleri kaydetmek için düzenli aralıklarla **Kaydet** simgesini seçin.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>Anlık yönetici için onay eylemi ekleme

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> Bu eylem, tatil isteğini **atanan** kutusundaki e-posta adresine gönderir, bu nedenle **yöneticiyi al (v2)** listesinden **e-posta** belirtecini ekleyin.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Satış ekibi için paralel bir dal onay eylemi ekleyin

1. **Get Manager (v2)** ve **bir onay başlatma** kartları arasında bulunan aşağı oku seçin.
2. Seçtikten sonra aşağı ok üzerinde görüntülenen artı işaretini seçin.
3. **Paralel dal Ekle ' yi**seçin.
4. **Eylem Ekle**' yi seçin.

    ![Yönetici yapılandırmasını al](./media/parallel-modern-approvals/add-parallel-branch.png)
5. ' İ bulun, seçin ve ardından, tatil isteğini satış ekibine gönderen bir **onay başlangıcı** eylemi yapılandırın. **Bir onay başlatma** eyleminin nasıl ekleneceğini bilmiyorsanız, [hemen yöneticiye onay eylemi eklemek için kullanılan adımlara](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager) bakın.

> [!IMPORTANT]
> **Onay 2 başlangıç** eyleminin **atanan** kutusunda Sales ekibinin e-posta adresini kullanın.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>İnsan kaynakları ekibi için paralel bir dal onay eylemi ekleyin

1. Satış ekibinin eklemek üzere bir [paralel dal](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) eklemek ve ardından insan kaynaklarına tatil istekleri göndermek için bir **onay Başlat** eylemi yapılandırmak için bu adımları tekrarlayın.

> [!IMPORTANT]
> **Onay 3** ' ün başlama eyleminin **atanan** kutusunda insan kaynakları ekibinin e-posta adresini kullanın.
> 
> 

Bunu takip ediyorsanız, akışınız Şu örneğe benzemelidir:

   ![paralel dallarla akış](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Paralel dallar eklendikten sonra Seçenekler

Paralel dallara eylem ekledikten sonra, akışınıza daha fazla adım eklemek için iki seçeneğiniz vardır:

1. Küçük **yeni adım Ekle** düğmesini (daldaki herhangi bir boşluğu veya bir dalın hemen altındaki alanı seçtiğinizde görüntülenen dairesel artı düğmesini) kullanın. Bu düğme, **belirli bir dala**bir adım ekler. Bu düğmeyle eklediğiniz adımlar, bu özel dal tamamlandıktan sonra çalışır.
1. Tüm iş akışının alt kısmındaki daha büyük **yeni adım** düğmesini kullanın. Bu düğmeyle eklediğiniz adımlar tüm dallar tamamlandıktan sonra çalışır.

Aşağıdaki bölümlerde, her dalda bu adımları gerçekleştirmek için küçük **yeni adım Ekle** düğmesini kullanıyoruz:

* Tatil isteğinin onaylandığını veya reddedildiğini denetleyen bir koşul ekleyin.
* Kararı çalışana bildiren bir e-posta gönderin.
* SharePoint 'teki tatil isteğini onay kararı ile güncelleştirin.

Daha sonra, tatil isteğinde yapılan tüm kararları özetleyen bir e-posta göndermek için daha büyük **yeni adım** düğmesini kullanıyoruz.

Devam edelim:

## <a name="add-a-condition-to-each-branch"></a>Her dala bir koşul ekleyin

1. **Bir onay dalı başlatma** üzerinde herhangi bir boşluk seçin.
2. Küçük **yeni adım Ekle** düğmesini (önceki adımda yer alan boşluk ' u seçtikten sonra görüntülenen dairesel artı düğmesini) seçin.
3. Görüntülenen menüden **Koşul Ekle** ' yi seçin.
4. **Koşul** kartındaki ilk kutuyu seçin ve ardından dinamik içerik listesindeki **onay Başlat** kategorisinden **Yanıt** belirtecini seçin.

    ![paralel dallar koşulunun bulunduğu akış](./media/parallel-modern-approvals/configure-approval-condition.png)
5. Listenin ( **koşul kartının**ortasında), **olarak**ayarlandığını onaylayın.
6. Son kutuya **Onayla** (Bu metin büyük/küçük harfe duyarlıdır) yazın.
7. Koşul kartınız şu örneğe benzemelidir:

    ![paralel dallar koşulunun bulunduğu akış](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Bu koşul, çalışanın yöneticisine giden **onay başlangıcı** eyleminden gelen yanıtı denetler.
   > 
   > 
8. Önceki adımları **bir onay başlangıcı** (satışlarla ilgili onay isteği) ve **bir onay 3** (insan kaynakları onay isteği) dallarına yeniden başlatın.

## <a name="add-email-actions-to-each-branch"></a>Her dala e-posta eylemleri ekleme

**Koşul** dalının **Evet** tarafında aşağıdaki adımları gerçekleştirin.

   Note: akışınız, istek onaylandığında e-posta göndermek için şu adımları kullanır:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![önceden onaylanmış e-posta şablonunu yapılandırma](includes/media/parallel-modern-approvals/yes-email-config.png)

Bir istek reddedildiğinde e-posta göndermek için **koşul** dalının **Hayır** ' ı kullanın ve ardından önceki adımları yineleyerek ret e-postası için bir şablon ekleyin.

Önceki adımları **bir onay başlangıcı** (satışlarla ilgili onay isteği) ve **bir onay 3** (insan kaynakları onay isteği) dallarına yeniden başlatın.

## <a name="update-the-vacation-request-with-the-decision"></a>Tatil isteğini kararlarla güncelleştirin

Kararları verirken SharePoint 'i güncelleştirmek için aşağıdaki adımları gerçekleştirin.

   Note: Bu adımları hem **if** hem de dalın **hiç** bir tarafında gerçekleştirdiğinizden emin olun.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![öğe yapılandırmasını Güncelleştir](./media/parallel-modern-approvals/configure-update-item.png)

**Bir onay başlangıcı oluşturma 2** ' de önceki adımları yineleyin ve **bir onay 3 dalı başlatın** .

## <a name="complete-the-flow"></a>Akışı doldurun

1. **Yeni adım** > **Eylem Ekle** ' yi seçin

    ![öğe yapılandırmasını Güncelleştir](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. Her onay sonucunu özetleyen bir e-posta göndermek için daha önce sunulan adımları kullanın. Bu e-postayı tatil isteğinde bulunan çalışana gönderin. Kartınız şu örneğe benzeyebilir:

   ![öğe yapılandırmasını Güncelleştir](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>Modern onaylar hakkında daha fazla bilgi edinin

[Modern onaylara giriş](modern-approvals.md)

