---
title: GDPR veri konu Isteği Özeti | Microsoft Docs
description: Microsoft Flow için GMBU veri konu taleplerini nasıl yanıtleyeceğinizi öğrenin.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: c4d2686e9da00aaccc46e62570de387678bd1ece
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548220"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Microsoft Flow için GDPR veri konusu Isteklerine yanıt verme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bu makale size ve kuruluşunuzu Avrupa Birliği 'nin Genel Veri Koruma Yönetmeliği (GDPR) için hazırlar. Bu makalede, Microsoft 'un GDPR için hazırlanması için ne yaptığını ve Ayrıca PowerApps, Microsoft Flow ve Common Data Service kullanırken GDPR uyumluluğunu desteklemek için şu adımları paylaşacağınızı açıklamaktadır.

## <a name="prerequisites"></a>Kaynakları

Kullanıcılar ve Yöneticiler bu makalede özetlenen eylemleri gerçekleştirebilir.

### <a name="users"></a>Kullanıcılarına

Bir kullanıcının [Microsoft Flow lisansı](https://preview.flow.microsoft.com/pricing/)olan etkin bir Azure Active Directory hesabı olması gerekir. Bu gereksinimi karşılamayan kullanıcıların, bir yöneticiden bu eylemleri gerçekleştirmesini istemesi gerekir.

### <a name="administrators"></a>Yönetim

[Microsoft Flow Yönetim Merkezi](https://admin.flow.microsoft.com/) 'Nde veya [PowerApps yönetici PowerShell](https://go.microsoft.com/fwlink/?linkid=871804) 'de bu izinlerin her ikisine de sahip bir hesapla oturum açarsanız, bu makalede özetlenen yönetici ayrıcalıkları gerektiren işlemleri gerçekleştirebilirsiniz:

- PowerApps plan 2 için ücretli veya deneme sürümü lisansı.

    [Deneme lisansının](http://web.powerapps.com/trial) süresi 30 gün içinde dolar.

- [Office 365 genel yönetici](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) veya [Azure Active Directory genel yönetici](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Yönetilmeyen kiracılar
[Yönetilmeyen bir kiracının](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover)üyesiyseniz, yanı Azure AD kiracınızda genel yönetici yoksa, kendi kişisel verilerinizi dışarı ve dışa aktarmak için bu makalede özetlenen adımları izleyebilirsiniz. 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Microsoft Flow müşteri verileri için DSRs 'ye yanıt verme

GDPR, bir işveren ya da başka bir kurum veya kuruluş (veri denetleyicisi veya yalnızca denetleyici olarak bilinir) tarafından toplanan kişisel verileri yönetmek için kişilere (GDPR veri konuları olarak bilinir) haklar verir. Kişisel veriler, tanımlanan veya tanımlanabilen doğal bir kişiyle ilgili herhangi bir veri olarak GDPR kapsamında çok büyük ölçüde tanımlanmıştır. GDPR, veri ilgililere kişisel verilerine özel haklar verir; Bu haklar, kişisel verilerin kopyalarını alma, bu üzerinde düzeltmeler isteme, bu işlemin işlenmesini kısıtlama, silme veya başka bir denetleyiciye taşınabilmesi için elektronik biçimde alma işlemlerini içerir. Bir denetleyiciye kişisel verileri üzerinde işlem yapması için bir veri konusunun resmi bir isteği, veri sahibi hakları (DSR) Isteği olarak adlandırılır.

Bu makalede, denetleyicilerin DSRs 'de yanıt alırken kişisel verileri bulmasına ve üzerinde işlem yapması için Microsoft 'un ürünlerinin, hizmetlerinin ve yönetim araçlarının nasıl kullanılacağı açıklanır. Özellikle, bu makalede Microsoft 'un bulutunda bulunan kişisel verileri bulma, erişme ve bunlara işlem yapma dahildir. Bu kılavuzda özetlenen işlemlere hızlı bir genel bakış aşağıda verilmiştir:

1. Keşfet: bir DSR 'nin konusu olabilecek müşteri verilerini daha kolay bulmak için arama ve bulma araçlarını kullanın. Potansiyel olarak yanıt veren belgeler toplandıktan sonra, isteğe yanıt vermek için aşağıdaki adımlarda açıklanan bir veya daha fazla DSR eylemini gerçekleştirebilirsiniz. Alternatif olarak, isteğin, DSRs 'ye yanıt vermek için kuruluşunuzun yönergelerini karşılamadığını belirleyebilirsiniz. [DSR bulma belgelerini Microsoft Flow](gdpr-dsr-discovery.md)

1. Erişim: Microsoft bulutunda bulunan kişisel verileri alın ve istenirse, veri konusu tarafından kullanılabilecek bir kopyasını oluşturun.

1. Rectify: uygun olduğunda, kişisel veriler üzerinde değişiklikler yapın veya istenen diğer eylemleri uygulayın.

    Bir veri konusu, kuruluşunuzda bulunan kişisel verilerini yeniden etkinleştirmenizi isterse, sizin ve kuruluşunuzun isteği kabul etmek için uygun olup olmadığını belirlemesi gerekir.  Verilerin düzeltilmesi, kişisel verileri Düzenle, redaketleme veya kaldırma gibi eylemleri almayı içerebilir.

    Azure Active Directory, Microsoft Flow kullanıcıların kimliklerini yönetmek için kullanabilirsiniz. Kurumsal müşteriler, belirli bir Microsoft hizmetinin doğası gereği sınırlı bir Düzenle özelliği de dahil olmak üzere DSR düzeltmek isteklerini yönetebilir.  Veri işlemcisi olarak, Microsoft, bu Günlükler doğru etkinlikleri yansıttığından ve Microsoft Hizmetleri içindeki olayların bir geçmiş kaydını oluşturduğundan, sistem tarafından oluşturulan günlükleri düzeltme olanağı sunmaz.  [DSR hakkında daha fazla bilgi edinin](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Kısıtla: çeşitli çevrimiçi hizmetler lisanslarını kaldırarak veya mümkün olduğunca istenen Hizmetleri kapatarak kişisel verilerin işlenmesini kısıtlayın. Ayrıca Microsoft bulutundaki verileri kaldırabilir ve şirket içinde veya başka bir konumda saklayabilirsiniz.

    Veri konuları, kişisel verilerinin işlenmesini kısıtlamanızı isteyebilir.  Microsoft bu amaçla uygulama programlama arabirimlerini (API 'Ler) ve kullanıcı arabirimlerini (UIS) sağlar.  Bu arabirimler, kurumsal müşterinin kiracı yöneticisinin veri dışa aktarma ve veri silme işleminin bir birleşimi aracılığıyla bu tür DSRs 'yi yönetmesine olanak tanır. Müşteri, hesap (ler), sistem tarafından oluşturulan Günlükler ve ilişkili Günlükler dahil olmak üzere kullanıcının kişisel verilerinin elektronik bir kopyasını dışarı aktarabilir (1) ve bu, Microsoft sistemlerinde bulunan hesabın ve ilişkili verilerin silinmesini (2) izler.

1. Sil: Microsoft 'un bulutunda bulunan kişisel verileri kalıcı olarak kaldırın. [Kişisel verileri silme hakkında daha fazla bilgi edinin](gdpr-dsr-delete.md).

1. Dışarı Aktar: veri konusunun kişisel verilerinin elektronik bir kopyasını (makine tarafından okunabilen bir biçimde) sağlayın. Bu makaledeki her bölümde, bir veri denetleyici kuruluşun Microsoft bulutundaki kişisel verilere yönelik bir DSR 'e yanıt vermek için götürebildiği teknik yordamlar özetlenmektedir. [Kişisel verileri dışarı aktarma hakkında daha fazla bilgi edinin](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Sistem tarafından oluşturulan Günlükler

Microsoft Flow için sistem tarafından oluşturulan Günlükler hakkında daha fazla bilgi için bu [kılavuza](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) bakın.
