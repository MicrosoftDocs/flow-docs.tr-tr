---
title: Bir iş akışından özel eylemler çağırma | Microsoft Docs
description: İş akışından özel eylem çağırmayı öğrenin
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
ms.openlocfilehash: 938410cf4484f8bed6509beee1d36c8cb3718e6f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461371"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Bir iş akışından özel eylemler çağırma

İş akışları, iş senaryolarını destekleyen birçok özelliğe sahiptir. Bir iş akışından bir kayıt için oluşturma, güncelleştirme ve silme gibi temel veri işlemi eylemlerini çağırmak birçok iş senaryosu için gerekli çözümleri sunacaktır. Ancak iş akışlarının özelliklerini doğrudan iş akışından çağrılan özel eylemlerin gücüyle birleştirdiğinizde kod yazmaya ihtiyaç duymadan uygulamanıza yepyeni iş senaryoları eklemiş olursunuz.  
  
 Şimdi iş akışından özel eylemin çağrıldığı bir senaryoya bakalım. Belirli bir fırsat için uygulanan indirim %20'yi aştığında yöneticinin onayını almak için özel bir eylem çağıracağız.  
  
<a name="action"></a>   
## <a name="dynamics-365-customer-engagement-example-create-a-custom-action-using-the-opportunity-entity"></a>Dynamics 365 müşteri katılımı örneği: Fırsat varlığını kullanarak özel eylem oluşturma
  
1. [Çözüm Gezgini](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer)'nde **İşlemler**'i seçin.  
  
2.  Gezinti çubuğunda, **Yeni**'yi seçin. İşlem bir ad verin ve **Eylem** kategorisini seçin.  
  
 İndirim durumunda onay almak için **Onay Süreci** adlı özel bir eylemi kullanacağız. Aşağıda görebileceğiniz gibi **SpecialNotes** adlı bir giriş parametresi ve yeni ileti oluşturup yöneticinin onayını almak üzere göndermek için **E-posta gönder** adımı ekledik.  
  
 ![Adım ekleme - e-posta gönder](media/enable-custom-action-approval-proces-sadd-email.png "Adım ekleme - e-posta gönder")  
  
 E-posta iletisini yapılandırmak için **Özellikleri Ayarla**'yı seçin. Form açıldığında ekran görüntüsünde gördüğünüz gibi e-postaya özel notları ve diğer bilgileri eklemek için **Form Yardımcısı**'nı kullanın. Özel notları eklemek için imleci iletide görünmesini istediğiniz yere götürün ve **Form Yardımcısı**'nın **Ara** bölümündeki ilk açılan listeden **Bağımsız Değişkenler**'i, ikinci açılan listeden **SpecialNotes** değerini ve ardından **Tamam**'ı seçin.  
  
 ![E-posta ayarlar](media/enable-custom-action-approval-process-setup-email.png "E-posta ayarları")  
  
 Eylemi bir iş akışından çağırabilmek için etkinleştirmeniz gerekir. Eylemi etkinleştirdikten sonra **Özellikleri görüntüle**'yi seçerek özelliklerini görüntüleyebilirsiniz.  
  
 ![Özel eylemi etkinleştirme - onay süreci](media/enable-custom-action-approval-process-activate-action.png "Özel eylemi etkinleştirme - onay süreci")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Özel eylemi iş akışından çağırma  
  
1. [Çözüm Gezgini](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer)'nde **İşlemler**'i seçin.   
  
2.  Gezinti çubuğunda, **Yeni**'yi seçin. İşlem bir ad verin ve **İş akışı** kategorisini seçin.  
  
 Bir fırsat için indirim oranı %20'yi aştığında yöneticiden onay isteyen **Onay Süreci** özel eylemini çağıran bir iş akışı oluşturduk.  
  
 ![İş akışından eylem özelliklerini ayarlama](media/enable-custom-action-from-workflow.png "İş akışından eylem özelliklerini ayarlama")  
  
 Eylemin giriş özelliklerini **Özellikleri Ayarla**'yı seçerek belirleyebilirsiniz. Özel notlara fırsatın ilgili olduğu hesabın adını ekledik. **Form Yardımcısı**'nın **Ara** bölümündeki ilk açılan listeden **Hesap**, ikinci açılan listeden **Hesap Adı**'nı ve ardından **Tamam**'ı seçin. **Hedef** özelliği gereklidir ve sistem tarafından doldurulur. **Hedef** özelliğindeki **{Fırsat(Fırsat)}**, çağıran iş akışının üzerinde çalıştığı fırsattır. Alternatif olarak arama seçeneğiyle hedef özelliği için belirli bir fırsatı seçebilirsiniz.  
  
 ![Onay Süreci eylemi için giriş parametrelerini ayarlama](media/enable-customaction-workflow-set-properties.png "Onay Süreci eylemi için giriş parametrelerini ayarlama")  
  



