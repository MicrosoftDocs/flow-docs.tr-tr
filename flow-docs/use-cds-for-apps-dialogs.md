---
title: Kılavuzlu işlemler için Common Data Service iletişim kutularını kullanma (Kullanım Dışı) | Microsoft Docs
description: İletişim kutuları, bir işlem boyunca kullanıcıları yönlendirmek için adım adım betikleri kullanarak bilgi toplayan ve işleyen eş zamanlı veya etkileşimli işlemlerdir.
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
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
ms.openlocfilehash: 90bdbc0ecf9b778ec6da3e4cac2b32b44e361fb0
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64463650"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Kılavuzlu işlemler için Common Data Service iletişim kutularını kullanma (Kullanım Dışı)

[İletişim kutuları kullanım dışı bırakılmıştır](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). İletişim kutularını, iş süreci akışları veya tuval uygulamalarıyla değiştirmelisiniz. Daha fazla bilgi: [İletişim kutularını iş süreci akışları veya tuval uygulamalarıyla değiştirme](replace-dialogs.md) 

İletişim kutuları, bir işlem boyunca kullanıcıları yönlendirmek için adım adım betikleri kullanarak bilgi toplayan ve işleyen Common Data Service uygulamasındaki zamanlı uyumlu veya etkileşimli işlemlerdir. Örneğin, servis talebi çözümü ve servis talebi yükseltme için hizmet temsilcilerinize yönelik bir kılavuz olarak hareket etmesi için iletişim kutuları oluşturabilirsiniz. Benzer şekilde, fırsat nitelendirmesi ve müşteri adayı puanlaması gibi satış işlemlerini standartlaştırmak için de iletişim kutuları oluşturabilirsiniz. Daha fazla bilgi için Dynamics 365 Customer Engagement Geliştirici Kılavuzu’nda [Kılavuzlu işlemler için iletişim kutularını kullanma](/dynamics365/customer-engagement/developer/use-dialogs-guided-processes) bölümüne bakın.

## <a name="differences-between-workflows-and-dialogs"></a>İş akışları ile iletişim kutuları arasındaki farklar

Aşağıdaki tabloda, Common Data Service iş akışları ile iletişim kutuları arasındaki farklarla ilgili bilgi sağlanmaktadır.  


| İş Akışları     |    İletişim Kutuları      |
|---------------|--------------|
|                                                                                                  Bir kullanıcı tarafından başlatılabilir veya otomatikleştirilebilir.                                                                                                   |                                                                                          Bir kullanıcı tarafından başlatılmalıdır.                                                                                          |
|                                  Zaman uyumsuz veya gerçek zamanlı işlemlerdir ve tamamlanıncaya kadar çalışması için kullanıcı girişi gerekmez. Gerçek zamanlı işlemler anında çalıştırılırken, zaman uyumsuz süreçler ise arka planda çalıştırılır.                                   | Tamamlanıncaya kadar çalışması için kullanıcı girişi gerektiren gerçek zamanlı işlemlerdir. Bu işlemleri çalıştırdığınızda, işlemleri çalıştırmak için uygun seçimleri yapabilmeniz için size sihirbaza benzer bir arabirim sunulur. |
|                                                    Zaman uyumsuz iş akışını çalıştırmaya yönelik ayrıntıları depolayan varlık `AsyncOperation` iken, gerçek zamanlı iş akışı için `Process` kullanılır.                                                     |                                                       Çalıştırılan bir iletişim kutusu tarafından oluşturulan bilgileri depolayan varlık, `ProcessSession` varlığıdır.                                                       |
|                  İş akışları için tetikleyiciler desteklenir. Desteklenen tetikleyicilerin listesi için bkz. [İşlemler için Desteklenen Türler, Tetikleyiciler ve Varlıklar](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   İletişim kutuları için tetikleyiciler desteklenmez.                                                                                    |
  
### <a name="see-also"></a>Ayrıca bkz.
[İletişim kutularını iş süreci akışları veya tuval uygulamalarıyla değiştirme](replace-dialogs.md)
