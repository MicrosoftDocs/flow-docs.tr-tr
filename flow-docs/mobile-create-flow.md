---
title: "Telefonunuzdan akış oluşturma | Microsoft Docs"
description: "Şablon kullanarak, belirttiğiniz bir adresten e-posta aldığınızda anında iletme bildirimi gönderen bir akış oluşturma"
services: 
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2016
ms.author: adiregev
ms.openlocfilehash: 27a2001e3fa154f9354ef5ad888e194f30b3d6ab
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>Microsoft Flow kullanarak telefonunuzdan akış oluşturma
Hizmetler listesinde arayarak, kategorilere göz atarak veya anahtar sözcükler belirterek bulabileceğiniz bir şablon kullanarak telefonunuzdan akış oluşturun. Bu konu başlığındaki adımları uygulayarak, yöneticinizden e-posta aldığınızda telefonunuza anında iletme bildirimi gönderen bir akış oluşturun.

Daha önce Microsoft Flow kullanmadıysanız [genel bakış edinin](getting-started.md).

## <a name="prerequisites"></a>Önkoşullar
* Bir [Microsoft Flow hesabı](sign-up-sign-in.md).
* [Desteklenen bir cihazda](getting-started.md#use-the-mobile-app) [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) veya [Windows Phone](https://aka.ms/flowmobilewindows) için Microsoft Flow mobil uygulaması. Bu konu başlığında kullanılan grafikler, uygulamanın iPhone sürümünden alınmıştır ancak Android cihazları ve Windows Phone için de benzer bir arabirim sunulur.
* Bu konu başlığında gösterilen şablonu kullanmak için ayrıca şunlar gerekir:
  
  * Office 365 kimlik bilgileri.
  * Telefonunuzda etkinleştirilmiş anında iletme bildirimleri.

## <a name="find-a-template"></a>Şablon bulma
1. Mobil uygulamayı açın ve ekranın altındaki **Gözat** düğmesine dokunun.
   
    ![Gözat simgesi](./media/mobile-create-flow/browse-icon.png)
   
    Şu adımlardan herhangi birini uygulayarak şablon bulabilirsiniz:
   
   * Ekranın üstündeki arama kutusunda bir anahtar sözcük belirtin.
   * Hizmetler listesindeki bir seçeneğe dokunun.
   * Çeşitli kategorileri göstermek için aşağı kaydırın ve herhangi bir kategorideki bir şablona dokunun.
     
       ![Gözat sekmesi](./media/mobile-create-flow/browse-tab.png)
     
     Bu öğreticide, yöneticinizden e-posta aldığınızda anında iletme bildirimi gönderen şablonu açacaksınız.
2. Hizmetler listesinde, **Tümünü göster**'e dokunun.
   
    ![Hizmetler listesini gösterme](./media/mobile-create-flow/list-services.png)
3. **Anında iletme bildirimi** simgesine dokunun.
   
    ![Anında iletme bildirimleri](./media/mobile-create-flow/push-notifications.png)
4. Arama çubuğuna **e-posta** yazın ve ardından yöneticinizden bir ileti aldığınızda anında iletme bildirimi gönderecek şablona dokunun.
   
    ![Şablon seçme](./media/mobile-create-flow/choose-template.png)
5. Seçtiğiniz şablonla ilgili ayrıntıların bulunduğu ekranda, **Bu şablonu kullan**'a dokunun.
   
    ![Şablonu onaylama](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Akışı sonlandırma
1. İstenirse **Oturum aç**'a dokunup Office 365 Outlook, Office 365 Kullanıcıları veya her ikisi için kullandığınız kimlik bilgilerinizi sağlayın.
   
    ![Office 365'te oturum açma](./media/mobile-create-flow/office-signin.png)
   
    Aynı bağlantıları, başka akışlar oluşturduğunuzda da kullanabilirsiniz.
2. Sağ üst köşede bulunan **İleri**'ye dokunun.
   
    ![İleri'ye dokunun](./media/mobile-create-flow/next.png)
   
    Sonraki ekranda, tetikleyici olayı ve sonucunda oluşan tüm eylemler gösterilir.
   
    ![Tetikleyici olay ve eylemler](./media/mobile-create-flow/flow-structure.png)
   
    Bu şablonda, yeni e-posta akışı tetiklenerek (yöneticinizin adresini de içeren) bilgileriniz alınır ve bu adresten e-posta aldığınızda size bir anında iletme bildirimi gönderilir. Bazı şablonların düzgün şekilde çalışması için bir takım özelleştirmeler gerekir ancak bu şablonda bunlara gerek yoktur.
3. (isteğe bağlı) Ekranın üst kısmına akış için farklı bir ad yazın.
   
    ![Akışı yeniden adlandırma](./media/mobile-create-flow/rename-flow.png)
4. Sağ üst köşedeki **Oluştur** düğmesine dokunun.
   
    ![Akış oluşturma](./media/mobile-create-flow/create-flow.png)
   
    Akışınız oluşturuldu ve siz akışı durdurana veya silene kadar yöneticinizden gelen e-postaları denetleyecek.

## <a name="next-steps"></a>Sonraki adımlar
* [Akış etkinliğinizi izleme](mobile-monitor-activity.md).
* [Akışlarınızı yönetme](mobile-manage-flows.md).

