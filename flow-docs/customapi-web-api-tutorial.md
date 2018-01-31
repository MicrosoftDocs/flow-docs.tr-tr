---
title: "Web API’si için özel bağlayıcı oluşturma | Microsoft Docs"
description: "Microsoft Flow’da Azure Active Directory kimlik doğrulamasıyla ASP.NET Web API’si oluşturmayı öğrenin."
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2016
ms.author: sunayv
ms.openlocfilehash: fef904b02d4b0f028edba236b73e19155b6f4919
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="build-a-custom-connector-for-a-web-api-in-microsoft-flow"></a>Microsoft Flow’da Web API’si için özel bağlayıcı oluşturma
Bu öğreticide, ASP.NET Web API’si oluşturmaya başlama, bunu Azure Web Apps’te barındırma, Azure Active Directory kimlik doğrulamasını etkinleştirme ve ardından ASP.NET Web API’yi Microsoft Flow’da kaydetme işlemleri gösterilir. API kaydedildikten sonra, bu API’ye bağlanabilir ve akışınızdan bunu çağırabilirsiniz. 

## <a name="prerequisites"></a>Önkoşullar
* Bir [Azure aboneliği](https://azure.microsoft.com/free/).
* Bir [PowerApps hesabı](https://powerapps.microsoft.com).
* [Visual Studio](https://www.visualstudio.com/vs/) 2013 veya üzeri.

## <a name="create-an-aspnet-web-api-and-deploy-it-to-azure"></a>ASP.NET Web API’si oluşturma ve Azure'a dağıtma
1. Visual Studio'da **Dosya** > **Yeni Proje**’ye tıklayarak yeni bir C# ASP.NET web uygulaması oluşturun.
   
    ![Yeni Web Uygulaması](./media/customapi-web-api-tutorial/newwebapp.png)
2. **Web API** şablonunu seçin.  **Bulutta barındır** seçeneğini işaretli bırakın.  **Kimlik Doğrulamasını Değiştir**’e tıklayın.
   
    ![Yeni Web Projesi Şablonu](./media/customapi-web-api-tutorial/new-web-api.png)
3. **Kimlik Doğrulaması Yok** ve ardından **Tamam**’a tıklayın.
   
    ![Kimlik Doğrulaması Yok](./media/customapi-web-api-tutorial/noauth.png)
4. **Yeni ASP.NET Projesi** iletişim kutusunda **Tamam**’a tıklayın.  Microsoft Azure Web Uygulamasını Yapılandır iletişim kutusu görüntülenir.
   
    ![Microsoft Azure Web uygulamasını yapılandırma](./media/customapi-web-api-tutorial/azure-publishing.png)]
   
    Azure hesabınızı seçin, bir **Web Uygulaması adı** yazın (veya varsayılanı değiştirmeyin) ve Azure **Aboneliğinizi** seçin.  Bir **App Service planı** (aboneliğinizdeki Web Uygulamalarının koleksiyonu) seçin veya oluşturun.  Bir **Kaynak grubu** (aboneliğinizdeki Azure kaynaklarının grubu) seçin veya oluşturun.  Web Uygulamasının dağıtılacağı bölgeyi seçin.  Web API’niz için gerekirse bir Azure **Veritabanı sunucusu** seçin veya oluşturun.  Son olarak, **Tamam**’a tıklayın.
5. Web API’nizi oluşturun.
   
   > [!NOTE]
   > Henüz Web API’si için hazır kodunuz yoksa, [ASP.NET Web API 2 (C#) ile Çalışmaya Başlama](https://www.asp.net/web-api/overview/getting-started-with-aspnet-web-api/tutorial-your-first-web-api) öğreticisini deneyin.
   > 
   > 
6. Web API’nizi PowerApps’e bağlamak için işlemlerini açıklayan bir [Swagger](http://swagger.io/) dosyası gerekir.  [Çevrimiçi düzenleyiciyi](http://editor.swagger.io/) kullanarak kendiniz bir OpenAPI yazabilirsiniz, ama bu öğreticide [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle/blob/master/README.md) adlı bir açık kaynak aracı kullanacaksınız.  **Araçlar** > **NuGet Paket Yöneticisi** > **Paket Yöneticisi Konsolu**’na tıklayarak Visual Studio projenize Swashbuckle Nuget paketini yükleyin, ardından Paket Yöneticisi Konsolu’nda `Install-Package Swashbuckle` komutunu yazın.
   
    ![Install-Package Swashbuckle](./media/customapi-web-api-tutorial/swashbuckle-console.png)
   
   > [!TIP]
   > Swashbuckle’ı yükledikten sonra Web API uygulamasını çalıştırdığınızda, `http://<your root URL>/swagger/docs/v1` URL’sinde bir OpenAPI dosyası oluşturulur.  `http://<your root URL>/swagger` adresinde, oluşturulmuş bir kullanıcı arabirimi de mevcuttur.
   > 
   > 
7. Web API'niz hazır olduğunda Azure’da yayımlayın. Visual Studio’dan yayımlamak için Çözüm Gezgini’nde web projesine sağ tıklayın, **Yayımla...** öğesine tıklayın ve ardından Yayımla iletişim kutusundaki uyarıları izleyin.
8. `https://<azure-webapp-url>/swagger/docs/v1` konumuna giderek OpenAPI JSON’u alın.  İçeriği JSON dosyası olarak kaydedin.  Tarayıcınıza bağlı olarak, metni boş bir metin dosyasına kopyalayıp yapıştırmanız gerekebilir.   
   
   > [!IMPORTANT]
   > Yinelenen işlem kimlikleri olan OpenAPI belgeleri geçersizdir. Örnek C# şablonunu kullanıyorsanız `Values_Get` işlem kimliği iki kez yinelenir. Örneği `Value_Get` olarak değiştirip yeniden yayımlayarak bunu düzeltebilirsiniz.
   > 
   > Ayrıca, bu öğreticiden de bir [örnek OpenAPI](https://pwrappssamples.blob.core.windows.net/samples/webAPI.json) indirebilirsiniz. Kullanmadan önce açıklamaları kaldırdığınızdan emin olun (`//` ile başlayarak).
   > 
   > 

## <a name="set-up-azure-active-directory-authentication"></a>Azure Active Directory kimlik doğrulamasını ayarlama
Şimdi Azure’da iki Azure Active Directory (AAD) uygulaması oluşturacaksınız.  Bunun nasıl yapıldığını gösteren örnek için bkz. [Azure Resource Manager öğreticisi](customapi-azure-resource-manager-tutorial.md#enable-authentication-in-azure-active-directory).

> [!IMPORTANT]
> Her iki uygulama da aynı dizinde olmalıdır.
> 
> 

### <a name="first-aad-application-securing-the-web-api"></a>Birinci AAD uygulaması: Web API’sini güvenli hale getirme
Birinci AAD uygulaması, Web API’sini güvenli hale getirmek için kullanılır. **webAPI** olarak adlandırın.  Yukarıdaki bağlantılı öğretici adımlarını izleyin ("Azure Active Directory’de kimlik doğrulamasını etkinleştirme" başlıklı bölüm) ve aşağıdaki değerleri kullanın:

* Oturum açma URL’si: `https://login.windows.net`
* Yanıt URL'si: `https://<your-root-url>/.auth/login/aad/callback`
* İstemci anahtarı gerekli değildir.
* Herhangi bir izin atanması gerekli değildir.
* **Önemli!** Uygulama kimliğini not alın.  Daha sonra gerekli olacaktır.

### <a name="second-aad-application-securing-the-custom-connector-and-delegated-access"></a>İkinci AAD uygulaması: Özel bağlayıcıyı ve temsilci erişimini güvenli hale getirme
İkinci AAD uygulaması özel bağlayıcı kaydının güvenliğini sağlamak ve birinci uygulama tarafından korunun Web API’sine temsilci erişimi almak için kullanılır. Bunu **webAPI-customAPI** olarak adlandırın.

* Oturum açma URL’si: `https://login.windows.net`
* Yanıt URL'si: `https://msmanaged-na.consent.azure-apim.net/redirect`
* Web API’sine temsilci erişimine yönelik izinleri ekleyin.
* Daha sonra bu uygulamanın da uygulama kimliği gerekli olacağından not edin.
* Bir istemci anahtarı oluşturun ve güvenli bir yerde saklayın. Daha sonra bu anahtar gerekli olacaktır.

## <a name="add-authentication-to-your-azure-web-app"></a>Azure Web Uygulamanıza kimlik doğrulaması ekleme
1. [Azure portalında](https://portal.azure.com) oturum açın ve birinci bölümde dağıttığınız Web Uygulamanızı bulun.
2. **Ayarlar**’a tıklayın ve ardından **Kimlik Doğrulaması / Yetkilendirme**’yi seçin.
3. **App Service Kimlik Doğrulaması**’nı etkinleştirin ve ardından **Azure Active Directory**’yi seçin.  Sonraki dikey pencerede **Ekspres**’i seçin.  
4. **Mevcut AD Uygulamasını Seç**’e tıklayın ve daha önce oluşturduğunuz **webAPI** AAD uygulamasını seçin.

Şu anda web uygulamanızın kimliğini doğrulamak için AAD kullanabilmeniz gerekir.

## <a name="add-the-custom-connector-to-microsoft-flow"></a>Özel bağlayıcıyı Microsoft Flow’a ekleme
1. `securityDefintions` nesnesini ve Web App’te kullanılan AAD kimlik doğrulamasını eklemek için OpenAPI dosyanızı değiştirin. OpenAPI dosyanızın **host** özelliğini içeren bölümü şöyle görünmelidir:

```javascript
// File header should be above here...

"host": "<your-root-url>",
"schemes": [
    "https"         //Make sure this is https!
],
"securityDefinitions": {
    "AAD": {
        "type": "oauth2",
        "flow": "accessCode",
        "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
        "tokenUrl" : "https://login.windows.net/common/oauth2/token",
        "scopes": {}
    }
},

// The rest of the OpenAPI follows...
```

1. [Microsoft Flow](https://flow.powerapps.com)’a göz atın ve [Microsoft Flow’da özel bağlayıcıları kaydetme ve kullanma](register-custom-api.md) başlığı altında açıklandığı gibi özel bağlayıcıyı ekleyin.
2. OpenAPI dosyanızı karşıya yüklediğinizde, sihirbaz Web API’niz için AAD kimlik doğrulaması kullandığınızı otomatik olarak algılar.
3. Özel bağlayıcı için AAD kimlik doğrulamasını yapılandırın.  
   
   * **İstemci Kimliği**: *webAPI-CustomAPI istemci kimliği*
   * **Parola**: *webAPI-CustomAPI istemci anahtarı*
   * **Oturum açma URL'si**: `https://login.windows.net`
   * **ResourceUri**: *webAPI istemci kimliği*
4. **Oluştur**’a tıklayın ve özel bağlayıcı için bağlantı oluşturun.

## <a name="next-steps"></a>Sonraki Adımlar
[Azure Resource Manager özel bağlayıcı öğreticisi](customapi-azure-resource-manager-tutorial.md) içinde verilen adımları izleyin.

