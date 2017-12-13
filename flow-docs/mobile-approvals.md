---
title: Mobil cihazdan istekleri onaylama | Microsoft Docs
description: "Microsoft Flow’da oluşturulan istekleri onaylamak için bir mobil cihaz kullanın."
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
ms.date: 07/20/2017
ms.author: deonhe
ms.openlocfilehash: 18546c044dc823d703544c48f5cda76a3581e99f
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>Microsoft Flow ile mobil cihazınızdan istekleri onaylayın
Bir akış, sizi onaylayan olarak tanımlıyorsa ve Microsoft Flow için mobil uygulamayı yüklediyseniz, onayınız gerektiğinde bir anında iletme bildirimi alırsınız.

Bu makalede Microsoft Flow için mobil uygulamada onay isteklerini yönettiğiniz sırada karşılaşabileceğiniz bazı yaygın senaryolar açıklanmaktadır.

> [!NOTE]
> Bu konu başlığındaki resimler bir Android cihazdan alınmıştır, ancak iOS’taki süreç de bununla benzerlik göstermektedir.
> 
> 

## <a name="prerequisites"></a>Önkoşullar
İzlenecek yolu tamamlamanız için şunlara ihtiyaç duyarsınız:

* Microsoft Flow mobil uygulamasını çalıştıran bir [Android](https://aka.ms/flowmobiledocsandroid) veya [iOS](https://aka.ms/flowmobiledocsios) cihaz.
* Bir onay akışında onaylayan olarak belirlenmek.
* Onay bekleyen istekler.

## <a name="view-pending-requests"></a>Bekleyen istekleri görüntüleme
1. Microsoft Flow mobil uygulamasını açın.
   
    ![mobil uygulamayı başlatma](./media/mobile-approvals/open-app.png)
2. Sağ üst köşeden **ONAYLAR** seçeneğini belirleyin.
   
    ![onayları seçme](./media/mobile-approvals/select-approvals.png)
3. Bekleyen tüm onayları görüntüleyin:
   
    ![bekleyen onay isteklerini görüntüleme](./media/mobile-approvals/show-pending-approval-requests.png)

Bekleyen onay isteği yoksa, bir [onay akışı](modern-approvals.md) oluşturup kendinizi onaylayan olarak belirleyin ve akışı tetikleyin. Akış tetiklendikten ve onay isteği gönderdikten birkaç saniye sonra onay istekleri, onay merkezinde görünür.

## <a name="approve-requests-and-leave-an-optional-comment"></a>İstekleri onaylama ve isteğe bağlı bir açıklama bırakma
1. Böyle yapmadıysanız, [bekleyen tüm onay isteklerini görüntülemek](mobile-approvals.md#view-pending-approval-requests) için önceki adımları takip edin.
2. Onaylamak istediğiniz istekte **ONAYLA** seçeneğini belirleyin.
   
    ![onayla seçeneğini belirleme](./media/mobile-approvals/select-approve.png)
3. **Açıklama ekle (isteğe bağlı)**  seçeneğini belirleyin (isteğe bağlı).
   
    ![açıklama ekle seçeneğini belirleme](./media/mobile-approvals/select-add-comment.png)
   
    **Açıklama ekle** ekranına bir açıklama girin.
   
    ![açıklamanızı girme](./media/mobile-approvals/enter-comment-for-approval.png)
4. Sağ üst köşeden **ONAYLA** seçeneğini belirleyin.
   
    ![işiniz bittiğinde onaylama](./media/mobile-approvals/tap-confirm-button.png)
   
    Akış, kararınızı kayıt altına aldıktan sonra işlem başarılı ekranı görüntülenir.
   
    ![işlem başarılı ekranı](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>İstekleri reddetme ve isteğe bağlı bir açıklama bırakma
[Bir isteği onaylama adımları](mobile-approvals.md#approve-requests-and-leave-an-optional-comment)nı takip edin, ancak ikinci adımda **REDDET** seçeneğini belirleyin.

## <a name="learn-more"></a>Daha fazla bilgi
[Modern onay akışları oluşturma](modern-approvals.md).
