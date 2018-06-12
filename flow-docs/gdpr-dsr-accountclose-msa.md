---
title: Microsoft Hesapları (MSA) için Microsoft Flow GDPR Veri Sahibi Hesap Kapatma İstekleri | Microsoft Docs
description: Microsoft Flow’u kullanarak Microsoft Hesapları için GDPR Veri Sahibi Hesap Kapatma İsteklerini yanıtlamayı öğrenin.
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
ms.date: 5/25/2018
ms.author: keweare
ms.openlocfilehash: 268e6039b4f2dbb43522fd07b1120d8c4256e9af
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34563269"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>Microsoft Flow için GDPR Veri Sahibi Hesap Kapatma İsteklerini yanıtlama

Kişisel verileri **silme hakkı**, GDPR’de önemli bir korunma yöntemidir. Bu hak, denetim günlüğü bilgileri dışında tüm kişisel verilerin kaldırılmasını kapsar. Bir kullanıcı, Microsoft Hesabını (MSA) kapatmaya karar verdiğinde kullanıcının temel alınan verileri de silinir.

Bu kaynaklar, bir kullanıcı MSA’yı kapattığında otomatik olarak silinen kişisel veriler içeriyor:

|Kişisel verileri kapsayan kaynaklar|
|------|
|Ürün ve hizmet etkinliği|
|Çalıştırma geçmişi|
|Akışlar|
|Etkinlik Akışı|
|Kullanıcı ayrıntıları|
|Bağlantılar|

## <a name="account-close-requests"></a>Hesap Kapatma istekleri

Bu adımlarda, GDPR için Hesap Kapatma isteklerine nasıl self servis sunulacağı açıklanmaktadır.

1. Microsoft Hesabınızı kullanarak [Microsoft Hesap Kapatma Portalı](http://go.microsoft.com/fwlink/?LinkId=523898)’nda oturum açın ve **İleri**’yi seçin.

    > [!NOTE]
    > Mevcut abonelikleri iptal etmeniz ve abone olmuş olabileceğiniz mevcut hizmetlerden verileri dışarı aktarmanız hatırlatılır.
    >
    >

    ![Abonelikleri iptal etme](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Yönetilen hizmet hesabınızı kapatmanın oluşturacağı etkiyi anladığınızı kabul edin ve sonra **Hesabı kapatılmak üzere işaretle** seçeneğini belirleyin.

    Hesabınızın 30 gün içinde kapatılacağını belirten bir bildirim görüntülenir. Bu 30 günlük süre boyunca herhangi bir zamanda bu hesabı yeniden açabilirsiniz.

    ![Hesap Kapatıldı](./media/gdpr-dsr-delete-msa/accountclosed.png)

    Bu 30 günlük süre sonunda bu MSA için tüm Microsoft Flow kaynaklarını silme işlemi başlar.

## <a name="learn-more"></a>Daha fazla bilgi

* [Microsoft Flow](getting-started.md) ile çalışmaya başlama
* Microsoft Flow ile ilgili [yenilikleri](release-notes.md) öğrenin
