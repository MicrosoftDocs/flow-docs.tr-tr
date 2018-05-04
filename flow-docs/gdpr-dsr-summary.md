---
title: GDPR Veri Sahibi İstek Özeti | Microsoft Docs
description: Microsoft Flow için GDPR Veri Sahibi İstekleri’ni yanıtlamayı öğrenin.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/18/2018
ms.author: keweare
ms.openlocfilehash: 9f9513ca0239f72c36e96387fc010040936bbd02
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Microsoft Flow için GDPR Veri Sahibi İstekleri’ni yanıtlama

Bu makale sizi ve kuruluşunuzu Avrupa Birliği’nin Genel Veri Koruma Yönetmeliği’ne (GDPR) hazırlar. Bu belgeler, yalnızca GDPR’ye hazırlanmak için Microsoft’un neler yaptığını açıklamakla kalmıyor, aynı zamanda PowerApps, Microsoft Flow ve Uygulamalar için Common Data Service kullanırken GDPR uyumluluğunu desteklemek için bir an önce atabileceğiniz adımların örneklerini paylaşıyor.

## <a name="prerequisites"></a>Önkoşullar

Kullanıcılar ve yöneticiler bu makalede ana hatlarıyla açıklanan eylemleri gerçekleştirebilir.

### <a name="users"></a>Kullanıcılar

Kullanıcının [Microsoft Flow lisansına](https://preview.flow.microsoft.com/pricing/) sahip etkin bir Azure Active Directory hesabının olması gerekir. Bu gereksinimi karşılayamayan kullanıcıların bir yöneticiden bu eylemleri gerçekleştirmesini istemesi gerekir.

### <a name="administrators"></a>Yöneticiler

Bu iki izne de sahip bir hesapla [Microsoft Flow Yönetim merkezi](https://admin.flow.microsoft.com/)  veya [PowerApps Yönetici PowerShell](https://go.microsoft.com/fwlink/?linkid=871804)’de oturum açtığınızda, bu makalede açıklanan yönetici ayrıcalıkları gerektiren işlemleri gerçekleştirebilirsiniz:

- PowerApps Plan 2 ücretli veya deneme lisansı.

    [Bir deneme lisansının](http://web.powerapps.com/trial) 30 gün içinde süresi dolar.

- [Office 365 Genel Yönetici](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) veya [Azure Active Directory Genel Yönetici](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Microsoft Flow müşteri verileri için DSR’leri yanıtlama

GDPR, kişilere (GDPR’de veri sahipleri olarak bilinir) bir işveren veya başka türde bir acente ya da kuruluş (veri sorumlusu ya da yalnızca sorumlu olarak bilinir) tarafından toplanan kişisel verileri yönetme hakkı verir. Kişisel veriler, tanımlı veya tanımlanabilir bir gerçek kişiyle ilişkili tüm veriler olarak GDPR kapsamında geniş bir şekilde tanımlanmıştır. GDPR, veri sahiplerine kişisel verilerine yönelik belirli haklar verir. Kişisel verilerin kopyalarını almak, bu verilere düzeltmeler yapılmasını istemek, verilerin işlenmesini kısıtlamak, verileri silmek veya başka bir sorumluya taşınabilmesi için elektronik biçimde almak bu haklara dahildir. Bir veri sahibinin bir sorumludan kişisel verileri üzerinde bir işlem yapmak üzere resmi istekte bulunmasına Veri Sahibi Hakları (DSR) İsteği adı verilir.

Bu makalede Microsoft’un ürünlerini, hizmetlerini ve yönetim araçlarını kullanarak, sorumluların DSR’leri yanıtlarken kişisel verileri bulup bu veriler üzerinde işlem yapmasına nasıl yardımcı olunacağı açıklanmaktadır. Özellikle bu makalede Microsoft’un bulutunda yer alan kişisel verileri bulma, bu verilere erişme ve bu veriler üzerinden işlem yapma şekli açıklanır. Bu kılavuzda gösterilen işlemlere hızlı bir genel bakışı burada bulabilirsiniz:

1. Keşfedin: Arama ve keşif araçlarını kullanarak bir DSR konusu olabilecek müşteri verilerini daha kolay bir şekilde bulun. Duyarlı olabilen belgeler toplandığında, isteği yanıtlamak için aşağıdaki adımlarda açıklanan DSR eylemlerinden bir veya daha fazlasını gerçekleştirebilirsiniz. Alternatif olarak, isteğin kuruluşunuzun DSR’leri yanıtlama yönergelerini karşılamadığını belirleyebilirsiniz. [Microsoft Flow DSR Keşif belgeleri](gdpr-dsr-discovery.md)

1. Erişim: Microsoft bulutunda yer alan kişisel verileri alın ve istenirse veri sahibinin kullanabileceği bir kopyasını oluşturun.

1. Düzeltin: Uygunsa kişisel veriler üzerinde değişiklikler yapın veya istenen diğer eylemleri uygulayın.

    Bir veri sahibi sizden kuruluşunuzda yer alan kişisel verilerini düzeltmenizi isterse, sizin ve kuruluşunuzun bu isteği yerine getirmenin uygun olup olmayacağını belirlemesi gerekir.  Verileri düzeltmeye, kişisel verileri düzenleme, hazırlama ve kaldırma gibi eylemler dahil olabilir.

    Azure Active Directory kullanarak Microsoft Flow kullanıcılarının kimliklerini yönetebilirsiniz. Kurumsal müşteriler, belirli bir Microsoft hizmetinin yapısı dahilinde sınırlı düzenleme özellikleri içeren DSR düzeltme isteklerini yönetebilir.  Sistem tarafından oluşturulmuş günlükler gerçek etkinlikleri yansıttığından ve Microsoft hizmetlerindeki etkinliklerin geçmiş kaydını oluşturduğundan, veri işlemcisi olarak Microsoft bu günlükleri düzeltme özelliği sunmaz.  [DSR hakkında daha fazla bilgi edinin](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Kısıtlayın: Mümkün olduğunda çeşitli çevrimiçi hizmetlerin lisanslarını kaldırarak veya istenen hizmetleri kapatarak kişisel verilerin işlenmesini kısıtlayın. Ayrıca verileri Microsoft bulutundan kaldırabilir ve şirket içinde ya da başka bir konumda saklayabilirsiniz.

    Veri sahipleri, kişisel verilerinin işlenmesini kısıtlamanızı isteyebilir.  Microsoft bu amaç doğrultusunda uygulama programı arabirimleri (API’ler) ve kullanıcı arabirimleri (UI’ler) sağlar.  Bu arabirimler, kurumsal müşterinin kiracı yöneticisinin bu tarz DSR’leri veri dışarı aktarma ve veri silmeyi birlikte kullanarak yönetmesine olanak sağlar. Bir müşteri (1) kullanıcının hesapları, sistem tarafından oluşturulmuş günlükleri ve ilişkili günlükleri içeren kişisel verilerinin bir elektronik kopyasını dışarı aktarabilir ve ardından (2) Microsoft sistemleri içinde yer alan hesabı ve ilişkili verileri silebilir.

1. Silin: Microsoft'un bulutunda yer alan kişisel verileri kalıcı olarak kaldırın. [Kişisel verileri silme hakkında daha fazla bilgi edinin](gdpr-dsr-delete.md).

1. Dışarı aktarın: Kişisel verilerin bir elektronik kopyasını (makine tarafından okunabilir bir biçimde) veri sahibine sağlayın. Bu makaledeki her bölüm, bir veri sorumlusu kuruluşun Microsoft’un bulutundaki kişisel verilere yönelik bir DSR’yi yanıtlamak için gerçekleştirebileceği teknik yordamları özetler. [Kişisel verileri dışarı aktarma hakkında daha fazla bilgi edinin](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Sistem tarafından oluşturulan günlükler

Bu [kılavuza](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) başvurarak Microsoft Flow için sistem tarafından oluşturulmuş günlükler hakkında daha fazla bilgi edinin.
