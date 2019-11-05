---
title: Mobil uygulama Microsoft Flow artık Microsoft Intune mobil uygulama yönetimini desteklemektedir. | Microsoft Docs
description: Mobil uygulama Microsoft Flow artık Microsoft Intune mobil uygulama yönetimini desteklemektedir.
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
ms.openlocfilehash: d5709d7f98c3f4cc1dcf7d0da8fc5c9501adb84c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547390"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>Mobil uygulama Microsoft Flow Microsoft Intune destekler
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

İOS ve Android için Microsoft Flow mobil uygulaması, cihaz kaydı olmadan Intune 'un mobil uygulama yönetimini (MAM) destekler. MAM kullanımı, BT yöneticilerinin kurumsal verileri korumak için mobil veri ilkeleri oluşturmalarına ve zorlayamalarına olanak sağlar.

## <a name="why-intune-support-is-important"></a>Intune desteğinin neden önemli olduğunu

Kuruluşlar, çalışan mobil cihazlarda bulunan veriler üzerinde daha fazla denetim arıyor. Kuruluşlar, bu verilerin cihaza nasıl taşındığını kısıtlamak ve verilerin kaldırıldığından emin olmak için çalışanın kuruluştan ayrılmasına izin vermek isteyebilir.

## <a name="what-is-microsoft-application-management-mam"></a>Microsoft uygulama yönetimi nedir (MAM)

MAM, kuruluşların bir kiracı içinde uygulamaların nasıl kullanıldığını yöneten ilkeler oluşturmalarına olanak tanır. Bu, uygulama veri şifrelemesini zorlamayı, yalnızca onaylanan uygulamalara veri kopyalama veya ayıklama veya bir cihazda PIN 'ı zorlama olanağını içerir.

### <a name="prerequisites"></a>Kaynakları

- Bir Intune [Uygulama koruma ilkesi](https://docs.microsoft.com/intune/app-protection-policies).
- Azure Active Directory (Azure AD) grubu.
- Şirket Portalı. MAM kullanmanın tek bir avantajı, cihazların Intune MAM 'e kaydolması gerekmez. Tüm gerekli olan Şirket Portalı, App Store ve Google Play mağazalarından erişilebilen.
- İOS, Android veya Windows Phone için Microsoft Flow mobil uygulamasının sürüm 2.31.0.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Uygulama koruma ilkesi oluşturma, ilkeye uygulama atama, ayarları tanımlama ve bir Azure AD grubuna kullanıcı ekleme

Microsoft Flow mobil uygulamanın yönetilmesi için şunları yapmanız gerekir:

1. Uygulama koruma ilkesi oluşturun.
1. Microsoft Flow mobil uygulamayı uygulama koruma ilkesine atayın.
1. İlke ayarlarını atayın. Örneğin, Microsoft Flow mobil uygulamayı çalıştıran mobil cihaza erişmek için bir PIN gerektirecek şekilde ilke atayabilirsiniz.
1. Uygulama koruma ilkesini belirli bir Azure AD grubuna uygulayın.
1. Uygulama koruma ilkesinin Azure AD grubuna uyguladığı tüm kullanıcıları ekleyin.

Mobil Uygulama kullanıcılarının uygulamaya erişebilmek için PIN girmelerini Microsoft Flow gerektiren bir [Uygulama koruma ilkesi](https://docs.microsoft.com/intune/app-protection-policies) oluşturmak için bu adımları izleyin. 


## <a name="test-the-app-protection-policy"></a>Uygulama koruma ilkesini test etme

Uygulama koruma ilkesini oluşturduktan ve kullanıcıları Azure AD grubuna atadıktan sonra, Microsoft Flow mobil uygulamanın kullanılması ve ilkenin çalıştığını onaylamanız zaman atalım.

İlkenin çalıştığından emin olmak için şu adımları izleyin:

1. Platformu uygulama koruma ilkesinde tanımladığınız platformlardan biriyle eşleşen bir cihaza Microsoft Flow Mobile uygulamasını yükleyebilirsiniz.
1. Mobil uygulamanın, PIN 'ı olan kullanıcılar için kullanımını sınırlayan Azure AD grubundaki bir hesapla oturum açın.

Sizden şunları yapmanız istenir:
1. Şirket Portalı 'i yükler.
1. Uygulama koruma ilkesinin ölçütlerine uyan bir PIN 'iniz yoksa PIN 'inizi ayarlayın.


## <a name="learn-more"></a>Daha fazla bilgi edinin

[Uygulama koruma ilkesi](https://docs.microsoft.com/intune/app-protection-policies)oluşturmayı öğrenin.

