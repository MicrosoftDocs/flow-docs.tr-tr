---
title: Akışa koşul ekleme | Microsoft Docs
description: Bir akışın yalnızca bir koşulun doğru olması durumunda bir veya daha fazla görev gerçekleştireceğini belirtin.
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
ms.date: 10/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c67991a008047b2c8c58de3b9ae8833a5874543
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544708"
---
# <a name="add-a-condition-to-a-flow"></a>Akışa koşul ekleme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bir akışın yalnızca bir koşulun doğru olması durumunda bir veya daha fazla görev gerçekleştireceğini belirtin. Örneğin, yalnızca bir anahtar sözcük içeren bir tweet, en az 10 kez yeniden kullanılabilir olduğunda bir e-posta alınacağını belirtin.

## <a name="prerequisites"></a>Kaynakları

* Şablondan [akış oluşturma](get-started-logic-template.md) -Bu öğretici [Bu şablonu](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) örnek olarak kullanır

## <a name="add-a-condition"></a>Koşul ekleme

1. [Microsoft Flow](https://flow.microsoft.com), üst gezinti çubuğunda **Akışlarım** ' ı seçin.

    Henüz oturum açmadıysanız oturum açmanız gerekebilir.

1. Akışlar listesinde, oluşturduğunuz akışlardan birini seçin.

    Bu öğreticide Twitter tetikleyicisi ve SharePoint eylemiyle birlikte bir örnek kullanılmıştır.

1. **Akışı Düzenle**' yi seçin.

1. Son eylem altında **yeni adım**' ı seçin.

1. **Koşul Ekle**' yi seçin.

    ![Koşul düğmesi](./media/add-condition/add-condition.png)

1. **Koşul** kartında, sol taraftaki kutuda boş bir alan seçin.

    **Dinamik içerik** listesi açılır.

1. Kutuya eklemek için **retweet Count** parametresini seçin.

1. **Koşul** kartının ortasındaki kutudan **büyük veya eşittir**' i seçin.

1. Sağ taraftaki kutuya **10**girin.

    ![Bir parametre içeren nesne adı kutusu](./media/add-condition/specify-condition.png)

1. Koşul içinde kullanmak istediğiniz eylemin üst bilgisini (örneğin, **öğe oluştur**) seçin ve **Evet ise**okuyan metnin altına sürükleyin.

    İmleci serbest bırakırsanız, eylem bu kutuya gider.

    ![Sürükle eylemi](./media/add-condition/drag-action.png)

1. Eylemi gereken şekilde yapılandırın.

1. Akışı kaydedin.

## <a name="edit-in-advanced-mode"></a>Gelişmiş modda Düzenle

Daha gelişmiş koşullar yazmak için **Gelişmiş modda Düzenle '** yi de seçebilirsiniz. Herhangi bir ifadeyi gelişmiş modda *Iş akışı Tanım dilinden* kullanabilirsiniz. Kullanılabilir tüm [ifadeler](https://msdn.microsoft.com/library/azure/mt643789.aspx)hakkında bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar

İfadeleri gelişmiş modda koşullarda nasıl [kullanacağınızı](use-expressions-in-conditions.md) öğrenin.
