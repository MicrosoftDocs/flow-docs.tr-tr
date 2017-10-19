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
ms.date: 02/15/2017
ms.author: deonhe
ms.openlocfilehash: 41f5d40ca2ad5fcce3a7967beef7104dd532b1d8
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
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
> Microsoft SharePoint veri ağ geçitleri HTTP trafiğini destekler ancak HTTPS trafiğini desteklemez.
> 
> 

## <a name="prerequisites"></a>Önkoşullar
* Microsoft Flow'a [kaydolmak](sign-up-sign-in.md) için kullandığınız kullanıcı adı ve parola.
* Bir ağ geçidi üzerinde yönetim izinleri.
  
  Bu izinlere, yüklediğiniz her ağ geçidi için varsayılan olarak sahip olursunuz. Başka bir ağ geçidinin yöneticisi, size kendi ağ geçidi için bu izinleri verebilir.
* Ağ geçitlerini destekleyen bir lisans. Daha fazla bilgi edinmek için [fiyatlandırma sayfasındaki](https://flow.microsoft.com/pricing/) “Bağlantı” bölümünü inceleyin.
* Yalnızca [varsayılan ortamınızda](environments-overview-maker.md) bir ağ geçidi ve şirket içi bağlantısı oluşturabilirsiniz.

## <a name="view-your-gateways"></a>Ağ geçitlerinizi görüntüleme
[Microsoft Flow web sitesinin](https://flow.microsoft.com) sağ üst köşesindeki dişli simgesine tıklayın veya dokunun ve sonra **Ağ geçitleri**’ne tıklayın veya dokunun.

![Yönetilen ağ geçidi][1]

**Not**: PowerApps’te bir ağ geçidi oluşturduysanız veya size bu ağ geçidine yönelik erişim izni verildiyse, bu ağ geçidi Microsoft Flow’daki **Ağ geçitlerim** listesinde görüntülenir.

## <a name="install-a-gateway"></a>Ağ geçidi yükleme
1. [Ağ Geçidi Yükleme Sihirbazı](http://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409)'nı indirin.
   
    Bu sihirbazı [Microsoft Flow web sitesinin](https://flow.microsoft.com) sağ üst köşesindeki dişli simgesine tıklayarak veya dokunarak, **Ağ geçitleri**'ne tıklayarak veya dokunarak ve sonra **Ağ geçidi oluştur**'a tıklayarak veya dokunarak da indirebilirsiniz.
   
    ![Ağ geçidi yüklemesi][2]
2. Sihirbazı Microsoft Flow'da oturum açmak için kullandığınız kimlik bilgilerini girerek çalıştırın.
   
    Ağ geçidinizi başarılı şekilde kaydedip yapılandırdıktan sonra, ağ geçidiniz Microsoft Flow’daki **Ağ geçitlerim** listesinde görünür.

Daha fazla bilgi edinmek için bkz. [Ağ geçitlerini anlama](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
[2]: ./media/manage-gateway/list-gateways.png
