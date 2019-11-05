---
title: Şirket içi veri ağ geçitlerini yönetmeyi öğrenin | Microsoft Docs
description: Microsoft Flow ' de şirket içi veri ağ geçidini görüntüleyin ve yükler.
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
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3991e739178f86bbea3ae1b68b9d3337c42b4727
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547660"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Microsoft Flow 'da şirket içi veri ağ geçidini yönetme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Çeşitli bulut tabanlı uygulamaları Microsoft Flow aracılığıyla şirket içi verileriniz ve uygulamalarınızla güvenli bir şekilde bütünleştirmek için şirket içi veri ağ geçidini yükleyip yönetin.

Ağ geçidiyle, bu bağlantılar üzerinden şirket içi verilere bağlanabilirsiniz:

* Apache Impala
* Oluşturduğunuz özel bağlayıcılar
* DB2
* Dosya sistemi
* Azure AD ile http
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (Önizleme)

> [!IMPORTANT]
> Microsoft SharePoint veri ağ geçitleri artık HTTP ve HTTPS trafiğini destekler.

## <a name="prerequisites"></a>Kaynakları

* Microsoft Flow [kaydolmak](sign-up-sign-in.md) için kullandığınız Kullanıcı adı ve parola.
* Ağ geçidinde yönetim izinleri.

  Bu izinlere, yüklediğiniz her ağ geçidi için varsayılan olarak sahip olursunuz. Ayrıca, başka bir ağ geçidinin Yöneticisi bu ağ geçidi için size bu izinleri verebilir.
* Ağ geçitlerini destekleyen bir lisans. Daha fazla bilgi için, [fiyatlandırma sayfasının](https://flow.microsoft.com/pricing/)"bağlantı" bölümüne bakın.

> [!NOTE]
> Yalnızca [varsayılan ortamınızda](environments-overview-maker.md)bir ağ geçidi ve şirket içi bağlantı oluşturabilirsiniz.

## <a name="install-a-gateway"></a>Ağ geçidi yüklemesi

Bir ağ geçidi yüklemek için, Şirket [içi veri ağ geçidini yüklemeyin](/data-integration/gateway/service-gateway-install)' daki adımları izleyin. _Şirket içi veri ağ geçidi (kişisel mod)_ yalnızca Power BI için kullanılabilir olduğundan ağ geçidini standart moda yükler.

## <a name="view-your-gateways"></a>Ağ geçitlerini görüntüleyin

[Microsoft Flow web sitesinin](https://flow.microsoft.com)sağ üst köşesinde dişli simgesini seçin ve **ağ geçitleri**' ni seçin.

![Yönetim altındaki Ağ Geçidi][1]

> [!NOTE]
> PowerApps 'te bir ağ geçidi için oluşturduğunuz veya erişim verildiyse, bu ağ geçidi Microsoft Flow içindeki **ağ geçitleri** listesinde görünür.

## <a name="cluster-your-gateways"></a>Ağ geçitlerini kümelerinizi yapın

Şirket içi veri kaynaklarına erişirken tek hata noktalarından kaçınmak için, Şirket [içi veri ağ geçidi yüklemelerinin yüksek kullanılabilirlik kümelerini](/data-integration/gateway/service-gateway-high-availability-clusters) oluşturabilirsiniz.

Varsayılan olarak, Microsoft Flow kümedeki birincil ağ geçidini kullanır. Birincil ağ geçidi kullanılamıyorsa, hizmet kümedeki sonraki ağ geçidine geçer ve bu şekilde devam eder.

Bir ağ geçidi kümesi ayarladıktan sonra, kümedeki tüm ağ geçitlerine trafiğin dağıtılmasına izin verebilirsiniz.

Trafiğinizi ağ geçitleriniz genelinde dağıtmak için şu adımları izleyin:

1. Sol taraftaki Gezinti çubuğunda bulunan **veriler** ' i seçin.
1. **Ağ geçitleri**' ni seçin.
1. Ağ geçitlerinizi seçin.
1. **Bu kümedeki tüm etkin ağ geçitleri arasında Istekleri dağıt**' ı seçin.
1. Değişikliklerinizi kaydetmek için **Uygula** ' yı seçin.

Daha fazla bilgi için bkz. [ağ geçitlerini anlama](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
