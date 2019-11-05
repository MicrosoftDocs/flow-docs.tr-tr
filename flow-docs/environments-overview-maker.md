---
title: Microsoft Flow ortamları hakkında bilgi edinin | Microsoft Docs
description: Akışlarını yalıtmak için ortamları nasıl kullanacağınızı öğrenin
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
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8890e621d14fb0f2d00af4cdf767f05ddeab9f21
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547950"
---
# <a name="choosing-an-environment"></a>Ortam seçme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bu makalede, akışları, ağ geçitlerini, bağlantılarınızı ve diğer kaynaklarınızı oluşturabileceğiniz ve güvenli bir şekilde ayırabilmeniz için kullanabileceğiniz **ortamlar** Microsoft Flow açıklanır.

Şunları öğreneceksiniz:

* Ortamların sağladığı özellikler.
* Ortamlar arasında geçiş yapma.
* Doğru ortamda akış oluşturma.

## <a name="environments-overview"></a>Ortamlara genel bakış

Bir akış oluşturduğunuzda, akışı barındıracak bir ortam ve akışın kullandığı kaynakları seçersiniz. Farklı senaryolar için ayrı ortamlar kullanabilirsiniz.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Ortamları kullanmaya yönelik bazı senaryolar aşağıda verilmiştir

Senaryon|Önerilen
-----|-----
Microsoft Common Data Service bağlantısını kullanan bir akış oluşturmak istiyorsunuz.|Akışınızı ve Common Data Service aynı ortama yerleştirin. Bu, tüm verilerin bu ortam içinde yalıtılması (yalıtım sınırı) sağlar.
Insan kaynakları departmanınız için bir akış oluşturuyorsunuz. Yalnızca Insan kaynakları departmanınızdaki kullanıcıların akışa erişimi olduğundan emin olmak istiyorsunuz.|Bir ortam oluşturun ve yalnızca ık kullanıcıları ekleyin. Akışı ve akışın kullandığı diğer kaynakları bu ortama yerleştirin.
Avrupa 'da SharePoint verilerini göstermek için akış kullanan kullanıcılar vardır.|Avrupa 'da bir ortam oluşturun ve ardından akışınızdan SharePoint bağlantısını oluşturun. Bu Avrupa ortamı, tüm kaynaklar Avrupa 'Da (veri konumu) yerel olduğundan Avrupa kullanıcılarına en iyi performansı verir.

Ortamları oluşturmak için bir Microsoft Flow yöneticisi olmanız gerekir. Ortamlara kimin erişimi olduğunu denetleyen yöneticiler. Ortamları oluşturma ve yönetme hakkında ayrıntılı bilgi için [ortamları yönetme](environments-overview-admin.md) konusuna bakın.

## <a name="switching-environments"></a>Ortamları değiştirme

Microsoft Flow ortamlar arasında geçiş yapmayı kolaylaştırır. Ortamları değiştirdiğinizde yalnızca ilgili ortamda oluşturulan öğeleri görürsünüz; başka bir ortamdaki öğelere yönelik olarak görmezsiniz veya erişiminiz yok.

İşte bir örnek.

*Insan kaynakları* ortamında *yeniçalışan* adlı bir akış oluşturdunuz. [Microsoft Flow](https://flow.microsoft.com), *Satış* ortamını açarsınız. *Yeniçalışan* akışı listelenmez. *Yeniçalışan* akışını görmek Için *insan kaynakları* ortamını açın. Aynı kuralların bağlantılar, ağ geçitleri, akışlar ve daha fazlası dahil olmak üzere, ortamda oluşturduğunuz diğer tüm öğeler için de uygulandığını unutmayın.

Ortamları değiştirmek için şu adımları izleyin:

1. [Microsoft Flow](https://flow.microsoft.com)oturum açın.
1. Sağ üst köşede, profilinizi temsil eden bir görüntü görürsünüz.

   ![profil resmi](./media/environments-overview-maker/default-environment.png)

1. Görüntüyü seçin. Açılan listede, size sunulan tüm ortamlar görüntülenir. Şu anda oturum açtığınız ortam işaretlendi:

   ![ortam görüntüsü listesi](./media/environments-overview-maker/all-environments.png)
1. Başka bir ortama geçiş yapmak için listeden bu ortamı seçin:

   ![geçiş yapmak için bir ortam seçin](./media/environments-overview-maker/select-europe.png)
1. Microsoft Flow yeni ortama geçiş yapar.

## <a name="create-flows-in-the-right-environment"></a>Doğru ortamda akış oluşturma

Bir akış oluşturmadan önce, akışını ve kaynaklarını ekleyeceğiniz ortamı seçin.

> [!NOTE]
> Yanlış ortamda bir akış oluşturursanız, onu silmeniz ve ardından doğru ortamda oluşturmanız gerekir.

Akışlarınızı barındırmak için bir ortam seçerken aşağıdaki faktörleri göz önünde bulundurun:

* Yalnızca varsayılan ortamda ağ geçitleri oluşturabilirsiniz. Bu nedenle, akışınızı şirket içi verilere bağlamak üzere bir ağ geçidi kullanmak istiyorsanız, varsayılan ortamı kullanmanız gerekir.
* Microsoft Common Data Service veritabanları belirli bir ortama bağlıdır. Bu nedenle, Common Data Service kullanan bir akış oluşturmak istiyorsanız, akışı veritabanını barındıran ortamda oluşturmanız gerekir.
* Kaynakları düzenleyebileceğiniz tüm ortamları görürsünüz. Ancak, bir yöneticiden akışları oluşturmak istediğiniz tüm ortamlara bir Oluşturucu olarak eklemesini istemeniz gerekir.

> [!NOTE]
> Her zaman varsayılan ortamda akış oluşturabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

* [Şablondan akış oluşturma](get-started-logic-template.md)
* [Akış oluşturma](get-started-logic-flow.md)
* [Yöneticiler için ortama genel bakış](environments-overview-admin.md)
