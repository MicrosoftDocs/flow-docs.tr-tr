---
title: "Veri kaybı önleme (DLP) ilkelerini kullanma | Microsoft Docs"
description: "Microsoft Flow’u kullanarak görevleri otomatikleştirirken, veri kaybı önleme ilkeleriyle hangi hizmetlerin veri paylaşabileceğini denetlemeyi öğrenin."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: vls4RPVP5xE
courseduration: 6m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 2e69fd07103cb16e6c91476462f39586810b4a5d
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="use-data-loss-prevention-dlp-policies"></a>Veri kaybı önleme (DLP) ilkelerini kullanma
[Microsoft Flow](https://flow.microsoft.com)’da iş akışları oluşturmak için kullanılabilen [hizmetler](https://flow.microsoft.com/services) her geçen gün arttığından SharePoint veya Salesforce gibi kurumsal hizmetlerde depolanan gizli veya kritik iş verilerini korumanız gerekebilir. Kuruluşunuzun, gizli iş verilerinin Twitter ve Facebook gibi tüketici hizmetlerine yayımlanmadığından emin olmak için bir ilke oluşturması gerekebilir. Microsoft Flow sayesinde, kullanıcılarınız akış oluşturduğunda iş verilerinizin hangi tüketici hizmetleriyle paylaşılacağını sıkı bir şekilde denetlemek için kolayca **veri kaybı önleme** (DLP) ilkeleri oluşturabilirsiniz.  

## <a name="terms-you-should-get-familiar-with"></a>Bilmeniz gereken terimler:
| Terim | Açıklama |
| --- | --- |
| **DLP** |Bu, veri kaybı önleme teriminin kısaltmasıdır. **Hizmetler** arasında veri paylaşımını yönetmek için DLP ilkesi oluşturursunuz. |
| **Hizmetler** |[Hizmetler](https://flow.microsoft.com/services) Salesforce, SharePoint ve Twitter gibi uygulamalardır. Bu hizmetler ve çok daha fazlası akış oluşturmak için kullanılır. |
| **Veri grubu** |Bir mantıksal hizmet gruplandırması. Veri paylaşmasına izin verilen hizmetleri aynı veri grubuna eklersiniz. İki veri grubu bulunur: **yalnızca iş verileri** ve **iş verilerine izin verilmez**. |
| **Ortam** |Bir DLP bir [ortama](../environments-overview-admin.md) uygulanır. Bir ortamda kullanıcılar bulunur. |
| **Kullanıcılar** |Kullanıcılar, ortamdaki üyeliklerine bağlı olarak bir DLP ilkesinin uygulanacağı kuruluş üyelerinizdir. |
| **Akış** |Akış, mevcut hizmetlerin herhangi bir birleşimini kullanan bir iş akışı uygulamasıdır. |

## <a name="all-about-how-dlp-policies-work"></a>DLP ilkelerinin çalışma şekli hakkında her şey
DLP ilkesi, basit tanımıyla her bir hizmeti birbirini dışlayan iki veri grubundan birine yerleştiren adlandırılmış bir kuraldır. Bu kural daha sonra bir ortama uygulanır. Ortam, kullanıcıların mantıksal şekilde gruplandırılmasıdır. Kullanıcıların, farklı veri gruplarına eklediğiniz hizmetler arasında veri paylaşan akışlar oluşturmalarına izin verilmez. Diğer bir deyişle, kullanıcılarınız yalnızca **tek** bir veri grubu içindeki hizmetler arasında veri paylaşan akışlar oluşturabilir. Veri grupları arasında paylaşıma izin verilmez.  

| **Veri grubu adı** | **Veri grubu tanımı** |
| --- | --- |
| **Yalnızca iş verileri** |Bu gruptaki tüm hizmetler kendi aralarında veri paylaşabilir. **İş verilerine izin verilmez** veri grubuyla veri paylaşamazlar. |
| **İş verilerine izin verilmez** |Bu gruptaki tüm hizmetler kendi aralarında veri paylaşabilir. **Yalnızca iş verileri** veri grubuyla veri paylaşamazlar. |

**Not**: Bir hizmeti bir veri grubuna eklemek, hizmeti otomatik olarak diğer veri grubundan kaldırır. Örneğin, Twitter şu anda **yalnızca iş verileri** veri grubunda bulunuyorsa ve iş verilerinin Twitter ile paylaşılmasına izin vermek istemiyorsanız Twitter hizmetini **iş verilerine izin verilmez** adlı veri grubuna eklemeniz yeterlidir. Bu işlem Twitter’ı **yalnızca iş verileri** grubundan kaldırır.

## <a name="heres-what-you-need-to-create-a-dlp"></a>DLP oluşturmak için bilmeniz gerekenler
* Microsoft Flow [yönetim merkezine](https://admin.flow.microsoft.com) erişim  
* Ortam Yöneticisi rolüne sahip bir hesap  
* Kendisine atanan kullanıcıları içeren bir ortam  

## <a name="create-a-dlp-policy"></a>DLP ilkesi oluşturma
Aşağıda, DLP ilkesi oluşturma konusu genel hatlarıyla özetlenmiştir:  

1. İlkeye bir ad verin
2. İlkenin uygulanacağı ortamı seçin
3. Hizmetleri iki veri grubundan birine ekleyin. Yalnızca belirli bir grupta bulunan hizmetlerin veri paylaşabildiğini, bu nedenle iki ayrı veri grubunda bulunan hizmetler arasında veri paylaşmak için oluşturulan akışların, akışı oluşturan kişi tarafından kaydedilirken otomatik olarak engelleneceğini unutmayın.  

DLP ilkeleri hakkında daha [ayrıntılı adım adım bir kılavuz](../prevent-data-loss.md) da bulunmaktadır.  

## <a name="examples"></a>Örnekler
* Akışları yalnızca SharePoint, Office 365 kullanıcıları, Office 365 Outlook, OneDrive İş, Dynamics 365, SQL Server ve Salesforce arasında iş verilerini paylaşmayla kısıtlayan bir ilke oluşturursanız bu ilke aşağıdaki gibi görünür:  
  ![](./media/learning-data-loss-prevention/a-few-business-centric-services.png)  
* Belirli bir ortamın üyelerinin, SharePoint verilerini paylaşan bir akış oluşturmasına izin vermeyen bir ilke oluşturursanız bu ilke aşağıdaki gibi görünür. SharePoint’in **yalnızca iş verileri** veri grubundaki tek hizmet olduğuna dikkat edin:  
  ![yalnızca iş verileri](./media/learning-data-loss-prevention/sharepoint-only-no-sharing-guided-learning.png)

