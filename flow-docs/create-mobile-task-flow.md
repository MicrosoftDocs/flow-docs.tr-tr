---
title: PowerApps ile bir mobil görev akışı oluşturma | MicrosoftDocs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ccd3b6c0e8cf97a490d01bb9ba5e5c3c4043fda5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546439"
---
# <a name="create-a-mobile-task-flow"></a>Mobil görev akışı oluşturma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Telefonlar için Dynamics 365 ' de veya kullanıcılarınızın gerçekleştirdiği ortak görevlere göre tabletlere yönelik Dynamics 365 ' de bir akış tasarlayın. Örneğin, istemci toplantılarından sonra düzenli olarak bir dizi izleme adımı gerçekleştirmesi gerekiyorsa, bir görev akışı oluşturun. Kullanıcılar mobil uygulamasındaki yeni göreve dokunduğunda, bu, önemli bir adımı unutmamak için başlangıçtan sona kadar sürer.  
  
 Görev akışları çoklu varlık formlarını ve mantığını kullanabilir ve görev akışı sayfalarında çalışan form mantığına sahip olabilir.  
  
## <a name="create-a-task-flow"></a>Görev akışı oluşturma
  
1. Sistem Yöneticisi veya Sistem Özelleştirici güvenlik rolüne ya da eşdeğer izinlere sahip olduğunuzdan emin olun. Yönetici, Başkan Yardımcısı veya CEO-Iş Yöneticisi, güvenlik rolleri mobil görev akışları da oluşturabilir. 
  
2. [Çözüm Gezginini](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) açın ve **süreçler**' ı seçin.  
  
3.  **Eylemler** araç çubuğunda **Yeni**' yi seçin.  
  
4.  **Işlem oluştur** iletişim kutusunda gerekli alanları doldurun:  
  
    -   İşlem adı girin.  
  
    -   **Kategori** listesinde **iş süreci akışı**' nı seçin.  
  
    -   **Varlık** listesinde, istediğiniz varlığı seçin.  
  
5.  **İşlemi bir görev akışı olarak çalıştır (mobil çevrimiçi)** seçeneğini belirleyin.  
  
6.  **Tamam ' ı**seçin.
  
     Görev akışı Tasarımcısı yeni bir pencerede açılır.  
  
     ![Görev akışı Tasarımcı penceresi](media/task-flow-designer-window.png "Görev akışı Tasarımcı penceresi") 
  
7.  Kullanıcılarınız bir sayfadan diğerine İlerleyebiliyorsanız, **sayfa** bileşenini ekranın sağ tarafındaki **Bileşenler** sekmesinden sürükleyin ve uygun noktanın + işaretine bırakın. Bir sayfa için ad eklemek için sayfayı seçin, **Özellikler** sekmesini seçin, yeni bir ad yazın ve **Uygula**' yı seçin.  
  
8.  Görev akışına bir dal eklemek için, **Bileşenler** sekmesinden **koşul** bileşenini sürükleyin ve uygun noktanın + işaretine bırakın. Koşulun özelliklerini ayarlamak için koşulu seçin, **Özellikler** sekmesinde özellikleri ayarlayın ve ardından **Uygula**' yı seçin.  
  
    > [!NOTE]
    >  Görev akışına sayfa ve koşullar eklerken, pencerenin sol alt köşesinde, görev akışındaki tüm sayfa ve koşulları gösteren bir mini Haritayı görürsünüz.  
  
9. Bir sayfaya alan, etiket veya bölüm etiketi eklemek için, **Bileşenler** sekmesinden **alan**, **etiket**veya **bölüm etiketini** uygun sayfaya sürükleyin. Bu öğelerden birinin özelliklerini değiştirmek için öğeyi seçin, **Özellikler sekmesinden özellikleri** ayarlayın ve ardından **Uygula**' yı seçin.  
  
10. Görev akışını doğrulamak için eylem çubuğunda **Doğrula** ' yı seçin.  
  
11. İşlemi taslak olarak kaydetmek için ekranın üst kısmındaki **Kaydet** ' i seçin. (Bir işlem taslak olduğu sürece insanlar bunu kullanamaz.)  
  
12. Kullanıcıların kullanabilmesi için görev akışını etkinleştirmek üzere **Etkinleştir**' i seçin.  
  
> [!TIP]
>  Tasarımcı penceresinde görev akışınız üzerinde çalışırken göz önünde bulundurmanız gereken birkaç ipucu aşağıda verilmiştir:  
>   
> -  Görev akışı penceresindeki her şeyin anlık görüntüsünü almak için eylem çubuğunda **anlık görüntü** ' yi seçin.  
> -  Geçerli bir bileşeni tasarımcıda başka bir geçerli bileşene bağlamak için eylem çubuğunda **bağlayıcı** ' yı seçin.  
> -  Ekranın sağ üst köşesindeki **Yakınlaştırma düzeyini artır** veya **Yakınlaştırma düzeyini azalt** düğmelerini seçerek ekrandaki görüntülerin daha büyük veya küçük olmasını sağlayabilirsiniz. Görüntüleri ekrana sığan en büyük boyuta kadar bnetme etmek için **tuvale Sığdır** düğmesini seçin.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 [İş süreci akışı oluşturma](create-business-process-flow.md)   

