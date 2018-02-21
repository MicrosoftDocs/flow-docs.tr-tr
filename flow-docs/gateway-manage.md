---
title: "Şirket içi veri ağ geçitlerini yönetme | Microsoft Docs"
description: "Microsoft Flow'da şirket içi veri ağ geçitlerini görüntüleme ve yükleme"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/05/2018
ms.author: deonhe
ms.openlocfilehash: 642cf26110a09404c8bd453f894540963904ebda
ms.sourcegitcommit: 0b7964058416fd8d5e355913eea27172f1c61992
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Microsoft Flow’da şirket içi veri ağ geçitlerini yönetme

Microsoft Flow aracılığıyla çeşitli bulut tabanlı uygulamalarınızı şirket içi verileriniz ve uygulamalarınızla güvenli bir şekilde tümleştirmek için bir şirket içi veri ağ geçidi yükleyin ve yönetin.

Ağ geçidi aracılığıyla şu bağlantılar üzerinden şirket içi verilere erişebilirsiniz:

* SharePoint
* SQL Server
* Oracle
* Informix
* Filesystem
* DB2

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
