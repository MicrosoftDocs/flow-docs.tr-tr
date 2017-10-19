---
title: "Özel bağlayıcıları kaydetme ve kullanma | Microsoft Docs"
description: "OpenAPI ve Postman kullanarak Microsoft Flow’da özel bağlayıcıları kaydedin ve kullanın."
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
ms.date: 05/09/2017
ms.author: sunayv
ms.openlocfilehash: 94d46b2948f03316162e1c1d45860ae94feb897c
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2017
---
# <a name="register-and-use-custom-connectors-in-microsoft-flow"></a>Microsoft Flow’da özel bağlayıcıları kaydetme ve kullanma
Microsoft Flow, kod kullanmadan iş akışları oluşturmanıza olanak tanır. Ama bazı durumlarda, Microsoft Flow’un özelliklerinin kapsamını genişletmeniz gerekebilir ve doğal olarak web hizmetleri buna çok uygundur. Akışınız bir hizmete bağlanabilir, işlemler gerçekleştirebilir ve verileri geri alabilirsiniz. Microsoft Flow’a bağlamak istediğiniz bir web hizmetiniz olduğunda, hizmeti bir özel bağlayıcı olarak kaydedersiniz. Bu işlem, Microsoft Flow’un web API’nizin özelliklerini, örneğin gerektirdiği kimlik doğrulamasını, desteklediği işlemleri ve bu işlemlerin her biri için parametreleri ve çıkışları anlamasına olanak tanır.

Bu konu başlığı altında, özel bağlayıcıyı kaydetmek ve kullanmak için gereken adımları gözden geçirecek ve Azure Bilişsel Hizmetler [Metin Analizi API’sini](https://www.microsoft.com/cognitive-services/text-analytics-api) kullanacağız. Bu API, kendisine geçirdiğiniz dili, duyguyu ve önemli tümcecikleri tanımlar.

## <a name="prerequisites"></a>Önkoşullar
* Bir [Microsoft Flow hesabı](https://flow.microsoft.com).
* JSON biçiminde bir OpenAPI 2.0 (eski adı Swagger) dosyası, OpenAPI tanımının URL’si veya API’niz için bir Postman Collection dosyası. Sizde bunlardan hiçbiri yoksa, size yol göstereceğiz.
* Özel bağlayıcınız için simge olarak kullanılacak bir görüntü (isteğe bağlı).

## <a name="steps-in-the-custom-connector-process"></a>Özel bağlayıcı işleminin adımları
Özel bağlayıcı işleminin aşağıda kısaca açıkladığımız çeşitli adımları vardır. Bu makalede zaten herhangi bir türde kimliği doğrulanmış erişimle bir RESTful API’nizin olduğu varsayıldığından, makalenin kalan bölümünde 3-6 arası adımlara odaklanacağız. 1. ve 2. adımların örneği için bkz. [Microsoft Flow için özel Web API’si oluşturma](customapi-web-api-tutorial.md).

1. Seçtiğiniz dilde ve platformda **bir RESTful API’si oluşturun**. Microsoft teknolojileri için, aşağıdakilerden birini öneririz (ama siz herhangi bir platformu kullanabilirsiniz):
   
   * Azure İşlevleri
   * Azure Web Uygulamaları
   * Azure API Uygulamaları
2. Aşağıdaki kimlik doğrulama mekanizmalarından birini kullanarak **API’nizin güvenliğini sağlayın**. Bağlayıcılarınıza kimliği doğrulanmamış erişime de izin verebilirsiniz, ancak bunu yapmanızı önermeyiz.
   
   * Azure Active Directory. Daha fazla bilgi için bkz. [Microsoft Flow’da Azure Active Directory’yi özel bağlayıcıyla kullanma](customapi-azure-resource-manager-tutorial.md).
   * Dropbox, Facebook ve SalesForce gibi belirli hizmetler için OAuth 2.0
   * Genel OAuth 2.0
   * API Anahtarı
   * Temel Kimlik Doğrulaması
3. Microsoft Flow’un API’nize bağlanabilmesi için, endüstri standardı iki yoldan birini kullanarak **API’nizi açıklayın**.
   
   * OpenAPI dosyası
   * Postman Collection
     
     Kayıt işlemi kapsamında 4. adımda bir OpenAPI dosyası da oluşturabilirsiniz.
4. Microsoft Flow’da bir sihirbaz kullanarak **özel bağlayıcınızı kaydedin**. Bu sihirbazda API açıklamasını, güvenlik ayrıntılarını ve diğer bilgileri belirtirsiniz.
5. Bir uygulamada **özel bağlayıcınızı kullanın**. Uygulamanızda bağlayıcıya bir bağlantı oluşturun ve aynı Microsoft Flow’da standart bağlantıları çağırdığınız gibi, API’nin sağladığı işlemlerden herhangi birini çağırın.
6. Aynı Microsoft Flow’daki diğer kaynaklarınız gibi **özel bağlayıcınızı da paylaşın**. Bu adım isteğe bağlıdır, ama çoğunlukla özel bağlayıcıları birden çok uygulama oluşturucusu arasında paylaşmak anlamlı olur.

## <a name="describe-your-api"></a>API'nizi açıklama
Herhangi bir türde kimliği doğrulanmış erişimle bir API’niz olduğu varsayıldığında, Microsoft Flow’un bu API’ye bağlanabilmesi için API’yi açıklamanın bir yolunu bulmanız gerekir. Bunu yapmak için, bir OpenAPI dosyası veya Postman Collection oluşturursunuz. Bu işlemi aşağıdakiler gibi *herhangi bir* REST API uç noktasından yapabilirsiniz:

* Genel kullanıma açık bağlayıcılar. Bazı örnekleri şunlardır: [Spotify](https://developer.spotify.com/), [Uber](https://developer.uber.com/), [Slack](https://api.slack.com/), [Rackspace](http://docs.rackspace.com/) ve diğerleri.
* Oluşturup Azure, Amazon Web Hizmetleri (AWS), Heroku ve Google Cloud gibi herhangi bir barındırma sağlayıcısına dağıttığınız bir API.
* API genel erişime açık İnternet’te gösterildiği sürece ağınıza dağıtılmış özel bir iş kolu API’si.

OpenAPI 2.0 (eski adı Swagger) ve Postman Collection dosyaları farklı biçimler kullanır, ama her ikisi de API’nizin işlemlerini ve parametrelerini açıklayan, dilden bağımsız, makine tarafından okunabilir belgelerdir:

* Bu belgeleri, API’nizin üzerinde oluşturulduğu dile ve platforma bağlı olarak çeşitli araçlar kullanarak oluşturabilirsiniz. OpenAPI dosyasının örneğini görmek için, [Metin Analizi API’si belgelerine](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/export?DocumentFormat=Swagger&ApiName=Azure) bakın.
* API’niz için henüz OpenAPI dosyanız yoksa ve yeni bir dosya oluşturmak istemiyorsanız, Postman Collection kullanarak özel bağlayıcınızı yine de kolayca oluşturabilirsiniz. Daha fazla bilgi için bkz. [Postman Collection oluşturma](postman-collection.md).
* Microsoft Flow sahne gerisinde aslında OpenAPI kullanır; dolayısıyla, Postman Collection ayrıştırılır ve bir OpenAPI tanım dosyasına çevrilir.

**Not**: Dosyanızın boyutu 1 MB’tan küçük olmalıdır.

### <a name="getting-started-with-openapi-and-postman"></a>OpenAPI ve Postman ile çalışmaya başlama
* OpenAPI’yi yeni kullanmaya başladıysanız, swagger.io sitesinde [OpenAPI ile çalışmaya başlama](http://swagger.io/getting-started/) konusuna bakın.
* Postman’i yeni kullanmaya başladıysanız, sitesinden [Postman uygulamasını](https://www.getpostman.com/apps) yükleyin.
* API’niz Azure API Uygulamaları veya Azure İşlevleri ile oluşturulduysa, daha fazla bilgi için bkz. [Azure’da barındırılan API’yi Microsoft Flow’a aktarma](https://docs.microsoft.com/azure/app-service/app-service-export-api-to-powerapps-and-flow).

## <a name="register-your-custom-connector"></a>Özel bağlayıcınızı kaydetme
Şimdi Microsoft Flow’da özel bağlayıcınızı kaydetmek için OpenAPI dosyasını veya Postman Collection’ı kullanırsınız.

1. [Flow.microsoft.com](https://flow.microsoft.com) sitesinin üst çubuğunda, dişli simgesini seçerek ayarlar menüsünü açın. **Özel Bağlayıcılar** seçeneğini belirtin.
   
    ![Özel bağlayıcı oluşturma](./media/register-custom-api/managecustomapi.png)  
2. **Özel bağlayıcı oluştur**’u seçin.
   
    ![Özel bağlayıcı özellikleri](./media/register-custom-api/newcustomapi.png)
3. **Genel** sekmesinde, özel bağlayıcıyı nasıl oluşturmak istediğinizi seçin.
   
   * OpenAPI’yi karşıya yükleme
   * OpenAPI URL’sini yapıştırma
   * Postman Collection V1’i karşıya yükleme
     
     ![Özel bağlayıcı nasıl oluşturulur](./media/register-custom-api/choosehowtocreate.png)
     
     Özel bağlayıcınız için bir simgeyi karşıya yükleyin. Açıklama, Konak ve Taban URL’si alanları normalde OpenAPI dosyasından gelen bilgilerle otomatik olarak doldurulur. Bunlar otomatik olarak doldurulmazsa, bu alanlara bilgileri ekleyebilirsiniz. **Devam**’ı seçin.
4. **Güvenlik** sekmesinde tüm kimlik doğrulama özelliklerini girin.
   
    ![Kimlik doğrulama türleri](./media/register-custom-api/authenticationtypes.png)
   
   * Kimlik doğrulama türü, OpenAPI `securityDefinitions` nesnenizde neyin tanımlandığı temel alınarak otomatik doldurulur. Aşağıda bir OAuth2.0 örneği verilmiştir.
     
       ```
       "securityDefinitions": {
           "AAD": {
           "type": "oauth2",
           "flow": "accessCode",
           "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
           "tokenUrl": "https://login.windows.net/common/oauth2/token"
           "scopes": {}
           }
       },
       ```
   * OpenAPI dosyası `securityDefintions` nesnesi kullanmıyorsa başka değer gerekmez.
   * Postman Collection kullanırken, kimlik doğrulama türünün otomatik olarak doldurulması için OAuth 2.0 veya Temel gibi desteklenen kimlik doğrulama türlerinin kullanılıyor olması gerekir.
   * Azure Active Directory (AAD) kimlik doğrulamasını ayarlama örneği için bkz. [Microsoft Flow için özel Web API’si oluşturma](customapi-web-api-tutorial.md#set-up-azure-active-directory-authentication).
5. **Tanımlar** sekmesinde, OpenAPI dosyanızda veya Postman Collection dosyanızda tanımlanan işlemlerin tümü, istek ve yanıt değerleriyle birlikte otomatik olarak doldurulur. Tüm gerekli işlemler tanımlandıysa, bu ekranda değişiklik yapmadan kayıt işleminin 6. adımına geçebilirsiniz.
   
    ![Tanım sekmesi](./media/register-custom-api/definitiontab.png)
   
    Mevcut eylemleri düzenlemek veya özel bağlayıcınıza yeni eylemler eklemek istiyorsanız, aşağıdan okumaya devam edin.
   
   1. Henüz OpenAPI dosyanızda veya Postman Collection dosyanızda bulunmayan yeni bir eylem eklemek istiyorsanız, sol bölmede **Yeni eylem**’i seçin ve **Genel** bölümünü işleminizin adı, açıklaması ve görünürlük durumu bilgileriyle doldurun.
   2. **İstek** bölümünde, sağ üst kısımdaki **Örnekten aktar**’ı seçin. Sağ taraftaki formda, örnek isteği yapıştırın. Çoğunlukla API belgelerinde örnek istekler sağlanır. Bu belgelerden **Fiil**, **İstek URL’si**, **Üst Bilgiler** ve **Gövde** alanlarını doldurmak için gereken bilgileri de alabilirsiniz. Örnek görmek için, [Metin Analizi API’si belgelerine](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/operations/56f30ceeeda5650db055a3c6) bakın.
      
      > [!IMPORTANT]
      > Microsoft Flow tarafından otomatik olarak eklenecek olan `Content-type` üst bilgisini eylemlerden kaldırmayı unutmayın. **Güvenlik** bölümünde tanımlanmış olan kimlik doğrulama üst bilgileri de eylem ve tetikleyicilerden kaldırılmalıdır. 
      > 
      > 
      
      ![Örnekten içeri aktarma](./media/register-custom-api/importfromsample.png)
   3. İstek tanımını tamamlamak için **İçeri Aktar**’ı seçin. Yanıtı da benzer şekilde tanımlayın.
6. Tüm işlemleriniz tanımlandıktan sonra, özel bağlayıcınızı oluşturmak için **Oluştur**’u seçin.
7. Özel bağlayıcınızı oluşturunca, API’de tanımlanan işlemleri test etmek için **Test** sekmesine gidin. Bir bağlantı seçin ve işlemi test etmek için giriş parametrelerini sağlayın.
   
    ![Özel bağlayıcıyı test etme](./media/register-custom-api/testcustomapi.png)
   
    Çağrı başarılı olursa, geçerli bir yanıt alırsınız.
   
    ![Bağlayıcı yanıtını test etme](./media/register-custom-api/testapiresponse.png)

### <a name="quota-and-throttling"></a>Kota ve azaltma
* Özel bağlayıcı oluşturma kotaları hakkındaki ayrıntılar için [Microsoft Flow Fiyatlandırması](https://flow.microsoft.com/pricing/) sayfasına bakın. Sizinle paylaşılan özel bağlayıcılar bu kotada sayılmaz.
* Özel bağlayıcıda oluşturulan her bağlantı için kullanıcılar dakikada en fazla 500 istek yapabilir.

## <a name="share-your-custom-connector"></a>Özel bağlayıcınızı paylaşma
Artık bir özel bağlayıcınız olduğuna göre, bunu kuruluşunuzdaki diğer kullanıcılarla paylaşabilirsiniz. Özel bağlayıcıyı paylaştığınızda, diğer kullanıcıların buna bağımlı olmaya başlayabileceğini ve özel bağlayıcı silindiğinde bağlayıcıya yönelik tüm bağlantıların da silindiğini aklınızda bulundurun. Kuruluşunuzun dışındaki kullanıcılara bağlayıcı sağlamak istiyorsanız, bkz. [Microsoft Flow’da özel bağlayıcılara sertifika vermeye genel bakış](api-connector-overview.md).

1. [Flow.microsoft.com](https://flow.microsoft.com) sitesinin üst çubuğunda, dişli simgesini seçerek ayarlar menüsünü açın. **Özel bağlayıcılar** seçeneğini belirtin.
   
    ![Yeni bağlantı](./media/register-custom-api/managecustomapi.png)
2. Bağlayıcınızın üç nokta (**. . .**) düğmesini seçin ve sonra da **Özellikleri görüntüle**’yi seçin.  
   
    ![Bağlayıcı özelliklerini görüntüleme](./media/register-custom-api/view-properties.png)
3. **Paylaş**’ı seçin ve ardından bağlayıcınıza erişim vermek istediğiniz kullanıcıları veya grupları girin.  
   
    ![Özel bağlayıcıyı paylaşma](./media/register-custom-api/sharecustomapi.png)
4. **Kaydet**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar
[Postman Collection oluşturmayı öğrenin](postman-collection.md)

[Özel OpenAPI uzantılarını öğrenin](customapi-how-to-swagger.md).

[ASP.NET Web API’si kullanma](customapi-web-api-tutorial.md).

[Azure Resource Manager API’sini kaydetme](customapi-azure-resource-manager-tutorial.md).

