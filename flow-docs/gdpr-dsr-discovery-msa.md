---
title: Microsoft Hesapları (MSA) için Microsoft Flow GDPR Veri Sahibi Bulma İstekleri | Microsoft Docs
description: Microsoft Flow’u kullanarak Microsoft Hesapları için GDPR Veri Sahibi Bulma İsteklerini yanıtlamayı öğrenin.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/16/2018
ms.author: keweare
ms.openlocfilehash: d31e91420f2235b201d3ae974b1950ae5fbc35c9
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34563313"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>GDPR Veri Sahibi Bulma İsteklerini yanıtlama 

Bir DSR isteğini yanıtlamadaki ilk adım, isteğin konusu olan kişisel verileri bulmaktır.
Microsoft Hesabı (MSA) ile kimlik doğrulaması yapan bir kullanıcının kişisel verilerini içeren Microsoft Flow kaynaklarının bir özeti aşağıda verilmiştir.

|Kaynak|Amaç|
|-----|-----|
|Çalıştırma geçmişi|Son 28 gün içindeki her akış yürütmesinin geçmişini sağlar. Bu veriler, her bir akış çalıştırması için başlangıç zamanı, bitiş zamanı, durum ve tüm giriş/çıkış bilgilerini içerir. [Akış çalıştırma geçmişi](https://flow.microsoft.com/blog/download-history-recurrence/) hakkında daha fazla bilgi edinin.|
|Etkinlik akışı| Çalışma durumu, hatalar ve bildirimler de dahil olmak üzere her bir akışın etkinliklerinin özetini sağlar.|
|Akışlar|Bir [akış](https://docs.microsoft.com/flow/get-started-logic-flow) için iş akışı mantığı.|
|Bağlantılar|Bağlayıcılar tarafından kullanılır ve API’lere, sistemlere, veritabanlarına vb.’ye bağlantı olanağı sağlar. [Bağlantılar](add-manage-connections.md) hakkında daha fazla bilgi edinin.|

