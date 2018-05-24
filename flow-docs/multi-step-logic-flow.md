---
title: Gelişmiş seçenek ve birden fazla eylem ekleme | Microsoft Docs
description: Akışı, gelişmiş bir seçenek içerecek şekilde (e-postayı yüksek öncelikli olarak ayarlamak gibi) genişletin ve aynı etkinlik için farklı bir eylem ekleyin.
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
ms.openlocfilehash: f6c936cbf5a2bd481adb52ec9b01545fb9ba7b0b
ms.sourcegitcommit: f0202f74ba9a2282a670a1751462f598a5ea0ce5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Akışa birden fazla eylem ve gelişmiş seçenek ekleme
Aynı tetikleyici için bir veya daha fazla gelişmiş seçenek ve birden fazla eylem ekleyerek akışı özelleştirin. Örneğin, bir e-posta iletisini yüksek öncelikli olarak gönderen gelişmiş bir seçenek ekleyin. SharePoint listesine bir öğe eklendiğinde e-posta göndermeye ek olarak Dropbox'ta aynı bilgileri içeren bir dosya oluşturun.

## <a name="prerequisites"></a>Önkoşullar
* [Akış oluşturma](get-started-logic-flow.md)

## <a name="add-another-action"></a>Farklı bir eylem ekleme
Bu yordamda, akışın ortasına bir eylem ekleyeceksiniz. Bu eylem, listedeki öğeyi arşivleyerek Dropbox hesabınıza bir dosya kaydeder.

1. [flow.microsoft.com](https://flow.microsoft.com)'da, üst gezinti çubuğunda bulunan **Akışlarım**'ı seçin.
2. Akış listesinde, düzenlemek istediğiniz akışı seçin.
3. **Yeni adım**'ı ve ardından **Eylem ekle**'yi seçin.
   
    ![Daraltılmış ekleme](./media/multi-step-logic-flow/add-action.png)
4. Olası eylemler listesinde, **Dosya oluştur**'u arayın ve ardından **Dropbox - Dosya oluştur**'u seçin.
   
    ![Dosya oluştur seçeneğini arayın](./media/multi-step-logic-flow/create-file-search.png)
5. İstenirse Dropbox kimlik bilgilerinizi sağlayın.
6. **Klasör yolu** kutusunun sağ tarafındaki klasör simgesini seçin.
7. Yeni dosyayı yerleştirmek istediğiniz klasörü bulun ve seçin.
   
    ![Dosya oluştur seçeneğini arayın](./media/multi-step-logic-flow/create-file-folder.png)
8. Yeni dosyanın adını **Dosya adı** kutusuna girin. Dosya adına ".txt" gibi bir uzantı eklemeyi unutmayın. Burada dosyaların benzersiz olduğundan emin olmak için dosya adına **TweetId** yazalım. **TweetId** belirtecini bulmak için **Daha fazla görüntüle**'yi seçmeniz gerekebilir.
9. Dosyanın içermesini istediğiniz metni **Dosya içeriği** kutusuna yazın. **Dosya içeriği** kutusuna belirteç de ekleyebilirsiniz.
   
    ![Dosya adı ve içeriği](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Dosyaya var olan dosyalardan (seçilen klasördeki) birinin adını verirseniz var olan dosyanın üzerine yazılır.
   > 
   > 
10. Ekranın üst tarafındaki menüde yer alan **Akışı güncelleştir**'i seçin.
11. Belirttiğiniz anahtar sözcüğü içeren bir tweet gönderin.
    
     Bir dakika içinde Dropbox hesabınızda bir dosya oluşturulur.

## <a name="reorder-or-delete-an-action"></a>Eylemi yeniden sıralama ve silme
* Dropbox'ta dosya oluşturulduktan sonra e-posta almak için, başlık çubuğunu e-posta eyleminin üzerine sürükleyerek Dropbox eylemini taşıyın. Dropbox eylemini tetikleyici (**Yeni bir tweet gönderildiğinde**) ile e-posta eylemi arasındaki okun üzerinde bırakın. (İmleç, eylemin doğru yerleştirilip yerleştirilmediğini belirtir.)
  
  > [!NOTE]
  > Bir adımdaki çıkışı kullanıyorsanız bu adımı başka bir adımın önüne taşıyamazsınız.
  > 
  > 
  
    ![Menüyü silme](./media/multi-step-logic-flow/draggingaction.png)
* Bir eylemi silmek için, silmek istediğiniz eyleme ait başlık çubuğunun sağ tarafında bulunan üç noktayı (...) seçip **Sil**'e tıklayın ve ardından **Tamam**'ı seçin.
  
    ![Menüyü silme](./media/multi-step-logic-flow/deletemenu.png)
  
     **Not:** Akışın herhangi bir yerinde, bir eyleme ait çıkışı kullanıyorsanız bu eylemi silemezsiniz. İlk olarak bu çıkışları alanlardan kaldırdıktan sonra eylemi silebilirsiniz.

## <a name="add-advanced-options"></a>Gelişmiş seçenekleri ekleme
**E-posta gönder** eylemine sahip bir akışla başlayın.

1. **E-posta gönder** kartının en altında yer alan **Gelişmiş seçenekleri göster**'i seçin.
   
     E-posta gönderimiyle ilgili gelişmiş seçenekleri göreceksiniz.
   
    ![SharePoint tetikleyicileri](./media/multi-step-logic-flow/advanced.png)
2. **Önem** listesinden **Yüksek** seçeneğini belirledikten sonra gelişmiş seçenekleri gizlemek için **Gelişmiş seçenekleri gizle**'yi seçin.
3. Ekranın üst tarafındaki menüde yer alan **Akışı güncelleştir**'i seçin.
   
     Bu adımla yaptığınız değişiklikler kaydedilir.

