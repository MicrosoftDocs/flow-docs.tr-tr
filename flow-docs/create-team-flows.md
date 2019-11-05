---
title: Bir akışa başka sahipler eklemeyi ve ekip akışları oluşturmayı öğrenin | Microsoft Docs
description: Microsoft Flow yinelenen görevleri otomatik hale getirmeyi kolaylaştırır. Kullanıcıları veya grupları sahip olarak ekleyebilir ve akışları tasarlamak ve yönetmek için bunlarla işbirliği yapabilirsiniz.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f2a986568a44f8329e55fc62aef4705207cdfc49
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547615"
---
# <a name="create-team-flows"></a>Ekip akışları oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Kuruluşunuzdaki diğer kişilerin sahiplerini sahip olarak ekleyerek bir ekip akışı oluşturun. Bir ekip akışının tüm sahipleri şu eylemleri gerçekleştirebilir:

* Akışın geçmişini (yani, her çalıştırma) görüntüleyin.
* Akışın özelliklerini yönetin (örneğin, akışı başlatın veya durdurun, bir bağlantı için sahipleri ekleyin veya kimlik bilgilerini güncelleştirin).
* Akışın tanımını düzenleyin (örneğin, bir eylem veya koşul ekleme veya kaldırma).
* Diğer sahipleri ekleyin ve kaldırın (akışın Oluşturucusu değil).
* Akışı silin.

Bir ekip akışının Oluşturucusu veya sahibiyseniz, bu dosyayı [Microsoft Flow](https://flow.microsoft.com) **Takım akışları** sekmesinde listelendiğini göreceksiniz.

![ekip akışları sekmesi](./media/create-team-flows/addowner5.png)

> [!NOTE]
> Paylaşılan Bağlantılar **yalnızca** oluşturuldukları akışta kullanılabilir.
> 
> 

Sahipler bir akışta hizmetleri kullanabilir, ancak başka bir sahibin oluşturduğu bir bağlantının kimlik bilgilerini değiştiremezler.

## <a name="prerequisites"></a>Kaynakları
Bir takım akışı oluşturmak için [ücretli bir Microsoft Flow planınız](https://flow.microsoft.com/pricing/) olmalıdır. Ayrıca, bir ekip akışından sahip eklemek/kaldırmak için Oluşturucu ya da sahip olmanız gerekir.

## <a name="create-a-team-flow"></a>Ekip akışı oluşturma
Bir takım akışı oluşturmak veya bir takım akışına daha fazla sahip eklemek için bu adımları izleyin.

1. [Microsoft Flow](https://flow.microsoft.com)oturum açın ve **Akışlarım**' ı seçin.
2. Değiştirmek istediğiniz akış için kişiler simgesini seçin:
   
    ![takım simgesi](./media/create-team-flows/addowner1.png)
3. Sahip olarak eklemek istediğiniz kişi veya grubun adını, e-posta adresini veya grup adını girin:
   
    ![Kullanıcı ara](./media/create-team-flows/addowner2.png)
4. Görüntülenen listede, sahip yapmak istediğiniz kullanıcıyı seçin:
   
    ![Kullanıcıyı seçin](./media/create-team-flows/addowner3.png)
   
     Seçtiğiniz kullanıcı veya Grup, akışın sahibi olur:
   
    ![Yeni sahip](./media/create-team-flows/addowner4.png)
   
     Tebrikler &mdash; takım akışınız oluşturuldu!

## <a name="add-a-list-as-a-co-owner"></a>Ortak sahip olarak liste ekleme

Listeye düzenleme erişimi olan herkesin otomatik olarak akışa yönelik düzenleme erişimi almasını sağlamak için bir akışa ortak sahip olarak SharePoint listeleri ekleyebilirsiniz. Akış paylaşıldıktan sonra yalnızca bir bağlantıyı dağıtabilirsiniz.

> [!TIP]
> Akış SharePoint 'e bağlıyken bir liste kullanın ve başka durumlarda bir grup kullanın.
>

## <a name="remove-an-owner"></a>Sahibini kaldırma

> [!IMPORTANT]
> Kimlik bilgileri Microsoft Flow hizmetlere erişmek için kullanılan bir sahibi kaldırdığınızda, akışın düzgün çalışmaya devam etmesi için bu bağlantıların kimlik bilgilerini güncelleştirmeniz gerekir.
> 
> 

1. Değiştirmek istediğiniz akış için kişiler simgesini seçin:
   
    ![kişi Seç simgesi](./media/create-team-flows/removeowner1.png)
2. Kaldırmak istediğiniz sahibin **silme** simgesini seçin:
   
    ![Sil ' i seçin](./media/create-team-flows/removeowner2.png)
3. Onay iletişim kutusunda, **Bu sahibi kaldır**' ı seçin:
   
    ![Kaldırmayı Onayla](./media/create-team-flows/removeowner3.png)
4. Tebrikler &mdash; kaldırdığınız Kullanıcı veya grup artık akışın sahibi olarak listelenmez:
   
    ![Kullanıcı kaldırıldı](./media/create-team-flows/removeowner4.png)


## <a name="update-connection-owner"></a>Bağlantı sahibini Güncelleştir

Mevcut sahibini kaldırırsanız bir akışta bağlantının sahibini değiştirmeniz gerekebilir. Akışın sahibini değiştirmek için şu adımları izleyin:

1. Sol taraftaki panelden **veri** seçin.
1. **Bağlantılar**' ı seçin.
1. Güncelleştirmek istediğiniz bağlantıyı arayın ve ardından seçin.
1. Seçtiğiniz bağlantıda **...** (daha fazla komut) seçeneğini belirleyin ve ardından **Hesap değiştir**' i seçin.
1. Bağlantı için farklı bir hesap kullanmak için adımları izleyin.

## <a name="embedded-and-other-connections"></a>Katıştırılmış ve diğer bağlantılar

Akışta kullanılan bağlantılar iki kategoriye ayrılır:

* **Katıştırılmış** &mdash; bu bağlantılar akışta kullanılır.
* **Diğer** &mdash; bu bağlantılar bir akış için tanımlanmıştır, ancak içinde kullanılmaz.

Bir akışta bağlantı kullanmayı durdurursanız, bu bağlantı **diğer** bağlantılar listesinde görünür ve burada, bir sahip tarafından akışa yeniden dahil edilene kadar kalır.

Gömülü bağlantılarda değişiklik yapmak üzere [bir bağlantı sahibini güncelleştirmek](./create-team-flows.md#update-connection-owner) için adımları izleyin.

Bağlantıların listesi, akışın özelliklerindeki sahipler listesi altında görüntülenir:

![katıştırılmış bağlantılar](./media/create-team-flows/embeddedconnections.png)

