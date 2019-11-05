---
title: İş süreci akışına isteğe bağlı iş akışı ekleme
description: ''
author: MSFTMAN
ms.author: Deonhe
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
ms.service: flow
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
ms.openlocfilehash: ab30f745d6465cff9551854034c25130697144ba
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546110"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>İş süreci akışına isteğe bağlı iş akışı ekleme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

İsteğe bağlı iş akışlarını iş süreci akışının içinden tetikleyebilirsiniz. Örneğin, bir aşama tamamlandığında görev veya e-posta gibi bir etkinliğin oluşturulması için bir iş süreci akışına isteğe bağlı bir iş akışı ekleyebilirsiniz. 

İş akışını iş süreci akış tasarımcısına sürüklediğiniz yere göre etkinleştirilir.
- İsteğe bağlı aşama süreçler. İş akışı bir iş süreci akış aşamasına bırakıldığında, iş akışı, aşamanın girişinde veya çıkıldığında tetiklenir. 
- İsteğe bağlı genel süreçler. İş akışı **küresel Iş akışları** alanına bırakıldığında, iş akışı işlem etkinleştirme veya işlem arşivleme üzerinde tetiklenir (durum uygulandı, tamamlandı, yeniden etkinleştirildi veya bırakıldı durumuna geçiş yaptığında). 

İş süreci akışına iş akışı eklediğinizde aşağıdaki gereksinimlere dikkat edin.
- Bir aşamaya eklenen iş akışları için: yalnızca, iş akışını eklediğiniz aşamanın aynı varlığı için oluşturulan etkin ve isteğe bağlı iş akışlarını kullanabilirsiniz.  
- Genel iş akışları için: yalnızca iş süreci akışının birincil varlığı için oluşturulan etkin ve isteğe bağlı iş akışlarını kullanabilirsiniz.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>İş süreci akış aşamasına isteğe bağlı iş akışı ekleme

İş akışı bileşenini bir işlem aşamasına veya küresel iş akışları bölümüne sürükleyerek iş süreci akış tasarımcısından isteğe bağlı bir iş akışı eklersiniz. 

[PowerApps](https://web.powerapps.com) sitesinde **model temelli** (Gezinti bölmesinin sol alt kısmında) öğesini seçin. 

İş süreci akış tasarımcısını açın. Bunu iki şekilde yapabilirsiniz.
- İş süreci akışı zaten bir uygulamaya eklendiyse, istediğiniz uygulamanın yanındaki **uygulamalar**' a gidin, sonra da **Düzenle** **' yi**seçin. Uygulama Tasarımcısı ' nda iş süreci akışını seçin ve sonra ![iş süreci akış Tasarımcısı](media/dynamics365-open-designer.PNG)aç ' ı seçin.  
- Aksi takdirde, [Çözüm Gezgini](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer)' ni açın, sol gezinti bölmesinde **işlemler**' i seçin ve istediğiniz iş süreci akışını seçin. 

İsteğe bağlı iş akışının aşağıdaki iş süreci akışı olaylarından biri tarafından tetiklenip tetiklenmeyeceğine karar verin. 
- İsteğe bağlı aşama süreçler. Girişte veya aşamadaki çıkışta iş akışını tetikler. 
- İsteğe bağlı genel süreçler. İşlem etkinleştirme ya da işlem arşivleme (durum uygulanan, tamamlanan, yeniden etkinleştirilen veya terk durumuna geçiş yaptığında) iş akışını tetikler. 

Aşağıdaki örnekte, iş süreci akışının **1. aşamasına** bir isteğe bağlı **iş akışı** adlı isteğe bağlı bir iş akışı eklenir. 

1. **Tetiklenen işlem** bölümünü açığa çıkarmak için 1. Aşama ' ı genişletin. 
2. **Bileşenler** sekmesini seçin ve **Iş akışını** **tetiklenen işlem** bölümüne sürükleyin.
    ![iş akışını bir aşamaya ekleme](media/add-workflow-to-bpf-1.png) alternatif olarak **, iş akışını** işlem etkinleştirme ya da işlem arşivleme üzerinde tetikleyen **genel iş akışları** bölümüne sürükleyebilirsiniz.
 ![etkinleştirme veya arşivlemeyi işlemek için subclipping ekleyin](media/add-workflow-to-bpf-global.png)
3. **Özellikler** sekmesinin arama kutusunda, iş süreci akış aşamasına eklemek istediğiniz isteğe bağlı iş akışının adını girip arayın ve ardından **Uygula**' yı seçin.
    ![adı girin ve Uygula ' yı seçin](media/add-workflow-to-bpf-2.png)
4. **Tetikleyici** altındaki **Özellikler** sekmesinde, **aşama girişi** ya da **aşama çıkışı**' nı seçin.  
    ![iş akışı tetikleyicisi seçin](media/workflow-trigger.png)
   
    Alternatif olarak, iş akışını **küresel Iş akışları** bölümüne bıraktığınızda tetikleyici seçenekleri **işlem uygulandı**, yeniden **etkinleştirilen**Işlem, **işlem terk edildi**ve **işlem tamamlandı**olarak işlenir.

5. İş süreci akış Tasarımcısı araç çubuğunda **Güncelleştir** ' i seçin.
 
## <a name="next-steps"></a>Sonraki adımlar
[Kullanıcı etkileşimi gerektirmeyen işlemleri otomatikleştirmek için Iş akışı süreçlerini kullanma](workflow-processes.md) <br/>
[Öğretici: işlemleri standartlaştırmak için bir iş süreci akışı oluşturma](create-business-process-flow.md) <br/>
[Dynamics 365 'de iş süreci akışı Otomasyonu](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
