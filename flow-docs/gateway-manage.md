---
title: Şirket içi veri ağ geçitlerini yönetme | Microsoft Docs
description: Microsoft Flow'da şirket içi veri ağ geçitlerini görüntüleme ve yükleme
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
ms.date: 02/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 04246007fabacabaf86914f906eee1741df217a1
ms.sourcegitcommit: b5395b7f3d6610990cbbeeff8f6972224bc2149a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48817953"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Microsoft Flow’da şirket içi veri ağ geçitlerini yönetme

Microsoft Flow aracılığıyla çeşitli bulut tabanlı uygulamalarınızı şirket içi verileriniz ve uygulamalarınızla güvenli bir şekilde tümleştirmek için bir şirket içi veri ağ geçidi yükleyin ve yönetin.

Ağ geçidi aracılığıyla şu bağlantılar üzerinden şirket içi verilere erişebilirsiniz:

* Apache Impala
* DB2
* Dosya Sistemi
* Azure AD ile Http
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (Önizleme)

> [!IMPORTANT]
> Microsoft SharePoint veri ağ geçitleri artık HTTP ve HTTPS trafiğini destekler.

## <a name="prerequisites"></a>Önkoşullar

* Microsoft Flow'a [kaydolmak](sign-up-sign-in.md) için kullandığınız kullanıcı adı ve parola.
* Bir ağ geçidi üzerinde yönetim izinleri.

  Yüklediğiniz her ağ geçidi için bu izinlere varsayılan olarak sahip olursunuz. Ayrıca, başka bir ağ geçidinin yöneticisi, ilgili ağ geçidi için size bu izinleri verebilir.
* Ağ geçitlerini destekleyen bir lisans. Daha fazla bilgi edinmek için [fiyatlandırma sayfasındaki](https://flow.microsoft.com/pricing/) “Bağlantı” bölümünü inceleyin.

> [!NOTE]
> Yalnızca [varsayılan ortamınızda](environments-overview-maker.md) bir ağ geçidi ve şirket içi bağlantısı oluşturabilirsiniz.



## <a name="view-your-gateways"></a>Ağ geçitlerinizi görüntüleme

[Microsoft Flow web sitesinin](https://flow.microsoft.com) sağ üst köşesindeki dişli simgesini seçip **Ağ geçitleri**’ni seçin.

![Yönetilen ağ geçidi][1]

> [!NOTE]
> PowerApps’te bir ağ geçidi oluşturduysanız veya size bu ağ geçidine yönelik erişim izni verildiyse, bu ağ geçidi Microsoft Flow’daki **Ağ geçitlerim** listesinde görüntülenir.



## <a name="install-a-gateway"></a>Ağ geçidi yükleme

1. [Ağ Geçidi Yükleme Sihirbazı](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409)'nı indirin.

1. Sihirbazı çalıştırın ve Microsoft Flow'da oturum açmak için kullandığınız kimlik bilgilerini girin.

    Ağ geçidinizi başarılı şekilde kaydedip yapılandırdıktan sonra, ağ geçidiniz Microsoft Flow’daki **Ağ geçitleri** listesinde görünür.

Daha fazla bilgi edinmek için bkz. [Ağ geçitlerini anlama](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
