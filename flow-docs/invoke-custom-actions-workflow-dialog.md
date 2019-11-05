---
title: Bir iş akışından özel eylemleri çağırma | MicrosoftDocs
description: Bir iş akışından özel bir eylemi çağırmayı öğrenin
ms.custom: ''
ms.date: 11/22/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 1fd5d39e-3dc8-4d1a-8b4b-ccaa303f4bbb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9ed3c2114bfb167eb8d4d6a5670ccec8050ee9d0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547430"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Bir iş akışından özel eylemleri çağırma
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

İş akışlarının iş senaryolarını destekleyen çok sayıda özelliği vardır. Bir iş akışı içinde oluşturma, güncelleştirme ve silme gibi temel veri işlemi eylemlerinin çağrılması, çok sayıda iş senaryosunu çözer. Ancak, iş akışlarının yeteneklerini doğrudan bir iş akışının içinden çağrılan özel eylemlerin gücüyle birlikte kullanırsanız, kod yazmak zorunda kalmadan uygulamanıza yeni bir iş senaryosu aralığı eklersiniz.  
  
 Bir iş akışından özel bir eylemin çağrıldığı senaryoya göz atalım. Belirli bir fırsatın indirimi %20 ' sini aştığında yöneticinin onayını istemek için özel bir eylem çağıracağız.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Örnek: fırsat varlığını kullanarak özel bir eylem oluşturma
  
1. [Çözüm Gezgini](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) ' nde **işlem**' ı seçin.  
  
2.  Gezinti çubuğunda **Yeni**' yi seçin. İşleme bir ad verin ve **eylem** kategorisini seçin.  
  
 İndirimle ilgili bir onay istemek için, **onay işlemi**adlı özel bir eylem kullanıyoruz. Burada gösterildiği gibi, yeni bir ileti oluşturmak ve yöneticinin onayı için bir istek göndermek üzere bir giriş parametresi, **Specialnotes**ve **e-posta gönder** adımı ekledik.  
  
 ![Adım &#45; Gönder e-postası ekleme](media/enable-custom-action-approval-proces-sadd-email.png "Bir adım Gönder e-postası ekleyin")  
  
 E-posta iletisini yapılandırmak için **Özellikleri ayarla**' yı seçin. Form açıldığında, ekran görüntüsünde vurgulanan şekilde e-postaya özel notlar ve diğer bilgileri eklemek için **Form Yardımcısını** kullanın. Özel notları eklemek için, imleci iletide görünmesini istediğiniz yere yerleştirin ve ardından **Form Yardımcısı**' nda, **Ara**' nın altında, Ilk açılan listede **bağımsız değişkenler** ' i seçin ve ikinci olarak **özelleştirilmiş notlar** ' ı seçin açılan liste ve sonra **Tamam**' ı seçin.  
  
 ![E-postayı ayarlama](media/enable-custom-action-approval-process-setup-email.png "E-postayı ayarlama")  
  
 Bir iş akışından eylemi çağırabilmeniz için önce etkinleştirmeniz gerekir. Eylemi etkinleştirdikten sonra özellikleri **görüntüle**' yi seçerek özelliklerini görüntüleyebilirsiniz.  
  
 ![Özel eylem &#45; onay işlemini etkinleştir](media/enable-custom-action-approval-process-activate-action.png "Özel eylemi etkinleştirme-onay işlemi")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Bir iş akışından özel bir eylem çağırma  
  
1. [Çözüm Gezgini](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) ' nde **işlem**' ı seçin.   
  
2.  Gezinti çubuğunda **Yeni**' yi seçin. İşleme bir ad verin ve **Iş akışı** kategorisini seçin.  
  
 Yöneticinin bir fırsat için %20 ' den fazla indirimle ilgili onayı gerektiğinde **onay süreci** özel eylemini çağıran bir iş akışı oluşturduk.  
  
 ![İş akışından eylem özelliklerini ayarlama](media/enable-custom-action-from-workflow.png "İş akışından eylem özelliklerini ayarlama")  
  
 **Özelliği ayarla**' yı seçerek eylemin giriş özelliklerini ayarlayabilirsiniz. Özel notlardaki fırsatla ilgili bir hesap adı ekledik. **Form Yardımcısı**' nda, **Ara**' nın altında, ilk açılan listede **Hesap** ' ı seçin, ikinci açılan listede **Hesap adı** ' nı seçin ve ardından **Tamam**' ı seçin. **Target** özelliği gereklidir ve sistem tarafından doldurulur. **Target** özelliğindeki **{fırsat (Fırsat)}** , çağıran iş akışının üzerinde çalıştığı fırsatla aynı fırsattır. Alternatif olarak, arama kullanarak hedef özelliği için belirli bir fırsat seçebilirsiniz.  
  
 ![ApprovalProcess eylemi için giriş parametrelerini ayarla](media/enable-customaction-workflow-set-properties.png "ApprovalProcess eylemi için giriş parametrelerini ayarla")  
  



