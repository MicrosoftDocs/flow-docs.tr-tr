---
title: Microsoft Flow ortamları hakkında bilgi edinin | Microsoft Docs
description: Akışlarınıza yalıtım uygulamak için ortamları kullanmayı öğrenin
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/27/2017
ms.author: sunayv
ms.openlocfilehash: e6667c1c1999c36177d40d52fa657edadd063516
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "31008323"
---
# <a name="choosing-an-environment"></a>Ortam seçme

Bu makalede akışlarınızı, ağ geçitlerinizi, bağlantılarınızı ve diğer kaynaklarınızı oluşturabileceğiniz ve güvenli bir şekilde yalıtabileceğiniz Microsoft Flow **ortamları** hakkında bilgi verilmektedir.

Şu öğeler hakkında bilgi edineceksiniz:

* Ortamların sunduğu özellikler.
* Ortamlar arasında geçiş yapma.
* Akışı doğru ortamda oluşturma.

## <a name="environments-overview"></a>Ortamlara genel bakış

Bir akış oluştururken, akışı barındıracak ortamı ve bu akışın kullanacağı kaynakları seçersiniz. Farklı senaryolar için ayrı ortamlar kullanabilirsiniz.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Aşağıda bazı ortam kullanma senaryolarına yer verilmiştir

Senaryo|Öneri
-----|-----
Microsoft Common Data Service bağlantısı kullanan bir akış oluşturmak istiyorsunuz.|Akış ve Common Data Service verilerinizi aynı ortamda barındırın. Bu, tüm verilerin bu ortamda yalıtılmasını sağlar (yalıtım sınırı).
İnsan Kaynakları departmanınız için bir akış oluşturuyorsunuz. Yalnızca İnsan Kaynakları departmanınızdaki kullanıcıların bu akışa erişebilmesini sağlamak istiyorsunuz.|Bir ortam oluşturun ve yalnızca İK kullanıcılarını ekleyin. Akışı ve akışın kullandığı diğer kaynakları bu ortama yerleştirin.
Avrupa'da SharePoint verilerini göstermek için akış kullanan kullanıcılar mevcuttur.|Akışı ve SharePoint bağlantısını barındırmak üzere Avrupa'da bulunan bir ortam oluşturun. Bu Avrupa ortamı, tüm kaynaklar Avrupa'da bulunduğu için (yerel veri konumu) Avrupa'daki kullanıcılara en iyi performansı sunar.

Ortam oluşturmak için Microsoft Flow yöneticisi olmanız gerekir. Ortam erişimlerini yöneticiler denetleyebilir. Ortam oluşturma ve yönetme hakkında ayrıntılı bilgi için bkz. [Ortamları yönetme](environments-overview-admin.md).

## <a name="switching-environments"></a>Ortamlar arasında geçiş yapma

Microsoft Flow, ortamlar arasında geçiş yapmayı kolaylaştırır. Ortamlar arasında geçiş yaptığınızda yalnızca belirli bir ortamda oluşturulmuş olan öğeleri görürsünüz. Diğer ortamlardaki öğeleri göremez ve bunlara erişemezsiniz.

İşte bir örnek:

*İnsan Kaynakları* ortamında *YeniÇalışan* adında bir akış oluşturdunuz. [Microsoft Flow](https://flow.microsoft.com)'da *Satış* ortamını açarsınız. *YeniÇalışan* akışı listelenmez. *YeniÇalışan* akışını görmek için *İnsan Kaynakları* ortamını açın. Bu kuralların bağlantılar, ağ geçitleri, akışlar gibi ortamda oluşturduğunuz diğer tüm öğeler için geçerli olacağını unutmayın.

Ortamlar arasında geçiş yapmak için aşağıdaki adımları izleyin:

1. [Microsoft Flow](https://flow.microsoft.com)'da oturum açın.
1. Sağ üst köşede profilinizi gösteren bir resim göreceksiniz.

   ![profil resmi](./media/environments-overview-maker/default-environment.png)

1. Görüntüyü seçin. Açılır listede, kullanabileceğiniz tüm ortamlar görüntülenir. Oturum açmış olduğunuz ortamın yanında onay işareti bulunur:

   ![ortam listesi görüntüsü](./media/environments-overview-maker/all-environments.png)
1. Farklı bir ortama geçmek için listeden o ortamı seçin:

   ![geçiş yapmak istediğiniz ortamı seçin](./media/environments-overview-maker/select-europe.png)
1. Microsoft Flow yeni ortama geçer.

## <a name="create-flows-in-the-right-environment"></a>Akışı doğru ortamda oluşturma

Akış oluşturduğunuz için akışı ve kaynaklarını ekleyeceğiniz ortamı seçmeniz gerekir.

> [!NOTE]
> Akışı yanlış bir ortamda oluşturduysanız silip doğru ortamda tekrar oluşturmanız gerekir.

Akışlarınızın barındırılacağı ortamı seçerken aşağıdaki unsurları göz önünde bulundurun:

* Yalnızca varsayılan ortamda ağ geçidi oluşturabilirsiniz. Bu nedenle şirket içi verilerinize bağlanmak için bir ağ geçidi kullanmak isterseniz varsayılan ortamı kullanmanız gerekir.
* Microsoft Common Data Service veritabanları belirli bir ortama bağlıdır. Bu nedenle Common Data Service kullanan bir akış oluşturmak isterseniz akışı, veritabanını barındıran ortamda oluşturmanız gerekir.
* İçindeki kaynakları düzenleyebileceğiniz tüm ortamları görürsünüz. Ancak yöneticinizden sizi akış oluşturmak istediğiniz tüm ortamlara üretici olarak eklemesini istemeniz gerekir.

> [!NOTE]
> Varsayılan ortamda akış oluşturmak için herhangi bir ek izne ihtiyacınız yoktur.

## <a name="next-steps"></a>Sonraki adımlar

* [Şablondan akış oluşturma](get-started-logic-template.md)
* [Akış oluşturma](get-started-logic-flow.md)
* [Yöneticiler için ortamlara genel bakış](environments-overview-admin.md)