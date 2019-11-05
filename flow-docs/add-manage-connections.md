---
title: Bağlantılar ve şirket içi veri ağ geçitleri kullanarak verilerinize bağlanmayı öğrenin | Microsoft Docs
description: SharePoint, SQL Server, OneDrive Iş, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drive ve diğer bağlantıları ekleyin veya yönetin
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1de8602cc573e800d721b6b70222df49cf1577e3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544764"
---
# <a name="manage-connections-in-microsoft-flow"></a>Microsoft Flow bağlantıları yönetme
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Microsoft Flow bir bağlantı oluşturursanız, akış oluştururken verilerinize kolayca erişebilirsiniz. Microsoft Flow, SharePoint, SQL Server, Office 365, OneDrive Iş, Salesforce, Excel, Dropbox, Twitter ve daha fazlasını içeren yaygın olarak kullanılan bağlantıları içerir. Bağlantılar PowerApps ile paylaşılır, bu nedenle bir üründe bir bağlantı oluşturduğunuzda, bağlantı diğer ' de görünür.

Örneğin, bu görevleri gerçekleştirmek için bir bağlantı kullanabilirsiniz:

* Bir SharePoint listesini güncelleştirin.
* OneDrive Iş veya Dropbox hesabınızda bir Excel dosyasından veri alın.
* Office 365 ' de e-posta gönderin.
* Bir tweet gönderin.

Birden çok senaryoda aşağıdaki gibi bir bağlantı oluşturabilirsiniz:

* [Şablondan akış](get-started-logic-template.md) oluşturma
* [Boş](get-started-logic-flow.md) bir akış oluşturma veya var olan bir akışı güncelleştirme
* [Microsoft Flow web sitesinde][1] doğrudan bağlantı oluşturma

Bu konuda [Microsoft Flow web sitesinde][1]bağlantıların nasıl yönetileceği gösterilmektedir.

## <a name="add-a-connection"></a>Bağlantı ekleme
1. [Microsoft Flow web sitesinde][1], iş veya kuruluş hesabınızla oturum açın.
2. Sağ üst köşedeki dişli simgesini ve ardından **Bağlantılar**' ı seçin.
   
    ![Bağlantıları seçin](./media/add-manage-connections/connections-menu.png)
3. **Bağlantı oluştur**' u seçin.
4. **Kullanılabilir bağlantılar**listesinde, kurmak istediğiniz bağlantıyı (SharePoint gibi) seçin.
5. **Bağlantı oluştur** düğmesini seçin ve ardından bağlantıyı kurmak için kimlik bilgilerinizi girin.

Bağlantı ayarlandığında **bağlantımda**listelenir.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Şirket içi veri ağ geçidi üzerinden verilerinize bağlanma
Bu yazma itibariyle, SQL Server ve SharePoint Server şirket içi veri ağ geçidini destekler. Ağ geçidi kullanan bir bağlantı oluşturmak için:

1. Bağlantı eklemek için bu konunun önceki kısımlarında bulunan adımları izleyin.
2. **Kullanılabilir bağlantılar**listesinde **SQL Server**' yi seçin ve ardından **Şirket Içi veri ağ geçidi üzerinden Bağlan** onay kutusunu seçin.
   
    ![Ağ geçidini seçin](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Microsoft SharePoint veri ağ geçitleri HTTP trafiğini destekler ancak HTTPS trafiğini desteklemez.
   > 
   > 
3. Bağlantının kimlik bilgilerini sağlayın ve ardından kullanmak istediğiniz ağ geçidini seçin.
   
    Daha fazla bilgi için bkz. [ağ geçitlerini yönetme](gateway-manage.md) ve [ağ geçitlerini anlama](gateway-reference.md).
   
    Bağlantı ayarlandığında **bağlantımda**listelenir.

## <a name="delete-a-connection"></a>Bir bağlantıyı silme
1. **Bağlantılarım** sayfasına gidin ve ardından silmek istediğiniz bağlantı için çöp kutusu simgesini seçin.
   
    ![Bağlantıyı Sil](./media/add-manage-connections/delete-connection.png)
2. Bağlantıyı silmek istediğinizi onaylamak için **Tamam ' ı** seçin.
   
    ![Silmeyi Onayla](./media/add-manage-connections/delete-confirmation.png)

Bir bağlantıyı sildiğinizde, hem PowerApps hem de Microsoft Flow kaldırılır.

## <a name="update-a-connection"></a>Bir bağlantıyı güncelleştirme
Hesap ayrıntılarınız veya parolanız değiştiğinden, çalışmayan bir bağlantıyı güncelleştirebilirsiniz.

1. **Bağlantılarım sayfasında,** güncelleştirmek istediğiniz bağlantı Için **Parolayı Doğrula** bağlantısını seçin.
   
    ![Parolayı Doğrula](./media/add-manage-connections/verify-password.png)
2. İstendiğinde, bağlantınızı yeni kimlik bilgileriyle güncelleştirin.

Bir bağlantıyı güncelleştirdiğinizde, hem PowerApps hem de Microsoft Flow için güncelleştirilir.

## <a name="troubleshoot-a-connection"></a>Bağlantı sorunlarını giderme
Kuruluşunuzun ilkelerine bağlı olarak, Microsoft Flow oturum açmak için aynı hesabı kullanmanız ve SharePoint, Office 365 veya OneDrive Iş ile bağlantı oluşturmanız gerekebilir.

Örneğin, *yourname@outlook.com* Microsoft Flow oturum açabilir ancak SharePoint 'e *yourname@contoso.com* bağlanmaya çalıştığınızda engellenir. Bunun yerine *yourname@contoso.com* Microsoft Flow için oturum açabilirsiniz ve SharePoint 'e bağlanabilirsiniz.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
