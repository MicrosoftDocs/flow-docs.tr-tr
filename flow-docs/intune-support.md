---
title: Microsoft Flow mobil uygulaması şimdi Microsoft Intune'un Mobil Uygulama Yönetimi'ni destekliyor. | Microsoft Docs
description: Microsoft Flow mobil uygulaması şimdi Microsoft Intune'un Mobil Uygulama Yönetimi'ni destekliyor.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 7cc2b37eb27ed0e2107eeaada02afb072d9a0098
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65060503"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>Microsoft Flow mobil uygulaması Microsoft Intune'u destekliyor

iOS ve Android için Microsoft Flow mobil uygulaması cihaz kaydı olmadan Intune'un Mobil Uygulama Yönetimi'ni (MAM) destekler. MAM'nin kullanılması kurumsal verileri koruma altına almak için BT yöneticilerinin mobil veri ilkeleri oluşturmasına ve zorlamasına olanak tanır.

## <a name="why-intune-support-is-important"></a>Intune desteği neden önemli?

Kuruluşlar çalışanların mobil cihazlarında duran veriler üzerinde daha fazla denetim elde etmek ister. Kuruluşlar bu verilerin cihaza taşınma yöntemini kısıtlamak ve çalışanın kuruluştan ayrılması durumunda bu verilerin kaldırıldığından emin olmak isteyebilir.

## <a name="what-is-microsoft-application-management-mam"></a>Microsoft Uygulama Yönetimi (MAM) nedir?

MAM kuruluşların kiracı içinde uygulamaların kullanımını yöneten ilkeler oluşturmasına olanak tanır. Bunlar uygulama verilerinin şifrelenmesini zorlamayı, verileri yalnızca onaylanan uygulamalara kopyalanacak veya ayıklanacak şekilde sınırlamayı ya da cihazda PIN'i zorunlu tutmayı içerir.

### <a name="prerequisites"></a>Önkoşullar

- Intune [uygulama koruma ilkesi](https://docs.microsoft.com/intune/app-protection-policies).
- Azure Active Directory (Azure AD) grubu.
- Şirket Portalı. MAM kullanmanın önemli avantajlarından biri cihazların Intune MAM'ye kaydedilmesinin gerekli olmamasıdır. Tek gereken App Store'dan ve Google Play mağazasından sağlanabilen Şirket Portalı'dır.
- iOS, Android veya Windows Phone için Microsoft Flow mobil uygulamasının 2.31.0 sürümü.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Uygulama ilkesi oluşturma, uygulamaları ilkeye atama, ayarları tanımlama ve Azure AD grubuna kullanıcı ekleme

Microsoft Flow mobil uygulamasının yönetilebilmesi için şunları yapmalısınız:

1. Uygulama koruma ilkesi oluşturmalısınız.
1. Microsoft Flow mobil uygulamasını uygulama koruma ilkesine atamalısınız.
1. İlke ayarlarını atamalısınız. Örneğin, Microsoft Flow mobil uygulamasının çalıştırıldığı mobil cihaza erişmek için PIN gerekmesini sağlayacak bir ilke atayabilirsiniz.
1. Uygulama koruma ilkesini belirli bir Azure AD grubuna uygulamalısınız.
1. Uygulama koruma ilkesinin uygulanacağı tüm kullanıcıları Azure AD grubuna ekleyin.

Şu adımları izleyerek Microsoft Flow mobil uygulaması kullanıcılarının uygulamaya erişmek için önce PIN girmelerini gerektiren bir [uygulama koruma ilkesi](https://docs.microsoft.com/intune/app-protection-policies) oluşturun. 


## <a name="test-the-app-protection-policy"></a>Uygulama koruma ilkesini test etme

Uygulama koruma ilkesini oluşturduktan ve kullanıcıları Azure AD grubuna atadıktan sonra, sıra Microsoft Flow mobil uygulamasını kullanmaya ve ilkenin çalıştığını onaylamaya gelir.

İlkenin çalıştığını onaylamak için aşağıdaki adımları izleyin:

1. Platformu, uygulama koruma ilkesinde tanımladığınız platformlardan biriyle eşleşen bir cihaza Microsoft Flow mobil uygulamasını yükleyin.
1. Mobil uygulamanın kullanımını PIN'i bilen kullanıcılarla kısıtlayan Azure AD grubundaki bir hesapla mobil uygulamada oturum açın.

Şunları yapmanız istenir:
1. Şirket Portalı'nı yükleyin.
1. Uygulama koruma ilkesinin ölçütlerine uyan bir PIN'iniz yoksa, PIN'inizi ayarlayın.


## <a name="learn-more"></a>Daha fazla bilgi

[Uygulama koruma ilkesi](https://docs.microsoft.com/intune/app-protection-policies) oluşturmayı öğrenin.

