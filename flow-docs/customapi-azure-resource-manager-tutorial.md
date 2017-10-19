---
title: "Azure Active Directory’yi özel bağlayıcıyla kullanma | Microsoft Docs"
description: "Azure Active Directory kimlik doğrulamasıyla Azure Resource Manager için özel bağlayıcı oluşturmayı öğrenin."
services: 
suite: flow
documentationcenter: 
author: msftman
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/03/2016
ms.author: deonhe
ms.openlocfilehash: d98a3505ab7d667f5a64eed9a23041efec95b1d7
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="use-azure-active-directory-with-a-custom-connector-in-microsoft-flow"></a>Microsoft Flow’da Azure Active Directory’yi özel bağlayıcıyla kullanma
Azure Resource Manager (ARM), Azure’da bir çözümün bileşenlerini (veritabanları, sanal makineler ve web uygulamaları gibi bileşenler) yönetmenize olanak tanır. Bu öğreticide Azure Active Directory’de kimlik doğrulamasını etkinleştirme, ARM API’lerinden birini özel bağlayıcı olarak kaydetme ve sonra da bunu Microsoft Flow’a bağlama işlemleri gösterilir. Azure kaynaklarını bir akışın parçası olarak yönetmek istediğinizde, bu kullanışlı olabilir. ARM hakkında daha fazla bilgi için bkz. [Azure Resource Manager’a Genel Bakış](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).

## <a name="prerequisites"></a>Önkoşullar
* Bir [Azure aboneliği](https://azure.microsoft.com/free/).
* Bir [Microsoft Flow hesabı](https://flow.microsoft.com).
* Bu öğreticide kullanılan [örnek OpenAPI dosyası](http://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json).

## <a name="enable-authentication-in-azure-active-directory"></a>Azure Active Directory’de kimlik doğrulamasını etkinleştirme
İlk olarak, ARM API uç noktasını çağırırken kimlik doğrulamasını gerçekleştirecek bir Azure Active Directory (AAD) uygulaması oluşturmanız gerekir.

1. [Azure portalında](https://portal.azure.com) oturum açın.  Birden fazla Azure Active Directory kiracınız varsa sağ üst köşedeki kullanıcı adınıza bakarak doğru dizinde oturum açtığınızdan emin olun.
   
    ![Kullanıcı Adı](./media/customapi-azure-resource-manager-tutorial/current-user.png)
2. Soldaki menüde **Diğer hizmetler**’e tıklayın.  **Filtre** metin kutusuna **Azure Active Directory** yazın ve ardından **Azure Active Directory**’ye tıklayın.
   
    ![Azure Active Directory](./media/customapi-azure-resource-manager-tutorial/azureaad.png)
   
    Azure Active Directory dikey penceresi açılır.   
3. Azure Active Directory dikey penceresindeki menüde **Uygulama kayıtları**’na tıklayın.
   
    ![Uygulama kayıtları](./media/customapi-azure-resource-manager-tutorial/azureapplication.png)
4. Kayıtlı uygulamalar listesinde **Ekle**’ye tıklayın.
   
    ![Ekle düğmesi](./media/customapi-azure-resource-manager-tutorial/add-app-btn.png)   
5. Uygulamanız için bir ad girin, **Web uygulaması / API** seçeneğini işaretli durumda bırakın ve sonra **Oturum Açma URL’si** için `https://login.windows.net` yazın.  **Oluştur**’a tıklayın.  
   
    ![Yeni uygulama formu](./media/customapi-azure-resource-manager-tutorial/newapplication.png)
6. Listede yeni uygulamaya tıklayın.
   
    ![Listede yeni uygulama](./media/customapi-azure-resource-manager-tutorial/newapplication2.png)
   
    Kayıtlı uygulama dikey penceresi açılır.  **Uygulama Kimliği**’ni not alın.  Daha sonra gerekli olacaktır.
7. Ayarlar dikey penceresi de açılmış olmalıdır.  Açılmadıysa **Ayarlar** düğmesine tıklayın.
   
    ![Ayarlar düğmesi](./media/customapi-azure-resource-manager-tutorial/settings-btn.png)
8. Ayarlar dikey penceresinde **Yanıt URL'leri** öğesine tıklayın. URL listesine `https://msmanaged-na.consent.azure-apim.net/redirect` öğesini ekleyin ve **Kaydet**’e tıklayın.
   
    ![Yanıt URL'leri](./media/customapi-azure-resource-manager-tutorial/reply-urls.png)
9. Ayarlar dikey penceresine geri dönüp **Gerekli izinler**’e tıklayın.  Gerekli izinler dikey penceresinde **Ekle**’ye tıklayın.
   
    ![Gerekli izinler](./media/customapi-azure-resource-manager-tutorial/permissions.png)
   
    API erişimi ekle dikey penceresi açılır.
10. **API seçin**’e tıklayın. Açılan dikey pencerede Azure Hizmet Yönetim API'si ile ilgili seçeneğe ve **Seç**’e tıklayın.
    
    ![API seçme](./media/customapi-azure-resource-manager-tutorial/permissions2.png)
11. **İzinleri seç**’e tıklayın.  *Temsilci izinleri* altında **Azure Hizmet Yönetimine kuruluş kullanıcıları olarak erişim** ve ardından **Seç**’e tıklayın.
    
    ![Temsilci izinleri](./media/customapi-azure-resource-manager-tutorial/permissions3.png)
12. API erişimi ekle dikey penceresinde **Bitti**’ye tıklayın.
13. Ayarlar dikey penceresine geri dönerek **Anahtarlar**’a tıklayın.  Anahtarlar dikey penceresinde anahtarınız için bir açıklama yazın, sona erme süresini seçin ve ardından **Kaydet**’e tıklayın.  Yeni anahtarınız görüntülenir.  Anahtar değerini not edin; bu da daha sonra gerekli olacak.  Azure portalını artık kapatabilirsiniz.
    
    ![Anahtar oluşturma](./media/customapi-azure-resource-manager-tutorial/configurekeys.png)

## <a name="add-the-connection-in-microsoft-flow"></a>Microsoft Flow'da bağlantı ekleme
Artık AAD uygulaması yapılandırıldığına göre, şimdi de özel bağlayıcıyı ekleyelim.

1. [Microsoft Flow web uygulamasında](https://flow.microsoft.com/) sayfanın sağ üst köşesindeki **Ayarlar** düğmesine tıklayın (dişli simgesiyle gösterilmiştir).  Ardından, **özel bağlayıcılara** tıklayın.
   
    ![Özel bağlayıcıları bulma](./media/customapi-azure-resource-manager-tutorial/finding-custom-apis.png)  
2. **Özel bağlayıcı oluştur**’a tıklayın.  
   
    API'nizin özellikleri sorulur.  
   
   | Özellik | Açıklama |
   | --- | --- |
   | Ad |Sayfanın üst kısmındaki **Adsız**’a tıklayın ve akışınıza bir ad verin. |
   | OpenAPI dosyası |[Örnek ARM OpenAPI dosyasına](http://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json) göz atın. |
   | API simgesini karşıya yükleme |Simge için bir görüntü dosyası seçmek üzere **Karşıya Yükleme simgesine** tıklayın. Boyutu 1 MB’den az olan herhangi bir PNG veya JPG dosyasını kullanabilirsiniz. |
   | Açıklama |Özel bağlayıcınızın açıklamasını yazın (isteğe bağlı). |
   
    ![Özel bağlayıcı oluşturma](./media/customapi-azure-resource-manager-tutorial/create-custom-api.png)  
   
    **Devam**’ı seçin.
3. OpenAPI dosyası kimlik doğrulaması için AAD uygulamamızı kullandığından, sonraki ekranda Flow’a uygulamamız hakkında bazı bilgiler vermemiz gerekiyor.  **İstemci kimliği** altında daha önce not aldığınız AAD **Uygulama Kimliğini** girin.  İstemci parolası için **anahtarı** kullanın.  Son olarak da **Kaynak URL’si** için `https://management.core.windows.net/` yazın.
   
   > [!IMPORTANT]
   > Kaynak URL’sini tam olarak yukarıdaki gibi sondaki eğik çizgiyle birlikte eklediğinizden emin olun.
   > 
   > 
   
    ![OAuth ayarları](./media/customapi-azure-resource-manager-tutorial/oauth-settings.png)
   
    Güvenlik bilgilerini girdikten sonra, sayfanın en üstünde yer alan akış adının yanındaki onay işaretine (**&#x2713;**) tıklayarak özel bağlayıcıyı oluşturun.
4. Özel bağlayıcınız artık **özel bağlayıcılar** altında gösterilir.
   
    ![Kullanılabilir API'ler](./media/customapi-azure-resource-manager-tutorial/list-custom-apis.png)  
5. Artık özel bağlayıcı kaydedildiğinden, uygulamalarınızda ve akışlarınızda kullanılabilmesi için bu özel bağlayıcıya bir bağlantı oluşturmalısınız.  Özel bağlayıcınızın adının sağındaki **+** öğesine tıklayın ve ardından oturum açma ekranını tamamlayın.

> [!NOTE]
> Örnek OpenAPI ARM işlemlerinin tümünü tanımlamaz ve şu anda yalnızca [Tüm abonelikleri listele](https://msdn.microsoft.com/library/azure/dn790531.aspx) işlemini içerir.  Bu OpenAPI dosyasını düzenleyebilir veya [çevrimiçi OpenAPI düzenleyicisini](http://editor.swagger.io/) kullanarak başka bir OpenAPI dosyası oluşturabilirsiniz.
> 
> Bu işlem AAD kullanılarak kimliği doğrulanmış herhangi bir RESTful API’sine erişim için kullanılabilir.
> 
> 

## <a name="next-steps"></a>Sonraki adımlar
Akış oluşturma hakkında daha ayrıntılı bilgi için bkz. [Microsoft Flow ile oluşturmaya başlama](get-started-logic-flow.md).

Özel bağlayıcılar hakkında soru sormak veya yorumda bulunmak için [topluluğumuza katılın](https://aka.ms/flow-community).

