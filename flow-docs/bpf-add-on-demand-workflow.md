---
title: İş süreci akışına isteğe bağlı iş akışı ekleme
description: ''
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 26c79c20-2987-476e-983a-406e0db13034
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: aa061d5e2f668e8950a6cdab89992996f64c6fe8
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460896"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>İş süreci akışına isteğe bağlı iş akışı ekleme

İsteğe bağlı iş akışlarını bir iş süreci iş akışının içinden tetikleyebilirsiniz. Örneğin bir iş süreci akışına isteğe bağlı iş akışı ekleyerek bir aşama tamamlandığında bir görevin veya e-postanın oluşturulmasını sağlayabilirsiniz. 

İş akışı, iş süreci akışı tasarımcısında bıraktığınız yere göre etkinleştirilir.
- İsteğe bağlı aşama süreçleri. İş akışı bir iş süreci akışı aşamasına bırakıldığında aşamanın girişinde veya çıkışında tetiklenir. 
- İsteğe bağlı genel süreçler. İş akışı **Genel İş Akışları** alanına bırakıldığında süreç etkinleştirildiğinde veya arşivlendiğinde (durum uygulandı, tamamlandı, yeniden etkinleştirildi veya bırakıldı olduğunda) tetiklenir. 

İş süreci akışına iş akışı eklerken aşağıdaki gereksinimleri göz önünde bulundurun.
- İş akışları için bir aşamaya eklendi: Yalnızca, iş akışını eklediğiniz aşama aynı varlık için oluşturulan etkin, isteğe bağlı iş akışları kullanabilirsiniz.  
- Genel iş akışları için: Yalnızca iş süreci akışı birincil varlık için oluşturulan etkin, isteğe bağlı iş akışları kullanabilirsiniz.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>İş süreci akışı aşamasında isteğe bağlı iş akışı ekleme

İş süreci akışı tasarımcısındaki bir isteğe bağlı iş akışı bileşenini süreç aşamasına veya genel iş akışları bölümüne sürükleyerek ekleyebilirsiniz. 

[PowerApps](https://web.powerapps.com) sitesinde **Model tabanlı** (gezinti bölmesinin sol alt bölümünde) seçeneğini belirleyin. 

İş süreci akışı tasarımcısını açın. Bunu yapmak için iki seçeneğiniz vardır.
- İş süreci akışı uygulamaya eklenmiş durumdaysa **Uygulamalar**'a gidin, istediğiniz uygulamanın yanındaki **…** simgesini ve ardından **Düzenle**'yi seçin. Uygulama tasarımcısında iş süreci akışını ve ardından ![İş süreci akışı tasarımcısını aç](media/dynamics365-open-designer.PNG)'ı seçin.  
- Aksi takdirde [Çözüm Gezgini](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer)'ni açın, sol taraftaki gezinti bölmesinde **Süreçler**'i seçin ve kullanmak istediğiniz iş süreci akışını belirleyin. 

İsteğe bağlı iş akışının tetiklenmesi için aşağıdaki iş süreci akışı olaylarından birini belirleyin. 
- İsteğe bağlı aşama süreçleri. İş akışını aşamanın girişinde veya çıkışında tetikler. 
- İsteğe bağlı genel süreçler. İş akışını süreç etkinleştirildiğinde veya arşivlendiğinde (durum uygulandı, tamamlandı, yeniden etkinleştirildi veya bırakıldı olduğunda) tetikler. 

Aşağıdaki örnekte **İsteğe bağlı iş akışım** adlı isteğe bağlı iş akışı, iş süreci akışının **Aşama 1** bölümüne eklenmiştir. 

1. Aşama 1'i genişleterek **Tetiklenen İşlem** bölümünü açın. 
2. **Bileşenler** sekmesini seçin ve **İş akışı** öğesini **Tetiklenen İşlem** bölümüne sürükleyin.
    ![İş akışını aşamaya ekleme](media/add-workflow-to-bpf-1.png) Alternatif olarak, **İş akışı** öğesini **Genel İş Akışları** bölümüne sürükleyerek iş akışının sürecin etkinleştirilmesi veya sürecin arşivlenmesi durumunda tetiklenmesini sağlayabilirsiniz.
 ![İş akışını süreç etkinleştirme veya arşivlenme olayına ekleme](media/add-workflow-to-bpf-global.png)
3. **Özellikler** sekmesindeki arama kutusuna iş süreci akışı aşamasına eklemek istediğiniz isteğe bağlı iş akışının adını girin ve ardından **Uygula**'yı seçin.
    ![Adı girin ve Uygula'yı seçin](media/add-workflow-to-bpf-2.png)
4. **Özellikler** sekmesinin **Tetikleyici** bölümünde **Aşama Girişi** veya **Aşama Çıkışı**'nı seçin.  
    ![İş akışı tetikleyicisini seçme](media/workflow-trigger.png)
   
    Alternatif olarak, iş akışını **Genel İş Akışları** bölümüne bıraktığınızda **İşlem uygulandı**, **İşlem yeniden etkinleştirildi**, **İşlem bırakıldı** ve **İşlem tamamlandı** tetikleyici seçenekleri görüntülenir.

5. İş süreci akışı tasarımcısı araç çubuğunda **Güncelleştir**'i seçin.
 
## <a name="next-steps"></a>Sonraki adımlar
[Kullanıcı etkileşimi gerektirmeyen işlemleri otomatikleştirmek için iş akışı işlemlerini kullanma](workflow-processes.md) <br/>
[Öğretici: Süreçleri standart hale getirmek için bir iş süreci akışı oluşturma](create-business-process-flow.md) <br/>
[Dynamics 365'te iş süreci akışı otomasyonu](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
