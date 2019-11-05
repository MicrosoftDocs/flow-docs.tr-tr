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
ms.openlocfilehash: 030e0563ce9adaa7c1c5c44f1446859e3152a398
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547437"
---
# <a name="learn-all-about-data-groups"></a>Veri grupları hakkında bilgi edinin
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-is-a-data-group"></a>Veri grubu nedir?
Veri grupları, bir [veri kaybı önleme (DLP) ilkesi](prevent-data-loss.md)içinde hizmetleri kategorilere ayırmanın basit bir yoludur. Kullanılabilir iki veri grubu, **yalnızca iş** **verilerine izin verilmez ve iş verisi yok** grubudur. Kuruluşlar, belirli bir veri grubuna hangi hizmetlerin yerleştirileceğini tespit etmek ücretsizdir. Hizmetleri kategorilere ayırmanın iyi bir yolu, bunları kuruluşa etkinin temel alınarak gruplara yerleştirkullanmaktır. Varsayılan olarak, tüm hizmetler **iş verilerine izin verilmez** veri grubuna yerleştirilir. Yönetim merkezinden bir DLP ilkesinin özelliklerini oluştururken veya değiştirirken bir veri grubundaki Hizmetleri yönetirsiniz.

## <a name="how-data-is-shared-between-data-groups"></a>Veri grupları arasında verilerin paylaşılması
Veriler farklı gruplarda bulunan hizmetler arasında paylaşılamaz. Örneğin, **yalnızca iş** verileri grubuna SharePoint ve Salesforce yerleştirirse ve **iş verilerine Izin verilmez** grubuna Facebook ve Twitter yerleştirirseniz, SharePoint ile Facebook arasında veri taşınan bir akış oluşturamazsınız. Veriler farklı gruplardaki hizmetler arasında paylaşılabilmesi için, belirli bir grup içindeki hizmetler arasında veri paylaşabilirsiniz. Bu nedenle, SharePoint ve Salesforce aynı veri grubuna yerleştirildiğinden, önceki örneğe geri dönerek, son kullanıcılarınızın oluşturacağı akışlar SharePoint ile Salesforce arasında veri paylaşabilir. Benzer şekilde, son kullanıcılar Facebook ve Twitter arasında veri paylaşan akışlar ve PowerApps oluşturabilir. Anahtar noktası, belirli bir gruptaki hizmetlerin veri paylaşabileceği, farklı gruplardaki hizmetler veri paylaşamıyor.  

Ayrıca, bir veri grubunun *varsayılan* grup olarak belirlenmesi gerekir. Başlangıçta, **iş verilerine izin verilmez** grubu *varsayılan* gruptur ve tüm hizmetler veri grubunda bulunur. Yönetici varsayılan veri grubunu **yalnızca iş verileri** veri grubu olarak değiştirebilir. **Unutmayın** akışa eklenen tüm yeni hizmetler, belirlenen *varsayılan* gruba yerleştirilir. Bu nedenle, iş verilerinin varsayılan grup olarak **yapılmasına izin verilmeyeceğini** ve kuruluşunuzun iş verilerinin yeni ile paylaşılmasına izin verme etkisini değerlendirdikten sonra **yalnızca iş** verileri grubuna el ile hizmet ekleyebilmenizi öneririz. hizmetle.

## <a name="add-services-to-a-data-group"></a>Bir veri grubuna hizmet ekleme
Bu kılavuzda, SharePoint ve Salesforce ' ı bir veri kaybı önleme (DLP) ilkesinin **yalnızca iş verileri** veri grubuna ekleyeceğiz. 

1. DLP ilkesinin **yalnızca iş verileri** Grup kutusunun içinde yer alan **+ Ekle** bağlantısını seçin:    
   ![resim ekleme](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. SharePoint ve Salesforce ' ı seçin ve sonra yalnızca iş verileri grubuna eklemek için **Hizmet Ekle** ' yi seçin:    
   ![Services görüntüsü ekleme](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Üstteki menüden **Ilkeyi kaydet** ' i seçin:  
   ilkeyi ![](./media/introduction-to-data-groups/add-to-data-group-4.png) Kaydet 
4. Hem SharePoint hem de Salesforce 'ın artık yalnızca iş verileri grubunda olduğuna dikkat edin:  
   ![güncelleştirilmiş iş verileri grubu](./media/introduction-to-data-groups/add-to-data-group-3.png)   

Bu kılavuzda, SharePoint ve Salesforce ' ı bir DLP ilkesinin **yalnızca iş verileri** veri grubuna eklediniz. DLP İlkesi ortamının bir parçası olan bir kişi SharePoint veya Salesforce ile **iş verilerine izin verilmez** veri grubundaki herhangi bir hizmet arasında veri paylaşan bir uygulama oluşturursa, uygulamanın çalışmasına izin verilmez.

## <a name="remove-services-from-a-data-group"></a>Bir veri grubundan Hizmetleri Kaldır
Tüm hizmetlerin kullanılabilir veri gruplarından birinde olması gerektiğinden, belirli bir gruptan bir hizmeti kaldırmak için, hizmeti başka bir gruba eklemeniz ve sonra ilkeyi kaydetmeniz yeterlidir.  

## <a name="change-the-default-data-group"></a>Varsayılan veri grubunu değiştirme
Bu kılavuzda, **iş verilerine izin verilmez** veri grubundan varsayılan veri grubunu **yalnızca iş** verileri veri grubu olarak değiştiririz.  

**Önemli** bir akışa eklenen tüm yeni hizmetler, belirlenen *varsayılan* gruba yerleştirilir. Bu nedenle, **iş verilerine izin verilmez** varsayılan grup olarak devam etmenizi ve Hizmetleri **yalnızca iş verileri** grubuna elle eklemenizi öneririz.

1. Varsayılan veri grubu olarak belirlemek istediğiniz veri grubunun sağ üst köşesinde bulunan **..** . öğesini seçin:    
   ![varsayılan grubu Değiştir](./media/introduction-to-data-groups/default-data-group-0.png)  
2. **Varsayılan grup olarak ayarla**' yı seçin:  
   ![varsayılan grubu Değiştir](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Üstteki menüden **Ilkeyi kaydet** ' i seçin:  
   ![varsayılan grubu Değiştir](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Veri grubunun artık varsayılan veri grubu olarak belirlendiğine dikkat edin:  
   ![Varsayılan grubu Değiştir](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Sonraki adımlar
* [Veri kaybı önleme (DLP) ilkeleri hakkında daha fazla bilgi edinin](prevent-data-loss.md)
* [Ortamlar hakkında daha fazla bilgi edinin](environments-overview-admin.md)   

