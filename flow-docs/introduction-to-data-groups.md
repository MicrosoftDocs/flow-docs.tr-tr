---
title: Microsoft Flow için veri grupları | Microsoft Docs
description: Microsoft PowerApps ve Microsoft Flow veri gruplarına giriş.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/26/2016
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: ba064461c34ce73faa712964791643ef67fca089
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461519"
---
# <a name="learn-all-about-data-groups"></a>Veri grupları hakkında bilgi edinin
## <a name="what-is-a-data-group"></a>Veri grubu nedir?
Veri grupları bir [veri kaybı önleme (DLP) ilkesi](prevent-data-loss.md) içindeki hizmetleri kategorilere ayırmanın basit bir yoludur. **Yalnızca iş verileri** grubu ve **Hiçbir iş verisi kullanılamaz** grubu kullanılabilir. Kuruluşlar belirli bir veri grubuna hangi hizmetlerin yerleştirileceğini belirlemekte serbesttir. Hizmetleri kategorilere ayırmanın iyi bir yolu, hizmetlerin kuruluşa etkisine göre gruplar halinde yerleştirilmesidir. Varsayılan olarak, tüm hizmetler **Hiçbir iş verisi kullanılamaz** veri grubuna yerleştirilir. Yönetim merkezinden bir DLP ilkesinin özelliklerini oluştururken veya değiştirirken veri grubundaki hizmetleri yönetebilirsiniz.

## <a name="how-data-is-shared-between-data-groups"></a>Veri grupları arasında veri paylaşma
Veriler farklı gruplarda bulunan hizmetler arasında paylaşılamaz. Örneğin, SharePoint ve Salesforce’u **Yalnızca iş verileri** grubuna, Facebook ve Twitter ise **Hiçbir iş verisi kullanılamaz** grubuna yerleştirirseniz, SharePoint ile Facebook arasında veri taşıyan bir akış oluşturamazsınız. Veriler farklı gruplardaki hizmetler arasında paylaşılamasa da, belirli bir grup içindeki hizmetler arasında veri paylaşabilirsiniz. Bu nedenle, önceki örneğe geri dönecek olursa, SharePoint ve Salesforce aynı veri grubuna yerleştirildiği için son kullanıcılarınızın oluşturduğu akışlar SharePoint ile Salesforce arasında veri paylaşabilir. Benzer şekilde, son kullanıcılar Facebook ile Twitter arasında veri paylaşan akışlar ve PowerApps oluşturabilir. Buradaki temel nokta, belirli bir gruptaki hizmetlerin veri paylaşabileceği, farklı gruplardaki hizmetlerin ise veri paylaşamayacağıdır.  

Ayrıca, bir grup *varsayılan* grup olarak belirlenmelidir. Başlangıçta, **Hiçbir iş verisi kullanılamaz** grubu *varsayılan* gruptur ve tüm hizmetler veri grubundadır. Bir yönetici, varsayılan grubu **Yalnızca iş verileri** veri grubu olarak değiştirebilir. **Not**: Akışa eklenen tüm yeni hizmetler, belirlenen *varsayılan* gruba yerleştirilir. Bu nedenle, **Hiçbir iş verisine izin verilmez** grubunu varsayılan grup olarak tutmanız ve kuruluşunuz iş verilerinin yeni hizmetle paylaşılmasına izin vermenin etkilerini değerlendirdikten sonra **Yalnızca iş verileri** grubuna el ile hizmet eklemeniz önerilir.

## <a name="add-services-to-a-data-group"></a>Veri grubuna hizmet ekleme
Bu kılavuzda SharePoint ve Salesforce bir veri kaybı önleme (DLP) ilkesinin **yalnızca iş verileri** veri grubuna eklenecektir. 

1. Bir DLP ilkesinin **Yalnızca iş verileri** grup kutusunun içindeki **+ Ekle** bağlantısını seçin:    
   ![Görüntü ekleme](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. SharePoint ve Salesforce’u seçin ve ardından her ikisini de yalnızca iş verileri grubuna eklemek için **Hizmet ekle** öğesini seçin:    
   ![Hizmet görüntüsü ekleme](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Üstteki menüden **İlkeyi Kaydet**’i seçin:  
   ![İlke kaydetme](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Hem SharePoint hem de Salesforce’un şu anda yalnızca iş verileri grubunda olduğuna dikkat edin:  
   ![güncelleştirilmiş iş verileri grubu](./media/introduction-to-data-groups/add-to-data-group-3.png)   

Bu kılavuzda SharePoint ve Salesforce’u bir DLP ilkesinin **yalnızca iş verileri** veri grubuna eklediniz. DLP ilkesinin ortamına dahil olmayan bir kişi, verileri SharePoint veya Salesforce ile **Hiçbir iş verisi kullanılamaz** veri grubundaki bir hizmet arasında paylaşan bir uygulama oluşturursa uygulamanın çalışmasına izin verilmez.

## <a name="remove-services-from-a-data-group"></a>Veri grubundan hizmet kaldırma
Tüm hizmetlerin, kullanılabilir veri gruplarının birinde olması gerektiğinden, belirli bir gruptan bir hizmeti kaldırmak için yalnızca hizmeti başka bir gruba eklemeniz ve sonra ilkeyi kaydetmeniz yeterlidir.  

## <a name="change-the-default-data-group"></a>Varsayılan veri grubunu değiştirme
Bu kılavuzda, **hiçbir iş verisi kullanılamaz** veri grubu olan varsayılan veri grubu, **yalnızca iş verileri** veri grubu olarak değiştirilecektir.  

**Önemli**: Akışa eklenen tüm yeni hizmetler, belirlenen *varsayılan* gruba yerleştirilir. Bu nedenle, **Hiçbir iş verisine izin verilmez** veri grubunu varsayılan grup olarak tutmanız ve **Yalnızca iş verileri** grubuna hizmetleri el ile eklemeniz önerilir.

1. Varsayılan veri grubu olarak belirlemek istediğiniz veri grubunun sağ üst köşesindeki **...** işaretini seçin:    
   ![varsayılan grubu değiştirme](./media/introduction-to-data-groups/default-data-group-0.png)  
2. **Varsayılan grup olarak ayarla**’yı seçin:  
   ![varsayılan grubu değiştirme](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Üstteki menüden **İlkeyi Kaydet**’i seçin:  
   ![varsayılan grubu değiştirme](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Veri grubunun varsayılan veri grubu olarak atandığını görebilirsiniz:  
   ![varsayılan grubu değiştirme](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Sonraki adımlar
* [Veri kaybı önleme (DLP) ilkeleri hakkında daha fazla bilgi edinin](prevent-data-loss.md)
* [Ortamlar hakkında daha fazla bilgi edinin](environments-overview-admin.md)   

