---
title: "Akışa koşul ekleme | Microsoft Docs"
description: "Bir akışın, yalnızca belirli bir koşulun doğru olması durumunda bir veya daha fazla görev gerçekleştirmesini belirtebilirsiniz."
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
ms.openlocfilehash: 1291b32f001be211acddbf1c83f3b1bdf03f2ac3
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="add-a-condition-to-a-flow"></a>Akışa koşul ekleme
Bir akışın, yalnızca belirli bir koşulun doğru olması durumunda bir veya daha fazla görev gerçekleştirmesini belirtebilirsiniz. Örneğin, anahtar sözcük içeren bir tweet'in yalnızca en az 10 kez retweetlenmesi durumunda bir e-posta alacağınızı belirtin.

**Önkoşullar**

* Şablondan [akış oluşturma](get-started-logic-template.md) - Bu öğreticide, örnek olarak [bu şablon kullanılacaktır](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/)

## <a name="add-a-condition"></a>Koşul ekleme
1. [flow.microsoft.com](https://flow.microsoft.com)'da, üst gezinti çubuğunda bulunan **Akışlarım**'ı seçin.
2. Akış listesinde, oluşturduğunuz bir akışı seçin. Bu öğreticide, bir Twitter tetikleyicisi ve SharePoint eylemi içeren bir örnek kullanılmıştır.
3. Son eylem altında, **Yeni adım** düğmesini seçin.
4. **Koşul ekle**'yi seçin.
   
    ![Koşul düğmesi](./media/add-a-condition/add-condition.png)
5. **Nesne adı**’nda boş bir alanı seçin ve **Dinamik içerik ekle**’yi seçerek dinamik içerik menüsünü açın.
6. Kutuya eklemek üzere **Retweet sayısı** parametresini seçin.
7. **Relationship** (İlişki) kutusunda, **is greater than or equal to**'yu (şundan büyük veya şuna eşittir) seçin.
8. **Value** (Değer) kutusuna **10** yazın.
   
    ![Parametre içeren OBJECT NAME (NESNE ADI) kutusu](./media/add-a-condition/specify-condition.png)
9. Koşulun içinde olmasını istediğiniz eylemin (**Create item (Öğe oluştur)** gibi) üst bilgisine tıklayın ve **IF YES (EVET İSE)** yazan metnin altına sürükleyin. İmleci serbest bıraktığınızda, eylem kutuya taşınmalıdır.
   
    ![Sürükleme eylemi](./media/add-a-condition/drag-action.png)
10. Akışı kaydedin.

## <a name="edit-in-advanced-mode"></a>Gelişmiş modda düzenleme
Daha gelişmiş koşullar yazmak için **Gelişmiş modda düzenle** bağlantısını da seçebilirsiniz. Buradaki  *İş akışı tanımlama dili* ’nden herhangi bir ifadeyi kullanabilirsiniz. Kullanılabilen işlevler [hakkında daha fazla bilgi edinin](https://msdn.microsoft.com/library/azure/mt643789.aspx).

