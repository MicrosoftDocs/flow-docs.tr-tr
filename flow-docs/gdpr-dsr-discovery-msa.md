---
title: Microsoft hesapları için Microsoft Flow GDPR veri konusu bulma Istekleri (MSA) | Microsoft Docs
description: Microsoft hesapları için guz veri konu bulma Isteklerini yanıtlamak üzere Microsoft Flow nasıl kullanacağınızı öğrenin.
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
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 06e88aa215089145f86f9027a6ad75b73c7cf627
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548111"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>GDPR veri konu bulma Isteklerini yanıtlama 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Bir DSR isteğine yanıt vermeye yönelik ilk adım, isteğin konusu olan kişisel verileri bullebiliyor.
Microsoft hesabı (MSA) ile kimlik doğrulaması yapan bir kullanıcıya ait kişisel verileri içeren Microsoft Flow kaynaklarının bir özeti aşağıda verilmiştir.

|Kaynak|Amaçla|
|-----|-----|
|çalıştırma geçmişi|Son 28 gün boyunca her akışın yürütme geçmişini sağlar. Bu veriler başlangıç zamanı, bitiş zamanı, durum ve her akış çalıştırmasının tüm giriş/çıkış bilgilerini içerir. [Akış çalıştırma geçmişi](https://flow.microsoft.com/blog/download-history-recurrence/)hakkında daha fazla bilgi edinin.|
|Etkinlik akışı| Çalışma durumu, başarısızlık ve bildirimler dahil olmak üzere her bir akışın etkinliklerini bir üst sınır sağlar.|
|Var|Bir [akışın](https://docs.microsoft.com/flow/get-started-logic-flow)iş akışı mantığı.|
|Bağlantının|Bağlayıcılar tarafından kullanılır ve API 'Lere, sistemlere, veritabanlarına ve daha fazlasına bağlantı sağlar. [Bağlantılar](add-manage-connections.md)hakkında daha fazla bilgi edinin.|

