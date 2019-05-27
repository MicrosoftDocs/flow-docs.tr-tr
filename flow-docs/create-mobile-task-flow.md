---
title: PowerApps ile mobil görev akışı oluşturma | MicrosoftDocs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 7f15f11a4e66d80762384f8183af7973fcca76bf
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456207"
---
# <a name="create-a-mobile-task-flow"></a>Mobil görev akışı oluşturma

Telefonlar için Dynamics 365 veya tabletler için Dynamics 365'te kullanıcılarınızın sık gerçekleştirdiği görevleri temel alan bir akış tasarlayabilirsiniz. Örneğin kullanıcılarınızın müşterilerle yaptıkları toplantıların ardından düzenli olarak gerçekleştirmesi gereken bir dizi adım varsa bunun için bir görev akışı oluşturabilirsiniz. Kullanıcılar cep telefonunda bu yeni göreve dokunduğunda süreci baştan sona kadar takip edip önemli bir adımı atlamadıklarından emin olabilirler.  
  
 Görev akışlarında birden çok varlığa sahip formların ve mantığın yanı sıra tüm görev akışı sayfalarında çalışan bir mantık da bulunabilir.  
  
## <a name="create-a-task-flow"></a>Görev akışı oluşturma
  
1. Sistem Yöneticisi veya Sistem Özelleştirici güvenlik rolüne ya da eşdeğer izinlere sahip olduğunuzdan emin olun. Dynamics 365 müşteri etkileşimini kullanıyorsanız Yönetici, Başkan Yardımcısı veya CEO-İşletme Yöneticisi güvenlik rolleri de mobil görev akışı oluşturabilir. 
  
2. [Çözüm Gezgini](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer)'ni açın ve **İşlemler**'i seçin.  
  
3.  **Eylemler** araç çubuğunda **Yeni**'yi seçin.  
  
4.  **İşlem Oluştur** iletişim kutusunda gerekli alanları doldurun:  
  
    -   İşlem adı girin.  
  
    -   **Kategori** listesinde **İş Süreci Akışı**'nı seçin.  
  
    -   **Varlık** listesinde kullanmak istediğiniz varlığı seçin.  
  
5.  **İşlemi görev akışı olarak çalıştır (Mobil çevrimiçi)** seçeneğini belirleyin.  
  
6.  **Tamam**’ı seçin.
  
     Görev akışı tasarımcısı yeni bir pencerede açılır.  
  
     ![Görev akışı tasarımcısı penceresi](media/task-flow-designer-window.png "Görev akışı tasarımcısı penceresi") 
  
7.  Kullanıcılarınız sayfalarda sırayla ilerleyecekse ekranın sağ tarafındaki **Bileşenler** sekmesinden **Sayfa** bileşenini ekrana sürükleyin ve uygun noktadaki + işaretinin üzerine bırakın. Sayfaya ad eklemek için sayfayı seçin, **Özellikler** sekmesini seçin, yeni bir ad yazın ve **Uygula**'yı seçin.  
  
8.  Görev akışına dal eklemek için **Bileşenler** sekmesindeki **Koşul** bileşenini sürükleyin ve uygun noktadaki + işaretinin üzerine bırakın. Koşulun özelliklerini ayarlamak için koşulu seçin, **Özellikler** sekmesinden özelliklerini ayarlayın ve **Uygula**'yı seçin.  
  
    > [!NOTE]
    >  Görev akışına sayfa ve koşul ekledikçe pencerenin sol alt köşesindeki mini haritada görev akışına eklenen sayfaları ve koşulları göreceksiniz.  
  
9. Bir sayfaya alan, etiket veya bölüm etiketi eklemek için **Bileşenler** sekmesindeki **Alan**, **Etiket** veya **Bölüm Etiketi** öğesini uygun sayfaya sürükleyin. Bu öğelerden birinin özelliklerini değiştirmek için öğeyi seçin, **Özellikler** sekmesinden özelliklerini ayarlayın ve **Uygula**'yı seçin.  
  
10. Görev akışını doğrulamak için eylem çubuğunda **Doğrula**'yı seçin.  
  
11. İşlemi taslak olarak kaydetmek için ekranın en üstündeki **Kaydet**'i seçin. (Taslak halindeki süreçler kullanıcılar tarafından kullanılamaz.)  
  
12. Görev akışını etkinleştirerek kişilerin kullanımına sunmak için **Etkinleştir**'i seçin.  
  
> [!TIP]
>  Aşağıda tasarımcı penceresinde görev akışınızın üzerinde çalışırken aklınızda bulundurmanız gereken bazı ipuçları verilmiştir:  
>   
> -  Görev akışı penceresindeki tüm öğelerin anlık görüntüsünü almak için eylem çubuğundaki **Anlık görüntü**'yi seçin.  
> -  Geçerli bir bileşeni tasarımcıdaki başka bir geçerli bileşene bağlamak için eylem çubuğunda **Bağlayıcı**'yı seçin.  
> -  Ekranın sağ üst köşesindeki **Yakınlaştırma düzeyini artır** veya **Yakınlaştırma düzeyini azalt** düğmelerini kullanarak ekrandaki görüntüleri daha büyük veya daha küçük hale getirebilirsiniz. Görüntüleri ekrana sığacak en büyük boyuta getirmek için **Tuvale sığdır** düğmesini seçin.  
  
## <a name="next-steps"></a>Sonraki adımlar  
 [İş süreci akışı oluşturma](create-business-process-flow.md)   

