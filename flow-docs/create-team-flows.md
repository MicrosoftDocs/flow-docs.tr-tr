---
title: "Bir akışa başka sahipler eklemeyi ve ekip akışları oluşturmayı öğrenme | Microsoft Docs"
description: "Microsoft Flow, yinelenen görevleri otomatikleştirmeyi kolaylaştırır. Kullanıcı veya grupları sahip olarak ekleyebilir, ayrıca akışları tasarlamak ve yönetmek için işbirliği yapabilirsiniz."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/21/2017
ms.author: deonhe
ms.openlocfilehash: d4e8de2f9f67c07861297e079948a5336ff66e7f
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="create-team-flows"></a>Takım akışları oluşturma
Kuruluşunuza başka kişileri de sahip olarak ekleyip bir takım akışı oluşturun. Takım akışının tüm sahipleri şu eylemleri gerçekleştirebilir:

* Akış geçmişini (yani her çalıştırmayı) görüntüleme.
* Akışın özelliklerini (akışı başlatma veya durdurma, sahip ekleme ya da bağlantı için kimlik bilgilerini güncelleştirme gibi) yönetin.
* Akışın tanımını (bir eylemi veya koşulu ekleme ya da kaldırma gibi) düzenleyin.
* Diğer sahipleri ekleyin ve kaldırın (akış oluşturucusu hariç).
* Akışı silme.

Bir akışın oluşturucusu veya sahibiyseniz, bu akışı [Microsoft Flow](https://flow.microsoft.com)’un **Takım akışları** sekmesindeki listede bulabilirsiniz.

![takım akışları sekmesi](./media/create-team-flows/addowner5.png)

> [!NOTE]
> Paylaşılan bağlantılar **yalnızca** oluşturuldukları akışın içinde kullanılabilir.
> 
> 

Akış sahipleri bir akışın içindeki hizmetleri kullanabilir ancak başka bir sahibin oluşturduğu bir bağlantı için kimlik bilgilerini değiştiremez.

## <a name="prerequisites"></a>Önkoşullar
Takım akışı oluşturmak için [ücretli bir Microsoft Flow planınız](https://flow.microsoft.com/pricing/) olmalıdır. Buna ek olarak, takım akışında sahipleri eklemek/kaldırmak için oluşturucu veya sahip olmanız gerekir.

## <a name="create-a-team-flow"></a>Takım akışı oluşturma
Takım akışı oluşturmak veya bir takım akışına sahip eklemek için aşağıdaki adımları izleyin.

1. [Microsoft Flow](https://flow.microsoft.com)’da oturum açın ve sonra **Akışlarım**’ı seçin.
2. Değiştirmek istediğiniz akış için kişiler simgesini seçin:
   
    ![takım simgesi](./media/create-team-flows/addowner1.png)
3. Sahip olarak eklemek istediğiniz kişi veya grubun adını, e-posta adresini veya grup adını girin:
   
    ![kullanıcı için arama yapma](./media/create-team-flows/addowner2.png)
4. Görüntülenen listede sahip olarak belirlemek istediğiniz kullanıcıyı seçin:
   
    ![kullanıcıyı seçme](./media/create-team-flows/addowner3.png)
   
     Seçmiş olduğunuz kullanıcı veya grup, akışın sahiplerinden biri olur:
   
    ![yeni sahip](./media/create-team-flows/addowner4.png)
   
     Tebrikler &mdash; takım akışınız oluşturuldu!

## <a name="remove-an-owner"></a>Akış sahibini kaldırma
> [!IMPORTANT]
> Kimlik bilgileri Microsoft Flow hizmetlerine erişmek için kullanılan bir sahibi kaldırırsanız, akışın düzgün çalışmaya devam etmesi için söz konusu bağlantıların kimlik bilgilerini güncelleştirmeniz gerekir.
> 
> 

1. Değiştirmek istediğiniz akış için kişiler simgesini seçin:
   
    ![kişi seç simgesi](./media/create-team-flows/removeowner1.png)
2. Kaldırmak istediğiniz sahip için **Sil** simgesini seçin:
   
    ![silmeyi seçme](./media/create-team-flows/removeowner2.png)
3. Onay iletişim kutusunda, **Bu sahibi kaldır**’ı seçin:
   
    ![kaldırmayı onaylama](./media/create-team-flows/removeowner3.png)
4. Tebrikler &mdash; kaldırdığınız kullanıcı veya grup artık akışın bir sahibi olarak listelenmez:
   
    ![kullanıcı kaldırıldı](./media/create-team-flows/removeowner4.png)

## <a name="embedded-and-other-connections"></a>Katıştırılmış ve diğer bağlantılar
Bir akışta kullanılan bağlantılar iki kategoriye ayrılır:

* **Katıştırılmış** &mdash; Bu bağlantılar akışın içinde kullanılır.
* **Diğer** &mdash; Bu bağlantılar bir akış için tanımlanmıştır ancak akışın içinde kullanılmaz.

Akışın içinde bir bağlantının kullanılmasını durdurursanız, bir sahip bağlantıyı akışa yeniden ekleyene kadar bu bağlantı **Diğer** bağlantılar listesinde görünür.

Bağlantılar listesi, akış özelliklerinde sahipler listesinin altında görünür:

![eklenmiş bağlantılar](./media/create-team-flows/embeddedconnections.png)

