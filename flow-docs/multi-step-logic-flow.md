---
title: Gelişmiş seçenek ve birden çok eylem ekleme | Microsoft Docs
description: Bir akışı, e-postayı yüksek öncelikli olarak ayarlama ve aynı olay için başka bir eylem ekleme gibi gelişmiş bir seçeneğe dahil etmek için genişletin.
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
ms.date: 04/20/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 668e69b1c8f1781cf5720443af8e48409f43d322
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548604"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Akışa birden fazla eylem ve gelişmiş seçenek ekleme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Aynı tetikleyici için bir veya daha fazla gelişmiş seçenek ve birden çok eylem ekleyerek bir akışı özelleştirin. Örneğin, bir e-posta iletisini yüksek öncelikli olarak gönderen gelişmiş bir seçenek ekleyin. Bir SharePoint listesine öğe eklendiğinde e-posta göndermeye ek olarak Dropbox 'ta aynı bilgileri içeren bir dosya oluşturun.

## <a name="prerequisites"></a>Kaynakları
* [Akış oluşturma](get-started-logic-flow.md)

## <a name="add-another-action"></a>Başka eylem ekleme
Bu yordamda, akışın ortasına bir eylem ekleyeceksiniz. Bu eylem, Dropbox 'inizdeki bir dosyayı kaydeder ve listedeki öğeyi arşivlemesini ister.

1. [Flow.Microsoft.com](https://flow.microsoft.com)' de, üst gezinti çubuğunda **Akışlarım** ' ı seçin.
2. Akışlar listesinde, düzenlemek istediğiniz akışı seçin.
3. **Yeni adım**' ı seçin ve ardından **Eylem Ekle**' yi seçin.
   
    ![Daraltılmış ekleme](./media/multi-step-logic-flow/add-action.png)
4. Olası Eylemler listesinde, **dosya oluştur**' u arayın ve ardından **Dropbox-dosya oluştur**' u seçin.
   
    ![dosya oluştur ara](./media/multi-step-logic-flow/create-file-search.png)
5. İstenirse Dropbox kimlik bilgilerinizi girin.
6. **Klasör yolu** kutusunun sağ tarafındaki klasör simgesini seçin.
7. Yeni dosyayı yerleştirmek istediğiniz klasörü bulun ve seçin.
   
    ![dosya oluştur ara](./media/multi-step-logic-flow/create-file-folder.png)
8. **Dosya adı** kutusuna yeni dosyanın adını girin. Dosya adına ". txt" gibi bir uzantı eklemediğinizden emin olun. Burada, dosyaların benzersizliğini sağlamak için dosyanın adı içindeki **Boyut** /gün sayısını kullanalım. Kesilebilir **Etıd** belirtecini bulmak için **daha fazla görüntüle** ' yi seçmeniz gerekebilir.
9. Dosya **içeriği** kutusuna yazarak dosyanın içermesini istediğiniz metni ekleyin. **Dosya içeriği** kutusuna belirteçler de ekleyebilirsiniz.
   
    ![dosya adı ve içeriği](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Dosyaya varolan bir dosyanın adıyla (seçili klasörde) eşleşen bir ad verirseniz, var olan dosyanın üzerine yazılır.
   > 
   > 
10. Ekranın üst kısmındaki menüde bulunan **akışı Güncelleştir**' i seçin.
11. Belirttiğiniz anahtar sözcüğü içeren bir tweet gönderin.
    
     Bir dakika içinde Dropbox hesabınızda bir dosya oluşturulur.

## <a name="reorder-or-delete-an-action"></a>Bir eylemi yeniden sıralama veya silme
* Dropbox 'ta Dosya oluşturulduktan sonra e-posta almak için, başlık çubuğunu e-posta eyleminin üzerine sürükleyerek Dropbox eylemini taşıyın. Dropbox eylemini tetikleyici (**Yeni bir tweet**gönderildiğinde) ve e-posta eylemi arasındaki ok üzerinde serbest bırakın. (İmleç, eylemin doğru şekilde konumlandırılıp yerleştirilmediğini gösterir.)
  
  > [!NOTE]
  > Bu adımdan herhangi bir çıkış kullanıyorsanız, bir adımı başka bir şekilde taşıyamazsınız.
  > 
  > 
  
    ![Menüyü Sil](./media/multi-step-logic-flow/draggingaction.png)
* Bir eylemi silmek için, silmek istediğiniz eylem için başlık çubuğunun sağ kenarının yanındaki üç nokta (...) simgesini seçin, **Sil**' i seçin ve ardından **Tamam**' ı seçin.
  
    ![Menüyü Sil](./media/multi-step-logic-flow/deletemenu.png)
  
     **Note:** Akıştaki herhangi bir yerden çıkış kullanıyorsanız, bir eylemi silemezsiniz. İlk olarak, bu çıktıları alanlardan kaldırın ve sonra eylemi silebilirsiniz.


## <a name="copy-and-paste-actions"></a>Kopyalama ve yapıştırma eylemleri

Bir akış tasarlarken eylemleri yinelemek istiyorsanız, bunları kopyalayabilir ve yapıştırabilirsiniz. Örneğin, bir koşul oluşturuyorsanız ve her iki eylemi de sıfırdan oluşturmak yerine, **Eğer Evet** tarafında ve **varsa** benzer eylemler istiyorsanız, ilk eylemi bir tarafta oluşturup diğer tarafa kopyalayabilirsiniz.


### <a name="to-copy-an-action"></a>Bir eylemi kopyalamak için
1. Eylem menüsünü (...) seçin. , eylemin sağ üst kısmında).
1. **Panonuzun Kopyala**' yı seçin. 
1. Eylemin gitmesini istediğiniz **yeni adım** ' u seçin. 

     Kopyaladığınız tüm eylemlerden seçim yapmanızı sağlayan **panonuzun** sekmesine dikkat edin.
1. Yapıştırmak istediğiniz öğeyi seçin.

## <a name="add-advanced-options"></a>Gelişmiş Seçenekler Ekle
**E-posta gönder** eylemine sahip bir akış ile başlayın.

1. **E-posta gönder** kartının altında bulunan **Gelişmiş seçenekleri göster**' i seçin.
   
     Daha sonra e-posta göndermek için gelişmiş seçenekleri görürsünüz.
   
    ![SharePoint Tetikleyicileri](./media/multi-step-logic-flow/advanced.png)
2. **Önem** listesinden **yüksek** ' ı seçin ve gelişmiş seçenekleri gizlemek için **Gelişmiş seçenekleri gizle** ' yi seçin.
3. Ekranın üst kısmındaki menüde bulunan **akışı Güncelleştir**' i seçin.
   
     Bu adım değişikliklerinizi kaydeder.

