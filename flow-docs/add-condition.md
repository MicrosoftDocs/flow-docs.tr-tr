---
title: Akışa koşul ekleme | Microsoft Docs
description: Bir akışın, yalnızca bir koşulun doğru olması durumunda bir veya daha fazla görev gerçekleştirmesini belirtebilirsiniz.
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
ms.openlocfilehash: b4407238f9d1782db802b47060b156b8b77c328b
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456377"
---
# <a name="add-a-condition-to-a-flow"></a>Akışa koşul ekleme

Bir akışın, yalnızca bir koşulun doğru olması durumunda bir veya daha fazla görev gerçekleştirmesini belirtebilirsiniz. Örneğin, anahtar sözcük içeren bir tweet'in yalnızca en az 10 kez retweetlenmesi durumunda bir e-posta alacağınızı belirtin.

## <a name="prerequisites"></a>Önkoşullar

* Şablondan [akış oluşturma](get-started-logic-template.md) - Bu öğreticide örnek olarak [bu şablon kullanılır](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/)

## <a name="add-a-condition"></a>Koşul ekleme

1. [Microsoft Flow](https://flow.microsoft.com)'da, üst gezinti çubuğundan **Akışlarım**'ı seçin.

    Henüz oturum açmadıysanız oturum açmanız gerekebilir.

1. Akış listesinde oluşturduğunuz akışlardan birini seçin.

    Bu öğreticide, bir Twitter tetikleyicisi ve SharePoint eylemi içeren bir örnek kullanılmıştır.

1. **Akışı düzenle**'yi seçin.

1. Son eylem altında, **Yeni adım**’ı seçin.

1. **Koşul ekle**'yi seçin.

    ![Koşul düğmesi](./media/add-condition/add-condition.png)

1. **Koşul** kartında, sol taraftaki kutudan boş bir alan seçin.

    **Dinamik içerik** listesi açılır.

1. Kutuya eklemek üzere **Retweet sayısı** parametresini seçin.

1. **Koşul** kartının ortasındaki kutudan **büyük veya eşit** öğesini seçin.

1. Sağ taraftaki kutuya **10** değerini girin.

    ![Parametre içeren OBJECT NAME (NESNE ADI) kutusu](./media/add-condition/specify-condition.png)

1. Koşulun içinde kullanmak istediğiniz eylemin (**Create item** gibi) üst bilgisine tıklayın ve **If yes** yazan metnin altına sürükleyin.

    İmleci serbest bıraktığınızda eylem bu kutuya taşınır.

    ![Sürükleme eylemi](./media/add-condition/drag-action.png)

1. Eylem gereken şekilde yapılandırın.

1. Akışı kaydedin.

## <a name="edit-in-advanced-mode"></a>Gelişmiş modda düzenleme

Daha gelişmiş koşullar yazmak için **Gelişmiş modda düzenle** öğesini de seçebilirsiniz. Gelişmiş moddaki *İş akışı tanımlama dili* içinden herhangi bir ifadeyi kullanabilirsiniz. Tüm kullanılabilir [ifadeler](https://msdn.microsoft.com/library/azure/mt643789.aspx) hakkında bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar

Gelişmiş moddaki koşullarda [ifadeleri kullanma](use-expressions-in-conditions.md) hakkında bilgi edinin.
