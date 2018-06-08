---
title: Bağlantılar ve şirket içi veri ağ geçitleri kullanarak verilerinize bağlanma | Microsoft Docs
description: SharePoint, SQL Server, OneDrive İş, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drive ve daha fazlası için bağlantı ekleme veya yönetme
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
ms.openlocfilehash: c0e115732e26bdeb0d7e4c3c60e1aa6c63e0ffc1
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23439785"
---
# <a name="manage-connections-in-microsoft-flow"></a>Microsoft Flow'da bağlantıları yönetme
Microsoft Flow’da bağlantı oluşturmak, akış oluştururken verilerinize kolayca erişmenizi sağlar. Microsoft Flow, yaygın olarak kullanılan bağlantıları (SharePoint, SQL Server, Office 365, OneDrive İş, Salesforce, Excel, Dropbox, Twitter ve daha fazlası) içerir. Bağlantılar PowerApps ile paylaşılır, böylece bir üründe bir bağlantı oluşturduğunuzda bu bağlantı diğer üründe görüntülenir.

Örneğin, bu görevleri gerçekleştirmek için bir bağlantı kullanabilirsiniz:

* SharePoint listesini güncelleştirme.
* OneDrive İş veya Dropbox hesabınızdaki bir Excel dosyasından veri alma.
* Office 365’te e-posta gönderme.
* Tweet gönderme.

Aşağıdakiler gibi birden fazla senaryo için bağlantı oluşturabilirsiniz:

* [Şablondan akış](get-started-logic-template.md) oluşturma
* [Boş akış](get-started-logic-flow.md) oluşturma veya var olan bir akışı güncelleştirme
* Doğrudan [Microsoft Flow web sitesinde][1] bağlantı oluşturma

Bu konuda, [Microsoft Flow web sitesindeki][1] bağlantıları nasıl yöneteceğiniz gösterilmektedir.

## <a name="add-a-connection"></a>Bağlantı ekleme
1. [Microsoft Flow web sitesinde][1] iş veya kuruluş hesabınızla oturum açın.
2. Sağ üst köşedeki dişli simgesini seçin ve sonra **Bağlantılar**’ı seçin.
   
    ![Bağlantıları seçme](./media/add-manage-connections/connections-menu.png)
3. **Bağlantı oluştur**’u seçin.
4. **Kullanılabilir bağlantılar** listesinde, ayarlamak istediğiniz bağlantıyı (SharePoint gibi) seçin.
5. **Bağlantı oluştur** düğmesini seçin ve sonra bağlantıyı ayarlamak için kimlik bilgilerinizi girin.

Bağlantı ayarlandığında **Bağlantılarım**’da listelenir.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Şirket içi veri ağ geçidi yoluyla verilerinize bağlanma
SQL Server ve SharePoint, şu andan itibaren şirket içi veri ağ geçidini desteklemektedir. Ağ geçidi kullanan bir bağlantı oluşturmak için:

1. Bağlantı eklemek için bu konu başlığında daha önceden anlatılan adımları uygulayın.
2. **Kullanılabilir bağlantılar** listesinde **SQL Server**’ı seçin ve sonra **Şirket içi veri ağ geçidi üzerinden bağlan** onay kutusunu seçin.
   
    ![Ağ geçidi seçme](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Microsoft SharePoint veri ağ geçitleri HTTP trafiğini destekler ancak HTTPS trafiğini desteklemez.
   > 
   > 
3. Bağlantının kimlik bilgilerini sağlayın ve sonra kullanmak istediğiniz ağ geçidini seçin.
   
    Daha fazla bilgi edinmek için bkz. [Ağ geçitlerini yönetme](gateway-manage.md) ve [Ağ geçitlerini anlama](gateway-reference.md).
   
    Bağlantı ayarlandığında **Bağlantılarım**’da listelenir.

## <a name="delete-a-connection"></a>Bağlantıyı silme
1. **Bağlantılarım** sayfasına gidin ve silmek istediğiniz bağlantı için çöp kutusu simgesini seçin.
   
    ![Bağlantıyı silme](./media/add-manage-connections/delete-connection.png)
2. Bağlantıyı silmek istediğinizi onaylamak için **Tamam**’ı seçin.
   
    ![Silmeyi onaylama](./media/add-manage-connections/delete-confirmation.png)

Bir bağlantıyı sildiğinizde, bağlantı hem PowerApps’ten hem de Microsoft Flow’dan kaldırılır.

## <a name="update-a-connection"></a>Bağlantı güncelleştirme
Hesabınızın ayrıntıları veya parolası değiştiği için çalışmayan bir bağlantıyı güncelleştirebilirsiniz.

1. **Bağlantılar** sayfasında, güncelleştirmek istediğiniz bağlantı için **Parolayı doğrula** bağlantısını seçin.
   
    ![Parolayı doğrulama](./media/add-manage-connections/verify-password.png)
2. İstenirse bağlantınızı yeni kimlik bilgileriyle güncelleştirin.

Bir bağlantıyı güncelleştirdiğinizde, bağlantı hem PowerApps hem de Microsoft Flow için güncelleştirilir.

## <a name="troubleshoot-a-connection"></a>Bir bağlantının sorunlarını giderme
Kuruluşunuzun ilkelerine bağlı olarak, Microsoft Flow’da oturum açarken ve SharePoint, Office 365 veya OneDrive İş’e bir bağlantı oluştururken aynı hesabı kullanmanız gerekebilir.

Örneğin, Microsoft Flow’da *yourname@outlook.com* ile oturum açabilir ancak *yourname@contoso.com* ile SharePoint’e bağlanmayı denediğinizde engellenebilirsiniz. Bunun yerine *yourname@contoso.com* ile Microsoft Flow’da oturum açarak SharePoint’e bağlanabilirsiniz.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
