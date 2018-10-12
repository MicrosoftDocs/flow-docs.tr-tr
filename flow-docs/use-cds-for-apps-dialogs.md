---
title: Kılavuzlu işlemler için Uygulamalar için CDS iletişim kutularını kullanma (Kullanım Dışı) | Microsoft Docs
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
ms.openlocfilehash: f8b2e87bdb9aed63e9f180d446349779cd37c25c
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689675"
---
# <a name="use-cds-for-apps-dialogs-for-guided-processes-deprecated"></a>Kılavuzlu işlemler için Uygulamalar için CDS iletişim kutularını kullanma (Kullanım Dışı)

[İletişim kutuları kullanım dışı bırakılmıştır](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). İletişim kutularını, iş süreci akışları veya tuval uygulamalarıyla değiştirmelisiniz. Daha fazla bilgi: [İletişim kutularını, iş süreci akışları veya tuval uygulamalarıyla değiştirme](replace-dialogs.md) 

İletişim kutuları, bir işlem boyunca kullanıcıları yönlendirmek için adım adım betikleri kullanarak bilgi toplayan ve işleyen Uygulamalar için Common Data Service (CDS) uygulamasındaki eş zamanlı veya etkileşimli işlemlerdir. Örneğin, servis talebi çözümü ve servis talebi yükseltme için hizmet temsilcilerinize yönelik bir kılavuz olarak hareket etmesi için iletişim kutuları oluşturabilirsiniz. Benzer şekilde, fırsat nitelendirmesi ve müşteri adayı puanlaması gibi satış işlemlerini standartlaştırmak için de iletişim kutuları oluşturabilirsiniz. Daha fazla bilgi için Dynamics 365 Customer Engagement Geliştirici Kılavuzu’nda [Kılavuzlu işlemler için iletişim kutularını kullanma](/dynamics365/customer-engagement/developer/use-dialogs-guided-processes) bölümüne bakın.

## <a name="differences-between-workflows-and-dialogs"></a>İş akışları ile iletişim kutuları arasındaki farklar

Aşağıdaki tabloda, Uygulamalar için CDS iş akışları ile iletişim kutuları arasındaki farklarla ilgili bilgi sağlanmaktadır.  


| İş Akışları     |    İletişim Kutuları      |
|---------------|--------------|
|                                                                                                  Bir kullanıcı tarafından başlatılabilir veya otomatikleştirilebilir.                                                                                                   |                                                                                          Bir kullanıcı tarafından başlatılmalıdır.                                                                                          |
|                                  Zaman uyumsuz veya gerçek zamanlı işlemlerdir ve tamamlanıncaya kadar çalışması için kullanıcı girişi gerekmez. Gerçek zamanlı işlemler anında çalıştırılırken, zaman uyumsuz süreçler ise arka planda çalıştırılır.                                   | Tamamlanıncaya kadar çalışması için kullanıcı girişi gerektiren gerçek zamanlı işlemlerdir. Bu işlemleri çalıştırdığınızda, işlemleri çalıştırmak için uygun seçimleri yapabilmeniz için size sihirbaza benzer bir arabirim sunulur. |
|                                                    Zaman uyumsuz iş akışını çalıştırmaya yönelik ayrıntıları depolayan varlık `AsyncOperation` iken, gerçek zamanlı iş akışı için `Process` kullanılır.                                                     |                                                       Çalıştırılan bir iletişim kutusu tarafından oluşturulan bilgileri depolayan varlık, `ProcessSession` varlığıdır.                                                       |
|                  İş akışları için tetikleyiciler desteklenir. Desteklenen tetikleyicilerin listesi için bkz. [İşlemler için Desteklenen Türler, Tetikleyiciler ve Varlıklar](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   İletişim kutuları için tetikleyiciler desteklenmez.                                                                                    |
  
### <a name="see-also"></a>Ayrıca bkz.
[İletişim kutularını iş süreci akışları veya tuval uygulamalarıyla değiştirme](replace-dialogs.md)
