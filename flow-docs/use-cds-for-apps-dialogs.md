---
title: Kılavuzlu süreçler için Common Data Service iletişim kutularını kullan (kullanım dışı) | MicrosoftDocs
description: İletişim kutuları, kullanıcıları bir işlem üzerinden yönlendirmek için adım adım betikleri kullanarak bilgileri toplayıp işleyen zaman uyumlu veya etkileşimli işlemlerdir.
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.service: flow
ms.assetid: d17f8ae2-854b-4f67-a115-5a03d4f0b8ce
caps.latest.revision: 25
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 05f0b9b72f2f9e2d7f02356ec40eeb520214a0cb
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548755"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Kılavuzlu süreçler için Common Data Service iletişimleri kullanma (kullanım dışı)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

[Iletişim kutuları kullanım dışı bırakılmıştır](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). İletişim kutularını iş süreci akışları veya tuval uygulamaları ile değiştirmelisiniz. Daha fazla bilgi: [iletişim kutularını iş süreci akışlarıyla veya tuval uygulamalarıyla değiştirin](replace-dialogs.md) 

İletişim kutuları, kullanıcıları bir işlem üzerinden yönlendirmek için adım adım betikleri kullanarak bilgi toplayıp işleyen Common Data Service zaman uyumlu veya etkileşimli işlemlerdir. Örneğin, servis temsilcileriniz için büyük/küçük/küçük harf yükseltme için bir kılavuz olarak davranacak iletişim kutuları oluşturabilirsiniz. Benzer şekilde, fırsat niteliği ve müşteri adayı puanlama gibi satış süreçlerini standartlaştırmaya yönelik iletişim kutuları da oluşturabilirsiniz.

## <a name="differences-between-workflows-and-dialogs"></a>İş akışları ve iletişim kutuları arasındaki farklar

Aşağıdaki tabloda Common Data Service iş akışları ve iletişim kutuları arasındaki farklılıklar hakkında bilgi verilmektedir.  


| sürdürülen     |    İletişimlerinin      |
|---------------|--------------|
|                                                                                                  , Bir kullanıcı tarafından başlatılabilir veya otomatikleştirilebilir.                                                                                                   |                                                                                          Bir kullanıcı tarafından başlatılmış olmalıdır.                                                                                          |
|                                  Zaman uyumsuz veya gerçek zamanlı işlemlerdir ve Kullanıcı girişinin tamamlanmasını gerektirmez. Zaman uyumsuz süreçler, gerçek zamanlı süreçler hemen çalıştırılırken arka planda çalışır.                                   | , Kullanıcı girişinin tamamlanmasını gerektiren gerçek zamanlı süreçlerdir. Bu süreçler çalıştırıldığında, işlem çalıştırmak için uygun seçimler yapabilmeniz için bir sihirbaz benzeri arabirim size sunulur. |
|                                                    Çalışan bir zaman uyumsuz iş akışı hakkındaki ayrıntıları depolayan varlık, bir `Process` gerçek zamanlı bir iş akışı için kullanıldığında `AsyncOperation`.                                                     |                                                       Çalışan bir iletişim kutusu tarafından oluşturulan bilgileri depolayan varlık `ProcessSession` varlıktır.                                                       |
|                  Tetikleyiciler, iş akışları için desteklenir. Desteklenen tetikleyicilerin listesi için bkz. [desteklenen türler, Tetikleyiciler ve süreçler Için varlıklar](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   İletişim kutuları için Tetikleyiciler desteklenmez.                                                                                    |
  
### <a name="see-also"></a>Ayrıca bkz.
[İletişim kutularını iş süreci akışlarıyla veya tuval uygulamalarıyla değiştirin](replace-dialogs.md)
